# How to Approach System Design?

## 🤔 Why it's needed

A structured approach to System Design helps you solve complex problems logically instead of randomly.

It ensures you:

- Understand the problem completely.
- Design scalable and reliable systems.
- Avoid missing important components.
- Communicate your thought process clearly during interviews.

---

## 🌍 Real-world example

Imagine you're asked to design **YouTube**.

A poor approach:

> Start talking about databases and servers immediately.

A good approach:

1. Understand the requirements.
2. Estimate the number of users.
3. Design the architecture.
4. Choose the database.
5. Add caching.
6. Identify bottlenecks.
7. Improve scalability.

Just like an architect creates a blueprint before constructing a building, a software engineer designs the system before implementing it.

---

## 🧠 Interview explanation

Most System Design interviews follow this approach:

### Step 1: Clarify Requirements

Understand exactly what the system should do.

- Functional Requirements
- Non-functional Requirements
- Constraints

---

### Step 2: Estimate Scale

Estimate:

- Number of users
- Requests per second (RPS)
- Data storage
- Bandwidth

These estimates help choose the right architecture.

---

### Step 3: High-Level Design

Draw the major components.

Example:

```text
Client
   │
Load Balancer
   │
Application Servers
   │
Cache (Redis)
   │
Database
```

---

### Step 4: Database Design

Choose the appropriate database.

- SQL
- NoSQL

Design:

- Tables
- Collections
- Relationships
- Indexes

---

### Step 5: API Design

Define APIs.

Example:

```
POST /users

GET /videos/{id}

POST /orders
```

---

### Step 6: Deep Dive

Explain:

- Caching
- Load balancing
- Replication
- Sharding
- Message queues
- Security
- Monitoring

---

### Step 7: Identify Bottlenecks

Ask yourself:

- What if the database crashes?
- What if traffic increases 100×?
- What if one server fails?

Design solutions for these problems.

---

### Step 8: Optimize

Improve the design using:

- Redis
- CDN
- Database Replication
- Sharding
- Auto Scaling
- Queue Systems

---

## ✍️ Syntax

General System Design flow:

```text
Understand Requirements
          │
          ▼
Estimate Scale
          │
          ▼
High-Level Design
          │
          ▼
Database Design
          │
          ▼
API Design
          │
          ▼
Deep Dive
          │
          ▼
Find Bottlenecks
          │
          ▼
Optimize the System
```

---

## 💻 Example queries

Practice designing:

- URL Shortener
- WhatsApp
- Instagram
- YouTube
- Netflix
- Uber
- Twitter (X)
- Google Drive
- Food Delivery System
- Online Shopping System
- Hotel Booking System
- Payment Gateway

---

## ❓ Common interview questions

- What are the functional requirements?
- What are the non-functional requirements?
- Why did you choose SQL instead of NoSQL?
- How will your system scale?
- Where would you use caching?
- What are the bottlenecks?
- How would you handle failures?
- How would you improve performance?
- How do you ensure high availability?
- What changes would you make for 100 million users?

---

## 📝 Practice exercises

### Beginner

- Design a Library Management System
- Design a Parking Lot
- Design a Student Management System

### Intermediate

- Design a URL Shortener
- Design a Chat Application
- Design a Notification Service

### Advanced

- Design YouTube
- Design WhatsApp
- Design Uber
- Design Netflix
- Design Google Drive

---

## ⚠️ Common mistakes

- Starting without clarifying requirements.
- Ignoring non-functional requirements.
- Skipping scale estimation.
- Choosing technologies without justification.
- Forgetting API design.
- Ignoring database indexing.
- Not discussing caching.
- Ignoring failure scenarios.
- Not identifying bottlenecks.
- Jumping into low-level implementation too early.

---

## 🔁 Revision summary

### System Design Approach

1. Clarify Requirements
2. Estimate Scale
3. Create High-Level Design
4. Design the Database
5. Design APIs
6. Deep Dive into Components
7. Identify Bottlenecks
8. Optimize for Scalability, Reliability, and Performance

> **Easy Revision Formula:**
>
> **Requirements → Scale → Architecture → Database → APIs → Bottlenecks → Optimization**
