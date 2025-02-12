# 3 Tier Architecture Using Terraform and AWS
## Overview
This project provisions a fully automated and scalable three-tier architecture on AWS using Terraform. The architecture consists of a VPC with public and private subnets, hosting EC2 instances in each tier. Terraform is used to define and manage infrastructure as code, ensuring consistency and repeatability. The public subnet hosts a publicly accessible EC2 instance, while the private subnet contains backend instances that communicate securely through internal networking.

## Architecture 
The architecture consists of the following components:

VPC: A Virtual Private Cloud for network isolation.
Public Subnet: Contains a publicly accessible EC2 instance.
Private Subnet: Contains an EC2 instance that does not have direct internet access.
Internet Gateway: Allows outbound internet access from the public subnet.
Route Table: Routes traffic from the public subnet to the internet and enables private subnet communication.
Security Groups: Controls inbound and outbound traffic for the EC2 instances.
Network ACLs: Provides an additional layer of security.
Infrastructure as Code (Terraform)
This project is implemented using Terraform for Infrastructure as Code (IaC). The Terraform configuration automates the provisioning of AWS resources.

## Prerequisites
Ensure you have the following installed:

Terraform (>= 1.0.0)
AWS CLI (configured with appropriate IAM credentials)
Terraform Files
The following Terraform files define the infrastructure:

data.tf - Defines data sources used in the configuration.
ec2.tf - Configures EC2 instances in the architecture.
local.tf - Defines local values and reusable variables.
main.tf - Defines the core VPC, subnets, and networking components.
network.tf - Configures networking resources, including subnets and route tables.
output.tf - Specifies the output values for key resources.
providers.tf - Specifies the required Terraform providers.
rds.tf - Configures the RDS database instance.
variables.tf - Contains configurable variables.
Deployment Steps
Initialize Terraform:
```bash
terraform init
```
Plan the deployment:
```bash
terraform plan
```
Apply the configuration:
```bash
terraform apply -auto-approve
```
Verify Resources:
Check the AWS Management Console.
Use aws ec2 describe-instances to verify instance creation.
Destroying the Infrastructure
To delete all resources:
```bash
terraform destroy -auto-approve
```
