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

---

## 🚀 Trigger GitHub Actions Pipeline

The GitHub Actions CI/CD pipeline is configured to trigger automatically on every `push` to the `main` branch.

### 🔄 Auto-Trigger on Code Push

Whenever you push any code changes to the `main` branch — such as Dockerfile changes, app logic, or configurations in `medusa-backend/` — the workflow will:

1. **Checkout the repository**
2. **Authenticate with AWS and DockerHub**
3. **Build & Push the Docker Image** to DockerHub
4. **Render ECS Task Definition**
5. **Deploy the latest container** to AWS ECS Fargate

#### ✅ Steps to Trigger

```bash
# Make changes to your Medusa backend or Dockerfile
cd medusa-backend
nano Dockerfile   # or modify source files

# Add and commit your changes
git add .
git commit -m "Updated backend logic or Dockerfile"

# Push to main branch
git push origin main
```

## 🧪 Verifying Successful Deployment

Once the GitHub Actions pipeline finishes successfully:

- ✅ **Access the Medusa Backend**  
  Visit the **ALB DNS Name** output by Terraform (or retrieve it from the AWS Console):
  - AWS Console → EC2 → Load Balancers → Select your ALB → Description tab → DNS Name

- ✅ **Check ECS Logs for Debugging or Confirmation**  
  Navigate to:
  - AWS Console → **ECS**
  - Select **Clusters**
  - Choose `medusa-cluster`
  - Go to **Tasks**
  - Select the running task
  - Click on the **Logs** tab to view container output
 
## 🧭 Running the Application Locally

To run the application locally, follow these steps:

```bash
cd medusa-backend
npm run start
```
🔐 Creating Admin Login Credentials
To create your admin user credentials, run the following command:
```
medusa user -e your-email@example.com -p yourPassword123
```
Replace your-email@example.com and yourPassword123 with your desired login credentials.

✅ Logging In
After creating the user, visit:

```
http://localhost:9000/app/login
```
Enter the email and password you just set — and you're in! 🚀


