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

## ✅ Prerequisites
AWS Account with permissions to use:

ECS

RDS

ALB

IAM

VPC/Subnets

Terraform (v1.5+)

Docker & DockerHub

GitHub Repository with:

GitHub Actions enabled

Repository secrets added

## 🔐 Required GitHub Secrets
In your GitHub repo, go to Settings > Secrets > Actions and add the following:


AWS_ACCESS_KEY_ID	
AWS_SECRET_ACCESS_KEY	
DOCKER_USERNAME	
DOCKER_PASSWORD	

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

