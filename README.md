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
# DEMO

# USA

https://github.com/user-attachments/assets/b210304c-fcb3-4329-93ca-afcb773b4ed8

# BRAZIL
https://github.com/user-attachments/assets/3492f7c2-0966-43d8-91d3-71a3739647dd

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

## CORE AWS RESOURCES

<div align="center">

![AWS](https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazonaws&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=for-the-badge&logo=terraform&logoColor=white)
![HCL](https://img.shields.io/badge/HCL-4B5563?style=for-the-badge)
![Terraform Language](https://img.shields.io/badge/Terraform%20Language-8B5CF6?style=for-the-badge)
![CloudFront](https://img.shields.io/badge/CloudFront-F59E0B?style=for-the-badge&logo=amazonaws&logoColor=white)
![Lambda@Edge](https://img.shields.io/badge/Lambda@Edge-F59E0B?style=for-the-badge&logo=awslambda&logoColor=white)
![Application Load Balancer](https://img.shields.io/badge/Application%20Load%20Balancer-8B5CF6?style=for-the-badge)
![EC2](https://img.shields.io/badge/EC2-F59E0B?style=for-the-badge&logo=amazonec2&logoColor=white)

<br/>

![Amazon VPC](https://img.shields.io/badge/Amazon%20VPC-4B5563?style=for-the-badge)
![Networking](https://img.shields.io/badge/Networking-0EA5E9?style=for-the-badge)
![Public Subnets](https://img.shields.io/badge/Public%20Subnets-2563EB?style=for-the-badge)
![Multi-AZ](https://img.shields.io/badge/MultiAZ-8B5CF6?style=for-the-badge)
![Internet Gateway](https://img.shields.io/badge/Internet%20Gateway-F59E0B?style=for-the-badge)
![Public Access](https://img.shields.io/badge/Public%20Access-4B5563?style=for-the-badge)

<br/>

![Security Groups](https://img.shields.io/badge/Security%20Groups-4B5563?style=for-the-badge)
![Stateful Firewall](https://img.shields.io/badge/Stateful%20Firewall-22C55E?style=for-the-badge)
![IAM](https://img.shields.io/badge/IAM-4B5563?style=for-the-badge)
![Least Privilege](https://img.shields.io/badge/Least%20Privilege-F97316?style=for-the-badge)
![Geo Routing](https://img.shields.io/badge/Geo%20Routing-4B5563?style=for-the-badge)
![Viewer Location](https://img.shields.io/badge/Viewer%20Location-14B8A6?style=for-the-badge)
![Multi-Origin](https://img.shields.io/badge/Multi--Origin-8B5CF6?style=for-the-badge)
![CloudFront CDN](https://img.shields.io/badge/CloudFront%20CDN-7C3AED?style=for-the-badge)

<br/>

![Edge Computing](https://img.shields.io/badge/Edge%20Computing-4B5563?style=for-the-badge)
![Low Latency](https://img.shields.io/badge/Low%20Latency-E11D48?style=for-the-badge)
![CDN](https://img.shields.io/badge/CDN-4B5563?style=for-the-badge)
![Global Delivery](https://img.shields.io/badge/Global%20Delivery-0284C7?style=for-the-badge)
![Load Balancing](https://img.shields.io/badge/Load%20Balancing-4B5563?style=for-the-badge)
![Highly Available](https://img.shields.io/badge/Highly%20Available-9333EA?style=for-the-badge)
![Amazon Linux](https://img.shields.io/badge/Amazon%20Linux-4B5563?style=for-the-badge)
![EC2 Web Hosts](https://img.shields.io/badge/EC2%20Web%20Hosts-F59E0B?style=for-the-badge)

<br/>

![Route Tables](https://img.shields.io/badge/Route%20Tables-4B5563?style=for-the-badge)
![Target Groups](https://img.shields.io/badge/Target%20Groups-0EA5E9?style=for-the-badge)
![Health Checks](https://img.shields.io/badge/Health%20Checks-22C55E?style=for-the-badge)
![Origin Request Policy](https://img.shields.io/badge/Origin%20Request%20Policy-8B5CF6?style=for-the-badge)
![Cache Policy](https://img.shields.io/badge/Cache%20Policy-F59E0B?style=for-the-badge)
![Archive Provider](https://img.shields.io/badge/Archive%20Provider-4B5563?style=for-the-badge)
![Lambda Packaging](https://img.shields.io/badge/Lambda%20Packaging-6366F1?style=for-the-badge)

<br/>

![Infrastructure as Code](https://img.shields.io/badge/Infrastructure%20as%20Code-4B5563?style=for-the-badge)
![Automated](https://img.shields.io/badge/Automated-6366F1?style=for-the-badge)
![Project](https://img.shields.io/badge/Project-4B5563?style=for-the-badge)
![Portfolio](https://img.shields.io/badge/Portfolio-22C55E?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-4B5563?style=for-the-badge)
![Production Inspired](https://img.shields.io/badge/Production%20Inspired-64DD17?style=for-the-badge)

</div>

##  PROJECT STRUCTURE

```text
.
├── build/
│   └── geo_router.zip
├── lambda/
│   └── geo_router.js.tftpl
├── scripts/
│   ├── ec2-webpage.sh
│   └── ec2-webpage2.sh
│   └── quick-run.sh
├── .gitignore
├── README.md
├── main.tf
├── output.tf
├── terraform.lock.hcl
└── var.tf
```

#   Quick start

1. Clone the repository

2. git clone https://github.com7twoduo/Geo-Routed-Multi-Origin-Web-Infrastructure-on-AWS.git

3. cd Geo-Routed-Multi-Origin-Web-Infrastructure-on-AWS

4. Review the backend config

Update the backend bucket if needed:

```text

terraform {
  backend "s3" {
    bucket = "YOUR_BACKEND_BUCKET"
    key    = "terraform.tfstate"
    region = "us-east-1"
  }
}
```
5. cd Geo-Routed-Multi-Origin-Web-Infrastructure-on-AWS/scripts
```text
In the terminal, run ./quick-apply.sh
```


After deployment, grab the CloudFront domain from Terraform output and open it in a browser.

It should look like:

https://xxxxxxxxxxxx.cloudfront.net
# Testing
1) Go to the cloudfront link and it should take you the US Server

2) To test the Brazil Origin, Get UrbanVPN and set it to Brazil

3) This changes your IP to simulate the IP of someone in brazil and now you can access the Brazil server

4) Proving the edge function works

## Expected behavior

Users hit a single CloudFront endpoint

Lambda@Edge chooses the origin based on viewer location

Traffic is forwarded to either:

Brazil ALB

US/default ALB

Each ALB forwards to its attached EC2 instance

The returned page differs depending on the routed backend

## Tear down

To remove the infrastructure:

Run

terraform destroy

In the Root Directory with the main.tf,var.tf,output.tf

## Security notes

This project uses:

Security groups for ALB and EC2

CloudFront as the public global entry point

IAM role for Lambda@Edge

Route-based separation of backend origins

# Current demo-style limitations

This is intentionally built as a portfolio/demo architecture, so there are a few production improvements that could be added later:

Restrict EC2 HTTP access to only the ALB security group

Move SSH access behind a tighter CIDR or bastion/SSM

Add HTTPS on the ALBs

Add a custom domain with ACM instead of default CloudFront certificate

Add AWS WAF in front of CloudFront

Add structured logging and alerting

Add autoscaling groups instead of single instances

# Problems encountered

1. Lambda@Edge packaging

Lambda@Edge requires a deployable zip artifact, so the JavaScript template is rendered and zipped before deployment.

2. CloudFront origin rewriting

CloudFront can declare multiple origins, but the routing logic still has to be handled in Lambda@Edge during the origin-request event.

3. Viewer location routing

Routing decisions depend on forwarded CloudFront viewer headers, so cache and origin request policies must be configured correctly.

4. State/backend workflow

The backend is stored in S3, and local lockfile behavior may require adjustment depending on workflow.

### Why this project matters

This project shows practical understanding of:

AWS networking

Edge computing

CDN behavior

CloudFront origin design

Lambda@Edge request manipulation

Load balancing

Terraform-based infrastructure provisioning



Author

Built as a production-inspired AWS edge routing project using:

Terraform

CloudFront

Lambda@Edge

Application Load Balancers

EC2

The goal of this repository is to demonstrate real infrastructure patterns, not just a basic static deployment.

⭐ If this project helped you or gave you ideas, consider starring the repository.
