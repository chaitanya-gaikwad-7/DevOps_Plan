
# 🐳 **Docker & Containerization**

---

## 🚀 **1. What Is Docker? Why Do We Need Containers?**

### 📌 Topics to Learn:

* **What is Docker?**

  * Containerization platform for packaging apps and dependencies together.
* **What are Containers?**

  * Lightweight, portable environments for running applications.
* **Docker vs Virtual Machines**

  * Understand differences in performance, resource usage, and isolation.
* **Why Containers Are Needed**

  * Solve “It works on my machine” problems.
  * Consistency across dev/test/prod environments.
  * Fast startup and low resource usage.

###  Outcomes:

* Clear understanding of **why Docker exists**.
* Know the **benefits of using containers** in DevOps and cloud-native environments.

---

## 📦 **2. Docker Images**

### 📌 Topics to Learn:

* **What is a Docker Image?**

  * A read-only template with app code, OS, dependencies.
* **Image Layers**

  * Docker images are built in layers; reuse and caching improve efficiency.
* **Official vs Custom Images**
* **How Images Are Built (via Dockerfile)**

### 🔧 Commands:

```bash
docker images       # List local images
docker pull nginx   # Pull image from Docker Hub
docker rmi <image>  # Remove image
```

###  Outcomes:

* Understand **what images are**, how they’re built, and reused.

---

## 🧱 **3. Docker Containers**

### 📌 Topics to Learn:

* **What is a Container?**

  * A running instance of an image.
* **Lifecycle of a Container**

  * Create → Start → Stop → Restart → Delete
* **Ephemeral Nature**

  * By default, containers don’t persist data after they’re stopped (unless volumes are used).

### 🔧 Commands:

```bash
docker run -it ubuntu bash   # Start a container interactively
docker ps -a                 # List all containers
docker stop <container>      # Stop container
docker rm <container>        # Remove container
docker exec -it <container> bash   # Run commands in running container
```

###  Outcomes:

* Confident running and managing containers.
* Know the difference between an image and a container.

---

## 📄 **4. Dockerfile (Custom Image Creation)**

### 📌 Topics to Learn:

* **What is a Dockerfile?**

  * Script with instructions to build a custom image.
* **Common Dockerfile Instructions:**

  * `FROM`: base image
  * `RUN`: execute shell commands
  * `COPY`, `ADD`: copy files into image
  * `CMD`, `ENTRYPOINT`: define container startup behavior
  * `EXPOSE`: define ports
  * `WORKDIR`: set working directory
  * `ENV`: set environment variables

### 🔧 Example Dockerfile:

```dockerfile
FROM python:3.9
WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .
CMD ["python", "app.py"]
```

### 🔧 Build & Run:

```bash
docker build -t my-python-app .
docker run -p 5000:5000 my-python-app
```

###  Outcomes:

* Able to **create your own Docker images** for any project.
* Understand how to optimize and troubleshoot Dockerfiles.

---

## ⚙️ **5. Docker Compose Basics**

### 📌 Topics to Learn:

* **What is Docker Compose?**

  * Tool to define and run **multi-container applications**.
* **`docker-compose.yml` structure**

  * `services`, `volumes`, `networks`, `build`, `ports`, etc.
* **Single vs Multi-Service Use Cases**

  * Example: Web app + database

### 🔧 Example:

```yaml
version: "3.9"
services:
  web:
    build: .
    ports:
      - "5000:5000"
  db:
    image: postgres
    environment:
      POSTGRES_PASSWORD: example
```

### 🔧 Commands:

```bash
docker-compose up --build
docker-compose down
docker-compose ps
```

###  Outcomes:

* Build and manage multi-container applications easily.
* Understand app orchestration at a basic level.

---

## 🗃️ **6. Docker Hub & Local Registries**

### 📌 Topics to Learn:

* **Docker Hub:**

  * Public registry to pull and push images.
  * Understand image tags (`nginx:latest`, `python:3.10-slim`)
* **Pushing Custom Images to Docker Hub:**

  * `docker login`
  * `docker tag`
  * `docker push`
* **Local Registries:**

  * Useful in air-gapped, internal, or regulated environments.
  * Can set up using `registry` image.

### 🔧 Commands:

```bash
docker login
docker tag my-image username/my-image:tag
docker push username/my-image:tag
```

###  Outcomes:

* Confidently use **Docker Hub to share images**.
* Understand **when and how to use local/private registries**.

---

## 📚 Bonus Topics (Optional but Valuable)

