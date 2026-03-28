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

## Architecture

<!-- Replace with your generated architecture image -->
<img src="YOUR_ARCHITECTURE_IMAGE_URL_HERE" alt="Architecture diagram" width="100%" />

### Request flow

```text
User
  ↓
CloudFront Distribution
  ↓
CloudFront cache behavior
  ↓
Lambda@Edge (origin-request)
  ├── Route to Brazil origin → ALB (alb_br) → Target Group (tg_br) → EC2 second_instance
  └── Route to US/default origin → ALB (alb_us) → Target Group (tg_us) → EC2 first_instance
