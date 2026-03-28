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
![CloudFront](https://img.shields.io/badge/CloudFront-FF9900?style=for-the-badge&logo=amazonaws&logoColor=black)
![Lambda@Edge](https://img.shields.io/badge/Lambda@Edge-FF9900?style=for-the-badge&logo=awslambda&logoColor=white)
![ALB](https://img.shields.io/badge/Application%20Load%20Balancer-8C4FFF?style=for-the-badge)
![EC2](https://img.shields.io/badge/EC2-FF9900?style=for-the-badge&logo=amazonec2&logoColor=white)
![Status](https://img.shields.io/badge/Status-Portfolio%20Project-success?style=for-the-badge)

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
