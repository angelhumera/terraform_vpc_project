# 🚀 Terraform Project: AWS VPC with Public & Private Subnets

This project provisions a secure and scalable **AWS Virtual Private Cloud (VPC)** using **Terraform**.  
It creates the complete networking foundation required for cloud applications, following AWS best practices.

---

## 📌 **Project Overview**

Using Terraform ensures that the infrastructure is:

- **Version-controlled**
- **Reusable**
- **Consistent across environments** (Dev / Test / Prod)
- **Fully automated using Infrastructure-as-Code (IaC)**

This setup avoids manual errors and makes the AWS network easily repeatable with a single command.

---

## 🏗️ **Architecture Components Created**

### ✔ 1. VPC  
Custom VPC with CIDR: `10.0.0.0/16`

### ✔ 2. Subnets  
- **Public Subnet:** `10.0.1.0/24` (Auto-assign public IP enabled)  
- **Private Subnet:** `10.0.2.0/24`

### ✔ 3. Internet Gateway  
Enables the public subnet to access the internet.

### ✔ 4. Public Route Table  
Route `0.0.0.0/0` → Internet Gateway

### ✔ 5. Elastic IP (EIP)  
Required for NAT Gateway.

### ✔ 6. NAT Gateway  
Placed inside the public subnet to allow **private subnet** resources to access the internet *securely*.

### ✔ 7. Outputs  
Terraform prints IDs for:
- VPC  
- Subnets  
- Route table  
- NAT Gateway  

---

## 📁 **Project Structure**
terraform-vpc-project/
│
├── main.tf # VPC, Subnets, IGW, NAT, Routes
├── provider.tf # AWS Provider configuration
├── output.tf # Outputs for resource IDs
├── variables.tf # Variables (optional)
└── .gitignore # Terraform ignore files

