# 🚀 VProfile AWS Re-Architecture Project
![AWS](https://img.shields.io/badge/AWS-Cloud-orange?logo=amazon-aws)
![Elastic Beanstalk](https://img.shields.io/badge/Platform-ElasticBeanstalk-green)
![RDS](https://img.shields.io/badge/Database-AmazonRDS-blue)
![ElastiCache](https://img.shields.io/badge/Cache-ElastiCache-red)
![ActiveMQ](https://img.shields.io/badge/Messaging-ActiveMQ-yellow)
![CloudFront](https://img.shields.io/badge/CDN-CloudFront-black)
![Route53](https://img.shields.io/badge/DNS-Route53-blueviolet)

## 📌 Overview
This project demonstrates the re-architecture of a traditional multi-tier web application (VPROFILE)
from on-prem / VM-based infrastructure to AWS Cloud using managed services.

The objective is to improve scalability, availability, automation, and cost efficiency
while reducing operational overhead.

---

## 🎯 Problem Statement
The existing system suffered from:
- High operational overhead
- Manual provisioning and deployments
- Scaling and uptime challenges
- Upfront CapEx and recurring OpEx
- Limited automation

---

## 📈 Solution Approach
The application was re-architected using AWS managed services with:
- Infrastructure automation readiness
- Pay-as-you-go cost model
- High availability and scalability
- Reduced system administration effort

---

## 🎯Results / Outcomes

- Improved scalability using Elastic Beanstalk auto-scaling
- Reduced infrastructure management overhead by ~70% (no manual VM ops)
- Achieved high availability with managed AWS services
- Reduced latency using CloudFront CDN and ElastiCache
- Enabled production-ready traffic routing via ALB + Route53

---

## 🏗️ Architecture 
![Architecture_diagram](diagrams/aws_rearchitecture.png)

## Key Architecture Decisions

- Chose Elastic Beanstalk over EC2 for managed scaling and reduced ops overhead
- Used ElastiCache to reduce database load and improve response latency
- Implemented ALB for layer 7 routing and SSL termination
- Integrated CloudFront to optimize global content delivery
- Used security group referencing for backend service isolation

### Traffic Flow:
User → Route53 (DNS) → CloudFront (CDN) → ALB → Elastic Beanstalk (App Tier) → RDS / ElastiCache / ActiveMQ

---

## 🔧 Technology Stack

| Category                | Technology                |
| ----------------------- | ------------------------- |
| Cloud                   | AWS                       |
| Compute                 | Elastic Beanstalk         |
| Database                | Amazon RDS (MySQL)        |
| Cache                   | ElastiCache (Memcached)   |
| Messaging               | Amazon MQ (ActiveMQ)      |
| Networking              | ALB, Route53, CloudFront  |
| Build Tool              | Maven                     |

---

## 🧠 Execution Flow 
![Execution_flow](diagrams/execution_flow.png)


---

## ▶️ How to Deploy (Quick Start)

* This section provides a high-level deployment flow.  
* Detailed steps are documented under `execution-flow/`.

### Prerequisites
- AWS account
- AWS CLI configured with appropriate IAM permissions
- Java and Maven installed
- Domain name (optional, for Route 53 and CloudFront)

### Production Considerations
- Multi-AZ deployment for RDS
- Auto Scaling enabled in Elastic Beanstalk
- HTTPS enforced via ALB + ACM
- CDN caching strategy applied via CloudFront

### Steps
#### 1. Clone the repository:
```bash
   git clone https://github.com/josephmj0303/vprofile-aws-rearchitecture.git
```
#### 2. Configure AWS credentials:
```
aws configure
```
#### 3. Provision AWS resources by following:
```
execution-flow/
├── phase-1-infra-setup.md
├── phase-2-app-deployment.md
└── phase-3-dns-cdn.md
```
#### 4. Build and deploy the application:

- Update backend configuration with AWS service endpoints

- Build artifact using Maven

- Deploy artifact to Elastic Beanstalk

#### 5. Deployment Validation
Runtime behavior was verified using:
- Successful application login and dashboard access
- Cache miss → DB fetch → cache insert
- Cache hit → data served from ElastiCache

---

## 🚀 DevOps Capabilities Demonstrated

- Cloud re-architecture (VM → managed services)
- Layered architecture design (CDN → LB → App → DB)
- Performance optimization using caching
- Secure service-to-service communication
- Deployment workflow design for production environments

---

## 📁 Repository Structure
```
vprofile-aws-rearchitecture/
│
├── README.md
│
├── architecture/
│   ├── current-state.md
│   ├── target-aws-architecture.md
│   └── aws-services-mapping.md
│
├── diagrams/
│   ├── aws-architecture.png
│   └── execution_flow.png
│   
├── infrastructure/
│   ├── security-groups.md
│   └── networking.md
│   
├── services/
│   ├── elastic-beanstalk.md
│   ├── rds.md
│   ├── elasticache.md
│   ├── active-mq.md
│   └── route53-cloudfront.md
│
├── execution-flow/
│   ├── phase-1-infra-setup.md
│   ├── phase-2-app-deployment.md
│   └── phase-3-dns-cdn.md
│
└── screenshots/
    ├── app-login.png
    ├── app-home.png
    ├── cache-miss.png
    └── cache-hit.png
```
---

## 🔐 Security Considerations

- IAM roles used for service-level access control
- Security groups restrict traffic between application tiers
- HTTPS enforced via ACM + ALB

---

## 🖥 Screenshots 



---


## 📈 Future Enhancements
- GitHub Actions pipeline for build → artifact → deploy to Elastic Beanstalk
- Terraform modules for reproducible infrastructure provisioning
- Blue-Green deployment using Elastic Beanstalk environments
- CloudWatch dashboards + alarms for observability

---

## 👨‍💻 Author
DevOps Portfolio Project  
AWS | Linux | Cloud Architecture

