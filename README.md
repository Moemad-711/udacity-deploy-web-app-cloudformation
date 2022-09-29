# Ddacity Deploy High Availability Web App Using Cloudformation
This is a repo for a project in the Cloud DevOps Nanodegree that includes templates for network Infrastructure and Servers deployments

## Project Diagram
![Project Diagram](https://github.com/Moemad-711/udacity-deploy-web-app-cloudformation/blob/main/ProjectDiagram.png) 

## Steps to deploy
- Create the Network Infrastructure Using the following CLI command: 
```console 
aws cloudformation Create-stack --stack-name <Stack Name> --template-body file://./NetworkInfrastructure/ourinfra.yml --parameters file://./NetworkInfrastructure/ourinfra.json  --region=<Region Name>
```
- Wait until the stack is created successfully

- Create the Network Infrastructure Using the following CLI command: 
```console 
aws cloudformation Create-stack --stack-name <Stack Name> --template-body file://./ServerDeployment/server.yml --parameters file://./ServerDeployment/server.json  --region=<Region Name>
```
- wait until the stack is created successfully

## Steps to SSH into the Web APP Host
- Copy the Web App SSH Key Pem File to the Bastion Host Using the following command: 
```console 
scp -i <BastionHostSSHKeyPemFile> <WebAppSSHKeyPemFile> ec2-user@<BastionHostIP>:/home/ec2-user/<WebAppSSHKeyPemFile>
```
- SSH to the Bastion Host by using the following Command (Open SSH):
```console 
ssh ec2-user@<Bastion Host Public IP> -i <BastionHostSSHKeyPemFile>
```
  or Use [Secure Shell Extension](https://chrome.google.com/webstore/detail/secure-shell/iodihamcpbpeioajjeobimgagajmlibd) of google chrome
  
- From Whithin the Bastion Host run the following commandw:
```console 
chmod 400 <WebAppSSHKeyPemFile>
ssh ubuntu@<Web App Private IP> -i <WebAppSSHKeyPemFile>
```
