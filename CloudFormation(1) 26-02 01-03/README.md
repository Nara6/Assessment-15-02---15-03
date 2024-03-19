# Assessment CloudFormation 1
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
    - app-subnet1: 10.0.24.0/24
    - app-subnet2: 10.0.25.0/24
    - app-subnet3: 10.0.26.0/24
- Create an EC2
    - OS: Ubuntu (or any OS you prefer)
    - Subnet: app-subnet-1
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
- Users can access the endpoint of NLB to access the website MediaWiki

## Infrastructure
<img src="./Infra-Cloudformation 1.png" width="1000"/>
