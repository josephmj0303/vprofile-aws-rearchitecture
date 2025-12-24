# Current State Architecture

The original VProfile application was deployed on
physical/virtual machines with manually managed services.

Characteristics:
- VM-based Tomcat servers
- MySQL running on EC2
- NGINX as load balancer
- Local DNS management
- Manual scaling & deployments

Limitations:
- Tight coupling
- Poor scalability
- High maintenance cost
