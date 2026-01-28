# ALB + Auto Scaling + NGINX Project

## Overview
High-Availability Web App with AWS ALB & Auto Scaling – Demonstrates scalable, load-balanced infrastructure using EC2, ALB, and ASG.

ALB	Distributes traffic and provides health checks
Auto Scaling Group	Automatically adds/removes EC2 instances based on load
EC2 (Amazon Linux 2 + NGINX)	Hosts the web app

- Application Load Balancer (ALB)
- Auto Scaling Group (ASG)
- NGINX on Amazon Linux 2
- Default VPC

The setup ensures high availability and automatic scaling.

## Steps Performed
1. Created a security group `web-sg` allowing HTTP (80) and SSH (22).  
2. Created a launch template `nginx-template` with User Data to install NGINX.  
3. Created a target group `web-tg` for ALB health checks.  
4. Created Auto Scaling Group `web-asg` with 2 instances attached to `web-tg`.  
5. Created an Internet-facing ALB `web-alb` attached to `web-tg`.  
6. Verified instances are healthy and NGINX serves the HTML page via ALB.

## Screenshots
- Auto Scaling Group Overview: ![ASG](screenshots/asg.png)  
- Target Group Healthy Status: ![Target Group](screenshots/target-group.png)  
- Launch Template Details: ![Launch Template](screenshots/launch-template.png)  
- Browser Showing NGINX via ALB: ![ALB Test](screenshots/alb-test.png)  

## Notes
- All resources are in the **default VPC**.  
- Instances automatically receive public IPv4 addresses.  
- NGINX is installed and enabled at launch.  
- This setup can scale automatically and supports high availability.
