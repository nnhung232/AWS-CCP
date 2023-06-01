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
Operational excellence pillar bao gồm ability to support development và run workloads effectively, gain insight into their operation, và continuously improve (*tóm gọn: là ability to run and monitor system*). 
**Design principles** for this Operational excellence pillar:
- perform operations as code / Infrastructure as code (nghĩa là manage through code chứ ko through manual process)
- make frequent, small, reversible changes
- refine operations procedures frequently
- anticipate failure
- learn from all operational failures
**Best practice**:
- understand business and customer needs 
- creates and uses procedures to respond to operational events, and validates their effectiveness.
- collects metrics that are used to measure the achievement
- design operations to support evolution over time in response to change
### 2. Security
Security pillar bao gồm ability to protect data, systems, and assets to take advantage of cloud technologies to improve security.
**Design principles**
- Implement a strong identity foundation
- Enable traceability
- Apply security at all layers
- Automate security best practices
- Protect data in transit and at rest
- Keep people away from data
- Prepare for security events
**Best practice**:
- Security: Before you architect any workload, you need to put in place practices that influence security.
- Identity and access management: control who can do what.
- Detection: be able to identify security incidents
- Infrastructure protection: protect your systems and services
- Data protection: maintain the confidentiality and integrity of data through data protection
- Incident response: have a well-defined and practiced process for responding to security incidents
- Application security: describes the overall process of how you design, build, and test the security properties of the workloads you develop.

### 3. Reliability
Reliability pillar là the ability of a workload to perform its intended function correctly and consistently 
**Design principles**:
- Automatically recover from failure
- Test recovery procedures
- Scale horizontally to increase aggregate workload availability
- Stop guessing capacity
- Manage change in automation
**Best practice**:
- Foundations: Before building any system, foundational requirements that influence reliability should be in place. For example, you must have sufficient network bandwidth to your data center.
- Workload architecture: design for both software and infrastructure. For reliability, there are specific patterns you must follow, such as loosely coupled dependencies, graceful degradation, and limiting retries.
- Change management: Changes to your workload or its environment must be anticipated and accommodated to achieve reliable operation of the workload
- Failure management: take steps to implement resiliency in your workload, such as fault isolation, automated failover to healthy resources, and a disaster recovery strategy.

### 4. Performance efficiency
Performance Efficiency pillar là khả năng to use computing resources efficiently to meet system requirements, and to maintain that efficiency as demand changes and technologies evolve
**Design principles**:
- Democratize advanced technologies: when making advanced technology implementation, delegating complex tasks to your cloud vendor, rather than asking your IT team to learn about hosting and running a new technology.
- Go global in minutes
- Use serverless architectures
- Experiment more often
- Consider mechanical sympathy: Understand how cloud services are consumed and always use the technology approach that aligns with your workload goals. For example, consider data access patterns when you select database or storage approaches.
**Best practice**:
- Selection: Take a data-driven approach to build high-performance architecture
- Review: Reviewing your choices on a regular basis 
- Monitoring: ensures you are aware of any deviance from expected performance.
- Tradeoffs: Make trade-offs in your architecture to improve performance, such as using compression or caching, or relaxing consistency requirements

### 5. Cost optimization
Cost Optimization pillar includes the ability to run systems to deliver business value at the lowest price point
**Design principles**
- Implement cloud financial management
- Adopt a consumption model: Pay only for what you require and increase or decrease usage depending on requirements, not by forecasting. 
- Measure overall efficiency: Measure the business output of the workload and the costs associated with delivering it.
- Stop spending money on undifferentiated heavy lifting
- Analyze and attribute expenditure
**Best practice**:
- Practice Cloud Financial Management
- Expenditure and usage awareness
- Cost-effective resources
- Manage demand and supply resources
- Optimize over time

### 6. Sustainability
The discipline of sustainability addresses the long-term environmental, economic, and societal impact of your business activities.
**Design principles**
- Understand your impact
- Establish sustainability goals
- Maximize utilization
- Anticipate and adopt new, more efficient hardware and software offerings
- Use managed services
- Reduce the downstream impact of your cloud workloads
**Best practice**:
- Region selection
- Alignment to demand: User behavior patterns can help you identify improvements to meet sustainability goals.
- Software and architecture: Implement software and architecture patterns to perform load smoothing and maintain consistent high utilization of deployed resources
- Data: Implement software and architecture patterns to perform load smoothing and maintain consistent high utilization of deployed resources
- Hardware and services
- Process and culture

