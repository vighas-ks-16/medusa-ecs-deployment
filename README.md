# 🚀 Deploy Medusa Headless Commerce Backend on AWS ECS Fargate using Terraform + GitHub Actions CI/CD

This project demonstrates how to deploy the **[Medusa.js](https://docs.medusajs.com/deployments/server/general-guide/)** backend on **AWS ECS with Fargate** using **Terraform** for Infrastructure as Code (IaC) and **GitHub Actions** for a complete CI/CD pipeline.

---

## 📁 Project Structure

```bash
.
├── terraform/
│   ├── main.tf
│   ├── variables.tf
│   ├── vpc.tf
│   ├── ecs.tf
│   ├── rds.tf
│   ├── alb.tf
│   ├── iam.tf
│   ├── security-groups.tf
│   ├── outputs.tf
│   └── ecs-task-def.json
├── medusa-backend/
│   ├── Dockerfile
│   └── # Medusa backend code
├── .github/
│   └── workflows/
│       └── deploy.yml
└── README.md
```

## Prerequisites

Ensure you have the following setup before proceeding:

### ✅ AWS Account Permissions

- [ ] **Amazon ECS** - Elastic Container Service for deploying Docker containers.
- [ ] **Amazon RDS** - Relational Database Service for database provisioning.
- [ ] **Application Load Balancer (ALB)** - For routing traffic to services.
- [ ] **IAM** - Access to create and manage IAM roles and policies.
- [ ] **VPC & Subnets** - Permissions to configure and use Virtual Private Cloud networking.

### ✅ Tools & Versions

- [ ] **Terraform** - Installed and configured (Version 1.5+ recommended).
- [ ] **Docker** - Installed and running on your local system.
- [ ] **DockerHub Account** - With access to push and pull images.

### ✅ GitHub Repository Setup

- [ ] **GitHub Actions Enabled** - Ensure workflows can be triggered.
- [ ] **Repository Secrets Configured**:
  - `DOCKER_USERNAME`
  - `DOCKER_PASSWORD`
  - `SERVER_IP`
  - `SERVER_USERNAME`
  - `SERVER_PASSWORD`


## 🧱 Terraform Infrastructure Setup
Navigate to the terraform/ directory and follow the steps below:

## 1️⃣ Initialize Terraform
```
cd terraform
terraform init
```
## 2️⃣ Review Terraform Plan
```
terraform plan
```
## 3️⃣ Apply Terraform Configurations
```
terraform apply
```
## 🚀 What This Setup Will Do

- [x] **Create a VPC** with both public and private subnets
- [x] **Provision an Application Load Balancer (ALB)** for traffic routing
- [x] **Create an ECS Cluster** and deploy a **Fargate service**
- [x] **Deploy the Medusa backend** as a Docker container
- [x] **Provision a PostgreSQL RDS instance** in the private subnet
- [x] **Output ALB DNS** name and **RDS endpoint** for external access

