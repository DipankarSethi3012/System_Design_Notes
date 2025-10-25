# Understanding Throughput in System Design

Throughput is a key performance metric in system design.  
Think of it like the rate at which an assembly line produces finished products.

---

## 1. What is Throughput?

**Throughput** is the measure of the amount of work a system can handle in a given period of time.  
It represents the actual, real-world performance output of a system.

**Simple Analogy:**  
If you are processing customer requests, your throughput is the number of requests you successfully complete per second.

**Key Idea:**  
High throughput means the system is efficient and can process a large volume of tasks or data quickly.

---

## 2. Units of Throughput

Throughput is measured as **items (or data) per unit of time.**  
The specific units vary depending on what the system does:

| **Context**       | **Common Units**            | **What it Measures** |
|--------------------|-----------------------------|----------------------|
| Web Systems        | RPS (Requests Per Second)   | Number of HTTP requests handled. |
| Databases          | TPS (Transactions Per Second) | Number of database transactions completed. |
| Networking         | bps / Mbps (bits per second / Megabits per second) | Amount of data successfully transferred. |
| General Systems    | Tasks/second or jobs/minute | The number of defined tasks completed. |

---

## 3. Throughput in Monolithic vs. Microservices Architecture

The architecture you choose significantly impacts your system's throughput potential.

| **Feature** | **Monolithic Architecture (Single, large application)** | **Microservices Architecture (Collection of small, independent services)** |
|--------------|---------------------------------------------------------|------------------------------------------------------------------------------|
| **Initial Throughput** | Generally High — communication between components is simple internal function calls (very fast). | Potentially Lower — communication involves network calls (HTTP/RPC) between services, adding a small overhead (latency). |
| **Scalable Throughput** | Low — to increase capacity, you must clone and run the entire application. If only one small part is slow, you still waste resources scaling the whole thing. The single large codebase can also become a bottleneck as it grows. | High — you can independently scale only the specific services that are under high load. This allows the system to handle a massive, growing workload much more effectively over time. |

**Conclusion:**  
Monolithic systems often have higher initial throughput (due to lower latency in internal calls),  
but **Microservices offer far more scalable throughput** for large, complex, and high-traffic applications.

---

## 4. Causes of Low Throughput (Bottlenecks)

Low throughput is caused by **bottlenecks**, which are points in the system that slow down the overall process.  
Common causes include:

1. **I/O Latency:** Slow read/write operations to storage (database, disk) compared to CPU processing.  
2. **Network Congestion/Overhead:** Excessive inter-service communication or slow network connections (common in microservices).  
3. **Inefficient Code/Algorithms:** Poorly optimized code or complex queries that take too long to execute.  
4. **Resource Contention (CPU/Memory):** Multiple tasks competing for the same limited resources.  
5. **Database Bottlenecks:** Poor indexing, deadlocks, or overloaded database servers.

---

## 5. Ways to Improve Throughput

Improving throughput involves **identifying and removing bottlenecks:**

### 🧠 Caching
Store frequently accessed data in a fast-access layer (like RAM).  
This reduces slow I/O operations and frees up the database.

### ⚖️ Load Balancing
Distribute incoming traffic across multiple servers.  
This prevents any single server from becoming overloaded and increases total request handling capacity.

### ⏳ Asynchronous Processing / Queues
Move long-running tasks (like sending thousands of emails) to background queues.  
This keeps the main server free to handle new requests quickly.

### 📈 Horizontal Scaling
Instead of buying a bigger server (**vertical scaling**), add more smaller servers (**horizontal scaling**).  
This is the primary advantage of microservices.

### 🗃️ Database Optimization
- **Indexing:** Add indexes on frequently queried columns to improve lookup speed.  
- **Query Tuning:** Optimize slow SQL queries.  
- **Replication/Sharding:** Distribute data or duplicate databases to handle high load efficiently.

---

*Authored by **Dipankar Sethi**, passionate about system design, scalability, and performance optimization.*
