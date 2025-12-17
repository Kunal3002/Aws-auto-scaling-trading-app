# AWS Auto Scaling & Failover Trading Application 🚀

## 📌 Project Overview
This project demonstrates a highly available and fault-tolerant trading web application built using AWS services.  
The system automatically scales based on load and performs DNS-level failover to ensure zero downtime.

---

## 🏗️ Architecture Summary
- EC2 instances host the trading application
- AMI created from a configured instance
- Launch Template used by Auto Scaling Group
- Auto Scaling Group replaces unhealthy instances automatically
- CloudWatch monitors CPU and instance health
- SNS sends email notifications for scaling and health events
- Route 53 health checks monitor application availability
- Route 53 failover routing redirects traffic to S3 if EC2 fails
- S3 hosts a static maintenance page as fallback

---

## 🔄 Failover Flow
1. User accesses domain via Route 53
2. Route 53 routes traffic to EC2 (Primary)
3. If EC2 health check fails:
   - Traffic is automatically routed to S3 maintenance page
   - Auto Scaling launches a new EC2 instance
4. SNS sends email notification about the event

---

## 🧰 AWS Services Used
- Amazon EC2
- AMI & Launch Templates
- Auto Scaling Group
- Amazon CloudWatch
- Amazon SNS
- Amazon Route 53 (Failover Routing & Health Checks)
- Amazon S3 (Static Website Hosting)
- Security Groups

---

## 📸 Screenshots
All screenshots showing setup, failover, and alerts are available in the `/screenshots` folder.

---

## 🎯 Key Learnings
- Designing highly available systems
- Implementing DNS-based failover
- Auto-healing infrastructure with Auto Scaling
- Monitoring and alerting using CloudWatch & SNS
- Cost-aware cloud resource management

---

## ⚠️ Note
AWS resources were deleted after successful implementation to avoid ongoing charges.
