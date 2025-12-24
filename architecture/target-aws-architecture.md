# Target AWS Architecture – VProfile Re-Architecture

## Overview
The target architecture migrates the VProfile application from VM-based infrastructure
to AWS managed services to improve scalability, reliability, and operational efficiency.

---

## Architecture Components

### Frontend & Access Layer
- Route 53 for DNS resolution
- CloudFront as CDN for low-latency content delivery
- SSL/TLS termination using ACM

### Application Layer
- Elastic Beanstalk hosting Java application
- Application Load Balancer for traffic distribution
- Auto Scaling enabled for high availability

### Backend Services
- Amazon RDS (MySQL) for relational database
- Amazon ElastiCache (Memcached) for caching
- Amazon ActiveMQ for message brokering

### Storage
- Amazon S3 for application artifacts
- Amazon EFS (if required) for shared storage

---

## Benefits
- No server-level maintenance
- Built-in scaling and fault tolerance
- Pay-as-you-go cost model
- Easier automation and CI/CD integration