## AWS Shared Responsibility Model 
- Customer is responsible for security IN the cloud (customer data, platforms, applications, OS, network configuration and security, firewall, client and server side encryption, etc)

- AWS is responsible for security of the cloud (compute, storage, database, networking, hardware, local access security, power, regions, availability zones and edge locations)

# Security and Compliance
AWS manages security OF the cloud; customer are responsible for security IN the cloud.
## Benefits of AWS Security
- Keep Your Data Safe – the AWS infrastructure puts strong safeguards in place to help.
- Protect your privacy – All data is stored in highly secure AWS data centers.
- Meet Compliance Requirements – AWS manages dozens of compliance programs in its infrastructure. This means that segments of your compliance have already been completed.
- Save Money – cut costs by using AWS data centers. Maintain the highest standard of s security without having to manage your own facility.
- Scale Quickly – security scales with your AWS Cloud usage. No matter the size of your business, the AWS infrastructure is designed to keep your data safe.
## AWS Cloud Compliance
Help you create framework compliant with a certain framework (Example: HIPPA, PCI DSS,...). As systems are built on top of AWS Cloud infrastructure, compliance responsibilities will be shared. Compliance programs include:
- Certifications / attestations.
- Laws, regulations, and privacy.
- Alignments / frameworks.
### AWS Artifact
AWS Artifact is your go-to, central resource for compliance-related information that matters to you.
It provides on-demand access to AWS’ security and compliance reports and select online agreements.
Reports available in AWS Artifact include our Service Organization Control (SOC) reports, Payment Card Industry (PCI) reports, and certifications from accreditation bodies across geographies and compliance verticals that validate the implementation and operating effectiveness of AWS security controls.
Agreements available in AWS Artifact include the Business Associate Addendum (BAA) and the Nondisclosure Agreement (NDA).

## Amazon GuardDuty
Amazon GuardDuty offers threat detection and continuous security monitoring for malicious or unauthorized behavior to help you protect your AWS accounts and workloads.
Intelligent threat detection service.
Detects account compromise, instance compromise, malicious reconnaissance, and bucket compromise.
Continuous monitoring for events across:
- AWS CloudTrail Management Events.
- AWS CloudTrail S3 Data Events.
- Amazon VPC Flow Logs.
- DNS Logs.

## AWS WAF & AWS Shield
### WAF:
- AWS WAF is a web application firewall.
- Protects against common exploits that could compromise application availability, compromise security, or consume excessive resources.
- WAF lets you create rules to filter web traffic based on conditions that include IP addresses, HTTP headers and body, or custom URIs.
- WAF makes it easy to create rules that block common web exploits like SQL injection and cross site scripting.
- The rules are known as Web ACLs.

### Shield:
- AWS Shield is a managed Distributed Denial of Service (DDoS) protection service.
- Safeguards web application running on AWS with always-on detection and automatic inline mitigations.
- Helps to minimize application downtime and latency.
- Two tiers – Standard and Advanced.

## AWS Key Management Service (AWS KMS)
AWS Key Management Service gives you centralized control over the encryption keys used to protect your data.
You can create, import, rotate, disable, delete, define usage policies for, and audit the use of encryption keys used to encrypt your data.
AWS Key Management Service is integrated with most other AWS services making it easy to encrypt the data you store in these services with encryption keys you control.
AWS KMS is integrated with AWS CloudTrail which provides you the ability to audit who used which keys, on which resources, and when.
AWS KMS enables developers to easily encrypt data, whether through 1-click encryption in the AWS Management Console or using the AWS SDK to easily add encryption in their application code.

## AWS CloudHSM
AWS CloudHSM is a cloud-based hardware security module (HSM) that enables you to easily generate and use your own encryption keys on the AWS Cloud.
With CloudHSM, you can manage your own encryption keys using FIPS 140-2 Level 3 validated HSMs.
CloudHSM offers you the flexibility to integrate with your applications using industry-standard APIs, such as PKCS#11, Java Cryptography Extensions (JCE), and Microsoft CryptoNG (CNG) libraries.

