# Availability in Numbers (Three 9s, Four 9s, Parallel vs Sequence)

## 🤔 Why it's needed

Availability is one of the most important **Non-Functional Requirements (NFRs)** in System Design.

Companies express availability as a **percentage**, such as:

- 99%
- 99.9%
- 99.99%
- 99.999%

These percentages indicate **how much downtime a system is allowed over a given period** (usually a year).

Understanding availability numbers helps you:

- Design highly available systems.
- Calculate expected downtime.
- Compare Service Level Agreements (SLAs).
- Answer System Design interview questions confidently.

---

## 🌍 Real-world example

Imagine two popular applications:

### 🎬 Video Streaming Platform

If the service is unavailable for **8 hours in a year**, most users may tolerate it.

Availability:

```
99.9%
```

---

### 🏦 Banking Application

If customers cannot transfer money for even **1 hour**, it can lead to major financial and reputational losses.

Banks aim for:

```
99.99% or 99.999%
```

Higher availability means **less downtime**.

---

## 🧠 Interview explanation

## What is Availability?

Availability is the probability that a system is **operational and accessible when users need it**.

### Formula

```text
Availability =
(Uptime / (Uptime + Downtime)) × 100%
```

---

## Availability Levels

### 99% Availability (Two 9s)

Allowed downtime:

| Time Period | Downtime    |
| ----------- | ----------- |
| Year        | ~3.65 days  |
| Month       | ~7.2 hours  |
| Week        | ~1.68 hours |

Suitable for:

- Internal tools
- Small business applications

---

### 99.9% Availability (Three 9s)

Allowed downtime:

| Time Period | Downtime      |
| ----------- | ------------- |
| Year        | ~8.76 hours   |
| Month       | ~43.8 minutes |
| Week        | ~10.1 minutes |

Suitable for:

- E-commerce websites
- SaaS products
- Online learning platforms

---

### 99.99% Availability (Four 9s)

Allowed downtime:

| Time Period | Downtime      |
| ----------- | ------------- |
| Year        | ~52.6 minutes |
| Month       | ~4.38 minutes |
| Week        | ~1.01 minutes |

Suitable for:

- Banking
- Payment gateways
- Healthcare systems

---

### 99.999% Availability (Five 9s)

Allowed downtime:

| Time Period | Downtime      |
| ----------- | ------------- |
| Year        | ~5.26 minutes |
| Month       | ~26.3 seconds |
| Week        | ~6 seconds    |

Suitable for:

- Telecom
- Mission-critical cloud services
- Stock exchanges

---

## Availability in Sequence (Series)

A system made of components connected **one after another**.

If **any one component fails**, the **entire system fails**.

### Example

```text
User
 │
 ▼
Load Balancer
 │
 ▼
Application Server
 │
 ▼
Database
```

If the database is down, the whole application is unavailable.

### Formula

```text
System Availability

= A × B × C × ...
```

### Example

Three services:

```
99.9%

99.9%

99.9%
```

Overall availability:

```
0.999 × 0.999 × 0.999

≈ 99.7%
```

**Observation**

Adding more components in sequence **reduces overall availability** because every component must work.

---

## Availability in Parallel

A system with **redundant components**.

If one component fails, another continues serving users.

### Example

```text
              User
                │
                ▼
         Load Balancer
          │        │
          ▼        ▼
     Server A   Server B
```

If Server A fails, Server B still handles requests.

The system remains available.

### Formula

For two identical servers:

```text
Availability

= 1 − (Failure₁ × Failure₂)
```

Where:

```
Failure

= 1 − Availability
```

### Example

Each server:

```
Availability = 99%

Failure = 1%
```

Overall availability:

```
1 − (0.01 × 0.01)

= 99.99%
```

**Observation**

Adding redundant components in parallel **increases overall availability**.

---

## Sequence vs Parallel

| Sequence (Series)               | Parallel                          |
| ------------------------------- | --------------------------------- |
| Components depend on each other | Components provide redundancy     |
| One failure can stop the system | Other components continue serving |
| Overall availability decreases  | Overall availability increases    |
| Lower fault tolerance           | Higher fault tolerance            |
| Simpler architecture            | More complex architecture         |

---

## ✍️ Syntax

### Availability Formula

```text
Availability

=

(Uptime)

─────────────── × 100%

(Uptime + Downtime)
```

---

### Sequential Architecture

```text
Client
  │
  ▼
Load Balancer
  │
  ▼
Application
  │
  ▼
Database
```

---

### Parallel Architecture

```text
              Client
                 │
                 ▼
          Load Balancer
            │       │
            ▼       ▼
      Server A   Server B
```

---

## 💻 Example queries

- What is 99.9% availability?
- What are Three 9s and Four 9s?
- How is availability calculated?
- Why does redundancy improve availability?
- What is the difference between sequence and parallel availability?
- How much downtime is allowed for 99.99% availability?

---

## ❓ Common interview questions

1. What is availability?
2. How is availability calculated?
3. What do Three 9s and Four 9s mean?
4. How much downtime does 99.9% availability allow?
5. Why does availability decrease in sequential systems?
6. Why does redundancy improve availability?
7. What is the difference between sequence and parallel availability?
8. Why do cloud providers use multiple servers?
9. What is the relationship between redundancy and availability?
10. Which architecture provides higher availability?

---

## 📝 Practice exercises

1. Calculate yearly downtime for:
   - 99%
   - 99.9%
   - 99.99%
   - 99.999%

2. Draw:
   - A sequential system.
   - A parallel system.

3. Explain why parallel systems are more fault tolerant.

4. Calculate the availability of:
   - Three sequential components (99.9% each).
   - Two parallel servers (99% each).

5. Identify where redundancy is used in AWS, Google Cloud, or Azure.

---

## ⚠️ Common mistakes

- Assuming 99.9% means almost no downtime.
- Confusing availability with reliability.
- Thinking adding more sequential components improves availability.
- Forgetting that redundant (parallel) components increase availability.
- Ignoring the cost and complexity of achieving high availability.

---

## 🔁 Revision summary

### Availability Levels

```text
99%      → ~3.65 days/year

99.9%    → ~8.76 hours/year

99.99%   → ~52.6 minutes/year

99.999%  → ~5.26 minutes/year
```

---

### Sequence (Series)

```text
More Components

↓

Lower Overall Availability
```

---

### Parallel

```text
More Redundant Components

↓

Higher Overall Availability
```

---

### Easy Revision Formula

```text
Sequence

All Components Must Work

↓

Availability Decreases
```

```text
Parallel

One Component Can Fail

↓

Availability Increases
```

### Memory Trick

```text
Sequence = Single Failure Stops Everything

Parallel = Backup Keeps the System Running
```

> **Remember:**
>
> - **Three 9s (99.9%)** allows about **8.76 hours** of downtime per year.
> - **Four 9s (99.99%)** allows about **52.6 minutes** of downtime per year.
> - **Sequential architectures decrease availability** as more dependent components are added.
> - **Parallel architectures improve availability** by introducing redundancy and eliminating single points of failure.
