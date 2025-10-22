## **Kubernetes mini projects**

---

## 🚀 1. **Simple Nginx Web Server Deployment**

**Goal**: Deploy a static web server using Nginx inside a Kubernetes cluster.

### 🧩 Concepts Covered:

* Pod
* Deployment
* Service (NodePort)
* Basic kubectl commands

### 📌 Tasks:

* Create a Deployment with Nginx image
* Expose it using a NodePort service
* Access it via browser using the node's IP and port
* Scale the deployment to 3 replicas
* Delete and recreate resources using YAML

---

## 🚀 2. **Multi-Container Pod with Logging App**

**Goal**: Run a multi-container Pod where one container is a simple Python app writing logs, and another container tails the log file.

### 🧩 Concepts Covered:

* Multi-container Pod
* Shared volume (`emptyDir`)
* Basic inter-container communication
* Pod lifecycle

### 📌 Tasks:

* Create a Pod with:

  * Python container writing logs to a shared volume
  * Sidecar container reading and printing those logs
* Use `kubectl logs` to monitor
* Practice restarting and debugging Pods

---

## 🚀 3. **Configurable App using ConfigMap and Secrets**

**Goal**: Deploy a simple app (like an environment variable viewer or dummy backend) that reads config from a `ConfigMap` and `Secret`.

### 🧩 Concepts Covered:

* ConfigMap
* Secret
* Environment variables in Pods
* Secure data management

### 📌 Tasks:

* Create a simple app (or use existing open-source one) that reads env vars
* Pass configuration using a `ConfigMap`
* Pass API keys or credentials via a `Secret`
* View logs to confirm data injection

---

## 🚀 4. **To-Do App with Frontend + Backend + DB**

**Goal**: Deploy a basic full-stack To-Do application in Kubernetes.

### 🧩 Concepts Covered:

* Multiple Deployments
* Inter-pod communication via Services
* Persistent volume basics (for database)
* YAML for multi-service apps

### 📌 Tasks:

* Use an open-source app like:

  * Frontend: React
  * Backend: Flask or Node.js
  * DB: PostgreSQL
* Create separate Deployments and Services
* Use labels/selectors for Services
* Make frontend talk to backend using internal service DNS

---

## 🚀 5. **Kubernetes Dashboard Setup (Local or Minikube)**

**Goal**: Deploy the Kubernetes Dashboard to visualize your cluster and apps.

### 🧩 Concepts Covered:

* Kubernetes system services
* Service Account and RBAC basics
* Exposing internal apps (kubectl proxy)

### 📌 Tasks:

* Deploy Kubernetes Dashboard
* Create admin `ServiceAccount` with permissions
* Access dashboard via `kubectl proxy`
* Explore deployed apps and Pods visually

---

## 📦 Bonus Tips

* Use **Minikube** or **Kind** (Kubernetes in Docker) for local testing
* Store your YAMLs in a Git repo (great for version control + practice Git)