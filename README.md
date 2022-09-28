# Ddacity Deploy High Availability Web App Using Cloudformation
This is a repo for a project in the Cloud DevOps Nanodegree that includes templates for network Infrastructure and Servers deployments

## Project Diagram
![Project Diagram](https://github.com/Moemad-711/udacity-deploy-web-app-cloudformation/blob/main/ProjectDiagram.png) 

## Steps to deploy
- Create the Network Infrastructure Using the following CLI command: 
  '''console
     aws cloudformation Create-stack --stack-name <Stack Name> --template-body file://./NetworkInfrastructure/ourinfra.yml --parameters file://./NetworkInfrastructure/ourinfra.json  --region=<Region Name>
  '''
- wait until the stack is created

- Create the Network Infrastructure Using the following CLI command: 
  '''console
     aws cloudformation Create-stack --stack-name <Stack Name> --template-body file://./ServerDeployment/server.yml --parameters file://./ServerDeployment/server.json  --region=<Region Name>
  '''
 
