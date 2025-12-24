# Phase 2 – Application Build & Deployment

## Objective
Deploy the VProfile backend application to AWS Elastic Beanstalk
and validate application health and backend integrations.

---

## Prerequisites
- Elastic Beanstalk environment created
- RDS, ElastiCache, and ActiveMQ running
- Security groups updated to allow backend communication
- Database initialized with required schema

---

## Deployment Steps

### 1. Backend Configuration Update
Update application configuration to point to AWS-managed services:
- RDS endpoint for database connectivity
- ElastiCache endpoint for caching
- ActiveMQ endpoint for messaging

These values are injected during the build or deployment phase.

---

### 2. Build Application Artifact
The application is packaged using Maven:

- Build generates a WAR/JAR artifact
- Backend service endpoints are embedded
- Artifact is verified locally before deployment

---

### 3. Upload Artifact
- Upload the build artifact to Amazon S3
- S3 acts as a centralized artifact store

---

### 4. Deploy to Elastic Beanstalk
- Deploy artifact via Elastic Beanstalk
- Application Load Balancer routes traffic to instances
- Auto Scaling group manages instance count

---

### 5. Health Check Configuration
- Health check endpoint updated to `/login`
- Ensures application-level health, not just instance availability

---

## Validation
- Application loads successfully via Beanstalk URL
- Login page accessible
- Backend services reachable
- No deployment or health check errors

---

## Outcome
The application is successfully deployed on AWS
with managed scaling, load balancing, and backend integrations.
