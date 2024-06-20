Jira User Requirement Ticket

Summary
Create an AWS VPC module in Terraform to set up a VPC in the eu-west-1 region with 3 private subnets in 3 different availability zones (eu-west-1a, eu-west-1b, and eu-west-1c). Additionally, create a security group and network ACLs (NACLs) for the VPC.

Description
As a DevOps Engineer,
we want to have a Terraform module that sets up an AWS VPC with specific configurations,
so that we can easily deploy infrastructure in the eu-west-1 region with predefined security and network settings.

Acceptance Criteria
VPC Creation:
Create a VPC in the eu-west-1 region.
Use the CIDR block 10.215.51.0/25.

Private Subnets:
Create 3 private subnets, each in a different availability zone:
Subnet 1: 10.125.51.0/26 in eu-west-1a
Subnet 2: 10.215.51.64/27 in eu-west-1b
Subnet 3: 10.215.51.96/27 in eu-west-1c
Security Group:

Create a security group for the VPC.
Allow inbound HTTP (port 80) and HTTPS (port 443) traffic from any IP (0.0.0.0/0).
Allow all outbound traffic to any IP (0.0.0.0/0).
Network ACL (NACL):

Create a NACL for the VPC.
Allow inbound HTTP (port 80) and HTTPS (port 443) traffic from any IP (0.0.0.0/0).
Allow all outbound traffic to any IP (0.0.0.0/0).
Terraform Module Structure:

Use the terraform-aws-modules/vpc/aws module from the Terraform public registry for VPC and subnet creation.
Define variables for VPC CIDR, private subnet CIDRs, and availability zones.
Include appropriate outputs for the VPC ID and private subnet IDs.
Tasks
Set Up Terraform Configuration:

Define the provider for AWS with the region eu-west-1.

VPC Module Implementation:
Use the terraform-aws-modules/vpc/aws module for creating the VPC and subnets.
Configure the VPC CIDR and private subnets with specified CIDR blocks and availability zones.
Security Group Configuration:

Create a security group resource with the required ingress and egress rules.
Network ACL Configuration:

Create a network ACL resource with the required rules for inbound and outbound traffic.
Variables and Outputs:

Define variables for VPC CIDR, private subnets, and availability zones.
Define outputs for the VPC ID and private subnet IDs.
Testing and Validation:

Test the Terraform configuration to ensure it creates the VPC, subnets, security group, and NACLs as specified.
Validate that the created resources meet the acceptance criteria.
Additional Information
Module Source: terraform-aws-modules/vpc/aws
Region: eu-west-1
VPC CIDR Block: 10.215.51.0/25
Private Subnets and Availability Zones:
Subnet 1: 10.125.51.0/26 in eu-west-1a
Subnet 2: 10.215.51.64/27 in eu-west-1b
Subnet 3: 10.215.51.96/27 in eu-west-1c
Security Group:
Allow inbound HTTP (80) and HTTPS (443) from 0.0.0.0/0
Allow all outbound traffic
Network ACL:
Allow inbound HTTP (80) and HTTPS (443) from 0.0.0.0/0
Allow all outbound traffic
