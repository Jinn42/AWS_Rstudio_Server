# AWS_Rstudio_Server
## Architecture
<div align=center><img src=“https://github.com/Jinn42/AWS_Rstudio_Server/blob/master/Architecture_diagram.png”/></div>

## Environment Setting
-Create a VPC (CIDR: 10.0.0.0/16)

-Create a Public Subnet (CIDR: 10.0.0.0/24)

-Create an Internet Gateway and attach it to the VPC

-Create and/or edit the Route Table

![](https://github.com/Jinn42/AWS_Rstudio_Server/blob/master/Routetable.png)

-In the Public Subnet, launch an EC2 instance (Amazon Linux 2 AMI)

-Allocate a new Elastic IP address and associate it to the EC2 instance

-Edit the Security Group of the EC2 instance (RStudio Server uses port 8787)

![](https://github.com/Jinn42/AWS_Rstudio_Server/blob/master/Security_Group.png)

## Connection to Rstudio Server

-Go to Downloads

```
cd Downloads
```

-Look for keypair

```
ls *.pem
```

-Allow instance to access <keypair.pem>
```
chmod 400 (keypair.pem)
```
-Connect to Rstudio Server
```
ssh -i “keypair.pem” ec2-user@<Rstusio_Server public IP>
```

## Install R and Rstudio Server 

-Update the package manager
```
sudo yum update -y
```
-Install R
```
sudo amazon-linux-extras install R3.4
```
-Download and install RStudio Server (for Red Hat / CentOS 6-7)
```
wget https://download2.rstudio.org/server/centos6/x86_64/rstudio-serverrhel-1.2.5019-x86_64.rpm
```
```
sudo yum -y install rstudio-server-rhel-1.2.5019-x86_64.rpm
```
-Create user (username and password)
```
sudo useradd my_username
```
```
echo my_username:my_password | sudo chpasswd
```
