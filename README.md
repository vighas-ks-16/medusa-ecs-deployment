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
This will:

Create VPC with public and private subnets

Provision ALB (Application Load Balancer)

Create ECS Cluster and Fargate service

Deploy Medusa backend container

Setup PostgreSQL RDS in private subnet

Output ALB DNS and RDS endpoint

