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
Auto Scaling configured to maintain 2–4 instances; scales out based on healthy target count or traffic increase.

## Steps Performed
1) Create launch template with userdata to install NGINX
2) Create target group for ALB health checks
3) Set up Auto Scaling Group
4) Verify instances healthy under ALB

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
-  Security group allows HTTP (80) and SSH (22)
- All public instances receive IPv4 addresses
- Could be improved by placing instances in private subnets with a NAT gateway
