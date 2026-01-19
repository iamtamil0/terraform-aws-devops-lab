# Terraform AWS DevOps Lab

This project demonstrates **end-to-end AWS infrastructure provisioning using Terraform**.
It covers networking, security, compute, and automation using Infrastructure as Code (IaC).

This lab was built as part of my DevOps learning journey and reflects real-world
cloud and DevOps practices.

---

## 🚀 What This Project Does

Using Terraform, this project automatically provisions:

- Custom AWS VPC (no default VPC dependency)
- Public Subnet
- Internet Gateway
- Route Table & Association
- Security Group (SSH + HTTP)
- EC2 Instance (Ubuntu 22.04)
- Automatic Docker installation using EC2 User Data

All resources are created and destroyed using Terraform commands.

---

## 🧱 Architecture Overview

- **VPC CIDR:** `10.0.0.0/16`
- **Subnet CIDR:** `10.0.1.0/24`
- **Inbound Access:**
  - SSH (22)
  - HTTP (80)
- **OS:** Ubuntu 22.04
- **Region:** ap-south-1 (Mumbai)

---

## 📁 Project Structure

```text
terraform-aws-devops-lab/
├── main.tf
├── provider.tf
├── variables.tf
├── terraform.tfvars
├── outputs.tf
└── README.md

⚙️ Prerequisites

AWS Account

IAM User with EC2 & VPC permissions
AWS CLI installed and configured
Terraform installed
Existing EC2 Key Pair (.pem file)

🔐 AWS Authentication

Configure AWS CLI before running Terraform:

aws configure

Verify:

aws sts get-caller-identity

🛠️ Terraform Commands (Run in Order)
Initialize Terraform
terraform init

Validate Configuration
terraform validate

Review Execution Plan
terraform plan

Create Infrastructure
terraform apply


Type:

yes

🔑 SSH into EC2

After apply, Terraform outputs the public IP.

ssh -i my-ec2-key.pem ubuntu@<PUBLIC_IP>


Fix key permissions if needed:

chmod 400 my-ec2-key.pem


🐳 Verify Docker Auto-Installation

Docker is installed automatically via EC2 user-data.

docker --version
docker ps

🧹 Destroy Infrastructure (Cost Control)
terraform destroy

Type:

yes

🎯 Key Learnings

Infrastructure as Code using Terraform
Custom VPC creation (no default VPC dependency)
AWS networking fundamentals
Security Groups as code
EC2 user-data automation
Docker auto-installation
Cost control using terraform destroy

🎯 Key Learnings

Infrastructure as Code using Terraform
Custom VPC creation (no default VPC dependency)
AWS networking fundamentals
Security Groups as code
EC2 user-data automation
Docker auto-installation
Cost control using terraform destroy

👤 Author

Tamilmani N

GitHub: https://github.com/iamtamil0
LinkedIn: https://www.linkedin.com/in/ntamilmanin


---

# ✅ UPLOAD EVERYTHING TO GITHUB (STEP-BY-STEP)

Run these commands inside your project folder:

```bash
git status