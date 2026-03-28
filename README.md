<div align="center">

# 🌍 Geo-Routed Multi-Origin Web Infrastructure on AWS

**Production-style edge routing with CloudFront, Lambda@Edge, Application Load Balancers, and EC2**

<br/>


<!-- Geo-Routed-Multi-Origin-Web-Infrastructure-on-AWS  -->


<img width="1407" height="768" alt="trio" src="https://github.com/user-attachments/assets/257180ff-d39d-4094-b56e-fec975e87fe9" />

<br/>
<br/>

![AWS](https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazonaws&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=for-the-badge&logo=terraform&logoColor=white)
![HCL](https://img.shields.io/badge/HCL-Terraform%20Language-844FBA?style=for-the-badge)
![CloudFront](https://img.shields.io/badge/CloudFront-FF9900?style=for-the-badge&logo=amazonaws&logoColor=black)
![Lambda@Edge](https://img.shields.io/badge/Lambda@Edge-FF9900?style=for-the-badge&logo=awslambda&logoColor=white)
![ALB](https://img.shields.io/badge/Application%20Load%20Balancer-8C4FFF?style=for-the-badge)
![EC2](https://img.shields.io/badge/EC2-FF9900?style=for-the-badge&logo=amazonec2&logoColor=white)
![VPC](https://img.shields.io/badge/Amazon%20VPC-Networking-0EA5E9?style=for-the-badge)
![Subnets](https://img.shields.io/badge/Public%20Subnets-MultiAZ-2563EB?style=for-the-badge)
![Internet Gateway](https://img.shields.io/badge/Internet%20Gateway-Public%20Access-0F766E?style=for-the-badge)
![Security Groups](https://img.shields.io/badge/Security%20Groups-Stateful%20Firewall-16A34A?style=for-the-badge)
![IAM](https://img.shields.io/badge/IAM-Least%20Privilege-DD6B20?style=for-the-badge)
![Geo Routing](https://img.shields.io/badge/Geo%20Routing-Viewer%20Location-14B8A6?style=for-the-badge)
![Multi Origin](https://img.shields.io/badge/Multi--Origin-CloudFront-7C3AED?style=for-the-badge)
![Edge Computing](https://img.shields.io/badge/Edge%20Computing-Low%20Latency-DC2626?style=for-the-badge)
![CDN](https://img.shields.io/badge/CDN-Global%20Delivery-0284C7?style=for-the-badge)
![Load Balancing](https://img.shields.io/badge/Load%20Balancing-Highly%20Available-9333EA?style=for-the-badge)
![Amazon Linux](https://img.shields.io/badge/Amazon%20Linux-EC2%20Web%20Hosts-F59E0B?style=for-the-badge)
![Infrastructure as Code](https://img.shields.io/badge/Infrastructure%20as%20Code-Automated-4F46E5?style=for-the-badge)
![Portfolio Project](https://img.shields.io/badge/Project-Portfolio-22C55E?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Production%20Inspired-success?style=for-the-badge)

</div>

---

## Overview

This project deploys a **geo-routed multi-origin web architecture on AWS** using Terraform.

A user hits a single **CloudFront distribution**, and **Lambda@Edge** decides which backend origin to use based on viewer location metadata. The request is then forwarded to one of two **Application Load Balancers**, which send traffic to separate **EC2 web servers**.

This demonstrates:

- CDN and edge routing concepts
- Lambda@Edge origin selection
- Multi-origin CloudFront design
- Load balancing with ALB target groups
- Public VPC networking on AWS
- Infrastructure as Code with Terraform

---

## What this builds

✅ A custom **VPC**  
✅ **2 public subnets** across different Availability Zones  
✅ An **Internet Gateway** and route table for public access  
✅ Security groups for **ALB** and **EC2**  
✅ **2 EC2 instances** serving different web pages  
✅ **2 Application Load Balancers**  
✅ **2 target groups** with health checks  
✅ A **Lambda@Edge** function for geo-based origin routing  
✅ A **CloudFront distribution** with custom cache/origin request policies  
✅ A default **`.cloudfront.net`** endpoint for global access  

---

Core AWS resources
Networking
VPC
2 public subnets
Internet Gateway
Route table + subnet associations
Compute
EC2 instance for US/default content
EC2 instance for Brazil content
Load balancing
ALB for US/default origin
ALB for Brazil origin
Separate target groups and listeners
Edge and CDN
CloudFront distribution
Lambda@Edge function
Custom cache policy
Custom origin request policy
IAM
Lambda execution role
Basic execution logging policy attachment
Project structure
.
├── build/
│   └── geo_router.zip
├── lambda/
│   └── geo_router.js.tftpl
├── scripts/
├── ec2-webpage.sh
├── ec2-webpage2.sh
├── main.tf
├── var.tf
├── output.tf
├── terraform.lock.hcl
└── README.md
Terraform versions
Terraform v1.14.8
AWS provider ~> 6.36.0
Archive provider ~> 2.7.1
Quick start
1. Clone the repository
git clone https://github.com/YOUR_USERNAME/Geo-Routed-Multi-Origin-Web-Infrastructure-on-AWS.git
cd Geo-Routed-Multi-Origin-Web-Infrastructure-on-AWS
2. Review the backend config

Update the backend bucket if needed:

terraform {
  backend "s3" {
    bucket = "YOUR_BACKEND_BUCKET"
    key    = "terraform.tfstate"
    region = "us-east-1"
  }
}
3. Set your variables

Create terraform.tfvars:

vpc_cidr           = "10.0.0.0/16"
subnet_cidr1       = "10.0.1.0/24"
subnet_cidr2       = "10.0.2.0/24"
public_access_cidr = "0.0.0.0/0"
origin_verify      = "your-secret-header-value"
4. Initialize Terraform
terraform init
5. Review the plan
terraform plan
6. Deploy
terraform apply
7. Get the CloudFront URL

After deployment, grab the CloudFront domain from Terraform output and open it in a browser.

It should look like:

https://xxxxxxxxxxxx.cloudfront.net
Expected behavior
Users hit a single CloudFront endpoint
Lambda@Edge chooses the origin based on viewer location
Traffic is forwarded to either:
Brazil ALB
US/default ALB
Each ALB forwards to its attached EC2 instance
The returned page differs depending on the routed backend
Security notes

This project uses:

Security groups for ALB and EC2
CloudFront as the public global entry point
IAM role for Lambda@Edge
Route-based separation of backend origins
Current demo-style limitations

This is intentionally built as a portfolio/demo architecture, so there are a few production improvements that could be added later:

Restrict EC2 HTTP access to only the ALB security group
Move SSH access behind a tighter CIDR or bastion/SSM
Add HTTPS on the ALBs
Add a custom domain with ACM instead of default CloudFront certificate
Add AWS WAF in front of CloudFront
Add structured logging and alerting
Add autoscaling groups instead of single instances
Problems encountered
1. Lambda@Edge packaging

Lambda@Edge requires a deployable zip artifact, so the JavaScript template is rendered and zipped before deployment.

2. CloudFront origin rewriting

CloudFront can declare multiple origins, but the routing logic still has to be handled in Lambda@Edge during the origin-request event.

3. Viewer location routing

Routing decisions depend on forwarded CloudFront viewer headers, so cache and origin request policies must be configured correctly.

4. State/backend workflow

The backend is stored in S3, and local lockfile behavior may require adjustment depending on workflow.

Why this project matters

This project shows practical understanding of:

AWS networking
Edge computing
CDN behavior
CloudFront origin design
Lambda@Edge request manipulation
Load balancing
Terraform-based infrastructure provisioning

This is the kind of architecture pattern used when building systems that need:

low-latency content delivery
regional request steering
edge logic before origin selection
globally distributed entry points with centralized control
Future improvements
Route 53 custom domain
ACM certificate for a branded domain
AWS WAF
CloudWatch dashboards and alarms
Auto Scaling Groups
Blue/green origin switching
Header-based origin verification enforcement
More regions and more origin choices
Better separation into Terraform modules
Tear down

To remove the infrastructure:

terraform destroy
Author

Built as a production-inspired AWS edge routing project using:

Terraform
CloudFront
Lambda@Edge
Application Load Balancers
EC2

The goal of this repository is to demonstrate real infrastructure patterns, not just a basic static deployment.

⭐ If this project helped you or gave you ideas, consider starring the repository.


A couple of cleanup notes before you use it: your pasted markdown file is for a different AWS RAG project, so I did not reuse those Bedrock-specific sections; instead I aligned the README to the Terraform for this geo-routing repo. :contentReference[oaicite:2]{index=2} :contentReference[oaicite:3]{index=3}

The most important pieces I matched from your actual code were the two ALBs and two EC2 instances, the Lambda@Edge `origin-request` association, and the CloudFront viewer country/city routing headers. :contentReference[oaicite:4]{index=4}

Send the GIF/image asset links and I’ll drop them into the README exactly where they belong.
