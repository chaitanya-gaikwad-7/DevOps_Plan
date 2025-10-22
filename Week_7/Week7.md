
# **Week 7: Security & Compliance in DevOps**

### **Tasks for Week 7:**

1. **Implement Least-Privilege IAM Roles in AWS:**

   * Create and manage IAM roles and users with the least-privilege principle, ensuring that your AWS resources are only given the minimal permissions required.
   * Example: Create a role that can only read from a specific S3 bucket, and assign that role to an EC2 instance.

2. **Scan Container Images with Trivy or Similar Tool:**

   * Use **Trivy** to scan a Docker image for known vulnerabilities.
   * Example: Run `trivy image your-image-name` to check for any outdated software or insecure packages.
   * Integrate this step into your CI/CD pipeline to automatically scan images before deployment.

3. **Add Secret Management to the CI/CD Pipeline:**

   * Use **GitHub Secrets** to securely store sensitive data like API keys and access tokens in your CI/CD pipeline.
   * Example: Store AWS credentials as secrets in GitHub, and then reference them in your GitHub Actions or Jenkins pipeline to avoid exposing them in plain text.

---

# **5 mini projects** 

### **1. AWS IAM Least Privilege Role Implementation**

#### **Project Objective:**

Create a set of **least-privilege IAM roles** and **policies** in AWS for different services (e.g., EC2, S3, Lambda), ensuring minimal access rights.

#### **Tasks:**

* Create an IAM user and assign the **least privilege** policy for accessing a specific S3 bucket (read-only access).
* Create an IAM role for an EC2 instance that allows it to read from an S3 bucket but not modify it.
* Enable **MFA** for IAM users with high privileges.
* Assign permissions to roles based on their actual needs (e.g., EC2 should not have access to S3 unless necessary).

#### **Skills Covered:**

* AWS IAM
* Least-privilege security principle
* MFA setup in AWS
* IAM policy creation

---

### **2. Docker Image Scanning for Vulnerabilities**

#### **Project Objective:**

Use **Trivy** to scan Docker images for known vulnerabilities and ensure the images are secure before deployment.

#### **Tasks:**

* Build a basic Docker image for a sample Python or Node.js app.
* Use **Trivy** to scan the Docker image for vulnerabilities.
* Integrate **Trivy** in your CI/CD pipeline (using GitHub Actions or Jenkins) to automatically scan the image every time new code is pushed.
* Set up the CI/CD pipeline to fail if vulnerabilities above a certain severity are found in the image.

#### **Skills Covered:**

* Docker image scanning with Trivy
* Integrating security tools in the CI/CD pipeline
* Automating vulnerability scans

---

### **3. Secrets Management in CI/CD Pipeline**

#### **Project Objective:**

Implement **secrets management** in a CI/CD pipeline to securely handle sensitive data (like AWS credentials, API keys) without exposing them in the codebase.

#### **Tasks:**

* Store sensitive data (e.g., AWS keys, API tokens) in **GitHub Secrets** or **Jenkins Credentials**.
* Create a **GitHub Actions** workflow or **Jenkins pipeline** that uses these secrets for deployment without exposing them in plain text.
* Ensure that secrets are not logged or displayed in the console during pipeline execution.
* Use **HashiCorp Vault** (optional) to securely manage and retrieve secrets in your pipeline.

#### **Skills Covered:**

* GitHub Secrets management
* Jenkins credentials and secure storage
* Secrets injection into CI/CD pipelines
* Secure handling of sensitive data

---

### **4. Penetration Testing on a Web Application (Basic)**

#### **Project Objective:**

Conduct basic **penetration testing** on a simple web application (e.g., a Flask app or Node.js app) to identify common security vulnerabilities.

#### **Tasks:**

* Deploy a simple web application (Flask/Node.js) on a local or cloud instance.
* Use **OWASP ZAP** or **Burp Suite** to scan the web application for vulnerabilities like SQL injection, Cross-Site Scripting (XSS), and insecure HTTP headers.
* Fix the vulnerabilities found in the app (e.g., parameterized queries for SQL injection, escaping inputs for XSS).
* Implement automated security tests using ZAP or similar tools within your CI/CD pipeline.

#### **Skills Covered:**

* Penetration testing basics
* OWASP ZAP tool usage
* Web application security
* Integrating security testing in CI/CD

---

### **5. Docker Runtime Security with Falco**

#### **Project Objective:**

Set up **Falco** (runtime security monitoring tool) to detect and alert on suspicious activity in your containerized application during runtime.

#### **Tasks:**

* Install and configure **Falco** to monitor containers running on your system.
* Set up **Falco rules** to detect specific behaviors such as privilege escalation, process execution from containers, or writing to the host filesystem.
* Integrate **Falco** with a centralized logging solution (e.g., **ELK Stack** or **AWS CloudWatch**) to visualize and alert on security incidents.
* Monitor runtime events of your Docker containers to identify security risks.

#### **Skills Covered:**

* Runtime security monitoring with Falco
* Container security best practices
* Writing and customizing Falco rules
* Centralized logging and monitoring

---

### **How These Projects Help You:**

* **IAM Least Privilege Implementation** ensures you understand the importance of restricting access in cloud environments.
* **Docker Image Scanning** helps integrate security measures into the containerization process, ensuring your applications are free from known vulnerabilities.
* **Secrets Management** emphasizes the need for keeping sensitive data secure, especially when automating deployments.
* **Penetration Testing** offers hands-on experience in identifying vulnerabilities and remediating them, a key part of security practices in DevOps.
* **Runtime Security with Falco** provides insight into detecting real-time container threats, crucial for maintaining secure applications in production.

---


