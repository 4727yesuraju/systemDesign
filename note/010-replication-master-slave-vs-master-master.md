# Replication: Master-Slave vs Master-Master

## 🤔 Why it's needed

As applications grow, a **single database server** can become a bottleneck.

Problems include:

- Too many read requests.
- Single point of failure.
- Slow query performance.
- Database downtime affecting the entire application.

**Replication** solves these problems by creating **multiple copies (replicas)** of the same database.

Benefits of replication:

- High Availability
- Fault Tolerance
- Better Read Performance
- Disaster Recovery
- Data Backup

The two most common replication patterns are:

- **Master-Slave Replication (Primary-Replica)**
- **Master-Master Replication (Multi-Primary)**

---

## 🌍 Real-world example

Imagine a **school** where teachers maintain student records.

### Master-Slave

Only the **Principal** can update student records.

Teachers can **view** the records but cannot modify them.

Whenever the Principal updates a record, all teachers receive the updated copy.

---

### Master-Master

Two Principals work in different campuses.

Both can update student records.

Whenever one Principal updates a record, the change is synchronized with the other Principal.

Both have equal authority to read and write.

---

## 🧠 Interview explanation

# What is Replication?

### Definition

Replication is the process of **copying data from one database server to one or more database servers**.

The copied databases are called **Replicas**.

Purpose:

- Improve availability
- Improve read performance
- Recover from failures
- Maintain backup copies

---

# 1. Master-Slave Replication (Primary-Replica)

### Definition

In **Master-Slave Replication**, only **one database (Master)** accepts **write operations**.

The **Slave (Replica)** databases receive updates from the Master and mainly handle **read operations**.

---

### Architecture

```text
                Application
                /         \
               ▼           ▼
          Read Requests   Write Requests
               │               │
               ▼               ▼
          Replica DB      Master DB
                               │
                               ▼
                        Replica DB
```

---

### How it works

1. Client sends a write request.
2. Master stores the data.
3. Master replicates the changes to all replicas.
4. Read requests are served by replicas.

---

### Advantages

- Excellent read performance.
- Simple architecture.
- Easy to scale reads.
- Better availability.
- Easier backup and recovery.

---

### Disadvantages

- Single write bottleneck.
- Master is a single point of failure (unless failover is configured).
- Replication delay may cause stale reads.

---

### Used In

- MySQL Replication
- PostgreSQL Streaming Replication
- Amazon RDS Read Replicas

---

# 2. Master-Master Replication (Multi-Primary)

### Definition

In **Master-Master Replication**, **both databases can perform read and write operations**.

Whenever one database is updated, the change is synchronized with the other database.

---

### Architecture

```text
            Application
            /          \
           ▼            ▼
     Master A ⇄ Master B
```

Both databases:

- Read
- Write
- Synchronize changes

---

### How it works

1. User updates Master A.
2. Data is replicated to Master B.
3. Another user can update Master B.
4. Changes are synchronized back to Master A.

---

### Advantages

- No single write server.
- Higher availability.
- Better fault tolerance.
- Faster disaster recovery.
- Supports geographically distributed systems.

---

### Disadvantages

- Conflict resolution is difficult.
- More complex synchronization.
- Higher implementation complexity.
- Risk of inconsistent data if conflicts aren't handled properly.

---

### Used In

- Multi-region cloud applications.
- Distributed enterprise systems.
- Global applications with regional writes.

---

# Master-Slave vs Master-Master

| Feature              | Master-Slave       | Master-Master                    |
| -------------------- | ------------------ | -------------------------------- |
| Write Server         | One                | Multiple                         |
| Read Servers         | Multiple           | Multiple                         |
| Write Scalability    | Low                | High                             |
| Read Scalability     | High               | High                             |
| Data Synchronization | Simple             | Complex                          |
| Conflict Resolution  | Not required       | Required                         |
| Availability         | High               | Very High                        |
| Complexity           | Low                | High                             |
| Best For             | Read-heavy systems | Multi-region write-heavy systems |

---

## ✍️ Syntax

### Master-Slave

```text
               Write
                 │
                 ▼
          Master Database
           /          \
          ▼            ▼
     Replica 1     Replica 2

Reads → Replicas

Writes → Master
```

---

### Master-Master

```text
         Master A

      ⇅ Synchronization

         Master B

Reads → Both

Writes → Both
```

---

## 💻 Example queries

- What is database replication?
- What is Master-Slave replication?
- What is Master-Master replication?
- What is the difference between Master-Slave and Master-Master?
- Why do replicas improve read performance?
- What is replication lag?
- How is conflict resolution handled in Master-Master replication?

---

## ❓ Common interview questions

1. What is replication?
2. Why is replication needed?
3. Explain Master-Slave replication.
4. Explain Master-Master replication.
5. What is replication lag?
6. Which replication pattern is easier to implement?
7. Why is conflict resolution needed in Master-Master replication?
8. Which pattern is suitable for read-heavy applications?
9. Which pattern is suitable for multi-region applications?
10. What happens if the Master fails?

---

## 📝 Practice exercises

1. Draw the architecture of Master-Slave replication.
2. Draw the architecture of Master-Master replication.
3. Explain replication in your own words.
4. Compare both replication patterns.
5. Identify which replication pattern is suitable for:
   - Blogging platform
   - Banking system
   - Social media
   - Global e-commerce application
6. Research how MySQL, PostgreSQL, or MongoDB implement replication.

---

## ⚠️ Common mistakes

- Thinking replication is the same as backup.
- Assuming replicas automatically improve write performance.
- Ignoring replication lag in Master-Slave setups.
- Believing Master-Master has no synchronization issues.
- Forgetting about write conflicts in Master-Master replication.
- Assuming replication alone provides complete disaster recovery.

---

## 🔁 Revision summary

### Replication

- Creates multiple copies of data.
- Improves availability and fault tolerance.
- Enhances read performance.

---

### Master-Slave

- One Master handles all writes.
- Replicas handle reads.
- Simple and efficient for read-heavy workloads.
- May experience replication lag.

---

### Master-Master

- Multiple Masters handle reads and writes.
- Data is synchronized between them.
- Higher availability and write scalability.
- Requires conflict resolution.

---

### Easy Revision Formula

```text
Master-Slave

One Writes

↓

Many Read
```

```text
Master-Master

Many Write

↓

Synchronize Changes
```

### Memory Trick

```text
Master-Slave

One Boss

Everyone Copies
```

```text
Master-Master

Two Bosses

Both Can Update

Must Stay in Sync
```

> **Remember:**
>
> - **Master-Slave Replication** is ideal for **read-heavy applications**, where a single database handles writes and replicas serve read requests.
> - **Master-Master Replication** is ideal for **high availability and multi-region systems**, where multiple databases can process writes, but synchronization and conflict resolution become more complex.
