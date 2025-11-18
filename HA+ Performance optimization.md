

# ⭐ **1. PERFORMANCE OPTIMIZATION (DevOps)**

### **Key Metrics**

* **CPU** — high CPU = compute bottleneck
* **Memory** — leaks, OOM kills
* **Latency** — slow API or DB
* **Error Rate** — failing endpoints
* **Disk I/O** — slow read/write
* **Throughput (RPS/QPS)** — system volume capability

### **Optimization Techniques**

* Add **autoscaling**
* Add **caching** (Redis/Memcached/CDN)
* Tune **DB queries & indexes**
* Optimize **load balancing**
* Add **read replicas** for databases
* Optimize container resources (`requests/limits`)
* Reduce startup latency (Cloud Run/GKE)
* Fix long GC cycles / memory leaks

### **Performance Testing Types**

* **Load Test:** typical traffic
* **Stress Test:** beyond limits
* **Spike Test:** sudden surge
* **Soak Test:** long run stability

---

# ⭐ **2. HIGH AVAILABILITY (HA)**

### **Design Principles**

* **No single point of failure**
* Deploy across **multiple zones**
* Use **managed services** (no self-managed DBs)
* Enable **health checks**
* Use **regional load balancers**
* Redundant **multi-instance** setup

### **HA Building Blocks**

* Multi-zone MIGs
* Regional GKE clusters
* Regional Cloud SQL
* HTTPS Global LB
* Failover mechanisms
* Self-healing infrastructure

---

# ⭐ **3. SCALABILITY**

### **Horizontal vs Vertical Scaling**

* **Vertical:** bigger machine (CPU/RAM increase)
* **Horizontal:** more machines (best practice)

### ➤ **Horizontal Scaling is preferred** for:

* GKE Workloads
* MIGs
* Cloud Run services

### **Scalability Strategies**

* Autoscaling (CPU, memory, custom metrics)
* Event-driven scaling (Pub/Sub → Cloud Run)
* Sharding & partitioning
* Stateless microservices
* Decoupling via queues

---

# ⭐ **4. CAPACITY PLANNING**

### **How to do it**

* Analyze 30–90 days of metrics (CPU/mem/latency/requests)
* Identify peak load patterns
* Add 20–30% buffer
* Use predictive autoscaling where applicable
* Estimate storage growth

---

# ⭐ **5. QUICK BEST PRACTICES (Always Mention These)**

* Use **autoscaling** everywhere
* Use **global HTTPS LB**
* Always deploy in **multi-zone**
* Add **health checks**
* Use **caching**
* Enable **Cloud Monitoring alerts**
* Build **stateless** services
* Prefer **managed databases**

---

# ✅ **PERFORMANCE OPTIMIZATION ANSWERS FOR GCP SERVICES**

Easy to memorize, powerful in interviews.

---

# ⭐ **1. GKE (Google Kubernetes Engine)**

**How to optimize performance in GKE?**

✔ Use **Cluster Autoscaler** to add/remove nodes
✔ Use **HPA/VPA** for Pods
✔ Optimize **Pod resource requests/limits**
✔ Use **node pools** for different workloads
✔ Use **Workload Identity** instead of service account keys
✔ Prefer **regional clusters** for HA
✔ Use **liveness/readiness probes**
✔ Use **filestore** or **PD-SSD** for high IOPS apps
✔ Monitor latency, CPU, memory in Cloud Monitoring

### **Real-life example (You can use this in interview):**

“For high CPU services, I would enable HPA based on CPU/memory, add a dedicated node pool for heavy workloads, and use liveness probes to ensure self-healing. I’d also optimize requests/limits to prevent node overcommit and use Cloud Monitoring dashboards to track performance.”

---

# ⭐ **2. Managed Instance Groups (MIGs)**

**How to optimize MIG performance?**

✔ Use **autoscaling** (CPU, requests-per-second, or custom metrics)
✔ Multi-zone MIG = higher availability
✔ Use **instance templates** for consistent configs
✔ Enable **health checks** to remove bad VMs
✔ Use **preemptible VMs** for batch jobs
✔ Add **Cloud CDN + LB** for web workloads

### **Real-life example**

“A MIG with autoscaling and proper health checks ensures traffic is balanced and failing VMs are replaced automatically without manual intervention.”

---

# ⭐ **3. Cloud Run**

**How to optimize Cloud Run performance?**

✔ Increase **min instances** to avoid cold starts
✔ Use **concurrency** wisely (e.g., 10–80 requests per instance)
✔ Use **Cloud Profiler** for analyzing code performance
✔ Use **Cloud Trace** to reduce latency
✔ Keep containers **lightweight** to reduce startup time
✔ Use **Pub/Sub + Cloud Run** for background tasks

### **Real-life example**

“I reduce Cloud Run cold start latency by setting `min-instances` and keeping the container lightweight. For spiky workloads, I let Cloud Run autoscale instantly based on traffic.”

---

# ⭐ **4. Cloud SQL**

**How to optimize performance for Cloud SQL databases?**

✔ Allocate enough CPU/RAM
✔ Enable **read replicas** for read-heavy workloads
✔ Use **connection pooling** (via Cloud SQL Proxy / connectors)
✔ Store static files in **GCS**, not DB
✔ Use **proper indexing**
✔ Monitor slow queries
✔ Use **I/O optimized** storage if needed
✔ Make database **regional** for HA

### **Real-life example**

“For a read-heavy system, I’ll add read replicas and tune connection pooling to avoid connection exhaustion. I’d also enable slow query logs and use Cloud Monitoring for DB latency metrics.”

---

# ⭐ **GCP Performance Optimization Summary Table**

| Service           | How to Optimize                                       |
| ----------------- | ----------------------------------------------------- |
| **GKE**           | HPA/VPA, cluster autoscaling, resource limits, probes |
| **MIG**           | Autoscaling, multi-zone, health checks, templates     |
| **Cloud Run**     | Min instances, concurrency tuning, lightweight images |
| **Cloud SQL**     | Read replicas, indexing, connection pooling           |
| **Load Balancer** | Caching, CDN, health checks, routing rules            |
| **GCS**           | Use appropriate storage class, parallel uploads       |
| **Pub/Sub**       | Increase subscribers, tune ack deadlines              |

---


### ✔ **Performance incident STAR stories customized to your experience**

### ✔ **GCP autoscaling cheat sheet (GKE, Cloud Run, MIG)**

Just tell me!
