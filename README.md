# Terraform Two-Tier AWS Architecture

## Project Overview

This project demonstrates Infrastructure as Code (IaC) using Terraform to deploy a two-tier AWS architecture. The infrastructure includes a custom VPC, public and private subnets, security groups, route tables, and EC2 instances.

The objective is to automate cloud infrastructure provisioning and eliminate manual AWS console configuration (ClickOps).

## Architecture

Internet → Internet Gateway → Public Subnet (Web Server)

↓

Private Subnet (Database Server)

### Components

* VPC (10.0.0.0/16)
* Public Subnet (10.0.1.0/24)
* Private Subnet (10.0.2.0/24)
* Internet Gateway
* Route Table
* Web Security Group (HTTP/SSH)
* Database Security Group (MySQL only from Web Tier)
* EC2 Web Server with Apache
* EC2 Database Server

## Project Structure

* main.tf – Provider configuration
* variables.tf – Input variables
* network.tf – VPC, subnets, routing
* security.tf – Security groups
* compute.tf – EC2 instances
* outputs.tf – Output values
* .gitignore – Excludes secrets and state files

## Deployment Steps

```bash
terraform init
terraform validate
terraform plan
terraform apply
```

## Verification

* Apache web server deployed successfully
* Public web page accessible through browser
* Infrastructure provisioned entirely through Terraform

## Cleanup

```bash
terraform destroy
```

## Technologies Used

* Terraform
* AWS EC2
* AWS VPC
* AWS Security Groups
* Git
* GitHub

## Learning Outcomes

* Infrastructure as Code
* AWS Networking
* Terraform Resource Dependencies
* Security Group Design
* Cloud Resource Lifecycle Management
