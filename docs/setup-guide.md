# Terraform Infrastructure Provisioning using Jenkins

## Overview

This project demonstrates Infrastructure as Code (IaC) using Terraform to provision AWS infrastructure and automate deployments through a Jenkins Pipeline.

The pipeline validates the Terraform configuration, generates an execution plan, and allows the user to either create or destroy infrastructure using Jenkins parameters.

---

# Architecture

```
Developer
    │
    ▼
GitHub Repository
    │
    ▼
Jenkins Pipeline
    │
    ├── Checkout Source Code
    ├── Terraform Init
    ├── Terraform Validate
    ├── Terraform Plan
    └── Terraform Apply / Destroy
                │
                ▼
            AWS Cloud
                │
                ▼
        Infrastructure Resources
```

---

# Prerequisites

- AWS Account
- Amazon Linux 2 EC2 Instance
- IAM Role attached to the EC2 instance
- Git Installed
- Jenkins Installed
- Terraform Installed

---

# Infrastructure

| Server | Purpose |
|---------|---------|
| Terraform Server | Executes Terraform commands |
| Jenkins Server | Runs the CI/CD pipeline |
| AWS | Hosts the infrastructure resources |

---

# Step 1 – Launch an EC2 Instance

Launch an Amazon Linux 2 EC2 instance.

Attach an **IAM Role** with the required AWS permissions (for example, `AdministratorAccess`) instead of using AWS access keys.

Verify IAM Role access:

```bash
aws sts get-caller-identity
```

---

# Step 2 – Install Terraform

Run the installation script.

```bash
sh scripts/terraform.sh
```

Verify installation.

```bash
terraform -version
```

---

# Step 3 – Install Jenkins

Run the Jenkins installation script.

```bash
sh scripts/jenkins.sh
```

Open Jenkins in your browser.

```
http://<JENKINS_PUBLIC_IP>:8080
```

Retrieve the initial administrator password.

```bash
cat /var/lib/jenkins/secrets/initialAdminPassword
```

Complete the Jenkins setup by installing the recommended plugins and creating the administrator account.

---

# Step 4 – Install Jenkins Plugin

Install the **Pipeline Stage View** plugin.

Navigate to:

```
Manage Jenkins
→ Plugins
→ Available Plugins
→ Pipeline Stage View
```

Install and restart Jenkins if required.

---

# Step 5 – Create the Jenkins Pipeline

Create a new **Pipeline** project.

Configure the pipeline to use the `Jenkinsfile` stored in this repository.

---

# Step 6 – Configure Build Parameter

Enable **This project is parameterized**.

Create a **Choice Parameter**.

| Parameter | Values |
|-----------|--------|
| action | apply, destroy |

This parameter determines whether Terraform provisions or destroys the infrastructure.

---

# Step 7 – Execute the Pipeline

Run the pipeline.

The pipeline performs the following stages:

1. Checkout source code
2. Terraform Init
3. Terraform Validate
4. Terraform Plan
5. Terraform Apply or Destroy

---

# Step 8 – Verify Infrastructure

After a successful deployment, verify the created resources.

Example:

```bash
terraform show
```

Check the AWS Console to confirm that the resources have been created.

---

# Step 9 – Visualize Infrastructure

Generate the infrastructure graph.

```bash
terraform graph
```

Copy the output and paste it into Graphviz Online to visualize the infrastructure dependencies.

---

# Repository Structure

```
terraform-jenkins-infrastructure/
│
├── README.md
├── Jenkinsfile
├── .gitignore
├── LICENSE
│
├── terraform/
│   ├── main.tf
│   ├── provider.tf
│   ├── variables.tf
│   ├── outputs.tf
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
```

---

# Skills Demonstrated

- Terraform
- Infrastructure as Code (IaC)
- Jenkins
- AWS
- IAM Roles
- Git & GitHub
- Linux Administration
- CI/CD Pipeline
- Terraform Graph

---

# Future Enhancements

- Remote Terraform State using Amazon S3
- DynamoDB State Locking
- Terraform Modules
- Multi-Environment Deployment
- GitHub Webhook Integration
- Infrastructure Testing
- Terraform Cloud Integration


