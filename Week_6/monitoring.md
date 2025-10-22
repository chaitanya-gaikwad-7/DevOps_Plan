
## 📅 **Week 6: Monitoring & Logging**

---

### 🎯 **Goal:**

Understand the fundamentals of monitoring and logging systems in a DevOps environment. By the end of the week, you'll be able to:

* Collect and view application metrics using **Prometheus**
* Visualize metrics using **Grafana dashboards**
* Analyze AWS infrastructure logs and metrics using **CloudWatch**
* Understand basics of log aggregation with **ELK/EFK stack**

---

## 🔍 Topics to Learn (with Breakdown)

---

### 1. ✅ **Monitoring: Concepts and Tools**

#### 🧠 What to Learn:

* What is monitoring?
* Difference between monitoring, logging, and observability
* Types of monitoring:

  * **Infrastructure Monitoring** (CPU, RAM, Disk)
  * **Application Monitoring** (HTTP latency, request counts, errors)
* Push vs Pull models
* Alerting basics (when and how to alert)

#### 🔧 Tools:

* Prometheus (metrics collection)
* Grafana (visualization)
* AWS CloudWatch (cloud resource metrics)
* Node Exporter / cAdvisor (exporters for Prometheus)

---

### 2. 📦 **Prometheus Fundamentals**

#### 🧠 What to Learn:

* Prometheus architecture: time-series database, pull model, exporters
* Prometheus configuration (`prometheus.yml`)
* How metrics are scraped
* PromQL (Prometheus Query Language) basics
* Common Prometheus metrics format:
  `http_requests_total{method="GET", handler="/login"} 12`

#### 📘 Practice:

* Set up Prometheus locally or in Docker
* Add `node_exporter` to expose system metrics
* Scrape a sample app exposing metrics on `/metrics` endpoint

---

### 3. 📊 **Grafana Fundamentals**

#### 🧠 What to Learn:

* What is Grafana? Why use it?
* How to connect Grafana to Prometheus
* Creating dashboards and panels
* Setting up alerts and thresholds
* Using variables and filters

#### 📘 Practice:

* Install Grafana (local or Docker)
* Create a dashboard with:

  * CPU usage
  * Memory consumption
  * HTTP request rate from app metrics

---

### 4. ☁️ **AWS CloudWatch (Cloud-native Monitoring)**

#### 🧠 What to Learn:

* What is CloudWatch?
* CloudWatch Metrics vs Logs vs Events
* How to view logs/metrics for:

  * EC2 instances
  * Lambda functions
  * S3 buckets
* Creating dashboards and metric filters
* Creating alarms (e.g., CPU > 80%)

#### 📘 Practice:

* Launch a basic EC2 instance
* Check CloudWatch metrics:

  * CPU Utilization
  * Disk I/O
* View system logs in CloudWatch Logs
* Set an alarm and test notification

---

### 5. 📁 **Logging with ELK/EFK Stack (Optional – Advanced)**

#### 🧠 What to Learn:

* What is centralized logging?
* ELK = Elasticsearch + Logstash + Kibana
* EFK = Elasticsearch + Fluentd + Kibana
* Log forwarding and parsing
* Viewing structured logs in Kibana

#### ⚙️ Tools:

* Filebeat / Fluentd: log shippers
* Elasticsearch: log storage and search
* Kibana: visualization

#### 📘 Practice:

* Run EFK stack using Docker Compose
* Forward logs from a sample app to Elasticsearch
* Visualize logs in Kibana (e.g., search for errors)

---

## 🧪 Hands-On Tasks (Projects for the Week)

| #   | Task                       | Description                                                                                          |
| --- | -------------------------- | ---------------------------------------------------------------------------------------------------- |
| 1️⃣ | **Prometheus Setup**       | Install Prometheus, configure to scrape metrics from a Node Exporter or sample app                   |
| 2️⃣ | **Grafana Dashboard**      | Connect Grafana to Prometheus and create dashboards (CPU, memory, custom app metrics)                |
| 3️⃣ | **AWS CloudWatch Metrics** | Launch an EC2 instance, monitor system metrics via CloudWatch dashboard                              |
| 4️⃣ | **AWS CloudWatch Logs**    | Send application or system logs from EC2 to CloudWatch Logs                                          |
| 5️⃣ | **EFK Stack (Optional)**   | Run EFK stack with Docker, ship logs from containerized app to Elasticsearch and visualize in Kibana |

---
---

## 🗓️ Daily Breakdown (7 Days)

| Day       | Focus                                                                       |
| --------- | --------------------------------------------------------------------------- |
| **Day 1** | Learn monitoring vs logging vs observability, intro to Prometheus           |
| **Day 2** | Install and configure Prometheus, use Node Exporter                         |
| **Day 3** | Install Grafana, connect to Prometheus, create dashboards                   |
| **Day 4** | Launch EC2 on AWS, explore CloudWatch metrics                               |
| **Day 5** | View CloudWatch Logs, set up basic alarms                                   |
| **Day 6** | (Optional) Set up EFK stack locally with Docker                             |
| **Day 7** | Recap, refine dashboards, write a blog/report summarizing what you've built |

---

## ✅ End of Week Outcomes

By the end of Week 6, you should be able to:

* Explain why monitoring and logging are important in DevOps
* Use Prometheus to scrape metrics from an app or server
* Create useful Grafana dashboards to visualize data
* Use AWS CloudWatch to monitor EC2 resources and logs
* (Optional) Understand log aggregation via EFK stack

---
