# AWS_Rstudio_Server
## Architecture
![](https://github.com/Jinn42/AWS_Rstudio_Server/blob/master/Architecture_diagram.png)
## Environment Setting
-Create a VPC (CIDR: 10.0.0.0/16)

-Create a Public Subnet (CIDR: 10.0.0.0/24)

-Create an Internet Gateway and attach it to the VPC

-Create and/or edit the Route Table
![](https://github.com/Jinn42/AWS_Rstudio_Server/blob/master/Routetable.png)

-In the Public Subnet, launch an EC2 instance (e.g., Amazon Linux 2 AMI)

-Allocate a new Elastic IP address and associate it to the EC2 instance

-Edit the Security Group of the EC2 instance (RStudio Server uses port 8787)
![](https://github.com/Jinn42/AWS_Rstudio_Server/blob/master/Security_Group.png)
