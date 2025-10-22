# **Week 7: Security & Compliance in DevOps**

---

## 1. **IAM Best Practices and Secrets Management**

**IAM (Identity and Access Management)** is a critical component of managing security in cloud environments (like AWS). This topic involves ensuring that you apply the **principle of least privilege**, meaning users, roles, and services should have only the permissions necessary for their task.

**Key Points:**

* **Principle of Least Privilege**: Grant the minimum set of permissions needed for a user or service to perform its tasks. For example, if you need an EC2 instance to read from S3 but not write, only grant the necessary read permissions for the specific S3 bucket.
* **IAM Roles vs IAM Users**: Roles should be used for services and temporary credentials, while users are for human access.
* **IAM Policies**: Policies define the permissions (read, write, execute) and should be crafted carefully, using specific actions, resources, and conditions.
* **Multi-Factor Authentication (MFA)**: Ensure that MFA is enabled for IAM users, especially for accounts with high privileges.
* **Role-Based Access Control (RBAC)**: Especially in Kubernetes, assign roles to different users based on their function in the system.

**Secrets Management**:

* **Secure Storage of Secrets**: Use a tool like **AWS Secrets Manager**, **HashiCorp Vault**, or **Docker Secrets** to store sensitive data such as database passwords, API keys, and private keys. Never hardcode secrets in your code or configuration files.
* **Environment Variables**: Use environment variables or secret management tools to inject sensitive data into your application at runtime, rather than storing it in source control.

---

## 2. **Container Security Basics (Image Scanning & Runtime Security)**

Containers are a major part of the DevOps process, but they also introduce security challenges due to shared environments and images that may contain vulnerabilities. In this section, you will learn how to secure containers at different stages of their lifecycle, from image creation to runtime.

**Key Topics:**

* **Image Scanning**:
  Use tools like **Trivy**, **Clair**, or **Anchore** to scan Docker images for vulnerabilities before deployment. These tools can identify common vulnerabilities like outdated software packages, missing patches, and misconfigurations in your container images.

  * **Trivy**: A lightweight and easy-to-use vulnerability scanner for containers.

    * Scans for vulnerabilities in base images (e.g., Alpine, Ubuntu) and packages.
    * Can be integrated into CI/CD pipelines to automatically check for vulnerabilities before deploying images.
  * **Best Practices for Image Security**:

    * **Use Minimal Base Images**: Prefer smaller, more secure images like **Alpine Linux** instead of larger, full-fledged images.
    * **Sign Images**: Use **Docker Content Trust** (DCT) to sign images and ensure that the image hasn’t been tampered with.
    * **Keep Images Up to Date**: Regularly update images to ensure that known vulnerabilities are patched.

* **Runtime Security**:
  At runtime, containers should be monitored for suspicious activity and secure configurations. Use tools like **Falco** (for real-time runtime security monitoring) and **AppArmor** or **SELinux** for controlling container access to system resources.

  **Best Practices for Container Runtime Security**:

  * **Limit Privileges**: Run containers with the least privileges, avoid running containers as the root user.
  * **Read-Only Filesystems**: Run containers with read-only filesystems where possible, reducing the risk of exploitation.
  * **Networking Security**: Avoid giving containers access to the host network unless absolutely necessary.

---

## 3. **CI/CD Security Measures**

**CI/CD security** ensures that the development pipeline does not introduce vulnerabilities, and it also secures the integration and delivery process. CI/CD processes must be secure from end to end, from the moment code is committed to the repository to the moment it is deployed to production.

**Key Points:**

* **Source Code Security**:

  * Use **Static Application Security Testing (SAST)** tools like **SonarQube** to analyze code for potential vulnerabilities (SQL injections, XSS, etc.) before deployment.
  * Integrate **Secret Detection** tools (e.g., **GitHub Secrets Scanner**) into your pipelines to ensure that sensitive information is not pushed to version control.
* **Secure Pipelines**:

  * **Environment Secrets Management**: Use **GitHub Secrets** or **HashiCorp Vault** to manage sensitive credentials in your CI/CD pipelines (e.g., AWS access keys, DB credentials).
  * **Code Signing and Integrity**: Use tools like **Notary** to sign your code and ensure that the code being deployed hasn’t been tampered with.
  * **Automated Vulnerability Scanning**: Implement vulnerability scans as part of the pipeline, using tools like **Trivy** or **Clair**, to scan the codebase and container images for security issues automatically.
  * **Access Control**: Ensure that only trusted individuals can access the CI/CD system and that roles and permissions are tightly controlled.
* **Automated Security Tests**:

  * **Penetration Testing**: You can integrate basic penetration testing tools (e.g., **OWASP ZAP**) to automatically test web applications and APIs for vulnerabilities.
  * **Compliance Checking**: Integrate compliance tools (e.g., **Checkov**, **Terraform-compliance**) to verify that your infrastructure code (like Terraform) adheres to security standards and policies.

---