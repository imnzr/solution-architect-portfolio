# Amazon Elastic Load Balancing 

![This is an alt text.](/amazon-web-services/elastic-load-balancing/lb.jpg "This is a sample image.")

## Introduction to Amazon Elastic Load Balancing 
AWS Elastic Load Balancing (ELB) is an AWS service that automatically distributes incoming traffic across multiple targets, such as EC2 instances, container, or IP addresses. The goal is to prevent any single server from being overhelmed, so you application stays fast and available. 

Think of it like a stuff member at a mall entrance who directs visitors to the casher with the shortest line 

### How it Works
1. Users access your application through a single address (the load balancer's DNS name)
2. The load balancer receives the request 
3. It performs health checks to determine which targets are healthy
4. Request are forwarded only to healthy targets, distributed evenly

If one server goes down, traffic is automatically redirected to the others without users noticing 

### Type of Load Balancers
1. Application Load Balancer (ALB): operates at layer 7 (HTTP/HTTPS). Ideal for web applications and microservices because it can route traffic based on URL, path, or header (for example, /api to server A, /image to server B).
2. Network Load Balancer (NLB): operates at layer 4 (TCP/UDP/TLS). Extremely fast and high-performing, suited for applications that need low latency or handle millions of request per second 
3. Gateway Load Balancer (GWLB): used to deploy and scale virtual security appliances such a firewalls and instruction detection systems.
4. Classic Load Balancer (CLB): the older generation, not recommended or new projects.

### Benefits 
1. High availability: traffic is spread accross multiple availability zones, so your application stays up even if one zone has problems.
2. Scalability: work together with Auto Scaling, so as servers are added or removed, the load balancer adjust automatically.
3. Security: supports SSL/TLS termination (HTTPS certificates managed at the load balancer) and integrates with AWS WAF
4. Efficiency: prevents on server from being overloaded while others sit idle 
5. Zero-downtime maintenance: you can take a server out of rotation for updates without disrupting users.

### Pricing 
Billed based on the number of hours the load balancer runs plus the capacity used (LCU), a measure based on new connections, active connections, and data processed. 