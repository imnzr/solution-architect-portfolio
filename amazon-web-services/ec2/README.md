# Amazon Web Services EC2 

## Introduction to Amazon EC2
AWS EC2 (Elastic Compute Cloud) is a service from Amazon Web Services that provides virtual servers (called instance) in the cloud. You can rent servers based on you needs without buying dan maintaining physical hardware. You choose the specs (CPU, RAM, storage, operating system), and the server is ready to use within minutes.


### How it works ?
1. Choose an AMI (Amazon Machine Image), a template for the operating system such as Linux, Windows, or Ubuntu.
2. Choose an instance type (for example, t3.micro for small workloads, or c5 for heavy computing)
3. Configure networking, security (security groups), and storage (EBS)
4. Launch the instance, then access it via SSH (Linux) or RDP (Windows)

### Use Case
1. Website and application hosting
2. Backend and API's
3. Database and testing 
4. Data processing and machine learning 
5. Backup and disaster recovery 

### Advantages
1. Scalable : add or remove servers depending on demand (auto scaling)
2. Pay-as-you-go : billed per second or hour, so no large upfront investment
3. Flexible : many instance types, operating system, and region worldwide (including jakarta)
4. Reliable and secure : aws infrastructure spread accross multiple availability zones 

### Pricing Models
1. On-demand : pay for what you use, no commitment.
2. Reserved Instance / Saving Plans : 1 - 3 Year commitment at a lower price
3. Spot instance : very cheap, but AWS can terminate them at any time


