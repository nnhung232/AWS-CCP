https://github.com/marcelorodrigo/aws-certified-cloud-practitioner-exam
https://github.com/antoniolofiego/CloudCertNotes/blob/master/AWSCertifiedCloudPractitioner.md
https://datmt.com/backend/aws-certified-cloud-practitioner-2022-learning-notes/
https://digitalcloud.training/category/aws-cheat-sheets/aws-cloud-practitioner/
https://rishabkumar7.github.io/CloudNotes/CPP.html

# AWS Cloud Concepts
## 6 Advantages of Cloud
- Trade capital expense for variable expense: Instead of having to invest in data centers & servers before you know how you're going to use them, you can only pay when you consume computing resources, and pay only for how much you consume.
- Benefit from massive economies of scale: by using cloud computing, you can achieve a lower variable cost than you can get on your own. Because usage from hundreds of thousands of customer is aggregated in the cloud, providers such as AWS can achieve higher economies of scale, which translates into lower pay as-you-go price.
- Stop guessing about capacity.
- Increase speed and agility.
- Stop spending money running and maintaining data centers
- Go global in minutes

## Cloud computing models
- Infrastructure as a Service (IaaS): Các service infrastructure cơ bản (basic building blocks for cloud IT). VD như: ta lauch và manage 1  cloud linux server, đó là IaaS. IaaS provide highest level of flexibility and management control over IT resources. Các IaaS:  Virtual private cloud (VPC), Elastic cloud compute (EC2), Elastic block store (EBS).
- Platform as a Service (PaaS): ở models này, AWS sẽ control a little bit infrastructure level. VD: relational database service, ở service này, AWS cung cấp server, operating system and everything to run that, người dùng chỉ cần administer database đó thôi.
- Software as a Service (SaaS): completed software product. VD: office365.
- Function as a Service (FaaS): aka Serverless Computing: build and run app mà ko cần thinking about servers. VD: Simple storage service, AWS lambda, DynamoDB.

## Type of Cloud Deployment
- Cloud: Fully deploy in cloud
- On-Premise: tại chỗ. It sometimes called the private cloud
- Hybrid: Là a way to connect infrastructure và application betwwen cloud-based resource và những resource ko ở trên cloud. *AWS Outpost* là service cho phép chạy AWS service trên on-premise infrastruture
## Cloud Architecture Design Principles
- Design for failure and making sure that our architure is fault tolerant. We do that by using architecture that spanning multiple avaiablitiy zones, multiple regions
- Elasticity: or auto-scaling depending on demand. (example: EC2 auto-scaling)
- Loose coupling: 
## The 6 Pillars of the AWS Well-Architected Framework
### 1. Operational excellence
Operational excellence pillar bao gồm ability to support development và run workloads effectively, gain insight into their operation, và continuously improve (*tóm gọn: là ability to run and monitor system*). Có 5 design principles for this Operational excellence pillar:
- perform operations as code / Infrastructure as code (nghĩa là manage through code chứ ko through manual process)
- make frequent, small, reversible changes
- refine operations procedures frequently
- anticipate failure
- learn from all operational failures
Best practice:
- understand business and customer needs 
- creates and uses procedures to respond to operational events, and validates their effectiveness.
- collects metrics that are used to measure the achievement
- design operations to support evolution over time in response to change
### 2. Security
Security pillar bao gồm ability to prote
### 3. Reliability
### 4. Performance efficiency
### 5. Cost optimization
### 6. Sustainability

## AWS Shared Responsibility Model 

# Security and Compliance
## VPC 
## VPN
## AWS Shield
## WAF 
## CloudFront
## AWS Compliance
## AWS Artifact
## AWS config
## IAM
## AWS Organization
## AWS CloudTrail
## AWS Resource for Security Support
### Amazon Inspector
### AWS Trusted Advisor
### AWS Report Abuse

# Technology
## Deployment and Operating in the AWS
### On premise & Hybrid
- Snowball
- Storage Gateway
- DNS
### Deployment / Infrastructure as Code
- Elastic Beanstalk
- CodeCommit
- CodePipeline
- CodeDeploy
- CloudFormation
- OpsWorks
- SDKs
- CLI
## AWS Global Infrastructure
- Region
- Avaiablity Zone
- Edge Location
- Direct Connect
- Global vs Regional services
## Core AWS services
- Object Storage
  - S3
  - Glacier
- EC2 (AMI, Storage options, types)
- ELB (Classic, application, network)
- CloudWatch
- Database
  - Relational: RDS, Aurora
  - NoSQL: DynamoDB
  - Data warehouse: Redshift
  - In memory storage: ElastiCache
- Serverless (Lambda, S3, DynamoDB, SNS, SQS)
- Machine learning (Amazon rekognition)
- Stream - Kinesis
## Technology support
- AWS support plan
  - Free
  - Developer
  - Business
  - Enterprise
- AWS partner network
- AWS professional services
- AWS quick start
- AWS personal health dashboard

# Billing and Pricing
### Pricing models for AWS
- On-Demand
- Spot
- Reserved
- Dedicated Host
- Saving Plans
- Per Second Billing
### Cost allocation tags
### Billing support
- AWS Billing dashboard
- AWS Cost and Usage report
- AWS Cost Explorer
- AWS Budgets / CloudWatch Billing alert
- AWS Free support
