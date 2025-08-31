
# High Availability Web Application with AWS Elastic Load Balancer (BookNow Project)

## 📖 Project Overview
This project demonstrates deploying and scaling a sample web application called **BookNow** on AWS. The application was hosted on **Amazon EC2 instances** and integrated with an **Elastic Load Balancer (ELB)** to ensure **high availability, scalability, and fault tolerance**.  

To showcase load balancing, two different versions of the website were deployed:
- **Instance 1:** Blue background theme  
- **Instance 2:** Black background theme  

When accessing the Load Balancer DNS, users may see either the blue or black themed page depending on which instance serves the request.

---

## 🚀 What is an EC2 Web Server?
An **EC2 web server** is a virtual server running on Amazon Elastic Compute Cloud (EC2) with web server software like Apache or Nginx. It allows hosting of applications/websites on the cloud with flexibility, scalability, and cost efficiency.

---

## ⚖️ What is an Elastic Load Balancer?
An **Elastic Load Balancer (ELB)** is an AWS service that distributes incoming traffic across multiple targets (EC2 instances, containers, IPs).  

**Key Features:**
- **High Availability:** Routes traffic only to healthy servers.  
- **Scalability:** Add/remove servers based on demand.  
- **Fault Tolerance:** Ensures no single server is overloaded.  
- **Flexibility:** Supports ALB, NLB, and Gateway LB.  

---

## 🛠️ Project Steps

### 1. Launch EC2 Instances
- Create **two EC2 instances** (Amazon Linux, t2.micro Free Tier).  
- Configure security group:
  - Inbound: **HTTP (80)** from `0.0.0.0/0`  
  - Inbound: **SSH (22)** from My IP  
  - Outbound: Allow all traffic  

---

### 2. Install Apache & Deploy Pages
#### Instance 1 (Blue Background):
- Install Apache (httpd).  
- Enable and start the Apache service.  
- Create `/var/www/html/index.html` with **blue background HTML**.  

#### Instance 2 (Black Background):
- Same steps, but use **black background HTML**.  

---

### 3. Create a Target Group
- **Target type:** Instances  
- **Protocol:** HTTP : 80  
- Register both EC2 instances.  
- Verify both targets become **healthy**.  

---

### 4. Create an Application Load Balancer
- Name: `my-elastic-load-balancer`  
- Scheme: Internet-facing  
- Map to at least **two subnets** across different AZs.  
- Security group: Allow **HTTP 80**.  
- Listener: HTTP : 80 → Forward to `myloadtarget` target group.  

---

### 5. Test the Load Balancer
- Get the ALB **DNS name** from the AWS console.  
- Open in browser → refresh multiple times.  
- Output alternates between **Blue (Instance 1)** and **Black (Instance 2)** pages.  

---

## 🎯 Project Outcome
- **High Availability:** Application stayed accessible even if one instance was down.  
- **Load Distribution:** Traffic was balanced across multiple instances.  
- **Scalability:** Additional servers can be added to handle more users.  
- **Fault Tolerance:** Healthy targets always responded to user requests.  

This project highlights the practical use of AWS services for **cloud-native web hosting**.  

---

## 📂 More Projects
👉 Check out more of my **Cloud, AWS, Linux, and DevOps projects** here:  
**[GitHub – Sanjaykumar-P](https://github.com/Sanjaykumar-P)**  

---

## 🌐 Portfolio
Explore my detailed case studies and projects:  
**[Sanjaykumar P – Linux & Cloud Specialist](https://sanjaykumar-p.github.io/Portfolio/)**  

