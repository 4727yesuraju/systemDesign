# Availability vs Consistency

## 🤔 Why it's needed

Availability and Consistency are two fundamental concepts in **Distributed Systems** and are part of the **CAP Theorem**.

Understanding the difference helps you:

- Design reliable distributed systems.
- Choose the right database for your application.
- Understand trade-offs during network failures.
- Answer System Design interview questions confidently.

In distributed systems, it is often impossible to achieve both perfect Availability and perfect Consistency during a network partition. You must decide which one is more important for your application.

---

## 🌍 Real-world example

Imagine you're using an **online banking application**.

### 🏦 Consistency

You transfer **₹5,000** from Account A to Account B.

Immediately after the transfer:

- Account A should show ₹5,000 less.
- Account B should show ₹5,000 more.

Every user should see the **same updated balance**.

This is **Consistency**.

---

### 🌐 Availability

Suppose one bank server crashes.

Even though one server is down, users should still be able to:

- Log in
- Check balances
- Perform transactions

The system continues responding to requests.

This is **Availability**.

---

## 🧠 Interview explanation

### Availability

**Definition:**

Availability means **every request receives a response**, even if some servers are down.

The response may not always contain the **latest data**, but the system remains operational.

**Goal:**

- Keep the application running.
- Minimize downtime.
- Ensure users always receive a response.

Example:

A social media app still shows an older version of your feed while some servers are recovering.

---

### Consistency

**Definition:**

Consistency means **every user sees the same, most recent data** after a successful update.

All replicas return identical data.

**Goal:**

- Prevent stale or conflicting data.
- Ensure data correctness.
- Maintain data integrity.

Example:

After updating your profile picture, every device immediately displays the new picture.

---

### Key Differences

| Availability                                  | Consistency                                        |
| --------------------------------------------- | -------------------------------------------------- |
| Every request receives a response             | Every request returns the latest data              |
| Prioritizes uptime                            | Prioritizes correct and up-to-date data            |
| Data may be stale                             | Data is always synchronized                        |
| Suitable for systems where uptime is critical | Suitable for systems where correctness is critical |

---

### When to Prioritize Availability

Examples:

- Social Media
- News Websites
- Video Streaming
- Product Catalogs
- Search Engines

Users prefer getting slightly outdated data rather than seeing an error.

---

### When to Prioritize Consistency

Examples:

- Banking Systems
- Payment Gateways
- Stock Trading Platforms
- Airline Reservation Systems
- Inventory Management

Users must always see the correct and latest data.

---

## ✍️ Syntax

### Availability

```text
Client
   │
   ▼
Server A ❌
Server B ✅
Server C ✅

User still receives a response.
```

---

### Consistency

```text
Write Data
      │
      ▼
Replica 1
Replica 2
Replica 3

All replicas contain the same updated data.
```

---

## 💻 Example queries

Availability-related:

- How do I make my application highly available?
- What causes downtime?
- How does load balancing improve availability?
- How does replication improve availability?

Consistency-related:

- What is strong consistency?
- What is eventual consistency?
- How do distributed databases maintain consistency?
- Why is consistency important in banking systems?

---

## ❓ Common interview questions

1. What is Availability?
2. What is Consistency?
3. Explain the difference between Availability and Consistency.
4. Can a distributed system guarantee both Availability and Consistency?
5. What is the CAP Theorem?
6. Which applications prioritize Availability?
7. Which applications prioritize Consistency?
8. What is eventual consistency?
9. How does replication affect consistency?
10. Why is consistency important for financial systems?

---

## 📝 Practice exercises

1. Explain Availability and Consistency in your own words.
2. List five real-world systems that prioritize Availability.
3. List five real-world systems that prioritize Consistency.
4. Compare Availability and Consistency using your own example.
5. Learn how the CAP Theorem relates to these concepts.

---

## ⚠️ Common mistakes

- Thinking Availability means the data is always correct.
- Thinking Consistency means the system is always available.
- Assuming all applications should prioritize Consistency.
- Ignoring the trade-offs in distributed systems.
- Confusing Availability with Reliability.

---

## 🔁 Revision summary

### Availability

- **What it means:** The system always responds to requests.
- **Focus:** Uptime and accessibility.
- **Goal:** Keep the application available, even during failures.

### Consistency

- **What it means:** Every user sees the same, latest data.
- **Focus:** Data correctness.
- **Goal:** Ensure accurate and synchronized data across all replicas.

### Easy Revision Formula

```text
Availability = Always Respond

Consistency = Always Correct
```

### Memory Trick

```text
Availability → "Can I access the system?"

Consistency → "Is the data the latest and correct?"
```

> **Remember:**
>
> During a network partition, a distributed system often has to choose between **Availability** and **Consistency** (as described by the **CAP Theorem**).
