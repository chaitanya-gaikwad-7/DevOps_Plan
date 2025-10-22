## 🔷 **WEEK 5: CI/CD PIPELINE ESSENTIALS (Detailed Plan)**

##  **Hands-On Tasks (Mini Projects)**

---

### 🧪 **Task 1: Jenkins Pipeline to Build and Test Code**

**Objective**: Set up Jenkins locally and build a pipeline for a sample Python or Node.js project.

#### Steps:

1. Install Jenkins (Docker or manual)
2. Create a sample Git repo with testable code
3. Write a `Jenkinsfile` with:

   * `Install dependencies`
   * `Run unit tests`
4. Trigger the pipeline on Git push

#### Jenkinsfile Example (Python):

```groovy
pipeline {
  agent any
  stages {
    stage('Install') {
      steps {
        sh 'pip install -r requirements.txt'
      }
    }
    stage('Test') {
      steps {
        sh 'pytest'
      }
    }
  }
}
```

---

### 🔁 **Task 2: GitHub Actions Workflow to Run Unit Tests**

**Objective**: Automate testing using GitHub Actions on every push.

#### Steps:

1. Add `.github/workflows/test.yml` in your repo
2. Write YAML file to run `pytest` or `unittest`
3. Push changes and observe GitHub Actions trigger

#### Example:

```yaml
name: Run Python Tests

on: [push]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v2

      - name: Set up Python
        uses: actions/setup-python@v2
        with:
          python-version: '3.9'

      - name: Install dependencies
        run: pip install -r requirements.txt

      - name: Run tests
        run: pytest
```

---

###  **Task 3: Add Linter to Jenkins and GitHub Actions**

**Objective**: Run `flake8` or `pylint` to enforce coding standards.

#### Jenkins:

Add a `Lint` stage:

```groovy
stage('Lint') {
  steps {
    sh 'flake8 .'
  }
}
```

#### GitHub Actions:

Add step after installing dependencies:

```yaml
- name: Run flake8
  run: flake8 .
```

---

### 🧪 Optional Bonus: Integrate Code Coverage Tools

* Use `coverage.py` to measure test coverage
* Generate reports and publish as GitHub Action artifacts or in Jenkins console

---

## 🗓️ **Suggested Daily Breakdown**

| Day         | Topics & Tasks                                               |
| ----------- | ------------------------------------------------------------ |
| **Day 1**   | CI/CD concepts → Hands-on Jenkins installation               |
| **Day 2**   | Jenkinsfile structure → Create and test basic pipeline       |
| **Day 3**   | GitHub Actions overview → Create simple test pipeline        |
| **Day 4**   | Add linting and static analysis tools                        |
| **Day 5**   | Refactor pipelines + clean-up + test multiple branches       |
| **Weekend** | Mini Project: End-to-end CI/CD pipeline with tests + linting |

---


##  5 Mini Projects Using Jenkins & GitHub Actions

---

### 🔧 **Project 1: Python App with Test Automation (GitHub Actions + Jenkins)**

**Objective:** Automate testing of a simple Python app using both GitHub Actions and Jenkins.

**Tech Stack:** Python, `pytest`, GitHub Actions, Jenkins

#### Features:

* Run unit tests on push via GitHub Actions
* Jenkins pipeline that clones repo, installs dependencies, and runs tests

#### Key Steps:

* Create a simple Python app (`calculator.py`)
* Write unit tests (`test_calculator.py`)
* Set up:

  * `.github/workflows/test.yml`
  * `Jenkinsfile` with `pip install -r requirements.txt` and `pytest`

---

### 🧼 **Project 2: Linting + Testing Pipeline (Code Quality Enforcement)**

**Objective:** Enforce code quality using linters + unit tests in CI pipelines.

**Tools:** GitHub Actions, Jenkins, `flake8`, `pylint`

#### Features:

* GitHub Actions pipeline:

  * Runs `flake8` and `pytest` on every push
* Jenkins pipeline:

  * Separate stages for linting and testing

#### Sample GitHub Workflow:

```yaml
- name: Lint Code
  run: |
    pip install flake8
    flake8 .
```

#### Jenkinsfile Stage:

```groovy
stage('Lint') {
  steps {
    sh 'flake8 .'
  }
}
```

---

### 📦 **Project 3: Build and Push Docker Image (GitHub Actions + Jenkins)**

**Objective:** Automate Docker image build and push to Docker Hub via CI tools.

**Tools:** Jenkins, GitHub Actions, Docker, GitHub Secrets

#### Steps:

* Create a basic Dockerfile for your app
* GitHub Actions:

  * Build Docker image on push
  * Push to Docker Hub using stored secrets
* Jenkins:

  * Trigger Docker build on Git changes
  * Optional: Tag builds with Git commit hash

#### Example Action Step:

```yaml
- name: Build Docker Image
  run: docker build -t myapp:latest .

- name: Push Image
  run: |
    echo "${{ secrets.DOCKER_PASSWORD }}" | docker login -u ${{ secrets.DOCKER_USERNAME }} --password-stdin
    docker push myapp:latest
```

---

### 🔄 **Project 4: Auto-Deploy Static Website with GitHub Actions**

**Objective:** Automatically deploy a static website (e.g., HTML/CSS/JS) to GitHub Pages or S3 after each commit.

**Tools:** GitHub Actions, AWS CLI (optional), HTML/CSS site

#### Features:

* Workflow to:

  * Build and test site (optional)
  * Deploy to:

    * GitHub Pages **OR**
    * S3 bucket (if you already have AWS access)

#### Sample Workflow (GitHub Pages):

```yaml
- name: Deploy to GitHub Pages
  uses: peaceiris/actions-gh-pages@v3
  with:
    github_token: ${{ secrets.GITHUB_TOKEN }}
    publish_dir: ./public
```

---

### 🔁 **Project 5: CI/CD Pipeline Comparison: Jenkins vs GitHub Actions**

**Objective:** Build and test the same project in both Jenkins and GitHub Actions and compare performance, logs, flexibility.

**Tech Stack:** Python or Node.js

#### Deliverables:

* Jenkins pipeline: `build → test → lint`
* GitHub Actions workflow: same steps
* Compare:

  * Speed
  * Logs/readability
  * Ease of setup
  * Secret management
* Document findings in a markdown report

---

## 📌 Tips for All Projects:

* Store secrets (e.g., Docker credentials) securely:

  * **GitHub** → Repository > Settings > Secrets
  * **Jenkins** → Credentials Manager
* Use `.env` or `config.yaml` to manage environment-specific values
* Version everything in Git — including your pipelines!

---
