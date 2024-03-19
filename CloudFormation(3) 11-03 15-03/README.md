# Assessment CloudFormation 3
## Purpose
<b>MediaWiki</b> is a free and open-source wiki engine where you can host an online documentation application.
It helps you collect and organize knowledge and make it available to people.
In this demo, we want you to be able to host a private MediaWiki website in AWS resources. So Users are able to access it from a specific
network.
You have to deploy it using a cloud formation template.

## Detail description

- Create the customed VPC 
    - VPC: 10.0.0.0/16
    - Tag: demo-vpc
- Create 3 private subnets with tags and subnets in 3 AZs as below:
    - pub-subnet1: 10.0.21.0/24
    - pub-subnet2: 10.0.22.0/24
    - pub-subnet3: 10.0.23.0/24 
    - app-subnet1: 10.0.24.0/24
    - app-subnet2: 10.0.25.0/24
    - app-subnet3: 10.0.26.0/24
    - private-subnet1: 10.0.27.0/24
    - private-subnet1: 10.0.28.0/24
    - private-subnet1: 10.0.29.0/24
- Create Amazon Aurora DB clusters
    - Aurora Mysql
    - Subnet: private-subnet1,2,3
- Create an ECS Cluster with tasks on EC2 Launch type plus Auto Scaling Service
    - OS: Ubuntu (or any OS you prefer)
    - Subnet: app-subnet-1,2,3
    - Instance type: t2-micro
    - Software: docker-ce and docker-compose
    - Internet: Required
    - Deployment of your docker-compose with services
        - using MediaWiki docker image as frontend service
        - using Mysql docker image as backend service
        - expose only the frontend port to an instance
- Create NLB
    - Target group: listener and health check with port 80 of ec2 instance
- Create Security Group
    - Allow only specific IP addresses of users to access this website
- Using cloud formation template to create all resources and MediaWiki service
## Output
- Export NLB Endpoint url
- Please send us the configuration of the cloud formation template as yaml or json
- Draw a Diagram of the description above
- Users can access the endpoint of NLB to access the website MediaWiki

## Infrastructure
<p align="center">
<img src="./Infra-Cloudformation 2.png" width="660"/>
</p>
