# AWS_Rstudio_Server
Architecture
![]
## Environment Setting
reate a VPC (CIDR: 10.0.0.0/16)

Create a Public Subnet (CIDR: 10.0.0.0/24)

Create an Internet Gateway and attach it to the VPC

Create and/or edit the Route Table
![]

In the Public Subnet, launch an EC2 instance (e.g., Amazon Linux 2 AMI)

If necessary, allocate a new Elastic IP address and associate it to the EC2 instance

Edit the Security Group of the EC2 instance (RStudio Server uses port 8787)
![]
