# Networking Design

## VPC Design
- Single VPC for application stack
- Public subnets for ALB
- Private subnets for backend services

---

## Traffic Flow
User → Route53 → CloudFront → ALB → Elastic Beanstalk → Backend Services

---

## Networking Benefits
- Backend services isolated from public access
- Controlled ingress and egress
- Improved security posture
