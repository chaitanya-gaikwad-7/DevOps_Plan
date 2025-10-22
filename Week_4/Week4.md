## 🔧 **TASKS FOR THE WEEK (Hands-on Practice)**

###  Task 1: **Launch EC2 instance via AWS Console**

* Choose Ubuntu AMI
* Generate key pair for SSH access
* Open port 22 in security group
* SSH into instance using your terminal

###  Task 2: **Launch the same EC2 instance using Terraform**

* Define AWS provider and `aws_instance` resource
* Output the public IP
* SSH into it

###  Task 3: **Create an S3 Bucket with Terraform**

* Define an `aws_s3_bucket` resource
* Enable versioning
* Optional: Add tags and configure for website hosting

###  Task 4: **Manage IAM roles and policies with Terraform**

* Create an IAM user with programmatic access
* Attach a policy allowing EC2 or S3 access
* Define resources:

  * `aws_iam_user`
  * `aws_iam_policy`
  * `aws_iam_user_policy_attachment`


---

## 📆 **Optional Daily Breakdown**

| Day | Focus                                                         |
| --- | ------------------------------------------------------------- |
| 1   | Intro to Cloud Computing + AWS Basics                         |
| 2   | EC2 in Console → Launch, Connect, Understand Pricing/Security |
| 3   | IAM basics → Create user, group, policy (GUI)                 |
| 4   | Terraform basics: Install, Provider setup, first EC2 with TF  |
| 5   | Add variables, outputs, and destroy EC2                       |
| 6   | Create S3 bucket with Terraform (enable versioning, tags)     |
| 7   | IAM resources with Terraform (user + policy + attachment)     |

---

##  Deliverables/Checklist

###  AWS

* [ ] EC2 instance launched via Console and SSH access tested
* [ ] IAM User and Role created
* [ ] S3 Bucket created manually

###  Terraform

* [ ] AWS Provider setup with credentials
* [ ] EC2 instance created via Terraform
* [ ] S3 bucket created with tags + versioning
* [ ] IAM user + policy managed with Terraform
* [ ] Project files organized into `main.tf`, `variables.tf`, etc.

---

## **5 beginner-friendly mini projects combining AWS + Terraform**

---

##  **1. Deploy a Static Website on S3 with Terraform**

### 🔹 Objective:

Host a simple static website (HTML/CSS) using **Amazon S3**, and automate the setup using Terraform.

### 🔸 What You'll Learn:

* Create S3 bucket with Terraform
* Enable **static website hosting**
* Set public access and bucket policies
* Upload a sample `index.html` page using AWS CLI or manually

### 🛠 Terraform Resources:

* `aws_s3_bucket`
* `aws_s3_bucket_policy`
* `aws_s3_bucket_website_configuration`

---

##  **2. Provision a Basic EC2 Web Server with Terraform**

### 🔹 Objective:

Use Terraform to launch an EC2 instance and install a basic web server (e.g., Nginx) using `user_data`.

### 🔸 What You'll Learn:

* Provision EC2 with a security group that opens port 80
* Use `user_data` to auto-install Nginx on boot
* Access the server via public IP and view the default Nginx page

### 🛠 Terraform Resources:

* `aws_instance`
* `aws_security_group`
* `user_data` script (inline Bash to install Nginx)

---

##  **3. Create IAM Users and Policies for a Dev Team**

### 🔹 Objective:

Set up IAM users and attach policies for a small DevOps team.

### 🔸 What You'll Learn:

* Create multiple IAM users
* Attach permissions based on roles (e.g., `EC2Admin`, `S3ReadOnly`)
* Use variable maps to dynamically provision users

### 🛠 Terraform Resources:

* `aws_iam_user`
* `aws_iam_policy`
* `aws_iam_user_policy_attachment`

---

##  **4. Set Up a VPC with Public & Private Subnets**

> *(Slightly more advanced, but worth trying once you complete basics)*

### 🔹 Objective:

Use Terraform to create a simple network with a **VPC**, one **public subnet**, and one **private subnet**.

### 🔸 What You'll Learn:

* Create custom VPC, subnets, internet gateway, and route tables
* Understand networking basics in AWS
* Launch EC2 instance in public subnet

### 🛠 Terraform Resources:

* `aws_vpc`
* `aws_subnet`
* `aws_internet_gateway`
* `aws_route_table`
* `aws_route_table_association`

---

##  **5. Schedule a Daily EC2 Snapshot Backup Using Terraform + AWS CLI**

### 🔹 Objective:

Use Terraform to create an EC2 instance and an Amazon **Data Lifecycle Manager (DLM)** policy to take daily snapshots of its attached EBS volume.

### 🔸 What You'll Learn:

* Launch EC2 with a new EBS volume
* Use DLM to automate EBS snapshot backups
* Learn about volume management and backup automation

### 🛠 Terraform Resources:

* `aws_instance`
* `aws_ebs_volume`
* `aws_ebs_volume_attachment`
* `aws_dlm_lifecycle_policy`

---


