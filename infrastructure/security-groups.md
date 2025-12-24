# Security Group Design

## Overview
Security Groups are designed using the principle of least privilege.

---

## Security Groups

### Beanstalk Environment SG
- Allows inbound HTTP/HTTPS from ALB
- Allows outbound access to backend services

### RDS Security Group
- Allows inbound MySQL traffic from Beanstalk SG only
- No public access

### ElastiCache Security Group
- Allows inbound from Beanstalk SG
- Restricted to VPC internal traffic

### ActiveMQ Security Group
- Allows inbound from application layer only

---

## Best Practices
- No public DB exposure
- SG-to-SG referencing
- Separate SGs per service
