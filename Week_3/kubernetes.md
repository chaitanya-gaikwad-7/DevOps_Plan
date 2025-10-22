
# Kubernetes

###  Learn:

* **Why Kubernetes?**

  * The **problem with just Docker**: Containers solve packaging, but **not orchestration**.
  * You need something to manage container **scaling, healing, networking, deployments**—this is where Kubernetes comes in.

* **What is Kubernetes?**

  * An **open-source container orchestration system** for automating:

    * Deployment
    * Scaling
    * Load balancing
    * Management of containerized apps

* **Kubernetes vs Docker**

  * Docker is for **building/running containers**
  * Kubernetes is for **managing** many containers in production

---

## 🧱 Core Kubernetes Architecture

###  Learn:

* **Cluster**: A group of machines (nodes) working together.

* **Node**:

  * **Master node** (Control Plane): Controls the cluster
  * **Worker node**: Runs applications (Pods)

* **Control Plane Components**:

  * `kube-apiserver`: Exposes the Kubernetes API
  * `etcd`: Stores all cluster data (key-value store)
  * `kube-scheduler`: Assigns Pods to nodes
  * `kube-controller-manager`: Maintains the cluster state

* **Worker Node Components**:

  * `kubelet`: Communicates with the control plane
  * `kube-proxy`: Manages networking rules
  * Container runtime: e.g., Docker or containerd

---

## 📦 Kubernetes Basic Concepts

###  1. **Pod**

* The **smallest deployable unit** in Kubernetes.
* A Pod wraps **one or more containers**.

**Topics**:

* Why use Pods instead of raw containers
* Single vs multi-container Pods
* Lifecycle of a Pod

---

###  2. **Deployment**

* Manages updates to Pods.
* Ensures the **desired number of Pods** are running at all times.

**Topics**:

* Writing a `Deployment` YAML
* Updating and rolling back deployments
* Rolling updates vs recreate

---

###  3. **ReplicaSet**

* Ensures that a specified number of **replica Pods** are running.
* Used by Deployments under the hood.

---

###  4. **Services**

* Expose Pods to other Pods or external traffic.

**Types**:

* **ClusterIP**: Internal communication
* **NodePort**: Exposes a port on every node (basic external access)
* **LoadBalancer**: Works with cloud providers to expose the service
* **Headless service**: No cluster IP; used for service discovery

---

###  5. **Namespaces**

* Used to **divide cluster resources** between multiple users or projects.

---

###  6. **Labels and Selectors**

* Labels: Key-value pairs attached to objects (e.g., Pods)
* Selectors: Used to **filter resources** by labels

---

###  7. **ConfigMaps and Secrets**

* **ConfigMaps**: Store non-sensitive config data (e.g., environment variables)
* **Secrets**: Store sensitive data (e.g., passwords, tokens)

---

###  8. **Volumes**

* Kubernetes abstraction to provide **persistent storage**.

**Topics**:

* EmptyDir
* hostPath
* PersistentVolume (PV)
* PersistentVolumeClaim (PVC)
* Storage Classes (just overview for now)

---

###  9. **Networking Basics**

* Kubernetes networking model:

  * Every Pod gets its **own IP**
  * **Flat network**: All Pods can talk to each other without NAT

**Concepts**:

* Pod-to-Pod communication
* Pod-to-Service communication
* Ingress (overview only)

---

###  10. **Basic Kubernetes CLI (kubectl)**

**Must-Know Commands**:

* `kubectl get`
* `kubectl describe`
* `kubectl apply -f`
* `kubectl delete`
* `kubectl logs`
* `kubectl exec`

---

## 🛠️ YAML Basics for Kubernetes

You’ll write YAML files for:

* **Pods**
* **Deployments**
* **Services**
* **ConfigMaps/Secrets**

###  Learn:

* Basic YAML syntax (indentation, key-value pairs)
* Structure of resource definition

  * `apiVersion`, `kind`, `metadata`, `spec`

---

## 🔁 Application Lifecycle in Kubernetes

###  Learn:

* How an app is packaged as a container
* How it’s deployed using a Deployment
* How it's exposed using a Service
* How it’s scaled or updated
* How it's monitored/logged

---

## ☁️ Bonus (for later in your learning)

These are intermediate but still fundamental. Bookmark them for later:

### 📌 Helm (Templating)

* Simplifies Kubernetes deployments
* Package manager for Kubernetes

### 📌 Ingress Controllers

* Manage HTTP/S routing into the cluster

### 📌 Liveness & Readiness Probes

* Health checks to manage Pod status

### 📌 Horizontal Pod Autoscaling (HPA)

* Automatically scale Pods based on metrics

---

## 📋 Suggested Study Flow (Beginner Kubernetes)

| Day | Topics                                                              |
| --- | ------------------------------------------------------------------- |
| 1   | What is Kubernetes, why it exists, architecture overview            |
| 2   | Pods, containers, basic kubectl commands                            |
| 3   | Deployments, ReplicaSets, updating Pods                             |
| 4   | Services (ClusterIP, NodePort), exposing apps                       |
| 5   | ConfigMaps and Secrets                                              |
| 6   | YAML writing basics, hands-on with writing resources                |
| 7   | Review + practice simple Pod/Deployment/Service YAMLs + use kubectl |

---

## 📘 Resources to Learn Kubernetes Fundamentals

| Type   | Resource                                                                                       |
| ------ | ---------------------------------------------------------------------------------------------- |
| Course | [Kubernetes for Beginners - FreeCodeCamp](https://www.youtube.com/watch?v=klcxkHSI0wI)         |
| Book   | *The Kubernetes Book* by Nigel Poulton (great for beginners)                                   |
| Labs   | [Katacoda Kubernetes scenarios](https://www.katacoda.com/courses/kubernetes) *(Free hands-on)* |
| Docs   | [Kubernetes Official Docs](https://kubernetes.io/docs/home/)                                   |

---

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