| Topic                             | Why It Matters                          |
| --------------------------------- | --------------------------------------- |
| **Volumes & Bind Mounts**         | Persist data from containers            |
| **Container Networking**          | Communicate between containers          |
| **Container Logs**                | `docker logs <container>`               |
| **Health Checks**                 | Keep containers healthy                 |
| **.dockerignore**                 | Avoid copying unnecessary files         |
| **Multi-stage Builds**            | Create smaller, production-ready images |
| **Security (User, Capabilities)** | Run containers as non-root users        |

---

## 📝 Learning Checklist

| Topic                                          | Covered? |
| ---------------------------------------------- | -------- |
| Understand container vs VM                     | ☐        |
| Pull, run, stop, and delete containers         | ☐        |
| Work with Docker images                        | ☐        |
| Write and optimize Dockerfiles                 | ☐        |
| Use Docker Compose for multi-container apps    | ☐        |
| Push/pull images to/from Docker Hub            | ☐        |
| Understand local registry setup                | ☐        |
| Use volumes for persistence                    | ☐        |
| Use `docker logs`, `docker exec` for debugging | ☐        |
| Use `.dockerignore` to optimize image build    | ☐        |

---

## 🧠 Summary: Why Learn Docker?

Docker is at the **core of modern DevOps**, used in:

* CI/CD pipelines
* Kubernetes deployments
* Cloud-native app development
* Infrastructure automation
* Scalable microservices

---
---
---

## 🧪 **1. Dockerize a Simple Python Web App**

### 🔧 Goal:

Build a basic Flask or FastAPI app and run it inside a Docker container.

### 🔍 Skills Practiced:

* Writing a `Dockerfile`
* Installing dependencies inside a container
* Port mapping
* Container logs and restarts

### 📁 Tech:

* Python (Flask or FastAPI)
* Docker

### ✅ Tasks:

* Create a simple web app (`/`, `/hello`)
* Write a `Dockerfile` to containerize it
* Run using `docker run -p 5000:5000`
* Add `.dockerignore` for cleaner build

---

## ⚙️ **2. Multi-Container App with Docker Compose (Web + DB)**

### 🔧 Goal:

Deploy a web app with a database using Docker Compose.

### 🔍 Skills Practiced:

* Compose file creation
* Networking between services
* Using environment variables
* Volume persistence

### 📁 Tech:

* Flask (or Node.js)
* PostgreSQL or MySQL
* Docker Compose

### ✅ Tasks:

* Define 2 services: `web`, `db`
* Use `depends_on` in `docker-compose.yml`
* Mount a volume for database persistence
* Connect app to DB using Docker Compose networking

---

## 🌍 **3. Custom Nginx Reverse Proxy Image**

### 🔧 Goal:

Create a Docker image that runs Nginx configured to reverse proxy traffic to another service (like your Flask app).

### 🔍 Skills Practiced:

* Writing custom Nginx config
* COPY and CMD in Dockerfile
* Exposing ports
* Multi-service setup (reverse proxy pattern)

### 📁 Tech:

* Nginx
* Flask (or static website)
* Docker

### ✅ Tasks:

* Write a custom Nginx config file
* Build and run a Docker image with it
* Proxy requests from Nginx to your app
* Use Compose or `docker network` to link containers

---

## 📦 **4. Private Docker Registry + Image Push/Pull**

### 🔧 Goal:

Set up a local Docker registry and push/pull your own custom image.

### 🔍 Skills Practiced:

* Running a registry container
* Tagging and pushing images
* Image versioning
* Managing local repositories

### 📁 Tech:

* Docker Registry
* Custom app image (any language)

### ✅ Tasks:

* Run local registry: `docker run -d -p 5000:5000 registry:2`
* Build and tag your app image: `myapp:v1`
* Push: `docker tag myapp localhost:5000/myapp && docker push localhost:5000/myapp`
* Pull and run from another machine/container

---

## 🛠️ **5. Create a Dockerized Dev Environment**

### 🔧 Goal:

Set up a local dev environment with preinstalled tools and config, using a custom image.

### 🔍 Skills Practiced:

* Building developer tool containers
* Shell scripting in containers
* Customizing the environment
* Volume mounting

### 📁 Tech:

* Docker
* Git, Python, Node, or any CLI tools

### ✅ Tasks:

* Build a custom image with tools (e.g., Git, curl, Python)
* Mount local code into container (`-v $(pwd):/app`)
* Set working directory and default shell
* Optionally add aliases or shell configs in the container

---

