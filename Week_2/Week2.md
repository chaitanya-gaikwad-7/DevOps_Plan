# Docker

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

