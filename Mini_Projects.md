
# Week 1 
## Projects with **Bash + Python + Git**

---

##  1. **Log File Analyzer with Git Versioning**

### 🔧 Stack:

* **Bash**: Automate log rotation, archiving
* **Python**: Parse and analyze log files (e.g., NGINX, Apache)
* **Git**: Version analysis scripts, track log changes

### 💡 Idea:

1. Use a Bash script to archive logs older than X days.
2. Python script to:

   * Parse logs
   * Count status codes
   * Output summary (e.g., top 5 IPs)
3. Version control everything with Git.
4. Track improvements in parsing or reports using Git history.

---

##  2. **Automated Backup System with Git Commit Tracking**

### 🔧 Stack:

* **Bash**: Automate file backups
* **Python**: Validate backup integrity (checksum)
* **Git**: Version configuration, backup scripts, logs

### 💡 Idea:

1. Bash script to:

   * Compress and back up a folder daily
   * Name backups with timestamp
2. Python script to:

   * Verify SHA256 checksum of each backup
   * Log results
3. Use Git to:

   * Track changes in the backup process
   * Maintain logs/versioning of config

> Bonus: Add a Git hook to prevent pushing large backup files.

---

##  3. **Custom CLI Tool for DevOps Tasks**

### 🔧 Stack:

* **Bash**: Wrap Python script with CLI support
* **Python**: Implement the logic (e.g., start/stop services, check system health)
* **Git**: Host and track changes to CLI tool

### 💡 Idea:

1. Python script:

   * Monitor disk usage, CPU load, memory
   * Send alerts if thresholds exceeded
2. Bash wrapper:

   * Easy interface like: `./devops-tool.sh --check-health`
3. Git:

   * Track tool versions
   * Create feature branches for new tools

> Optional: Use GitHub to store and share your CLI tool.

---

##  4. **Deployment Tracker CLI Tool**

### 🔧 Stack:

* **Python**: CLI tool to record deployments
* **Bash**: Pre-deploy and post-deploy actions
* **Git**: Maintain a changelog, tag deployments

### 💡 Idea:

1. Create a Python CLI:

   * Run: `python deploy_tracker.py --env staging --version v1.2.3`
   * Logs timestamp, branch, user, and env
2. Bash pre/post deploy:

   * Notify team, validate environment
3. Git:

   * Use `git describe`, `git tag` to mark deployments
   * Auto-update `CHANGELOG.md` using Git logs

---

##  5. **Environment Setup Automation Script**

### 🔧 Stack:

* **Bash**: Install tools (Python, Git, Docker, etc.)
* **Python**: Validate installations and versions
* **Git**: Track all setup files, use `.gitignore`

### 💡 Idea:

1. Bash script:

   * Install and configure tools
   * Create config files
2. Python script:

   * Validate each tool (e.g., correct versions installed)
   * Output summary as a report
3. Git:

   * Manage versions of the environment setup
   * Document changes with clear commits and branches

---

## 📁 Folder Structure Suggestion for All Projects:

```
project-name/
├── README.md
├── scripts/
│   ├── main.py
│   ├── helper.sh
├── logs/
├── config/
│   └── settings.json
├── .gitignore
└── .git/
```

---

##  Key Concepts You’ll Practice

| Skill               | Involved In Projects              |
| ------------------- | --------------------------------- |
| Bash scripting      | Automation, CLI wrappers          |
| Python fundamentals | Parsing, validation, CLI tools    |
| Git essentials      | Version control, changelogs, tags |
| DevOps workflows    | Deployment, logging, monitoring   |
| Tool integration    | Bash ↔ Python ↔ Git               |

---

# Week 2
## Projects with **Bash + Python + Git + Docker**
---

### 🔧 1. **Daily System Info Logger (Beginner Edition)**

#### 📝 Description:

Write a script that logs the system's CPU usage, memory, and disk usage every time it’s run.

#### 🔨 Tools:

* **Bash** for system commands
* **Python** for formatting and saving
* **Docker** (basic container to run the script)
* **Git** to manage your project

#### 📌 Tasks:

* Use `bash` to fetch:

  * `top` or `uptime`
  * `df -h`
  * `free -m`
