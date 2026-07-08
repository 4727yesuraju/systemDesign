📄 **File Name:**

```text
failover-active-active-active-passive.md
```

# Failover, Active-Active & Active-Passive

## 🤔 Why it's needed

Modern applications are expected to be available **24×7**. However, servers, databases, or even entire data centers can fail due to hardware issues, software bugs, or network outages.

To minimize downtime and ensure business continuity, distributed systems use **Failover** strategies.

The two most common failover architectures are:

- **Active-Active**
- **Active-Passive**

These patterns help achieve:

- High Availability
- Fault Tolerance
- Better User Experience
- Disaster Recovery

---

## 🌍 Real-world example

Imagine a **hospital emergency department**.

### Active-Active

There are **two doctors** on duty.

Patients are distributed between both doctors.

If one doctor becomes unavailable, the other continues treating patients.

The hospital remains operational.

---

### Active-Passive

There is **one doctor** treating patients.

Another doctor is on standby.

If the first doctor leaves unexpectedly, the standby doctor immediately takes over.

Patients continue receiving treatment with minimal interruption.

---

## 🧠 Interview explanation

## 1. What is Failover?

### Definition

**Failover** is the process of **automatically switching traffic from a failed component to a healthy backup component**.

Its goal is to keep the application running even when failures occur.

### Example

```text
Primary Server ❌

↓

Backup Server ✅

↓

Application Continues Running
```

### Benefits

- High Availability
- Minimal Downtime
- Automatic Recovery
- Better Reliability

---

# 2. Active-Active Architecture

### Definition

In an **Active-Active** architecture, **all servers are active simultaneously** and share the incoming traffic.

Every server handles user requests.

If one server fails, the load balancer automatically routes all traffic to the remaining healthy servers.

---

### Architecture

```text
             Users
                │
                ▼
          Load Balancer
          /          \
         ▼            ▼
   Server A       Server B
   (Active)       (Active)
```

---

### How it works

1. Both servers are running.
2. Both receive requests.
3. Traffic is distributed.
4. If one server fails,
5. Remaining server continues serving users.

---

### Advantages

- Very high availability
- Better resource utilization
- Higher throughput
- Excellent scalability
- No idle servers

---

### Disadvantages

- More complex architecture
- Data synchronization challenges
- Higher implementation complexity
- Conflict resolution may be required

---

### Used In

- Google Search
- Netflix
- Amazon
- Facebook
- Cloud Platforms
- Kubernetes Clusters

---

# 3. Active-Passive Architecture

### Definition

In an **Active-Passive** architecture, only **one server actively serves requests**.

The second server stays on **standby**.

If the active server fails, the passive server automatically becomes active.

---

### Architecture

```text
             Users
                │
                ▼
          Load Balancer
                │
                ▼
        Server A (Active)
                │
        Server B (Passive)
```

---

### How it works

1. Active server handles all traffic.
2. Passive server continuously synchronizes data.
3. Health checks monitor the active server.
4. If the active server fails,
5. Passive server becomes active.

---

### Advantages

- Simple architecture
- Easy to manage
- Easier data consistency
- Lower synchronization complexity

---

### Disadvantages

- Backup server remains idle most of the time
- Resource wastage
- Slight downtime during failover
- Lower throughput than Active-Active

---

### Used In

- Banking Systems
- Payment Gateways
- Enterprise Databases
- Disaster Recovery Systems

---

# Active-Active vs Active-Passive

| Feature              | Active-Active                    | Active-Passive                     |
| -------------------- | -------------------------------- | ---------------------------------- |
| Active Servers       | Multiple                         | One                                |
| Backup Server        | No dedicated backup (all active) | Dedicated standby server           |
| Traffic Handling     | Shared across all servers        | Only active server handles traffic |
| Resource Utilization | High                             | Lower                              |
| Failover Time        | Almost Instant                   | Small delay                        |
| Scalability          | Excellent                        | Moderate                           |
| Complexity           | High                             | Low                                |
| Cost                 | Higher                           | Lower                              |
| Best For             | Large-scale systems              | Critical business systems          |

---

## ✍️ Syntax

### Failover

```text
Primary Server

↓

Failure

↓

Backup Server Takes Over
```

---

### Active-Active

```text
             Users
                │
                ▼
          Load Balancer
          /          \
         ▼            ▼
   Active A      Active B
```

---

### Active-Passive

```text
             Users
                │
                ▼
          Load Balancer
                │
                ▼
        Active Server

        Passive Server
       (Standby Backup)
```

---

## 💻 Example queries

- What is Failover?
- What is Active-Active architecture?
- What is Active-Passive architecture?
- What is the difference between Active-Active and Active-Passive?
- Which architecture provides higher availability?
- Which architecture is easier to implement?
- How does failover work?
- Why do cloud providers use Active-Active?

---

## ❓ Common interview questions

1. What is Failover?
2. Explain Active-Active architecture.
3. Explain Active-Passive architecture.
4. What are the advantages of Active-Active?
5. What are the advantages of Active-Passive?
6. Which architecture offers better scalability?
7. Which architecture has better resource utilization?
8. What is failover time?
9. Which architecture is commonly used in banking systems?
10. When would you choose Active-Active over Active-Passive?

---

## 📝 Practice exercises

1. Draw an Active-Active architecture.
2. Draw an Active-Passive architecture.
3. Explain Failover using your own words.
4. Compare Active-Active and Active-Passive in a table.
5. Identify which architecture is suitable for:
   - Netflix
   - Banking System
   - E-commerce Website
   - Payment Gateway
6. Research how AWS Multi-AZ and Google Cloud achieve failover.

---

## ⚠️ Common mistakes

- Thinking Failover and Backup are the same.
- Assuming Active-Passive uses both servers to handle traffic.
- Believing Active-Active has no synchronization challenges.
- Ignoring health checks in failover systems.
- Forgetting that Active-Passive has a small failover delay.
- Choosing Active-Active for systems where strong consistency is more important than scalability.

---

## 🔁 Revision summary

### Failover

- Automatically switches traffic to a healthy server when the primary fails.
- Improves availability.
- Minimizes downtime.

---

### Active-Active

- Multiple active servers.
- All handle requests simultaneously.
- Higher scalability.
- Better resource utilization.
- More complex synchronization.

---

### Active-Passive

- One active server.
- One standby server.
- Easier to manage.
- Better for strong consistency.
- Slight delay during failover.

---

### Easy Revision Formula

```text
Failover

Failure

↓

Automatic Switch

↓

System Continues Running
```

```text
Active-Active

Active + Active

↓

Share Traffic

↓

High Scalability
```

```text
Active-Passive

Active + Standby

↓

Take Over on Failure

↓

Simple & Reliable
```

### Memory Trick

```text
Failover
↓

Switch to Backup

Active-Active
↓

Everyone Works

Active-Passive
↓

One Works, One Waits
```

> **Remember:**
>
> - **Failover** is the mechanism that keeps a system running after a failure.
> - **Active-Active** means **multiple servers actively handle traffic**, providing high scalability and near-instant failover.
> - **Active-Passive** means **one server handles traffic while another waits as a standby**, offering simpler management and easier consistency at the cost of some unused resources.
