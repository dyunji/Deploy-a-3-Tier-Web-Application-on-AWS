# Deploying a High Available, Fault Tolerant and Secure AWS 3-Tier Web Architecture

## Project Overview

The purpose of this project is to create a scalable and highly available, fault tolerant three-tier architecture on AWS. The architecture consists of a web tier, application tier, and database tier, enabling the deployment of a web application with efficient resource utilization.

## Architecture Overview
The 3-tier architecture is designed to separate the presentation layer (web tier), application logic layer (application tier), and data storage layer (database tier). This separation allows for modular development, scalability, and flexibility.

![3TierArch](https://github.com/dyunji/Deploy-a-3-Tier-Web-Application-on-AWS/assets/150227567/65702d56-3dd5-400e-b76b-6ede7b399ca2)


## Infrastructure Setup
The infrastructure is set up on AWS using the following components:

* Virtual Private Cloud (VPC): A logically isolated section of the AWS cloud where the architecture is deployed.
* Subnets: Six subnets are created within the VPC to distribute the resources across availability zones for high availability.
* Security Groups: Network-level access control to allow specific traffic between the tiers and restrict unauthorized access.

### Creating VPC
![VPC](https://github.com/dyunji/Deploy-a-3-Tier-Web-Application-on-AWS/assets/150227567/9c82fc20-0ee9-4aa7-9520-8f95ceca505c)

### Creating Six Subnets
![Subnets](https://github.com/dyunji/Deploy-a-3-Tier-Web-Application-on-AWS/assets/150227567/a4081da8-7290-47bc-aa9c-3a0b614e69fb)

### Creating Route Table and Subnet Association
![Route Tables](https://github.com/dyunji/Deploy-a-3-Tier-Web-Application-on-AWS/assets/150227567/0bb49840-6368-459d-b893-d2b315400fbf)

### Creating Internet Gateways and attach to VPC
![Internet Gateways](https://github.com/dyunji/Deploy-a-3-Tier-Web-Application-on-AWS/assets/150227567/98c3dbd5-4813-4c25-a9b5-1082516d2229)

### Creating NAT Gateways with Elastic IP Address for Private Subnets
![NAT Gateways](https://github.com/dyunji/Deploy-a-3-Tier-Web-Application-on-AWS/assets/150227567/7f6771c6-6ec3-4362-8c96-02114083ea57)

![Elastic IP Address](https://github.com/dyunji/Deploy-a-3-Tier-Web-Application-on-AWS/assets/150227567/53d7c099-7f29-4257-bf26-7f24d858c87d)

### Creating Security Groups
![Security Groups](https://github.com/dyunji/Deploy-a-3-Tier-Web-Application-on-AWS/assets/150227567/81a64c7a-8b51-4138-87d4-0014c5597fdb)


## Component Details
1. Web Tier:
   
* The web tier consists of EC2 instances running web servers, serving as the front-end layer.
* The web servers receive HTTP requests from users and pass them to the application tier for processing.
  
![EC2](https://github.com/dyunji/Deploy-a-3-Tier-Web-Application-on-AWS/assets/150227567/2a8a6a2d-ad86-4b7b-a5f7-b78d32a47c88)

2. Application Tier:
   
* The application tier contains EC2 instances running the application server software.
* The application servers process requests from the web tier, handle business logic, and interact with the database tier.

![EC2](https://github.com/dyunji/Deploy-a-3-Tier-Web-Application-on-AWS/assets/150227567/a9fa7fef-676e-4d56-918a-30b46367b891)


3. Database Tier:
   
* Subnet Groups
* The database tier consists of Amazon RDS, a managed relational database service.
* MySQL is used as the database engine.
* The database stores and manages the application's data.
  
![RDS Subnet Groups](https://github.com/dyunji/Deploy-a-3-Tier-Web-Application-on-AWS/assets/150227567/aad1f9fe-5f5e-4bf8-9d0f-c8a0b2c14b33)

![RDS](https://github.com/dyunji/Deploy-a-3-Tier-Web-Application-on-AWS/assets/150227567/9aae3d06-c76e-4813-9a4a-1f4a3b7649f8)

## Scalability and High Availability

The architecture supports scalability and high availability through the following mechanisms:

* Auto Scaling: Auto Scaling groups are configured in both the web and application tiers to automatically adjust the number of instances based on the workload.
* Elastic Load Balancer: A load balancer is placed in front of the web servers to distribute incoming traffic and ensure high availability.

Creating Launch Templates, Target Groups, Application Load Balancers and Auto Scalling Group

![Launch Templates](https://github.com/dyunji/Deploy-a-3-Tier-Web-Application-on-AWS/assets/150227567/4fef476d-1bd0-498f-a4d7-dc14be2e05bd)
![Target Groups](https://github.com/dyunji/Deploy-a-3-Tier-Web-Application-on-AWS/assets/150227567/4173d9b9-5993-48ba-b025-c1c1315b66f6)
![Load Balancers](https://github.com/dyunji/Deploy-a-3-Tier-Web-Application-on-AWS/assets/150227567/15aeb1b7-ddb1-421d-86f0-201bbcb3eb1a)
![Auto Scalling Groups](https://github.com/dyunji/Deploy-a-3-Tier-Web-Application-on-AWS/assets/150227567/89cb6509-6096-4fc0-a05c-69818662a2cb)

## Conclusion
This project documentation outlines a 3-tier architecture deployed on AWS, aiming to create a scalable and highly available and fault tolerant web application. The architecture consists of a web tier, application tier, and database tier, with each tier fulfilling specific functions. The infrastructure setup involves a Virtual Private Cloud (VPC) with six subnets, security groups, and appropriate network configurations.



