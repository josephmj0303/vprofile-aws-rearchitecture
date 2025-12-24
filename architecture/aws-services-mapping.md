# AWS Services Mapping

## Legacy vs AWS Services

| Legacy Component | AWS Service |
|-----------------|------------|
| Tomcat on VM | Elastic Beanstalk |
| NGINX Load Balancer | Application Load Balancer |
| MySQL on VM | Amazon RDS |
| Memcached on VM | Amazon ElastiCache |
| RabbitMQ on VM | Amazon ActiveMQ |
| Local DNS | Route 53 |
| No CDN | CloudFront |
| Local Storage | S3 / EFS |

---

## Design Rationale
AWS managed services reduce operational overhead,
improve resiliency, and simplify scaling without
manual intervention.
