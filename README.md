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
