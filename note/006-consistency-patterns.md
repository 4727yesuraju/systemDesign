# Consistency Patterns

## 🤔 Why it's needed

In distributed systems, data is often stored on **multiple servers (replicas)** for scalability and fault tolerance.

When data is updated, all replicas may not receive the update at the same time.

**Consistency Patterns** define **how and when all replicas should reflect the latest data**.

Understanding these patterns helps you:

- Design scalable distributed systems.
- Choose the right consistency model.
- Balance performance, availability, and data correctness.
- Answer System Design interview questions confidently.

---

## 🌍 Real-world example

Imagine you update your **profile picture** on a social media platform.

### Strong Consistency

Immediately after updating:

- Mobile app shows the new picture.
- Web app shows the new picture.
- Friends see the new picture.

Everyone sees the **same latest data instantly**.

---

### Eventual Consistency

You update your profile picture.

- Mobile app shows the new picture immediately.
- Web app still shows the old picture for a few seconds.
- After a short time, all devices show the new picture.

The system eventually becomes consistent.

---

## 🧠 Interview explanation

A **Consistency Pattern** defines **how replicas synchronize data after updates**.

The most common consistency patterns are:

### 1. Strong Consistency

**Definition**

After a successful write, **every read immediately returns the latest value**.

No user can read stale data.

#### Example

```
Update Balance → ₹5000

Immediately

ATM → ₹5000 ✅
Mobile App → ₹5000 ✅
Website → ₹5000 ✅
```

#### Advantages

- Always correct data.
- No stale reads.
- Easy to reason about.

#### Disadvantages

- Higher latency.
- Lower availability during failures.
- More coordination between servers.

#### Used In

- Banking
- Payment Systems
- Stock Trading
- Airline Reservation

---

### 2. Eventual Consistency

**Definition**

After a write, replicas **eventually** receive the update.

Until synchronization completes, some users may read old data.

#### Example

```
Update Post

↓

Server A → Updated ✅

↓

Server B → Old Data

↓

Few Seconds Later

↓

Server B → Updated ✅
```

#### Advantages

- High availability.
- Better scalability.
- Faster responses.

#### Disadvantages

- Temporary stale data.
- More complex conflict resolution.

#### Used In

- Social Media
- DNS
- Product Catalogs
- News Feeds

---

### 3. Weak Consistency

**Definition**

There is **no guarantee** when updated data will become visible.

Users may read old data for an unpredictable amount of time.

#### Example

A live view counter may show different values on different servers.

#### Advantages

- Very high performance.
- Minimal synchronization overhead.

#### Disadvantages

- Data may remain stale.
- Not suitable for critical applications.

#### Used In

- Analytics Dashboards
- View Counters
- Monitoring Systems

---

### Comparison

| Pattern              | Latest Data Guaranteed? | Read Speed | Availability | Typical Use Cases   |
| -------------------- | ----------------------- | ---------- | ------------ | ------------------- |
| Strong Consistency   | ✅ Yes                  | Slower     | Lower        | Banking, Payments   |
| Eventual Consistency | ❌ Not immediately      | Fast       | High         | Social Media, DNS   |
| Weak Consistency     | ❌ No guarantee         | Very Fast  | Very High    | Analytics, Counters |

---

## ✍️ Syntax

### Strong Consistency

```text
Write
  │
  ▼
All Replicas Updated
  │
  ▼
Users Read Latest Data
```

---

### Eventual Consistency

```text
Write
  │
  ▼
Some Replicas Updated
  │
  ▼
Synchronization
  │
  ▼
All Replicas Updated
```

---

### Weak Consistency

```text
Write
  │
  ▼
Replication Happens Later
  │
  ▼
No Guarantee When All Replicas Match
```

---

## 💻 Example queries

- What is Strong Consistency?
- What is Eventual Consistency?
- What is Weak Consistency?
- Why do distributed databases use Eventual Consistency?
- Which consistency model is best for banking?
- Which consistency model is best for social media?

---

## ❓ Common interview questions

1. What is a consistency pattern?
2. Explain Strong Consistency with an example.
3. What is Eventual Consistency?
4. What is Weak Consistency?
5. Why is Eventual Consistency popular in distributed systems?
6. Which consistency model is used in banking systems?
7. Which consistency model is suitable for social media?
8. What are stale reads?
9. How do consistency patterns relate to the CAP Theorem?
10. What are the trade-offs between Strong and Eventual Consistency?

---

## 📝 Practice exercises

1. Explain all three consistency patterns in your own words.
2. Give three real-world examples for each pattern.
3. Compare Strong and Eventual Consistency.
4. Identify which consistency model popular applications (e.g., banking, social media, streaming) are likely to use.
5. Research how distributed databases like Cassandra or MongoDB implement consistency.

---

## ⚠️ Common mistakes

- Thinking Strong Consistency always means better performance.
- Assuming Eventual Consistency means data is permanently inconsistent.
- Confusing Availability with Consistency.
- Ignoring the trade-offs between consistency and latency.
- Using Strong Consistency where Eventual Consistency would be sufficient.

---

## 🔁 Revision summary

### Strong Consistency

- Every read returns the latest data.
- Highest data correctness.
- Higher latency.
- Used in banking and payments.

### Eventual Consistency

- Data becomes consistent after some time.
- High availability and scalability.
- Temporary stale reads.
- Used in social media and DNS.

### Weak Consistency

- No guarantee on when updates become visible.
- Highest performance.
- Suitable for non-critical data.

### Easy Revision Formula

```text
Strong Consistency
↓
Latest Data Immediately

Eventual Consistency
↓
Latest Data Eventually

Weak Consistency
↓
No Timing Guarantee
```

### Memory Trick

```text
Strong = Always Latest

Eventual = Latest After Some Time

Weak = Maybe Latest
```

> **Remember:**
>
> Choosing a consistency pattern is a trade-off between **data correctness**, **availability**, and **performance**. The best choice depends on your application's requirements.
