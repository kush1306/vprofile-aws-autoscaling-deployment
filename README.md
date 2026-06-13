# vprofile-aws-autoscaling-deployment

End-to-end AWS deployment of VProfile using S3 artifact storage, EC2, ALB, Auto Scaling Groups, and Tomcat.

## About this project

I put this project together to get hands-on experience deploying a real Java web application (VProfile) on AWS in a way that's actually scalable and highly available — not just a single server running the app, but a full setup that can handle traffic spikes and instance failures gracefully.

The application artifact (WAR file) is stored in Amazon S3 and deployed onto EC2 instances running Apache Tomcat. An Application Load Balancer sits in front to distribute incoming traffic, and an Auto Scaling Group keeps the right number of instances running based on demand.

## AWS Services Used

- **Amazon EC2** – hosts the application on Apache Tomcat
- **Amazon S3** – stores the deployment artifact (WAR file)
- **Application Load Balancer (ALB)** – distributes traffic across instances
- **Auto Scaling Group (ASG)** – scales instances up/down and maintains availability
- **IAM Roles** – allows EC2 to pull the artifact from S3 securely, without hardcoded credentials
- **Security Groups** – controls inbound and outbound traffic to the instances

## Architecture Diagram

![Architecture Diagram](Architecture.drawio%20(1).png)

## Deployment Workflow

Here's how the deployment process actually came together, step by step:

1. Built the application artifact (WAR file).
2. Uploaded the WAR file to an S3 bucket.
3. Launched EC2 instances to host the application.
4. Installed and configured Apache Tomcat on each instance.
5. Pulled the artifact from S3 onto the instances using the AWS CLI.
6. Deployed the WAR file on Tomcat.
7. Set up an Application Load Balancer to route traffic to the instances.
8. Configured an Auto Scaling Group to handle scaling and availability.
9. Verified the application was accessible and running correctly.

## Screenshots

A few screenshots from the process:

- Application running in the browser
- EC2 dashboard showing running instances
- Load Balancer configuration
- Target group health checks
- Auto Scaling Group setup
- S3 bucket with the stored artifact
- Deployment session via SSH
- Security Group rules

## What This Project Helped Me Practice

- Working with AWS cloud infrastructure
- Basic Linux server administration
- Deploying Java applications on Apache Tomcat
- Using the AWS CLI for artifact management
- Setting up and using IAM roles
- Configuring Application Load Balancers
- Setting up Auto Scaling Groups
- Managing deployment artifacts with S3

## What I Learned

This project gave me a much clearer picture of how production-style deployments work on AWS — not just spinning up servers, but thinking about scalability, availability, and how services like EC2, S3, ALB, and Auto Scaling all work together. It also helped me get more comfortable working on Linux servers from the command line and managing a deployment end to end, from build to live application.
