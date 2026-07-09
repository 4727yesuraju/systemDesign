# Availability Patterns

## 🤔 Why it's needed

Availability Patterns are design techniques used to **keep a system running and accessible even when some components fail**.

In real-world applications, servers, databases, or network connections can fail unexpectedly. Availability patterns help ensure users can still access the application with minimal downtime.

Understanding these patterns helps you:

- Build highly available systems.
- Minimize service downtime.
- Improve fault tolerance.
- Design reliable distributed systems.
- Answer System Design interview questions confidently.

---

## 🌍 Real-world example

Imagine you're watching a movie on a streaming platform.

Suddenly, one server crashes.

Instead of showing an error, your request is automatically routed to another healthy server, and the movie continues playing without interruption.

This is possible because the system follows **Availability Patterns**.

---

## 🧠 Interview explanation

Availability Patterns are architectural techniques that ensure a system **continues serving users even during failures**.

The most common availability patterns are:

---

### 1. Replication

#### Definition

Replication means **keeping multiple copies of the same data on different servers**.

If one server fails, another server can continue serving requests.

#### Example

```text
          Client
             │
             ▼
      Load Balancer
        │       │
        ▼       ▼
   Database A  Database B
   (Primary)   (Replica)
```

#### Advantages

- High availability
- Fault tolerance
- Faster read operations

#### Disadvantages

- Data synchronization complexity
- Replication delay

#### Used In

- MySQL Replication
- PostgreSQL Replication
- MongoDB Replica Sets

---

### 2. Failover

#### Definition

Failover automatically switches traffic from a failed server to a healthy backup server.

#### Example

```text
Primary Server ❌
        │
Automatic Switch
        ▼
Backup Server ✅
```

#### Advantages

- Minimal downtime
- Automatic recovery
- Better user experience

#### Disadvantages

- Backup infrastructure cost
- Failover configuration complexity

#### Used In

- Banking Systems
- Cloud Platforms
- Enterprise Applications

---

### 3. Load Balancing

#### Definition

A Load Balancer distributes incoming requests across multiple servers.

If one server becomes unavailable, traffic is redirected to healthy servers.

#### Example

```text
              Users
                 │
                 ▼
         Load Balancer
        /      |      \
       ▼       ▼       ▼
   Server 1 Server 2 Server 3
```

#### Advantages

- High availability
- Better performance
- Prevents server overload

#### Disadvantages

- Additional infrastructure
- Load balancer itself can become a single point of failure (unless redundant)

#### Used In

- Web Applications
- APIs
- Microservices

---

### 4. Health Checks

#### Definition

Health checks continuously monitor whether servers are healthy.

If a server fails, it is removed from receiving new traffic.

#### Example

```text
Health Check

Server A ✅

Server B ❌

Only Server A receives requests.
```

#### Advantages

- Automatic failure detection
- Improved reliability

#### Disadvantages

- Additional monitoring overhead

#### Used In

- Kubernetes
- AWS Elastic Load Balancer
- NGINX

---

### 5. Redundancy

#### Definition

Redundancy means having **extra resources** (servers, databases, networks, power supplies) so the system continues working if one component fails.

#### Example

```text
Server A (Active)

Server B (Standby)
```

#### Advantages

- High fault tolerance
- Improved reliability

#### Disadvantages

- Higher infrastructure cost

#### Used In

- Data Centers
- Banking
- Cloud Infrastructure

---

## Comparison

| Pattern        | Purpose                     | Main Benefit                            | Example                 |
| -------------- | --------------------------- | --------------------------------------- | ----------------------- |
| Replication    | Copy data across servers    | Data remains available                  | Database replicas       |
| Failover       | Switch to backup on failure | Minimal downtime                        | Primary → Backup server |
| Load Balancing | Distribute traffic          | Prevent overload & improve availability | NGINX, AWS ELB          |
| Health Checks  | Detect unhealthy servers    | Automatic failure detection             | Kubernetes probes       |
| Redundancy     | Maintain spare resources    | Fault tolerance                         | Backup servers          |

---

## ✍️ Syntax

### Replication

```text
Primary Database
      │
      ▼
Replica 1
Replica 2
```

---

### Failover

```text
Primary Server ❌
        │
        ▼
Backup Server ✅
```

---

### Load Balancing

```text
Users
  │
  ▼
Load Balancer
 ├── Server 1
 ├── Server 2
 └── Server 3
```

---

### Health Checks

```text
Health Check
      │
      ▼
Healthy? → Yes → Accept Traffic

Healthy? → No → Remove from Traffic
```

---

### Redundancy

```text
Active Server

Backup Server
```

---

## 💻 Example queries

- What is replication?
- What is failover?
- How does load balancing improve availability?
- What are health checks?
- Why is redundancy important?
- How do cloud providers achieve high availability?

---

## ❓ Common interview questions

1. What are Availability Patterns?
2. How does replication improve availability?
3. What is failover?
4. What is the purpose of a load balancer?
5. Why are health checks important?
6. What is redundancy?
7. What is the difference between replication and redundancy?
8. How do cloud platforms achieve high availability?
9. Can a load balancer become a single point of failure?
10. Which availability pattern would you use for a banking system?

---

## 📝 Practice exercises

1. Explain each availability pattern in your own words.
2. Draw an architecture using a load balancer and replicated servers.
3. Compare replication and redundancy.
4. Research how Kubernetes performs health checks.
5. Identify availability patterns used by popular cloud providers like AWS, Azure, or Google Cloud.

---

## ⚠️ Common mistakes

- Confusing replication with backup.
- Thinking redundancy automatically means replication.
- Assuming load balancing alone guarantees high availability.
- Forgetting to perform health checks.
- Ignoring failover planning.
- Not considering the load balancer as a potential single point of failure.

---

## 🔁 Revision summary

### Replication

- Multiple copies of data.
- Improves availability and fault tolerance.

### Failover

- Automatically switches to a backup server when the primary fails.

### Load Balancing

- Distributes traffic across multiple servers.
- Prevents overload and improves availability.

### Health Checks

- Detect unhealthy servers.
- Remove failed servers from traffic automatically.

### Redundancy

- Extra resources ready to take over during failures.

### Easy Revision Formula

```text
Replication → Copy Data

Failover → Switch Server

Load Balancer → Distribute Traffic

Health Check → Detect Failures

Redundancy → Keep Backup Resources
```

### Memory Trick

```text
Replication = Duplicate Data

Failover = Automatic Backup Switch

Load Balancer = Traffic Manager

Health Check = System Doctor

Redundancy = Spare Resources
```

> **Remember:**
>
> **Availability Patterns work together.** A highly available system often combines **Replication + Load Balancing + Health Checks + Failover + Redundancy** to minimize downtime and provide a seamless user experience.
