# Response Time vs Latency vs Throughput

## 🤔 Why it's needed

Response Time, Latency, and Throughput are important **performance metrics** used to measure how well a system performs.

Understanding these metrics helps you:

- Analyze system performance.
- Identify bottlenecks.
- Optimize applications.
- Answer System Design interview questions confidently.

Although these terms are related, they measure different aspects of a system.

---

## 🌍 Real-world example

Imagine you're ordering food from a restaurant.

### 🕒 Latency

You place an order.

It takes **2 minutes** before the chef starts preparing it.

This waiting time is **Latency**.

---

### 🍽️ Response Time

You place an order.

The restaurant takes:

- 2 minutes to start preparing.
- 8 minutes to cook.
- 5 minutes to serve.

Total time = **15 minutes**

This is the **Response Time**.

---

### 👥 Throughput

The restaurant serves **300 customers per hour**.

This is its **Throughput**.

---

## 🧠 Interview explanation

### Response Time

**Definition:**

Response Time is the **total time taken from sending a request until receiving the complete response.**

It includes:

- Network delay
- Server processing
- Database queries
- Response transmission

**Formula**

```text
Response Time = Latency + Processing Time
```

Example:

```
Request Sent → Server Processes → Response Received

Total = 200 ms
```

Focus:

> **How long does the user wait?**

---

### Latency

**Definition:**

Latency is the **delay before the system starts responding to a request.**

It is mainly caused by:

- Network delay
- Distance between client and server
- Routing
- Initial processing delay

Example:

```
Client ----100 ms----> Server
```

Latency = **100 ms**

Focus:

> **How long does it take for the request to reach the server (or for the first byte of the response to start coming back)?**

---

### Throughput

**Definition:**

Throughput is the **number of requests or operations a system can process in a given amount of time.**

Common units:

- Requests/second (RPS)
- Transactions/second (TPS)
- MB/second

Example:

```
1000 Requests
──────────────
    1 Second

Throughput = 1000 RPS
```

Focus:

> **How much work can the system handle?**

---

### Key Differences

| Metric        | Measures                                   | Unit     | Goal                      |
| ------------- | ------------------------------------------ | -------- | ------------------------- |
| Response Time | Total time to complete a request           | ms, sec  | Faster user experience    |
| Latency       | Initial delay before processing/response   | ms       | Lower communication delay |
| Throughput    | Number of requests processed per unit time | RPS, TPS | Higher system capacity    |

---

## ✍️ Syntax

### Response Time

```text
Request
   │
Network Delay
   │
Server Processing
   │
Database
   │
Response
   │
Client

Total = Response Time
```

---

### Latency

```text
Client
   │
Network Delay
   │
Server

Delay = Latency
```

---

### Throughput

```text
1000 Requests
      │
      ▼
 Processed in 1 Second

Throughput = 1000 RPS
```

---

## 💻 Example queries

Response Time

- What is my API response time?
- Why is my website taking 3 seconds to load?
- How can I reduce response time?

Latency

- Why is network latency high?
- How can I reduce latency?
- What causes latency in distributed systems?

Throughput

- How many requests can my server handle?
- What is the throughput of my API?
- How do I increase requests per second?

---

## ❓ Common interview questions

1. What is Response Time?
2. What is Latency?
3. What is Throughput?
4. Explain the difference between Response Time and Latency.
5. Can a system have low latency but poor throughput?
6. How do you improve response time?
7. How do you improve throughput?
8. Which metric affects user experience the most?
9. How is throughput measured?
10. Why is latency important in distributed systems?

---

## 📝 Practice exercises

1. Explain all three metrics using a real-world example.
2. Measure your application's API response time.
3. Find factors that increase network latency.
4. Calculate throughput for an API handling 5,000 requests in 10 seconds.
5. Research techniques to improve response time, latency, and throughput.

---

## ⚠️ Common mistakes

- Confusing Response Time with Latency.
- Assuming low latency always means fast response time.
- Thinking throughput measures speed—it measures capacity.
- Ignoring server processing time when calculating response time.
- Optimizing only one metric while neglecting the others.

---

## 🔁 Revision summary

### Response Time

- **What it measures:** Total time from request to complete response.
- **Focus:** User waiting time.
- **Goal:** Lower response time.

### Latency

- **What it measures:** Initial communication delay before processing/response.
- **Focus:** Network and communication delay.
- **Goal:** Lower latency.

### Throughput

- **What it measures:** Number of requests processed per unit time.
- **Focus:** System capacity.
- **Goal:** Higher throughput.

### Easy Revision Formula

```text
Response Time = Total Time

Latency = Initial Delay

Throughput = Requests per Second
```

### Memory Trick

```text
Response Time → "How long did I wait?"

Latency → "How long before anything started happening?"

Throughput → "How many requests can the system handle?"
```
