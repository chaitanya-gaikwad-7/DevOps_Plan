##  **Terraform Fundamentals (IaC Tool)**

Terraform helps you declare infrastructure as code. You'll use it to automate everything you did manually in the AWS Console.

### 1. **What is Infrastructure as Code (IaC)?**

* Why IaC is better than manual provisioning
* Declarative vs imperative IaC tools (Terraform is declarative)
* Benefits: repeatability, version control, automation

### 2. **Terraform Setup**

* Install Terraform locally
* Setup AWS CLI and credentials
* Connect Terraform to AWS using `provider "aws"`

---

### 3. **Core Terraform Concepts to Learn:**

| Concept            | What to Learn                                                                |
| ------------------ | ---------------------------------------------------------------------------- |
| **Provider**       | Used to connect Terraform to a cloud platform (e.g., `aws`)                  |
| **Resource**       | The actual cloud object you want to create (`aws_instance`, `aws_s3_bucket`) |
| **Variables**      | Dynamic inputs (`variable "region" {}` etc.)                                 |
| **Outputs**        | Display values after a run (e.g., public IP of EC2)                          |
| **State File**     | Tracks what's been provisioned (`terraform.tfstate`)                         |
| **Init/Plan/App**  | `terraform init`, `plan`, `apply`, `destroy` — core CLI commands             |
| **Data Sources**   | Fetch existing resources (optional for now)                                  |
| **Remote Backend** | (Optional, advanced) Store state remotely (e.g., in S3)                      |

---

### 4. **Terraform Project Structure**

```
main.tf       # Core resources
variables.tf  # Variables and their types/defaults
outputs.tf    # Output values (e.g. IPs, bucket names)
terraform.tfvars  # Actual values for variables
```

---