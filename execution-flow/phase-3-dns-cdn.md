# Phase 3 – DNS, CDN & HTTPS Configuration

## Objective
Expose the application securely to end users
using DNS, CDN, and HTTPS.

---

## DNS Configuration (Route 53)

### Steps
1. Create or update hosted zone in Route 53
2. Add DNS record pointing to CloudFront distribution
3. Ensure low TTL during initial testing

---

## CDN Setup (CloudFront)

### Configuration
- Origin: Application Load Balancer (Elastic Beanstalk)
- Cache behavior configured for static and dynamic content
- Forward required headers and cookies

---

## HTTPS Enablement

### SSL Certificate
- SSL certificate provisioned using AWS Certificate Manager (ACM)
- Certificate attached to:
  - CloudFront distribution
  - Application Load Balancer (HTTPS listener on port 443)

---

### Listener Configuration
- HTTP (80) → HTTPS (443) redirection
- Ensures secure access by default

---

## Validation Steps
- Application accessible using custom domain
- HTTPS enabled and trusted certificate verified
- CDN caching behavior confirmed
- End-to-end request flow validated

---

## Outcome
The application is securely exposed to users with:
- DNS-based routing
- Global content delivery
- Encrypted HTTPS traffic
