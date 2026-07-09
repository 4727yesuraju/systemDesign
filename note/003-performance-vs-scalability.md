# Performance vs Scalability

## 🤔 Why it's needed

Performance and Scalability are two of the most important **Non-Functional Requirements (NFRs)** in System Design.

Many beginners confuse them because both relate to how well a system works. However, they solve different problems.

Understanding the difference helps you:

- Design efficient systems.
- Choose the right optimization strategy.
- Answer System Design interview questions confidently.

---

## 🌍 Real-world example

Imagine a restaurant.

### 🍽️ Performance

A chef prepares one order in **10 minutes**.

If there are only **5 customers**, everyone gets their food quickly.

This represents **good performance**.

---

### 👥 Scalability

Now imagine **500 customers** arrive at the same time.

One chef cannot handle all the orders.

The restaurant hires **10 more chefs**.

Now, even with many customers, the restaurant continues serving efficiently.

This represents **good scalability**.

**Performance = Speed of serving one customer.**

**Scalability = Ability to serve many customers without slowing down significantly.**

---

## 🧠 Interview explanation

### Performance

**Definition:**

Performance is **how fast and efficiently a system performs a task**.

It measures:

- Response time
- Latency
- Throughput
- Resource utilization (CPU, Memory, Disk)

Example:

- A search request returns results in **50 ms**.

The focus is on **speed**.

---

### Scalability

**Definition:**

Scalability is the **ability of a system to handle increasing workloads by adding resources without significantly degrading performance**.

Resources can include:

- More servers
- More CPUs
- More memory
- More databases

Example:

- A website handles **1,000 users today**.
- After adding more servers, it handles **1,000,000 users**.

The focus is on **growth**.

---

### Key Differences

| Performance                                       | Scalability                                                      |
| ------------------------------------------------- | ---------------------------------------------------------------- |
| Focuses on speed                                  | Focuses on handling growth                                       |
| Measures response time and latency                | Measures ability to handle increased load                        |
| Improves a single request                         | Improves overall system capacity                                 |
| Usually optimized through better code or hardware | Usually improved by adding resources or redesigning architecture |

---

## ✍️ Syntax

### Performance

```text
Fast Response
        +
Efficient Resource Usage
        =
Good Performance
```

---

### Scalability

```text
More Users
      │
      ▼
Add Resources
      │
      ▼
System Continues to Perform Well
```

---

## 💻 Example queries

Performance-related:

- Why is my API taking 5 seconds?
- How can I reduce database query time?
- How can I decrease latency?
- Why is CPU usage high?

Scalability-related:

- How can my application support 10 million users?
- How do I scale a web application?
- How do I distribute traffic across servers?
- How can I scale my database?

---

## ❓ Common interview questions

1. What is the difference between Performance and Scalability?
2. Can a system have good performance but poor scalability?
3. Can a scalable system have poor performance?
4. How do you improve performance?
5. How do you improve scalability?
6. Which is more important: Performance or Scalability?
7. What metrics are used to measure performance?
8. What techniques improve scalability?

---

## 📝 Practice exercises

1. Explain Performance and Scalability in your own words.
2. Give three real-world examples of each.
3. List five ways to improve application performance.
4. List five ways to improve system scalability.
5. Compare Vertical Scaling and Horizontal Scaling.

---

## ⚠️ Common mistakes

- Thinking Performance and Scalability are the same.
- Assuming adding more servers always improves performance.
- Ignoring scalability when designing for future growth.
- Optimizing performance too early without identifying bottlenecks.
- Confusing latency with scalability.

---

## 🔁 Revision summary

### Performance

- Focuses on **speed**.
- Measures response time, latency, and throughput.
- Goal: Make operations faster and more efficient.

### Scalability

- Focuses on **growth**.
- Measures the ability to handle increasing users or workload.
- Goal: Support more traffic without significant performance degradation.

### Easy Revision Formula

```text
Performance = How Fast?

Scalability = How Much Load?
```

> **Remember:**
>
> **Performance answers:** _"How quickly can the system perform a task?"_
>
> **Scalability answers:** _"Can the system continue performing well as the number of users or requests grows?"_
