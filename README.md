# AWS Infrastructure Provisioning using Terraform & Jenkins

## 📌 Project Overview

This project demonstrates Infrastructure as Code (IaC) using Terraform to provision AWS resources and automate infrastructure deployment through a Jenkins CI/CD pipeline.

Instead of manually creating cloud resources, Terraform is used to define the infrastructure in code, while Jenkins automates validation, planning, and deployment.

---

## 🚀 Project Objectives

- Provision AWS infrastructure using Terraform
- Automate infrastructure deployment using Jenkins
- Validate Terraform configuration
- Generate execution plans before deployment
- Apply or destroy infrastructure using pipeline parameters
- Visualize infrastructure dependencies using Terraform Graph

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| Terraform | Infrastructure as Code |
| Jenkins | CI/CD Automation |
| AWS EC2 | Compute Service |
| IAM Role | Secure AWS Authentication |
| Git & GitHub | Version Control |
| Linux | Operating System |

---

## 🏗️ Infrastructure Setup

| Server | Purpose |
|---------|---------|
| Terraform Server | Executes Terraform |
| Jenkins Server | Runs Infrastructure Pipeline |
| AWS | Cloud Infrastructure |

---

## 🔄 Pipeline Workflow

1. Developer pushes Terraform code to GitHub.
2. Jenkins checks out the repository.
3. Terraform initializes the working directory.
4. Terraform validates the configuration.
5. Terraform generates an execution plan.
6. User selects **apply** or **destroy**.
7. Terraform provisions or removes AWS resources.

---

## ⚙️ Jenkins Pipeline Stages

- Checkout
- Terraform Init
- Terraform Validate
- Terraform Plan
- Terraform Apply / Destroy

---

## 📂 Repository Structure

```
terraform-jenkins-infrastructure
│
├── README.md
├── Jenkinsfile
├── .gitignore
├── LICENSE
│
├── terraform/
│   ├── main.tf
│   ├── variables.tf
│   ├── outputs.tf
│   ├── provider.tf
│   └── terraform.tfvars.example
│
├── scripts/
│   ├── terraform.sh
│   └── jenkins.sh
│
├── docs/
│   └── setup-guide.md
│
└── images/
    ├── architecture.png
    ├── jenkins-pipeline.png
    ├── terraform-plan.png
    ├── terraform-graph.png
    └── aws-resources.png
```

---

## ✨ Key Features

- Infrastructure as Code
- Automated Infrastructure Deployment
- Terraform State Management
- Jenkins Pipeline Automation
- IAM Role Authentication
- Infrastructure Validation
- Execution Planning
- Automated Apply/Destroy
- Infrastructure Visualization

---

## 📁 Project Files

| File | Description |
|------|-------------|
| Jenkinsfile | CI/CD Pipeline |
| main.tf | Infrastructure Definition |
| provider.tf | AWS Provider Configuration |
| variables.tf | Input Variables |
| outputs.tf | Output Values |
| terraform.sh | Terraform Installation |
| jenkins.sh | Jenkins Installation |

---

## 📸 Screenshots


- Jenkins Dashboard
- Pipeline Stage View
- Terraform Init
- Terraform Plan
- Terraform Apply
- AWS EC2 Console
- Terraform Graph
- Successful Pipeline

---

## 📚 Skills Demonstrated

- Terraform
- Infrastructure as Code (IaC)
- Jenkins
- AWS
- IAM Roles
- Git & GitHub
- Linux
- CI/CD
- Terraform Graph

---

## 🔮 Future Enhancements

- Provision VPC, Subnets & Security Groups
- Store Terraform State in S3
- Use DynamoDB for State Locking
- Multi-Environment Deployment
- Terraform Modules
- GitHub Webhooks
- Integrate SonarQube