* Use **Python** to parse/save these results to a `.txt` or `.json` file
* Run everything inside a **basic Docker container**
* Save your script to a **Git repo**

#### 💡 Goal:

Get comfortable using Bash commands, mixing them with Python, and running inside Docker.

---

### 📦 2. **Simple File Backup Tool**

#### 📝 Description:

Create a basic backup tool that copies a folder (e.g., Documents) to another directory with a timestamp.

#### 🔨 Tools:

* Bash for the core script
* Python (optional) for naming and log formatting
* Git for version tracking
* Docker (optional, basic use only)

#### 📌 Tasks:

* Bash:

  * Use `cp` or `rsync` to copy files
  * Add a date-based folder name using `date` command
* Python (optional):

  * Log success/failure with timestamps
* Docker: run this backup job using `docker run`
* Push to Git

#### 💡 Goal:

Understand how automation scripts work, even for local tasks.

---

### 🔁 3. **Git Commit Logger**

#### 📝 Description:

Build a script that prints the last 5 Git commits in a local repo and logs them to a file.

#### 🔨 Tools:

* Bash for running Git commands
* Python for formatting commit messages
* Git for version control (obviously!)
* Docker (for running the logger inside a container)

#### 📌 Tasks:

* Use `git log -n 5 --pretty=oneline` in Bash
* Save logs to a file
* Python script can format logs into JSON
* Run this script using Docker
* Store the whole project in Git

#### 💡 Goal:

Reinforce Git usage and basic Bash scripting.

---

### 🐍 4. **Python Script Runner (Inside Docker)**

#### 📝 Description:

Write a simple Python program that does a task (e.g., print multiplication table), and package it with Docker.

#### 🔨 Tools:

* Python for logic
* Docker for packaging
* Git for source control

#### 📌 Tasks:

* Create a Python script:

  ```python
  # multiplication_table.py
  for i in range(1, 11):
      print(f"5 x {i} = {5*i}")
  ```
* Create a `Dockerfile` to run the script
* Run it with `docker build` and `docker run`
* Push it to Git

#### 💡 Goal:

Understand the structure of a basic Python project and how Docker containers work with simple apps.

---

### 📁 5. **Directory Organizer Tool**

#### 📝 Description:

Create a Python + Bash script that organizes files in a folder (like Downloads) into subfolders by type (e.g., `.pdf`, `.jpg`, etc.)

#### 🔨 Tools:

* Python for file handling
* Bash for directory creation and control
* Docker (optional)
* Git

#### 📌 Tasks:

* Bash:

  * Create folders if they don’t exist
* Python:

  * Move files based on extensions
  * Log each move into a text file
* Store everything in a Git repo

#### 💡 Goal:

Practice file system operations and automation.

---

## 🧠 Summary Table

| Project                 | Skills Practiced                         | Docker Use      |
| ----------------------- | ---------------------------------------- | --------------- |
| System Info Logger      | Bash commands, Python file writing, Git  | Basic container |
| File Backup Tool        | Bash copy + timestamp, Git               | Optional        |
| Git Commit Logger       | Git CLI in Bash, Python formatting       | Simple usage    |
| Python Script in Docker | Python logic + Dockerfile                | Containerized   |
| Directory Organizer     | File handling in Python + Bash scripting | Optional        |

---

# Week 6
## 🚀 **Project: Monitor & Visualize a Dockerized Web App Using Prometheus + Grafana + Git + Bash**

### 📌 **Project Name:**
**DevOps Monitoring Stack — "Hello Metrics"**

---

### 🧰 **Tools Involved:**

| Tool           | Purpose                                         |
| -------------- | ----------------------------------------------- |
| **Docker**     | Containerize and run the app & monitoring tools |
| **Git**        | Version control and repo management             |
| **Bash**       | Script automation (setup, cleanup, etc.)        |
| **Prometheus** | Scrape app metrics via `/metrics` endpoint      |
| **Grafana**    | Visualize metrics from Prometheus               |

---

## 🎯 **Project Goal:**

Set up a **local observability environment** that:

1. Runs a simple **Python web app** exposing metrics.
2. Uses **Prometheus** to collect metrics from the app.
3. Uses **Grafana** to create a dashboard of the app’s health.
4. All components run inside **Docker** containers.
5. Set up the project with **Git versioning** and reusable **Bash scripts**.

