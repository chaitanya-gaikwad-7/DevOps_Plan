
## 🔷 **WEEK 5: CI/CD PIPELINE ESSENTIALS (Detailed Plan)**

---

### 🎯 **Weekly Goal**

By the end of the week, you should be able to:

* Understand core CI/CD concepts
* Set up basic pipelines using **Jenkins** and **GitHub Actions**
* Automate builds, tests, and static analysis of code

---

## 📚 **Topics to Learn in Detail**

### 🔹 1. **CI/CD Fundamentals**

| Concept                                 | Description                                                                                                                   |
| --------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| **CI (Continuous Integration)**         | Automatically building and testing code when changes are pushed to version control. Helps detect issues early.                |
| **CD (Continuous Delivery/Deployment)** | Automatically delivering or deploying code to staging/production after successful CI.                                         |
| **Pipeline**                            | A series of automated steps like install dependencies → run tests → build → deploy.                                           |
| **Pipeline as Code**                    | Defining pipelines in YAML or script files (e.g., `Jenkinsfile`, `.github/workflows/main.yml`) within the project repository. |

> ⏱️ Estimated Time: 1 day

---

### 🔹 2. **Jenkins Basics**

| Topic                | Details                                      |
| -------------------- | -------------------------------------------- |
| Jenkins Architecture | Understand Master/Agent model                |
| Installing Jenkins   | Locally via Docker or on a VM                |
| Jenkins UI           | Create jobs, install plugins                 |
| Jenkinsfile          | Pipeline as code (written in Groovy DSL)     |
| Stages and Steps     | Define build → test → deploy in clear stages |
| Triggers             | Build on Git push or schedule                |

> ⏱️ Estimated Time: 2 days

---

### 🔹 3. **GitHub Actions Basics**

| Topic               | Details                                                   |
| ------------------- | --------------------------------------------------------- |
| Actions Overview    | Native CI/CD system in GitHub                             |
| Workflow File       | `.github/workflows/main.yml`                              |
| Triggers            | `on: push`, `on: pull_request`, `schedule`, `manual`      |
| Jobs and Steps      | Define multiple jobs (build, test)                        |
| Actions Marketplace | Use pre-built actions (e.g., for Python, Node.js, Docker) |
| Artifacts           | Upload and store build/test results                       |

> ⏱️ Estimated Time: 1.5 days

---

### 🔹 4. **Add Linting & Static Code Analysis**

| Topic           | Details                                                                 |
| --------------- | ----------------------------------------------------------------------- |
| Linting         | Code formatting checks (e.g., `flake8`, `pylint` for Python)            |
| Static Analysis | Tools like `bandit` (Python security), `sonar-scanner`                  |
| Integration     | Add these tools as steps in your Jenkinsfile or GitHub Actions pipeline |

> ⏱️ Estimated Time: 0.5 day

---