# Project Name: Grafana-EKS-Automation

## Overview
This project provisions and manages resources for setting up Amazon EKS (Elastic Kubernetes Service) clusters and deploying Grafana dashboards. It uses Terraform to automate infrastructure provisioning and GitHub Actions workflows for deployment and destruction of resources.
 
## Features
- Provisioning of EKS clusters using Terraform.
- Deployment of Grafana dashboards for monitoring Kubernetes clusters.
- Automated workflows for creating and destroying resources using GitHub Actions.

## Prerequisites
- **Terraform**: Ensure you have Terraform installed. You can download it from [Terraform's official site](https://www.terraform.io/downloads).
- **AWS CLI**: Install and configure AWS CLI with the necessary credentials.
- **kubectl**: Install `kubectl` to interact with the Kubernetes cluster.
- **GitHub Repository**: Clone the project repository.

## Setup Instructions

### 1. Clone the Repository
```bash
 git clone https://github.com/Vaibhav871/terraform-automation.git
```

### 2. Configure AWS Credentials
Ensure that your AWS CLI is configured with sufficient permissions to create and manage EKS resources.
```bash
aws configure
```

### 3. Initialize Terraform
Run the following command to initialize Terraform in the project directory:
```bash
terraform init
```

### 4. Plan the Infrastructure
Preview the changes Terraform will apply to your AWS environment:
```bash
terraform plan
```

### 5. Apply the Infrastructure
Deploy the infrastructure by running:
```bash
terraform apply
```

### 6. Destroy the Infrastructure
To clean up resources and destroy the infrastructure, run:
```bash
terraform destroy
```

Alternatively, use the GitHub Actions workflow for destruction.

## GitHub Actions Workflows

### Destroy Workflow
To destroy the resources via GitHub Actions:
1. Navigate to **Actions** in the GitHub repository.
2. Select **Destroy-EKS-Grafana-Dashboards** workflow.
3. Click **Run workflow** and confirm.

### Provision Workflow
To Provision the resources via GitHub Actions:
1. Navigate to **Actions** in the GitHub repository.
2. Select **EKS-Grafana-Dashboards** workflow.
3. Click **Run workflow** and confirm.

## Common Issues and Resolutions

### Error: DependencyViolation
**Description:** Resources like subnets cannot be deleted due to dependencies.
**Resolution:**
- Ensure all resources dependent on the subnet (e.g., NAT gateways, route tables) are deleted.
- Use `terraform refresh` to sync the Terraform state file with the real-world infrastructure.

### Error: Duplicate Resource Definitions
**Description:** Errors related to duplicate provider configurations, modules, or data blocks.
**Resolution:**
- Check for redundant definitions in the Terraform files and remove duplicates.
- Use the `alias` argument for multiple configurations of the same provider.

## Useful Terraform Commands
- **Refresh State:**
  ```bash
  terraform refresh
  ```
  Syncs the Terraform state with real-world infrastructure.

- **Check Plan:**
  ```bash
  terraform plan
  ```
  Previews the changes Terraform will make.

- **Destroy Resources:**
  ```bash
  terraform destroy
  ```
  Deletes all resources managed by Terraform.

## Contributors

- **Vaibhav Jaiswal** - [GitHub Profile](https://github.com/vaibhavjaiswal)
- **Rehan Khan** - [GitHub Profile](https://github.com/Rehankhan008)
- **Shriyanshu Dwivedi** - [GitHub Profile](https://github.com/mrkhalnayak)

Feel free to contribute to this project by submitting pull requests or raising issues.

## Contributing
Contributions are welcome! Please follow the standard GitHub flow:
1. Fork the repository.
2. Create a feature branch.
3. Submit a pull request with your changes.
---

For any questions or support, feel free to reach out via the repository's issue tracker.