---

## 🧱 **Project Architecture:**

```
+---------------------+
|  Python Web App     |
|  (/metrics endpoint)|
+---------------------+
           |
           ↓
+---------------------+
|     Prometheus      |
|  (scrapes metrics)  |
+---------------------+
           |
           ↓
+---------------------+
|      Grafana        |
| (dashboards/views)  |
+---------------------+

All run via Docker Compose
```

---

## 📝 **Step-by-Step Breakdown**

---

### ✅ 1. **Create Project Directory Structure**

```bash
mkdir devops-monitoring-stack && cd devops-monitoring-stack
mkdir app prometheus grafana scripts
```

---

### ✅ 2. **Create a Simple Python Web App (Flask + Metrics)**

📁 `app/app.py`

```python
from flask import Flask
from prometheus_client import Counter, generate_latest

app = Flask(__name__)
REQUEST_COUNT = Counter("hello_requests_total", "Total hello requests")

@app.route("/")
def hello():
    REQUEST_COUNT.inc()
    return "Hello, DevOps!"

@app.route("/metrics")
def metrics():
    return generate_latest(), 200, {'Content-Type': 'text/plain'}

if __name__ == "__main__":
    app.run(host="0.0.0.0", port=5000)
```

📁 `app/requirements.txt`

```
flask
prometheus_client
```

📁 `app/Dockerfile`

```Dockerfile
FROM python:3.9-slim
WORKDIR /app
COPY . .
RUN pip install -r requirements.txt
EXPOSE 5000
CMD ["python", "app.py"]
```

---

### ✅ 3. **Create Prometheus Config**

📁 `prometheus/prometheus.yml`

```yaml
global:
  scrape_interval: 5s

scrape_configs:
  - job_name: "python_app"
    static_configs:
      - targets: ["app:5000"]
```

---

### ✅ 4. **Grafana Setup**

You don’t need a custom config for beginner projects. Grafana will be run with default config.

---

### ✅ 5. **Docker Compose File**

📁 `docker-compose.yml`

```yaml
version: '3.8'

services:
  app:
    build: ./app
    ports:
      - "5000:5000"

  prometheus:
    image: prom/prometheus
    volumes:
      - ./prometheus/prometheus.yml:/etc/prometheus/prometheus.yml
    ports:
      - "9090:9090"

  grafana:
    image: grafana/grafana
    ports:
      - "3000:3000"
```

---

### ✅ 6. **Write Bash Scripts**

📁 `scripts/start.sh`

```bash
#!/bin/bash
echo "🚀 Starting DevOps Monitoring Stack..."
docker-compose up --build -d
```

📁 `scripts/stop.sh`

```bash
#!/bin/bash
echo "🛑 Stopping and cleaning containers..."
docker-compose down
```

📁 `scripts/status.sh`

```bash
#!/bin/bash
docker ps --format "table {{.Names}}\t{{.Status}}"
```

👉 Make them executable:

```bash
chmod +x scripts/*.sh
```

---

### ✅ 7. **Initialize Git Repo**

```bash
git init
echo -e "venv/\n__pycache__/\n*.pyc\n*.log" > .gitignore
git add .
git commit -m "Initial commit: monitoring stack project"
```

---

### ✅ 8. **Run the Project**

```bash
./scripts/start.sh
```

* Visit:

  * Flask app: [http://localhost:5000](http://localhost:5000)
  * Prometheus: [http://localhost:9090](http://localhost:9090)
  * Grafana: [http://localhost:3000](http://localhost:3000) (Default login: admin / admin)

---

### ✅ 9. **Create Grafana Dashboard**

Once Grafana is running:

1. Add **Prometheus** as a data source.
2. Create a dashboard:

   * Panel 1: `hello_requests_total`
   * Panel 2: CPU / memory if you add Node Exporter later
3. Save and export the dashboard JSON (for reuse).

---

### 🧪 Optional Extensions (Stretch Goals)

* Add Node Exporter to monitor host metrics
* Add alerting rules in Prometheus
* Push to GitHub and automate `docker-compose up` via GitHub Actions

---