## AWS Certificate Manager
AWS Certificate Manager is a service that lets you easily provision, manage, and deploy public and private Secure Sockets Layer/Transport Layer Security (SSL/TLS) certificates for use with AWS services and your internal connected resources.
SSL/TLS certificates are used to secure network communications and establish the identity of websites over the Internet as well as resources on private networks.
AWS Certificate Manager removes the time-consuming manual process of purchasing, uploading, and renewing SSL/TLS certificates.

## AWS Inspector and AWS Trusted Advisor
### AWS Inspector:
- Inspector is an automated security assessment service that helps improve the security and compliance of applications deployed on AWS.
- Inspector automatically assesses applications for vulnerabilities or deviations from best practices.
- Uses an agent installed on EC2 instances.
- Instances must be tagged.

### AWS Trusted Advisor:
- Trusted Advisor is an online resource that helps to reduce cost, increase performance, and improve security by optimizing your AWS environment.
- Trusted Advisor provides real time guidance to help you provision your resources following best practices.
- Advisor will advise you on Cost Optimization, Performance, Security, and Fault Tolerance.

Trusted Advisor scans your AWS infrastructure and compares is to AWS best practices in five categories:
- Cost Optimization.
- Performance.
- Security.
- Fault Tolerance.
- Service Limits.

Trusted Advisor comes in two versions:
Core Checks and Recommendations (free):
- Access to the 7 core checks to help increase security and performance.
- Checks include S3 bucket permissions, Security Groups, IAM use, MFA on root account, EBS public snapshots, RDS public snapshots.

Full Trusted Advisor Benefits (business and enterprise support plans):
- Full set of checks to help optimize your entire AWS infrastructure.
- Advises on security, performance, cost, fault tolerance and service limits.
- Additional benefits include weekly update notifications, alerts, automated actions with - CloudWatch and programmatic access using the AWS Support API.

## AWS Single Sign-On (AWS SSO)
AWS Single Sign-On is a cloud-based single sign-on (SSO) service that makes it easy to centrally manage SSO access to all your AWS accounts and cloud applications.
It helps you manage SSO access and user permissions across all your AWS accounts in AWS Organizations.
AWS SSO also helps you manage access and permissions to commonly used third-party software as a service (SaaS) applications, AWS SSO-integrated applications as well as custom applications that support Security Assertion Markup Language (SAML) 2.0.
AWS SSO includes a user portal where your end-users can find and access all their assigned AWS accounts, cloud applications, and custom applications in one place.

## Amazon Cognito
Amazon Cognito lets you add user sign-up, sign-in, and access control to your web and mobile apps quickly and easily.
Amazon Cognito scales to millions of users and supports sign-in with social identity providers, such as Apple, Facebook, Google, and Amazon, and enterprise identity providers via SAML 2.0 and OpenID Connect.
The two main components of AWS Cognito are user pools and identity pools:
- User pools are user directories that provide sign-up and sign-in options for your app users.
- Identity pools enable you to grant your users access to other AWS services.
You can use identity pools and user pools separately or together.

## AWS Directory Services
AWS provides several directory types.
The following three types currently feature on the exam and will be covered on this page:
- Active Directory Service for Microsoft Active Directory.
- Simple AD.
- AD Connector.
As an alternative to the AWS Directory service you can build your own Microsoft AD DCs in the AWS cloud (on EC2).

## AWS Systems Manager Parameter Store
Provides secure, hierarchical storage for configuration data management and secrets management.
It is highly scalable, available, and durable.
You can store data such as passwords, database strings, and license codes as parameter values.
You can store values as plaintext (unencrypted data) or ciphertext (encrypted data).
You can then reference values by using the unique name that you specified when you created the parameter.

## AWS Secrets Manager
Like Parameter Store.
Allows native and automatic rotation of keys.
Fine-grained permissions.
Central auditing for secret rotation

## Amazon Virtual Private Cloud (VPC) 
![image](https://github.com/nnhung232/AWS-CCP/assets/4153181/e60a3d97-19e8-4183-b79f-34c77e3ea586)

## VPN
## CloudFront
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
