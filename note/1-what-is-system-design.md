````markdown
# What is System Design?

## 🤔 Why it's needed

System Design is needed to **plan and organize how a software system should be built** before writing code.

It helps us:

- Build scalable applications.
- Handle millions of users.
- Improve performance.
- Ensure reliability and availability.
- Make systems easy to maintain and extend.

Without proper system design, an application may become slow, difficult to maintain, or fail as the number of users grows.

---

## 🌍 Real-world example

Imagine you're building an **online food delivery app**.

Instead of directly writing code, you first decide:

- How users place orders.
- How restaurants receive orders.
- How delivery partners are assigned.
- Where order details are stored.
- How payments are processed.
- How notifications are sent.

All these decisions together form the **System Design** of the application.

Just like an architect creates a blueprint before constructing a building, a software engineer designs the system before implementing it.

---

## 🧠 Interview explanation

**Definition:**

> **System Design is the process of designing the architecture, components, and interactions of a software system to meet functional and non-functional requirements.**

In System Design interviews, the interviewer is **not interested in code**.

Instead, they evaluate how you:

- Understand the problem.
- Break it into smaller components.
- Choose appropriate technologies.
- Design scalable and reliable systems.
- Handle failures and bottlenecks.
- Explain your decisions clearly.

A typical system consists of:

```text
Client
   │
Load Balancer
   │
Application Server
   │
Cache
   │
Database
```

System Design is about deciding **how these components work together efficiently**.

---

## ✍️ Syntax

There is **no programming syntax** for System Design.

A simple design flow looks like this:

```text
Problem
    │
    ▼
Requirements
    │
    ▼
Architecture
    │
    ▼
Database
    │
    ▼
APIs
    │
    ▼
Optimization
```

---

## 💻 Example queries

Common System Design interview questions:

- Design a URL Shortener.
- Design WhatsApp.
- Design YouTube.
- Design Instagram.
- Design Netflix.
- Design Uber.
- Design Google Drive.
- Design Twitter (X).
- Design an Online Shopping System.
- Design a Food Delivery System.

---

## ❓ Common interview questions

1. What is System Design?
2. Why is System Design important?
3. What is the difference between High-Level Design (HLD) and Low-Level Design (LLD)?
4. What are functional requirements?
5. What are non-functional requirements?
6. How do you start a System Design interview?
7. What makes a system scalable?
8. How do you ensure high availability?
9. What is a bottleneck in a system?
10. How do you improve system performance?

---

## 📝 Practice exercises

### Beginner

1. Explain System Design in your own words.
2. Draw a basic Client → Server → Database architecture.
3. Identify the components of a simple Library Management System.

### Intermediate

1. Design a Student Management System.
2. Design a Parking Lot System.
3. Design a Movie Ticket Booking System.

### Advanced

1. Design a URL Shortener.
2. Design a Chat Application.
3. Design a Video Streaming Platform.

---

## ⚠️ Common mistakes

- Thinking System Design is only about writing code.
- Jumping into technology choices without understanding requirements.
- Ignoring scalability and reliability.
- Forgetting non-functional requirements.
- Designing without considering failures.
- Overcomplicating the architecture for simple problems.
- Not explaining the reasoning behind design decisions.

---

## 🔁 Revision summary

### Definition

System Design is the process of planning the architecture, components, and interactions of a software system to build scalable, reliable, and efficient applications.

### Key Points

- Focuses on the **big picture**, not individual functions.
- Helps build systems that scale to millions of users.
- Involves architecture, databases, APIs, caching, and scalability.
- Prioritizes solving business problems over writing code.

### Easy Revision Formula

```text
Problem
   ↓
Requirements
   ↓
Architecture
   ↓
Database
   ↓
APIs
   ↓
Optimization
```

> **Remember:**  
> **Coding builds features. System Design builds the entire system.**
````
