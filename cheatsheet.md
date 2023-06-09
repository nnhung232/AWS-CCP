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
- Hybrid: Là a way to connect infrastructure và application betwwen cloud-based resource và những resource ko ở trên cloud. *AWS Outposts* là service cho phép chạy AWS service trên on-premise infrastruture

## AWS Global Infrastructure
![image](https://github.com/nnhung232/AWS-CCP/assets/4153181/6a1786fb-e0d4-4e40-8d7c-c3db44c3ee7a)

### Regions
A region is a geographical area.
Each region consists of 3 or more availability zones.
Each Amazon Region is designed to be completely isolated from the other Amazon Regions.
Each AWS Region has multiple Availability Zones and data centers.
You can replicate data within a region and between regions using private or public Internet connections.
You retain complete control and ownership over the region in which your data is physically located, making it easy to meet regional compliance and data residency requirements.
Note that there is a charge for data transfer between regions.
When you launch an EC2 instance, you must select an AMI that’s in the same region. If the AMI is in another region, you can copy the AMI to the region you’re using.

Regions and Endpoints:
- When you work with an instance using the command line interface or API actions, you must specify its regional endpoint.
- To reduce data latency in your applications, most Amazon Web Services offer a regional endpoint to make your requests.
- An endpoint is a URL that is the entry point for a web service.
- For example, https://dynamodb.us-west-2.amazonaws.com is an entry point for the Amazon DynamoDB service.

### Availability Zones
Availability Zones are physically separate and isolated from each other.
AZs span one or more data centers and have direct, low-latency, high throughput, and redundant network connections between each other.
Each AZ is designed as an independent failure zone.
When you launch an instance, you can select an Availability Zone or let AWS choose one for you.
If you distribute your EC2 instances across multiple Availability Zones and one instance fails, you can design your application so that an instance in another Availability Zone can handle requests.
You can also use Elastic IP addresses to mask the failure of an instance in one Availability Zone by rapidly remapping the address to an instance in another Availability Zone.
An Availability Zone is represented by a region code followed by a letter identifier; for example, us-east-1a.
To ensure that resources are distributed across the Availability Zones for a region, AWS independently map Availability Zones to names for each AWS account.
For example, the Availability Zone us-east-1a for your AWS account might not be the same location as us-east-1a for another AWS account.
To coordinate Availability Zones across accounts, you must use the AZ ID, which is a unique and consistent identifier for an Availability Zone.
AZs are physically separated within a typical metropolitan region and are in lower risk flood plains.
AZs use discrete UPS and onsite backup generation facilities and are fed via different grids from independent facilities.
AZs are all redundantly connected to multiple tier-1 transit providers.
The following graphic shows three AWS Regions each of which has three Availability Zones:

### Local Zones
AWS Local Zones place compute, storage, database, and other select AWS services closer to end-users.
With AWS Local Zones, you can easily run highly demanding applications that require single-digit millisecond latencies to your end-users.
Each AWS Local Zone location is an extension of an AWS Region where you can run your latency sensitive applications using AWS services such as Amazon Elastic Compute Cloud, Amazon Virtual Private Cloud, Amazon Elastic Block Store, Amazon File Storage, and Amazon Elastic Load Balancing in geographic proximity to end-users.
AWS Local Zones provide a high-bandwidth, secure connection between local workloads and those running in the AWS Region, allowing you to seamlessly connect to the full range of in-region services through the same APIs and tool sets.

### AWS Wavelength
AWS Wavelength enables developers to build applications that deliver single-digit millisecond latencies to mobile devices and end-users.
AWS developers can deploy their applications to Wavelength Zones, AWS infrastructure deployments that embed AWS compute and storage services within the telecommunications providers’ datacenters at the edge of the 5G networks, and seamlessly access the breadth of AWS services in the region.
AWS Wavelength brings AWS services to the edge of the 5G network, minimizing the latency to connect to an application from a mobile device.

### AWS Outposts
AWS Outposts bring native AWS services, infrastructure, and operating models to virtually any data center, co-location space, or on-premises facility.
You can use the same AWS APIs, tools, and infrastructure across on-premises and the AWS cloud to deliver a truly consistent hybrid experience.
AWS Outposts is designed for connected environments and can be used to support workloads that need to remain on-premises due to low latency or local data processing needs.

### Edge Locations and Regional Edge Caches
Edge locations are Content Delivery Network (CDN) endpoints for CloudFront.
There are many more edge locations than regions.
Currently there are over 200 edge locations.
Regional Edge Caches sit between your CloudFront Origin servers and the Edge Locations.
A Regional Edge Cache has a larger cache-width than each of the individual Edge Locations.
The following diagram shows CloudFront Edge locations:
![image](https://github.com/nnhung232/AWS-CCP/assets/4153181/683907da-4712-46bd-b743-40ac53b75da2)

## Cloud Architecture Design Principles
- Design for failure and making sure that our architure is fault tolerant. We do that by using architecture that spanning multiple avaiablitiy zones, multiple regions
- Elasticity: or auto-scaling depending on demand. (example: EC2 auto-scaling)
- Loose coupling: This means that IT systems should be designed in a way that reduces interdependencies—a change or a failure in one component should not cascade to other components.

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

## AWS Identity and Access Management (IAM)
AWS Identity and Access Management (IAM) is a web service that helps you securely control access to AWS resources.
You use IAM to control who is authenticated (signed in) and authorized (has permissions) to use resources. Think of IAM as the control center to all AWS resources. 
IAM makes it easy to provide multiple users secure access to AWS resources.
When you first create an AWS account, you begin with a single sign-in identity that has complete access to all AWS services and resources in the account.
This identity is called the AWS account root user and is accessed by signing in with the email address and password that you used to create the account.

IAM can be used to manage:
- Users.
- Groups.
- Access policies.
- Roles.
- User credentials.
- User password policies.
- Multi-factor authentication (MFA).
- API keys for programmatic access (CLI).

IAM provides the following features:
- Shared access to your AWS account.
- Granular permissions.
- Secure access to AWS resources for application that run on Amazon EC2.
- Multi-Factor authentication.
- Identity federation.
- Identity information for assurance.
- PCI DSS compliance.
- Integrated with many AWS services.
- Eventually consistent.
- Free to use.

You can work with AWS Identity and Access Management in any of the following ways:
- AWS Management Console.
- AWS Command Line Tools.
- AWS SDKs.
- IAM HTTPS API.

By default new users are created with NO access to any AWS services – they can only login to the AWS console.
Permission must be explicitly granted to allow a user to access an AWS service.
IAM users are individuals who have been granted access to an AWS account.

Each IAM user has three main components:
- A username.
- A password.
- Permissions to access various resources.

You can apply granular permissions with IAM.
You can assign users individual security credentials such as access keys, passwords, and multi-factor authentication devices.
IAM is not used for application-level authentication.
Identity Federation (including AD, Facebook etc.) can be configured allowing secure access to resources in an AWS account without creating an IAM user account.
Multi-factor authentication (MFA) can be enabled/enforced for the AWS account and for individual users under the account.
MFA uses an authentication device that continually generates random, six-digit, single-use authentication codes.

You can authenticate using an MFA device in the following two ways:
- Through the AWS Management Console – the user is prompted for a user name, password, and authentication code.
- Using the AWS API – restrictions are added to IAM policies and developers can request temporary security credentials and pass MFA parameters in their AWS STS API requests.
- Using the AWS CLI by obtaining temporary security credentials from STS (aws sts get-session-token).

It is a best practice to always setup multi-factor authentication on the root account.
IAM is universal (global) and does not apply to regions.
IAM replicates data across multiple data centers around the world.
The “root account” is the account created when you setup the AWS account. It has complete Admin access and is the only account that has this access by default.
It is a best practice to avoid using the root account for anything other than billing.
Power user access allows all permissions except the management of groups and users in IAM.
Temporary security credentials consist of the AWS access key ID, secret access key, and security token.
IAM can assign temporary security credentials to provide users with temporary access to services/resources.
To sign-in you must provide your account ID or account alias in addition to a user name and password.
The sign-in URL includes the account ID or account alias, e.g.:
https://My_AWS_Account_ID.signin.aws.amazon.com/console/
Alternatively, you can sign-in at the following URL and enter your account ID or alias manually: https://console.aws.amazon.com/
IAM integrates with many different AWS services.
Authentication Methods

Console password:
- A password that the user can enter to sign in to interactive sessions such as the AWS Management Console.
- You can allow users to change their own passwords.
- You can allow selected IAM users to change their passwords by disabling the option for all users and using an IAM policy to grant permissions for the selected users.

Access Keys:
- A combination of an access key ID and a secret access key.
- You can assign two active access keys to a user at a time.
- These can be used to make programmatic calls to AWS when using the API in program code or at a command prompt when using the AWS CLI or the AWS PowerShell tools.
- You can create, modify, view, or rotate access keys.
- When created IAM returns the access key ID and secret access key.
- The secret access is returned only at creation time and if lost a new key must be created.
- Ensure access keys and secret access keys are stored securely.
- Users can be given access to change their own keys through IAM policy (not from the console).
- You can disable a user’s access key which prevents it from being used for API calls.

Server certificates:
- SSL/TLS certificates that you can use to authenticate with some AWS services.
- AWS recommends that you use the AWS Certificate Manager (ACM) to provision, manage and deploy your server certificates.
- Use IAM only when you must support HTTPS connections in a region that is not supported by ACM.
![image](https://github.com/nnhung232/AWS-CCP/assets/4153181/fd616bf0-742e-4ec4-a6f8-c5d3f7da049a)

### IAM Users
An IAM user is an entity that represents a person or service.

Can be assigned:
- An access key ID and secret access key for programmatic access to the AWS API, CLI, SDK, and other development tools.
- A password for access to the management console.

By default, users cannot access anything in your account.
The account root user credentials are the email address used to create the account and a password.
The root account has full administrative permissions, and these cannot be restricted.

Best practice for root accounts:
- Don’t use the root user credentials.
- Don’t share the root user credentials.
- Create an IAM user and assign administrative permissions as required.
- Enable MFA.

IAM users can be created to represent applications, and these are known as “service accounts”.
You can have up to 5000 users per AWS account.
Each user account has a friendly name and an ARN which uniquely identifies the user across AWS.

A unique ID is also created which is returned only when you create the user using the API, Tools for Windows PowerShell, or the AWS CLI.
You should create individual IAM accounts for users (best practice not to share accounts).
The Access Key ID and Secret Access Key are not the same as a password and cannot be used to login to the AWS console.
The Access Key ID and Secret Access Key can only be used once and must be regenerated if lost.
A password policy can be defined for enforcing password length, complexity etc. (applies to all users).
You can allow or disallow the ability to change passwords using an IAM policy.
Access keys and passwords should be changed regularly.

### Groups
Groups are collections of users and have policies attached to them.
A group is not an identity and cannot be identified as a principal in an IAM policy.
Use groups to assign permissions to users.
Use the principle of least privilege when assigning permissions.
You cannot nest groups (groups within groups).

### Roles
Roles are created and then “assumed” by trusted entities and define a set of permissions for making AWS service requests.
With IAM Roles you can delegate permissions to resources for users and services without using permanent credentials (e.g. user name and password).
IAM users or AWS services can assume a role to obtain temporary security credentials that can be used to make AWS API calls.
You can delegate using roles.
There are no credentials associated with a role (password or access keys).
IAM users can temporarily assume a role to take on permissions for a specific task.
A role can be assigned to a federated user who signs in using an external identity provider.
Temporary credentials are primarily used with IAM roles and automatically expire.
Roles can be assumed temporarily through the console or programmatically with the AWS CLI, Tools for Windows PowerShell, or the API.

IAM roles with EC2 instances:
- IAM roles can be used for granting applications running on EC2 instances permissions to AWS API requests using instance profiles.
- Only one role can be assigned to an EC2 instance at a time.
- A role can be assigned at the EC2 instance creation time or at any time afterwards.
- When using the AWS CLI or API instance profiles must be created manually (it’s automatic and transparent through the console).
- Applications retrieve temporary security credentials from the instance metadata.

Role Delegation:
- Create an IAM role with two policies:
  - Permissions policy – grants the user of the role the required permissions on a resource.
  - Trust policy – specifies the trusted accounts that are allowed to assume the role.
- Wildcards (\*) cannot be specified as a principal.
- A permissions policy must also be attached to the user in the trusted account.

### Policies
Policies are documents that define permissions and can be applied to users, groups, and roles.
Policy documents are written in JSON (key value pair that consists of an attribute and a value).
All permissions are implicitly denied by default.
The most restrictive policy is applied.
The IAM policy simulator is a tool to help you understand, test, and validate the effects of access control policies.
The Condition element can be used to apply further conditional logic.

![image](https://github.com/nnhung232/AWS-CCP/assets/4153181/2ef8a276-e285-4968-bcc6-d01feb37425f)

### Comparing AWS IAM Role vs Policy vs Group
In AWS IAM, roles, policies, and groups are all used to manage access to AWS resources.
A role defines a set of permissions and access policies that determine what actions a user or AWS service can take. Roles are useful when you want to grant (temporary) access to AWS resources to a third-party entity, such as an AWS service or a user outside of your AWS account.
A policy, on the other hand, is a document that defines a set of permissions and specifies which AWS resources those permissions grant access to. Policies can be attached to roles, groups, or individual users to define their level of access to AWS resources. Policies are useful when you want to define and enforce specific permissions for a particular resource or set of resources.
A group is a collection of users that share common permissions. Groups make it easy to manage permissions for multiple users at once, as policies can be attached to a group and apply to all users within that group. By assigning permissions to a group, you can grant or revoke access for multiple users with a single action.
Overall, roles are used to grant access to specific resources or services, policies are used to define the permissions for those resources or services, and groups are used to organize and manage multiple users with similar permissions. Overall, roles, policies, and groups are all critical components of AWS IAM, each serving a unique purpose in managing user access to AWS resources.

### AWS Security Token Service (AWS STS)
The AWS STS is a web service that enables you to request temporary, limited-privilege credentials for IAM users or for users that you authenticate (federated users).

Temporary security credentials work almost identically to long-term access key credentials that IAM users can use, with the following differences:
- Temporary security credentials are short-term.
- They can be configured to last anywhere from a few minutes to several hours.
- After the credentials expire, AWS no longer recognizes them or allows any kind of access to API requests made with them.
- Temporary security credentials are not stored with the user but are generated dynamically and provided to the user when requested.
- When (or even before) the temporary security credentials expire, the user can request new credentials, if the user requesting them still has permission to do so.

Advantages of STS are:
- You do not have to distribute or embed long-term AWS security credentials with an application.
- You can provide access to your AWS resources to users without having to define an AWS identity for them (temporary security credentials are the basis for IAM Roles and ID Federation).
- The temporary security credentials have a limited lifetime, so you do not have to rotate them or explicitly revoke them when they’re no longer needed.
- After temporary security credentials expire, they cannot be reused (you can specify how long the credentials are valid for, up to a maximum limit)

Users can come from three sources.
**1. Federation (typically AD):**
- Uses SAML 2.0.
- Grants temporary access based on the users AD credentials.
- Does not need to be a user in IAM.
- Single sign-on allows users to login to the AWS console without assigning IAM credentials.
**2. Federation with Mobile Apps:**
- Use Facebook/Amazon/Google or other OpenID providers to login.
**3. Cross Account Access:**
- Allows users from one AWS account access resources in another.
- To make a request in a different account the resource in that account must have an attached resource-based policy with the permissions you need.
- Or you must assume a role (identity-based policy) within that account with the permissions you need.

### IAM Best Practices
Lock away the AWS root user access keys.
Create individual IAM users.
Use AWS defined policies to assign permissions whenever possible.
Use groups to assign permissions to IAM users.
Grant least privilege.
Use access levels to review IAM permissions.
Configure a strong password policy for users.
Enable MFA.
Use roles for applications that run on AWS EC2 instances.
Delegate by using roles instead of sharing credentials.
Rotate credentials regularly.
Remove unnecessary credentials.
Use policy conditions for extra security.
Monitor activity in your AWS account.

## Amazon Virtual Private Cloud (VPC) 
![image](https://github.com/nnhung232/AWS-CCP/assets/4153181/e60a3d97-19e8-4183-b79f-34c77e3ea586)
A virtual private cloud (VPC) is a virtual network dedicated to your AWS account.
Analogous to having your own DC inside AWS.
It is logically isolated from other virtual networks in the AWS Cloud.
Provides complete control over the virtual networking environment including selection of IP ranges, creation of subnets, and configuration of route tables and gateways.
You can launch your AWS resources, such as Amazon EC2 instances, into your VPC.
When you create a VPC, you must specify a range of IPv4 addresses for the VPC in the form of a Classless Inter-Domain Routing (CIDR) block; for example, 10.0.0.0/16.
This is the primary CIDR block for your VPC.
A VPC spans all the Availability Zones in the region.
You have full control over who has access to the AWS resources inside your VPC.
You can create your own IP address ranges, and create subnets, route tables and network gateways.
When you first create your AWS account a default VPC is created for you in each AWS region.
A default VPC is created in each region with a subnet in each AZ.
By default you can create up to 5 VPCs per region.
You can define dedicated tenancy for a VPC to ensure instances are launched on dedicated hardware (overrides the configuration specified at launch).
A default VPC is automatically created for each AWS account the first time Amazon EC2 resources are provisioned.
The default VPC has all-public subnets.
Public subnets are subnets that have:
- “Auto-assign public IPv4 address” set to “Yes”.
- The subnet route table has an attached Internet Gateway.
Instances in the default VPC always have both a public and private IP address.
AZs names are mapped to different zones for different users (i.e. the AZ “ap-southeast-2a” may map to a different physical zone for a different user).

**Components of a VPC:**
- **A Virtual Private Cloud:** A logically isolated virtual network in the AWS cloud. You define a VPC’s IP address space from ranges you select.
- **Subnet:** A segment of a VPC’s IP address range where you can place groups of isolated resources (maps to an AZ, 1:1).
- **Internet Gateway:** The Amazon VPC side of a connection to the public Internet.
- **NAT Gateway:** A highly available, managed Network Address Translation (NAT) service for your resources in a private subnet to access the Internet.
- **Hardware VPN Connection:** A hardware-based VPN connection between your Amazon VPC and your datacenter, home network, or co-location facility.
- **Virtual Private Gateway:** The Amazon VPC side of a VPN connection.
- **Customer Gateway:** Your side of a VPN connection.
- **Router:** Routers interconnect subnets and direct traffic between Internet gateways, virtual private gateways, NAT gateways, and subnets.
- **Peering Connection:** A peering connection enables you to route traffic via private IP addresses between two peered VPCs.
- **VPC Endpoints:** Enables private connectivity to services hosted in AWS, from within your VPC without using an Internet Gateway, VPN, Network Address Translation (NAT) devices, or firewall proxies.
- **Egress-only Internet Gateway:** A stateful gateway to provide egress only access for IPv6 traffic from the VPC to the Internet.

Options for securely connecting to a VPC are:
- AWS managed VPN – fast to setup.
- Direct Connect – high bandwidth, low-latency but takes weeks to months to setup.
- VPN CloudHub – used for connecting multiple sites to AWS.
- Software VPN – use 3rd party software.

An Elastic Network Interface (ENI) is a logical networking component that represents a NIC.
ENIs can be attached and detached from EC2 instances, and the configuration of the ENI will be maintained.
Flow Logs capture information about the IP traffic going to and from network interfaces in a VPC.
Flow log data is stored using Amazon CloudWatch Logs.

Flow logs can be created at the following levels:
- VPC.
- Subnet.
- Network interface.
Peering connections can be created with VPCs in different regions (available in most regions now).

### Subnets
After creating a VPC, you can add one or more subnets in each Availability Zone.
When you create a subnet, you specify the CIDR block for the subnet, which is a subset of the VPC CIDR block.
Each subnet must reside entirely within one Availability Zone and cannot span zones.
Types of subnet:
- If a subnet’s traffic is routed to an internet gateway, the subnet is known as a public subnet.
- If a subnet doesn’t have a route to the internet gateway, the subnet is known as a private subnet.
- If a subnet doesn’t have a route to the internet gateway, but has its traffic routed to a virtual private gateway for a VPN connection, the subnet is known as a VPN-only subnet.
An Internet Gateway is a horizontally scaled, redundant, and highly available VPC component that allows communication between instances in your VPC and the internet.

## VPC Wizard
The VPC Wizard can be used to create the following four configurations:

VPC with a Single Public Subnet:
- Your instances run in a private, isolated section of the AWS cloud with direct access to the Internet.
- Network access control lists and security groups can be used to provide strict control over inbound and outbound network traffic to your instances.
- Creates a /16 network with a /24 subnet. Public subnet instances use Elastic IPs or Public IPs to access the Internet.

VPC with Public and Private Subnets:
- In addition to containing a public subnet, this configuration adds a private subnet whose instances are not addressable from the Internet.
- Instances in the private subnet can establish outbound connections to the Internet via the public subnet using Network Address Translation (NAT).
- Creates a /16 network with two /24 subnets.
- Public subnet instances use Elastic IPs to access the Internet.
- Private subnet instances access the Internet via Network Address Translation (NAT).

VPC with Public and Private Subnets and Hardware VPN Access:
- This configuration adds an IPsec Virtual Private Network (VPN) connection between your Amazon VPC and your data center – effectively extending your data center to the cloud while also providing direct access to the Internet for public subnet instances in your Amazon VPC.
- Creates a /16 network with two /24 subnets.
- One subnet is directly connected to the Internet while the other subnet is connected to your corporate network via an IPsec VPN tunnel.

VPC with a Private Subnet Only and Hardware VPN Access:
- Your instances run in a private, isolated section of the AWS cloud with a private subnet whose instances are not addressable from the Internet.
- You can connect this private subnet to your corporate data center via an IPsec Virtual Private Network (VPN) tunnel.
- Creates a /16 network with a /24 subnet and provisions an IPsec VPN tunnel between your Amazon VPC and your corporate network.

## VPN
## CloudFront

## AWS Organizations
AWS organizations allows you to consolidate multiple AWS accounts into an organization that you create and centrally manage.

Available in two feature sets:
- Consolidated Billing.
- All features.

Includes root accounts and organizational units.
Policies are applied to root accounts or OUs.

Consolidated billing includes:
- Paying Account – independent and cannot access resources of other accounts.
- Linked Accounts – all linked accounts are independent.
![image](https://github.com/nnhung232/AWS-CCP/assets/4153181/91b292e3-7d54-452e-9f8d-d3ad03e2a4bd)

## AWS Control Tower
Simplifies the process of creating multi-account environments.
Sets up governance, compliance, and security guardrails for you.

Integrates with other services and features to setup the environment for you including:
- AWS Organizations, SCPs, OUs, AWS Config, AWS CloudTrail, Amazon S3, Amazon SNS, AWS CloudFormation, AWS Service Catalog, AWS Single Sign-On (SSO).

Examples of guardrails AWS Control Tower can configure for you include:
- Disallowing public write access to Amazon Simple Storage Service (Amazon S3) buckets.
- Disallowing access as a root user without multi-factor authentication.
- Enabling encryption for Amazon EBS volumes attached to Amazon EC2 instances.

## AWS Config
AWS Config is a fully managed service that provides you with an AWS resource inventory, configuration history, and configuration change notifications to enable security and regulatory compliance.
With AWS Config, you can discover existing and deleted AWS resources, determine your overall compliance against rules, and dive into configuration details of a resource at any point in time. AWS Config enables compliance auditing, security analysis, resource change tracking, and troubleshooting.
![image](https://github.com/nnhung232/AWS-CCP/assets/4153181/428f8237-053c-4d69-947b-f88d16de47bc)

## AWS Service Catalog
AWS Service Catalog allows organizations to create and manage catalogs of IT services that are approved for use on AWS.
AWS Service Catalog allows you to centrally manage commonly deployed IT services.
IT services can include virtual machine images, servers, software, and databases and multi-tier application architectures.
Enables users to quickly deploy only the approved IT services they need.

## AWS Systems Manager
Manages many AWS resources including Amazon EC2, Amazon S3, Amazon RDS etc.

Systems Manager Components:
- Automation.
- Run Command.
- Inventory.
- Patch Manager.
- Session Manager.
- Parameter Store.

## AWS Personal Health Dashboard
AWS Personal Health Dashboard provides alerts and remediation guidance when AWS is experiencing events that may impact you.
Personal Health Dashboard gives you a personalized view into the performance and availability of the AWS services underlying your AWS resources.
The dashboard displays relevant and timely information to help you manage events in progress.
Also provides proactive notification to help you plan for scheduled activities.
Alerts are triggered by changes in the health of AWS resources, giving you event visibility, and guidance to help quickly diagnose and resolve issues.
You get a personalized view of the status of the AWS services that power your applications, enabling you to quickly see when AWS is experiencing issues that may impact you.
Also provides forward looking notifications, and you can set up alerts across multiple channels, including email and mobile notifications, so you receive timely and relevant information to help plan for scheduled changes that may affect you.
Alerts include remediation details and specific guidance to enable you to take immediate action to address AWS events impacting your resources.
Can integrate with Amazon CloudWatch Events, enabling you to build custom rules and select targets such as AWS Lambda functions to define automated remediation actions.
The AWS Health API allows you to integrate health data and notifications with your existing in-house or third-party IT Management tools.

## Service Health Dashboard
AWS publishes up-to-the-minute information on service availability.
This information is not personalized to you (unlike Personal Health Dashboard).

## AWS OpsWorks
AWS OpsWorks is a configuration management service that provides managed instances of Chef and Puppet.
Updates include patching, updating, backup, configuration, and compliance management.

## AWS Trusted Advisor
AWS Trusted Advisor is an online tool that provides you real time guidance to help you provision your resources following AWS best practices.
Trusted Advisor checks help optimize your AWS infrastructure, improve security and performance, reduce your overall costs, and monitor service limits.
AWS Basic Support and AWS Developer Support customers get access to 6 security checks (S3 Bucket Permissions, Security Groups – Specific Ports Unrestricted, IAM Use, MFA on Root Account, EBS Public Snapshots, RDS Public Snapshots) and 50 service limit checks.
AWS Business Support and AWS Enterprise Support customers get access to all 115 Trusted Advisor checks (14 cost optimization, 17 security, 24 fault tolerance, 10 performance, and 50 service limits) and recommendations.

## AWS CloudFormation
AWS CloudFormation provides a common language for you to describe and provision all the infrastructure resources in your cloud environment.
CloudFormation allows you to use a simple text file to model and provision, in an automated and secure manner, all the resources needed for your applications across all regions and accounts.
This file serves as the single source of truth for your cloud environment.
You can use JSON or YAML to describe what AWS resources you want to create and configure.

## AWS Resource for Security Support
### AWS Report Abuse

# Technology
## Deployment and Operating in the AWS
### On premise & Hybrid

### NAT Instances
NAT instances are managed by you.
Used to enable private subnet instances to access the Internet.
When creating NAT instances always disable the source/destination check on the instance.
NAT instances must be in a single public subnet.
NAT instances need to be assigned to security groups.
NAT Gateways
NAT gateways are managed for you by AWS.
NAT gateways are highly available in each AZ into which they are deployed.
They are preferred by enterprises.
Can scale automatically up to 45Gbps.
No need to patch.
Not associated with any security groups.

### AWS Direct Connect (DX)
![image](https://github.com/nnhung232/AWS-CCP/assets/4153181/91a9bcfe-c342-4f52-b168-ae2c566b91fa)
AWS Direct Connect is a network service that provides an alternative to using the Internet to connect a customer’s on-premises sites to AWS.
Data is transmitted through a private network connection between AWS and a customer’s data center or corporate network.

Benefits of Direct Connect:
- Reduce cost when using large volumes of traffic.
- Increase reliability (predictable performance).
- Increase bandwidth (predictable bandwidth).
- Decrease latency.

Each AWS Direct Connect connection can be configured with one or more virtual interfaces (VIFs).
Public VIFs allow access to public services such as S3, EC2, and DynamoDB.
Private VIFs allow access to your VPC.
From Direct Connect you can connect to all AZs within the Region.
You can establish IPSec connections over public VIFs to remote regions.
Direct Connect is charged by port hours and data transfer.
Available in 1Gbps and 10Gbps.
Speeds of 50Mbps, 100Mbps, 200Mbps, 300Mbps, 400Mbps, and 500Mbps can be purchased through AWS Direct Connect Partners.
Each connection consists of a single dedicated connection between ports on the customer router and an Amazon router.
for HA you must have 2 DX connections – can be active/active or active/standby.
Route tables need to be updated to point to a Direct Connect connection.

### AWS Global Accelerator
AWS Global Accelerator is a service that improves the availability and performance of applications with local or global users.
It provides static IP addresses that act as a fixed entry point to application endpoints in a single or multiple AWS Regions, such as Application Load Balancers, Network Load Balancers or EC2 instances.
Uses the AWS global network to optimize the path from users to applications, improving the performance of TCP and UDP traffic.
AWS Global Accelerator continually monitors the health of application endpoints and will detect an unhealthy endpoint and redirect traffic to healthy endpoints in less than 1 minute.

### AWS Outposts
AWS Outposts is a fully managed service that offers the same AWS infrastructure, AWS services, APIs, and tools to virtually any datacenter, co-location space, or on-premises facility for a truly consistent hybrid experience.
AWS Outposts is ideal for workloads that require low latency access to on-premises systems, local data processing, data residency, and migration of applications with local system interdependencies.
AWS compute, storage, database, and other services run locally on Outposts, and you can access the full range of AWS services available in the Region to build, manage, and scale your on-premises applications using familiar AWS services and tools.
Outposts is available as a 42U rack that can scale from 1 rack to 96 racks to create pools of compute and storage capacity.
Services you can run on AWS Outposts include:
- Amazon EC2.
- Amazon EBS.
- Amazon S3.
- Amazon VPC.
- Amazon ECS/EKS.
- Amazon RDS.
- Amazon EMR.

### Firewalls
Network Access Control Lists (ACLs) provide a firewall/security layer at the subnet level.
Security Groups provide a firewall/security layer at the instance level.

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

## AWS Analytics Services
### Amazon Elastic Map Reduce
Amazon EMR is a web service that enables businesses, researchers, data analysts, and developers to easily and cost-effectively process vast amounts of data.
EMR utilizes a hosted Hadoop framework running on Amazon EC2 and Amazon S3.
Managed Hadoop framework for processing huge amounts of data.
Also support Apache Spark, HBase, Presto and Flink.
Most commonly used for log analysis, financial analysis, or extract, translate and loading (ETL) activities.
A Step is a programmatic task for performing some process on the data (e.g. count words).
A cluster is a collection of EC2 instances provisioned by EMR to run your Steps.
EMR uses Apache Hadoop as its distributed data processing engine, which is an open source, Java software framework that supports data-intensive distributed applications running on large clusters of commodity hardware.
EMR is a good place to deploy Apache Spark, an open-source distributed processing used for big data workloads which utilizes in-memory caching and optimized query execution.
You can also launch Presto clusters. Presto is an open-source distributed SQL query engine designed for fast analytic queries against large datasets.
EMR launches all nodes for a given cluster in the same Amazon EC2 Availability Zone.
You can access Amazon EMR by using the AWS Management Console, Command Line Tools, SDKS, or the EMR API.
With EMR you have access to the underlying operating system (you can SSH in).

### Amazon Athena
Amazon Athena is an interactive query service that makes it easy to analyze data in Amazon S3 using standard SQL.
Athena is serverless, so there is no infrastructure to manage, and you pay only for the queries that you run.
Athena is easy to use – simply point to your data in Amazon S3, define the schema, and start querying using standard SQL.
Amazon Athena uses Presto with full standard SQL support and works with a variety of standard data formats, including CSV, JSON, ORC, Apache Parquet and Avro.
While Amazon Athena is ideal for quick, ad-hoc querying and integrates with Amazon QuickSight for easy visualization, it can also handle complex analysis, including large joins, window functions, and arrays.
Amazon Athena uses a managed Data Catalog to store information and schemas about the databases and tables that you create for your data stored in Amazon S3.

### AWS Glue
AWS Glue is a fully managed, pay-as-you-go, extract, transform, and load (ETL) service that automates the time-consuming steps of data preparation for analytics.
AWS Glue automatically discovers and profiles data via the Glue Data Catalog, recommends and generates ETL code to transform your source data into target schemas.
AWS Glue runs the ETL jobs on a fully managed, scale-out Apache Spark environment to load your data into its destination.
AWS Glue also allows you to setup, orchestrate, and monitor complex data flows.
You can create and run an ETL job with a few clicks in the AWS Management Console.
Use AWS Glue to discover properties of data, transform it, and prepare it for analytics.
Glue can automatically discover both structured and semi-structured data stored in data lakes on Amazon S3, data warehouses in Amazon Redshift, and various databases running on AWS.
It provides a unified view of data via the Glue Data Catalog that is available for ETL, querying and reporting using services like Amazon Athena, Amazon EMR, and Amazon Redshift Spectrum.
Glue automatically generates Scala or Python code for ETL jobs that you can further customize using tools you are already familiar with.
AWS Glue is serverless, so there are no compute resources to configure and manage.

### Amazon Kinesis
Amazon Kinesis makes it easy to collect, process, and analyze real-time, streaming data so you can get timely insights and react quickly to new information.
Collection of services for processing streams of various data.
Data is processed in “shards”.
There are four types of Kinesis service, and these are detailed below.

**1. Kinesis Video Streams**
Kinesis Video Streams makes it easy to securely stream video from connected devices to AWS for analytics, machine learning (ML), and other processing.
Durably stores, encrypts, and indexes video data streams, and allows access to data through easy-to-use APIs.
Producers provide data streams.
Stores data for 24 hours by default, up to 7 days.
Consumers receive and process data.
Can have multiple shards in a stream.
Supports encryption at rest with server-side encryption (KMS) with a customer master key.

**2. Kinesis Data Streams**
Kinesis Data Streams enables you to build custom applications that process or analyze streaming data for specialized needs.
Kinesis Data Streams enables real-time processing of streaming big data.
Kinesis Data Streams is useful for rapidly moving data off data producers and then continuously processing the data.
Kinesis Data Streams stores data for later processing by applications (key difference with Firehose which delivers data directly to AWS services).

Common use cases include:
- Accelerated log and data feed intake.
- Real-time metrics and reporting.
- Real-time data analytics.
- Complex stream processing.

**3. Kinesis Data Firehose**
Kinesis Data Firehose is the easiest way to load streaming data into data stores and analytics tools.
Captures, transforms, and loads streaming data.
Enables near real-time analytics with existing business intelligence tools and dashboards.
Kinesis Data Streams can be used as the source(s) to Kinesis Data Firehose.
You can configure Kinesis Data Firehose to transform your data before delivering it.
With Kinesis Data Firehose you don’t need to write an application or manage resources.
Firehose can batch, compress, and encrypt data before loading it.
Firehose synchronously replicates data across three AZs as it is transported to destinations.

**4. Kinesis Data Analytics**
Amazon Kinesis Data Analytics is the easiest way to process and analyze real-time, streaming data.
Can use standard SQL queries to process Kinesis data streams.
Provides real-time analysis.
Use cases:
- Generate time-series analytics.
- Feed real-time dashboards.
- Create real-time alerts and notifications.

Quickly author and run powerful SQL code against streaming sources.
Can ingest data from Kinesis Streams and Kinesis Firehose.
Output to S3, RedShift, Elasticsearch and Kinesis Data Streams.
Sits over Kinesis Data Streams and Kinesis Data Firehose.

Each delivery stream stores data records for up to 24 hours.

## AWS Monitoring and Logging Services
### Amazon CloudWatch
Amazon CloudWatch is a monitoring service for AWS cloud resources and the applications you run on AWS.
CloudWatch is for performance monitoring (CloudTrail is for auditing).
Used to collect and track metrics, collect, and monitor log files, and set alarms.
Automatically react to changes in your AWS resources.

Monitor resources such as:
- EC2 instances.
- DynamoDB tables.
- RDS DB instances.
- Custom metrics generated by applications and services.
- Any log files generated by your applications.

Gain system-wide visibility into resource utilization.
CloudWatch monitoring includes application performance.
Monitor operational health.
CloudWatch is accessed via API, command-line interface, AWS SDKs, and the AWS Management Console.
CloudWatch integrates with IAM.
Amazon CloudWatch Logs lets you monitor and troubleshoot your systems and applications using your existing system, application, and custom log files.
CloudWatch Logs can be used for real time application and system monitoring as well as long term log retention.
CloudWatch Logs keeps logs indefinitely by default.
CloudTrail logs can be sent to CloudWatch Logs for real-time monitoring.
CloudWatch Logs metric filters can evaluate CloudTrail logs for specific terms, phrases, or values.

CloudWatch retains metric data as follows:
- Data points with a period of less than 60 seconds are available for 3 hours. These data points are high-resolution custom metrics.
- Data points with a period of 60 seconds (1 minute) are available for 15 days.
- Data points with a period of 300 seconds (5 minute) are available for 63 days.
- Data points with a period of 3600 seconds (1 hour) are available for 455 days (15 months).

Dashboards allow you to create, customize, interact with, and save graphs of AWS resources and custom metrics.
Alarms can be used to monitor any Amazon CloudWatch metric in your account.
Events are a stream of system events describing changes in your AWS resources.
Logs help you to aggregate, monitor and store logs.
Basic monitoring = 5 mins (free for EC2 Instances, EBS volumes, ELBs and RDS DBs).
Detailed monitoring = 1 min (chargeable).
Metrics are provided automatically for several AWS products and services.
There is no standard metric for memory usage on EC2 instances.
A custom metric is any metric you provide to Amazon CloudWatch (e.g. time to load a web page or application performance).

Options for storing logs:
- CloudWatch Logs.
- Centralized logging system (e.g. Splunk).
- Custom script and store on S3.

Do not store logs on non-persistent disks:
Best practice is to store logs in CloudWatch Logs or S3.
CloudWatch Logs subscription can be used across multiple AWS accounts (using cross account access).
Amazon CloudWatch uses Amazon SNS to send email.

### AWS CloudTrail
AWS CloudTrail is a web service that records activity made on your account and delivers log files to an Amazon S3 bucket.
CloudTrail is for auditing (CloudWatch is for performance monitoring).
CloudTrail is about logging and saves a history of API calls for your AWS account.
Provides visibility into user activity by recording actions taken on your account.
API history enables security analysis, resource change tracking, and compliance auditing.

Logs API calls made via:
- AWS Management Console.
- AWS SDKs.
- Command line tools.
- Higher-level AWS services (such as CloudFormation).

CloudTrail records account activity and service events from most AWS services and logs the following records:
- The identity of the API caller.
- The time of the API call.
- The source IP address of the API caller.
- The request parameters.
- The response elements returned by the AWS service.

CloudTrail is enabled by default.
CloudTrail is per AWS account.

You can consolidate logs from multiple accounts using an S3 bucket:
1. Turn on CloudTrail in the paying account.
2. Create a bucket policy that allows cross-account access.
3. Turn on CloudTrail in the other accounts and use the bucket in the paying account.

You can integrate CloudTrail with CloudWatch Logs to deliver data events captured by CloudTrail to a CloudWatch Logs log stream.
CloudTrail log file integrity validation feature allows you to determine whether a CloudTrail log file was unchanged, deleted, or modified since CloudTrail delivered it to the specified Amazon S3 bucket.

## AWS Content Delivery and DNS Services
### Amazon Route 53
Amazon Route 53 is the AWS Domain Name Service.

Route 53 performs three main functions:
- Domain registration – Route 53 allows you to register domain names.
- Domain Name Service (DNS) – Route 53 translates name to IP addresses using a global network of authoritative DNS servers.
- Health checking – Route 53 sends automated requests to your application to verify that it’s reachable, available, and functional.

You can use any combination of these functions.

Route 53 benefits:
- Domain registration.
- DNS service.
- Traffic Flow (send users to the best endpoint).
- Health checking.
- DNS failover (automatically change domain endpoint if system fails).
- Integrates with ELB, S3, and CloudFront as endpoints.

Routing policies determine how Route 53 DNS responds to queries.
- Simple: Simple DNS response providing the IP address associated with a name
- Failover: If primary is down (based on health checks), routes to secondary destination
- Geolocation:	Uses geographic location you’re in (e.g. Europe) to route you to the closest region
- Geoproximity:	Routes you to the closest region within a geographic area
- Latency: Directs you based on the lowest latency route to resources
- Multivalue answer: Returns several IP addresses and functions as a basic load balancer
- Weighted: Uses the relative weights assigned to resources to determine which to route to

### Amazon CloudFront
Amazon CloudFront is a content delivery network (CDN) that allows you to store (cache) your content at “edge locations” located around the world.
This allows customers to access content more quickly and provides security against DDoS attacks.
CloudFront can be used for data, videos, applications, and APIs.

CloudFront benefits:
- Cache content at Edge Location for fast distribution to customers.
- Built-in Distributed Denial of Service (DDoS) attack protection.
- Integrates with many AWS services (S3, EC2, ELB, Route 53, Lambda).

Origins and Distributions:
- An origin is the origin of the files that the CDN will distribute.
- Origins can be either an S3 bucket, an EC2 instance, an Elastic Load Balancer, or Route 53 – can also be external (non-AWS).
- To distribute content with CloudFront you need to create a distribution.

CloudFront uses Edge Locations and Regional Edge Caches:
- An edge location is the location where content is cached (separate to AWS regions/AZs).
- Requests are automatically routed to the nearest edge location.
- Regional Edge Caches are located between origin web servers and global edge locations and have a larger cache.
- Regional Edge caches aim to get content closer to users.

The diagram below shows where Regional Edge Caches and Edge Locations are placed in relation to end users:
![image](https://github.com/nnhung232/AWS-CCP/assets/4153181/7f82c413-cdbb-4958-a1d0-d306545cc6fd)

## AWS Storage Services
### Amazon Simple Storage Service (S3)
Amazon S3 is object storage built to store and retrieve any amount of data from anywhere – web sites and mobile apps, corporate applications, and data from IoT sensors or devices.
You can store any type of file in S3.
S3 is designed to deliver 99.999999999% durability, and stores data for millions of applications used by market leaders in every industry.
S3 provides comprehensive security and compliance capabilities that meet even the most stringent regulatory requirements.
S3 gives customers flexibility in the way they manage data for cost optimization, access control, and compliance.

Typical use cases include:
- Backup and Storage – Provide data backup and storage services for others.
- Application Hosting – Provide services that deploy, install, and manage web applications.
- Media Hosting – Build a redundant, scalable, and highly available infrastructure that hosts video, photo, or music uploads and downloads.
- Software Delivery – Host your software applications that customers can download.
- Static Website – you can configure a static website to run from an S3 bucket.

S3 provides query-in-place functionality, allowing you to run powerful analytics directly on your data at rest in S3. And Amazon S3 is the most supported cloud storage service available, with integration from the largest community of third-party solutions, systems integrator partners, and other AWS services.
Files can be anywhere from 0 bytes to 5 TB.
There is unlimited storage available.
Files are stored in buckets.
Buckets are root level folders.
Any subfolder within a bucket is known as a “folder”.
S3 is a universal namespace so bucket names must be unique globally.

There are seven S3 storage classes.
- S3 Standard (durable, immediately available, frequently accessed).
- S3 Intelligent-Tiering (automatically moves data to the most cost-effective tier).
- S3 Standard-IA (durable, immediately available, infrequently accessed).
- S3 One Zone-IA (lower cost for infrequently accessed data with less resilience).
- S3 Glacier Instant Retrieval (data that is rarely accessed and requires retrieval in milliseconds).
- S3 Glacier Flexible Retrieval (archived data, retrieval times in minutes or hours).
- S3 Glacier Deep Archive (lowest cost storage class for long term retention).

When you successfully upload a file to S3 you receive a HTTP 200 code.
S3 is a persistent, highly durable data store.
Persistent data stores are non-volatile storage systems that retain data when powered off.
This contrasts with transient data stores and ephemeral data stores which lose the data when powered off.
The following table provides a description of persistent, transient, and ephemeral data stores and which AWS service to use:
- Persistent Data Store:	Data is durable and sticks around after reboots, restarts, or power cycles (S3, Glacier, EBS, EFS)
- Transient Data Store:	Data is just temporarily stored and passed along to another process or persistent store	(SQS, SNS)
- Ephemeral Data Store:	Data is lost when the system is stopped	(EC2 Instance Store, Memcached)

Bucket names must follow a set of rules:
- Names must be unique across all of AWS.
- Names must be 3 to 63 characters in length.
- Names can only contain lowercase letters, numbers, and hyphens.
- Names cannot be formatted as an IP address.

Objects consist of:
- Key (name of the object).
- Value (data made up of a sequence of bytes).
- Version ID (used for versioning).
- Metadata (data about the data that is stored).

Subresources:
- Access control lists.
- Torrent.

Object sharing – the ability to make any object publicly available via a URL.
Lifecycle management – set rules to transfer objects between storage classes at defined time intervals.
Versioning – automatically keep multiple versions of an object (when enabled).
Encryption can be enabled for bucket.
Data is secured using ACLs and bucket policies.

Charges:
- Storage.
- Requests.
- Storage management pricing.
- Data transfer pricing.
- Transfer acceleration.

When you create a bucket you need to select the region where it will be created.
It is a best practice to create buckets in regions that are physically closest to your users to reduce latency.

### AWS Snowball
With AWS Snowball (Snowball), you can transfer hundreds of terabytes or petabytes of data between your on-premises data centers and Amazon Simple Storage Service (Amazon S3).
Uses a secure storage device for physical transportation.
AWS Snowball Client is software that is installed on a local computer and is used to identify, compress, encrypt, and transfer data.
Uses 256-bit encryption (managed with the AWS KMS) and tamper-resistant enclosures with TPM.
The table below describes the AWS Snow offerings at a high-level:
- AWS Snowball:	Bulk data transfer, edge storage, and edge compute
- AWS Snowmobile:	A literal shipping container full of storage (up to 100PB) and a truck to transport it
- AWS Snowcone:	The smallest device in the range that is best suited for outside the data center

Snowball can import to S3 or export from S3.
Import/export is when you send your own disks into AWS – this is being deprecated in favor of Snowball.
Snowball must be ordered from and returned to the same region.
To speed up data transfer it is recommended to run simultaneous instances of the AWS Snowball Client in multiple terminals and transfer small files as batches.
### Amazon Elastic Block Store (EBS)
Amazon Elastic Block Store (Amazon EBS) provides persistent block storage volumes for use with Amazon EC2 instances in the AWS Cloud.

Each Amazon EBS volume is automatically replicated within its Availability Zone to protect you from component failure, offering high availability and durability.

Amazon EBS volumes offer the consistent and low-latency performance needed to run your workloads. With Amazon EBS, you can scale your usage up or down within minutes – all while paying a low price for only what you provision.

The following EBS volumes appear most often on the AWS exams:
| Volume Type |	EBS Provisioned IOPS SSD (io1/io2) | EBS General Purpose SSD (gp2/gp3) | Throughput Optimized HDD (st1) | Cold HDD (sc1) |
| ----------- |	---------------------------------- | --------------------------------- | -------------------------------|--------------- |
|Short Description |	Highest performance SSD volume designed for latency-sensitive transactional workloads |	General Purpose SSD volume that balances price performance for a wide variety of transactional workloads |	Low-cost HDD volume, designed for frequently accessed. Throughput intensive workloads |	Lowest cost HDD volume designed for less frequently accessed workloads |
| Use Cases |	I/O-intensive NoSQL and relational databases |	Boot volumes, low-latency interactive apps, dev & test |	Big-data, data warehouses, log processing |	Colder data requiring fewer scans per day |
| Volume Size |	4 GiB – 16 TiB |	1 GiB – 16 TiB |	125 GB – 16 TiB |	125 GB – 16 TiB |
| Max IOPS** / Volume |	64,000 |	16,000 |	500 |	250 |
| Max Throughput\*\*\*Volume |	1,000 MiB/s |	250 MiB/s (gp2) 1000 MiB/s (gp3) | 500 MiB/s |	250 MiB/s |
| Can be boot volume? |	Yes |	Yes |	No |	No |
| EBS Multi-attach |	Supported |	Not Supported |	Not Supported |	Not Supported |

EBS volume data persists independently of the life of the instance.
EBS volumes do not need to be attached to an instance.
You can attach multiple EBS volumes to an instance.
You cannot attach an EBS volume to multiple instances (use Elastic File Store instead).
EBS volumes must be in the same AZ as the instances they are attached to.
Termination protection is turned off by default and must be manually enabled (keeps the volume/data when the instance is terminated).
Root EBS volumes are deleted on termination by default.
Extra non-boot volumes are not deleted on termination by default.
The behavior can be changed by altering the “DeleteOnTermination” attribute.

EBS Snapshots:
- Snapshots capture a point-in-time state of an instance.
- Snapshots are stored on S3.
- Does not provide granular backup (not a replacement for backup software).
- If you make periodic snapshots of a volume, the snapshots are incremental, which means that only the blocks on the device that have changed after your last snapshot are saved in the new snapshot.
- Even though snapshots are saved incrementally, the snapshot deletion process is designed so that you need to retain only the most recent snapshot to restore the volume.
- Snapshots can only be accessed through the EC2 APIs.
- EBS volumes are AZ specific, but snapshots are region specific.
![image](https://github.com/nnhung232/AWS-CCP/assets/4153181/b5bc66c7-e994-4145-9d8c-22ff31afe49a)

### Instance Store Volumes
Instance store volumes are high performance local disks that are physically attached to the host computer on which an EC2 instance runs.
Instance stores are ephemeral which means the data is lost when powered off (non-persistent).
Instances stores are ideal for temporary storage of information that changes frequently, such as buffers, caches, or  scratch data.
Instance store volume root devices are created from AMI templates stored on S3.
Instance store volumes cannot be detached/reattached.

### Amazon Elastic File System (EFS)
EFS is a fully managed service that makes it easy to set up and scale file storage in the Amazon Cloud.
Good for big data and analytics, media processing workflows, content management, web serving, home directories etc.
EFS uses the NFS protocol.
Pay for what you use (no pre-provisioning required).
Can scale up to petabytes.
EFS is elastic and grows and shrinks as you add and remove data.
Can concurrently connect 1 to 1000s of EC2 instances, from multiple AZs.
A file system can be accessed concurrently from all AZs in the region where it is located.
By default you can create up to 10 file systems per account.
On-premises access can be enabled via Direct Connect or AWS VPN.
Can choose General Purpose or Max I/O (both SSD).
The VPC of the connecting instance must have DNS hostnames enabled.
EFS provides a file system interface, file system access semantics (such as strong consistency and file locking).
Data is stored across multiple AZs within a region.
Read after write consistency.
Need to create mount targets and choose AZs to include (recommended to include all AZ’s).
Instances can be behind an ELB.

There are two performance modes:
- “General Purpose” performance mode is appropriate for most file systems.
- “Max I/O” performance mode is optimized for applications where tens, hundreds, or thousands of EC2 instances are accessing the file system.

Amazon EFS is designed to burst to allow high throughput levels for periods of time.
![image](https://github.com/nnhung232/AWS-CCP/assets/4153181/e6a0ab43-4607-4e4f-97c7-2979a2b6ec47)

### AWS Storage Gateway
AWS Storage Gateway is a hybrid cloud storage service that gives you on-premises access to virtually unlimited cloud storage.
Customers use Storage Gateway to simplify storage management and reduce costs for key hybrid cloud storage use cases.
These include moving backups to the cloud, using on-premises file shares backed by cloud storage, and providing low latency access to data in AWS for on-premises applications.

To support these use cases, Storage Gateway offers three different types of gateways:
- File Gateway – provides file system interfaces to on-premises servers.
- Volume Gateway – provides block-based access for on-premises servers.
- Tape Gateway – provides a virtual tape library that is compatible with common backup software (block and file interfaces).

### AWS Backup
The AWS Backup service offers a centralized backup console, APIs, and command line interface for managing backups across AWS services, including:
- Amazon Simple Storage Service (S3)
- Amazon Elastic Block Store (EBS)
- Amazon FSx
- Amazon Elastic Compute Cloud (EC2)
- Amazon Relational Database Service (RDS)
- Amazon DynamoDB
- Amazon Elastic File System (EFS)
- AWS Storage Gateway
- … and more

AWS Backup allows you to centrally manage backup policies that meet your backup requirements and apply them across your AWS resources across AWS services as well as hybrid cloud workloads. This enables you to back up your application data consistently and in accordance with compliance requirements. Moreover, AWS Backup’s centralized backup console offers a consolidated view of your backups and backup activity logs, making it easier to audit your backups.

### Amazon FSX for Lustre
For compute workloads, Amazon FSx for Lustre provides scalable, high-performance, cost-effective storage for compute workloads. Based on Lustre, the world’s most popular high-performance file system, FSx for Lustre provides shared storage with sub-ms latencies, up to terabytes of throughput, and millions of IOPS. It is also possible to link FSx for Lustre file systems to Amazon Simple Storage Service (S3) buckets, allowing you to access and process data simultaneously from both.
A number of the fastest computers in the world use the Lustre open source file system to process ever-growing data sets quickly and cheaply. It is suitable for workloads ranging from genome sequencing to video transcoding to machine learning to fraud detection. Lustre has been battle-tested across a wide range of industries – from energy to life sciences to media production to financial services.

### Amazon FSX for Windows File Server
Your applications and end users can access reliable, performant, and secure shared file storage with Amazon FSx for Windows File Server. Using Amazon FSx, you can create highly available and durable file systems that span multiple availability zones (AZs) and can be accessed from up to thousands of computing instances.
In addition to providing a rich set of administrative and security features, it also integrates with Microsoft Active Directory (AD). For a variety of workloads, Amazon FSx provides high levels of file system throughput and IOPS as well as consistent sub-millisecond latencies.
Based on Windows Server, Amazon FSx includes a rich set of administrative features, including end-user file restore, user quotas, and access control lists (ACLs). Windows Server supports the SMB protocol natively, allowing Windows-based applications to access shared file storage. SMB file shares can also be accessed from Linux and MacOS, so any application or user can access the storage. AWS Microsoft Managed AD and your on-premises Microsoft Active Directory can be integrated with Amazon FSx to control user access.

## AWS Compute Services
### Amazon EC2
Amazon Elastic Compute Cloud (Amazon EC2) is a web service with which you can run virtual server “instances” in the cloud.
Amazon EC2 instances can run the Windows, Linux, or MacOS operating systems.
The EC2 simple web service interface allows you to obtain and configure capacity with minimal friction.
EC2 is designed to make web-scale cloud computing easier for developers.
Amazon EC2 changes the economics of computing by allowing you to pay only for capacity that you use.
Amazon EC2 provides developers the tools to build failure resilient applications and isolate them from common failure scenarios.

Benefits of EC2 include:
- Elastic Web-Scale computing – you can increase or decrease capacity within minutes not hours and commission one to thousands of instances simultaneously.
- Completely controlled – You have complete control include root access to each instance and can stop and start instances without losing data and using web service APIs.
- Flexible Cloud Hosting Services – you can choose from multiple instance types, operating systems, and software packages as well as instances with varying memory, CPU, and storage configurations.
- Integrated – EC2 is integrated with most AWS services such as S3, RDS, and VPC to provide a complete, secure solution.
- Reliable – EC2 offers a highly reliable environment where replacement instances can be rapidly and predictably commissioned with SLAs of 99.99% for each region.
- Secure – EC2 works in conjunction with VPC to provide a secure location with an IP address range you specify and offers Security Groups, Network ACLs, and IPSec VPN features.
- Inexpensive – Amazon passes on the financial benefits of scale by charging very low rates and on a capacity consumed basis.

An Amazon Machine Image (AMI) is a special type of virtual appliance that is used to create a virtual machine within the Amazon Elastic Compute Cloud (“EC2”).

An AMI includes the following:
- One or more EBS snapshots, or, for instance-store-backed AMIs, a template for the root volume of the instance (for example, an operating system, an application server, and applications).
- Launch permissions that control which AWS accounts can use the AMI to launch instances.
- A block device mapping that specifies the volumes to attach to the instance when it’s launched.

AMIs come in three main categories:
- Community AMIs – free to use, generally you just select the operating system you want.
- AWS Marketplace AMIs – pay to use, generally come packaged with additional, licensed software.
- My AMIs – AMIs that you create yourself.

![image](https://github.com/nnhung232/AWS-CCP/assets/4153181/904ceb8e-bbbf-4d80-bbe9-52fe19677593)

Metadata and User Data:
- User data is data that is supplied by the user at instance launch in the form of a script.
- Instance metadata is data about your instance that you can use to configure or manage the running instance.
- User data is limited to 16KB.
- User data and metadata are not encrypted.
- Instance metadata is available at http://169.254.169.254/latest/meta-data.
The Instance Metadata Query tool allows you to query the instance metadata without having to type out the full URI or category names.

### Pricing
On-demand:
- Good for users that want the low cost and flexibility of EC2 without any up-front payment or long-term commitment.
- Applications with short term, spiky, or unpredictable workloads that cannot be interrupted.
- Applications being developed or tested on EC2 for the first time.

Reserved:
- Applications with steady state or predictable usage.
- Applications that require reserved capacity.
- Users can make up-front payments to reduce their total computing costs even further.
- Standard Reserved Instances (RIs) provide up to 75% off on-demand price.
- Convertible RIs provide up to 54% off on-demand price – provides the capability to change the attributes of the RI if the exchange results in the creation of RIs of equal or greater value.
- Scheduled RIs are available to launch within the time window you reserve. This option allows you to match your capacity reservation to a predictable recurring schedule that only requires a fraction of a day, a week, or a month.

Spot:
- Applications that have flexible start and end times.
- Applications that are only feasible at very low compute prices.
- Users with an urgent need for a large amount of additional compute capacity.
- If Amazon terminate your instances you do not pay, if you terminate you pay for the hour.

Dedicated hosts:
- Physical servers dedicated just for your use.
- You then have control over which instances are deployed on that host.
- Available as On-Demand or with Dedicated Host Reservation.
- Useful if you have server-bound software licenses that use metrics like per-core, per-socket, or per-VM.
- Each dedicated host can only run one EC2 instance size and type.
- Good for regulatory compliance or licensing requirements.
- Predictable performance.
- Complete isolation.
- Most expensive option.
- Billing is per host.

Dedicated instances:
- Virtualized instances on hardware just for you.
- Also uses physically dedicated EC2 servers.
- Does not provide the additional visibility and controls of dedicated hosts (e.g. how instances are placed on a server).
- Billing is per instance.
- May share hardware with other non-dedicated instances in the same account.
- Available as On-Demand, Reserved Instances, and Spot Instances.
- Cost additional $2 per hour per region.

Savings Plans:
- Savings Plans is a flexible pricing model that provides savings of up to 72% on your AWS compute usage.
- This pricing model offers lower prices on Amazon EC2 instances usage, regardless of instance family, size, OS, tenancy, or AWS Region.
- Also applies to AWS Fargate and AWS Lambda usage.

### Instance Types
Amazon EC2 provides a wide selection of instance types optimized to fit different use cases.
Instance types comprise varying combinations of CPU, memory, storage, and networking capacity and give you the flexibility to choose the appropriate mix of resources for your applications.
Each instance type includes one or more instance sizes, allowing you to scale your resources to the requirements of your target workload.
The table below helps you to understand some of the various EC2 instance families and their intended use case:
| Family |	Hint |	Purpose/Design |
|--------|-------|-----------------|
| D	| DATA	| Heavy data usage (e.g. file servers, DWs) |
| R	| RAM	| Memory optimized |
| M	| MAIN	| General purpose (e.g. app servers) |
| C	| COMPUTE	| Compute optimized |
| G	| GRAPHICS	| Graphics intensive workloads |
| I	| IOPS	| Storage I/O optimized (e.g. NoSQL, DWs) |
| F	| FAST	| FPGA hardware acceleration for applications |
| T	| CHEAP (think T2)	| Lowest cost (e.g. T2-micro) |
| P	| GPU	| GPU requirements |
| X	| EXTREME RAM	| Heavy memory usage (e.g. SAP HANA, Apache Spark) |
| U	| HIGH MEMORY	| High memory and bare metal performance – use for in memory DBs including | SAP HANA |
| Z	| HGH COMPUTE & MEMORY	| Fast CPU, high memory, and NVMe-based SSDs – use when high overall performance is required |
| H	| HIGH DISK THROUGHPUT	| Up to 16 TB of HDD-based local storage |

### Amazon Elastic Container Service (ECS)
Amazon Elastic Container Service (ECS) is another product in the AWS Compute category. It provides a highly scalable, high performance container management service that supports Docker containers and allows you to easily run applications on a managed cluster of Amazon EC2 instances.
Amazon ECS eliminates the need for you to install, operate, and scale your own cluster management infrastructure.
Using API calls you can launch and stop container-enabled applications, query the complete state of clusters, and access many familiar features like security groups, Elastic Load Balancing, EBS volumes and IAM roles.
Amazon ECS can be used to schedule the placement of containers across clusters based on resource needs and availability requirements.
An Amazon ECS launch type determines the type of infrastructure on which your tasks and services are hosted.
There are two launch types, and the table below describes some of the differences between the two launch types:
| Amazon EC2	| Amazon Fargate |
| - | - |
| You explicitly provision EC2 instances	| The control plane asks for resources and Fargate automatically provisions |
| You’re responsible for upgrading, patching, care of EC2 pool	| Fargate provisions compute as needed |
| You must handle cluster optimization	| Fargate handles cluster optimization |
| More granular control over infrastructure	| Limited control, as infrastructure is automated |

The Elastic container registry (ECR) is a managed AWS Docker registry service for storing, managing, and deploying Docker images.
There is no additional charge for Amazon ECS. You pay for AWS resources (e.g. EC2 instances or EBS volumes) you create to store and run your application.
Amazon ECR is integrated with Amazon EC2 Container Service (ECS).
With Amazon ECR, there are no upfront fees or commitments. You pay only for the amount of data you store in your repositories and data transferred to the Internet.

### AWS Lambda
AWS Lambda is a serverless computing technology that allows you to run code without provisioning or managing servers.
AWS Lambda executes code only when needed and scales automatically.
You pay only for the compute time you consume (you pay nothing when your code is not running).

Benefits of AWS Lambda:
- No servers to manage.
- Continuous scaling.
- Millisecond billing.
- Integrates with almost all other AWS services.

Primary use cases for AWS Lambda:
- Data processing.
- Real-time file processing.
- Real-time stream processing.
- Build serverless backends for web, mobile, IOT, and 3rd party API requests.

### Amazon LightSail
Amazon LightSail Instances
Amazon LightSail is one of the newest services in the AWS Compute suite of products. Amazon LightSail is great for users who do not have deep AWS technical expertise as it makes it very easy to provision compute services.
Amazon LightSail provides developers compute, storage, and networking capacity and capabilities to deploy and manage websites, web applications, and databases in the cloud.
Amazon LightSail includes everything you need to launch your project quickly – a virtual machine, SSD-based storage, data transfer, DNS management, and a static IP.
Amazon LightSail provides preconfigured virtual private servers (instances) that include everything required to deploy and application or create a database.
The underlying infrastructure and operating system is managed by Amazon LightSail.
Best suited to projects that require a few dozen instances or fewer.
Provides a simple management interface.
Good for blogs, websites, web applications, e-commerce etc.
Can deploy load balancers and attach block storage.
Public API.
Limited to 20 Amazon LightSail instances, 5 static IPs, 3 DNS zones, 20 TB block storage, 40 databases, and 5 load balancers per account.
Up to 20 certificates per calendar year.
Can connect to each other and other AWS resources through public Internet and private (VPC peering) networking.
Application templates include WordPress, WordPress Multisite, Drupal, Joomla!, Magento, Redmine, LAMP, Nginx (LEMP), MEAN, Node.js, and more.
Amazon LightSail currently supports 6 Linux or Unix-like distributions: Amazon Linux, CentOS, Debian, FreeBSD, OpenSUSE, and Ubuntu, as well as 2 Windows Server versions: 2012 R2 and 2016.

### Amazon LightSail Databases
Amazon LightSail databases are instances that are dedicated to running databases.
An Amazon LightSail database can contain multiple user-created databases, and you can access it by using the same tools and applications that you use with a stand-alone database.
Amazon LightSail managed databases provide an easy, low maintenance way to store your data in the cloud.
Amazon LightSail manages a range of maintenance activities and security for your database and its underlying infrastructure.
Amazon LightSail automatically backs up your database and allows point in time restore from the past 7 days using the database restore tool.
Amazon LightSail databases support the latest major versions of MySQL. Currently, these versions are 5.6, 5.7, and 8.0 for MySQL.
Amazon LightSail databases are available in Standard and High Availability plans.
High Availability plans add redundancy and durability to your database, by automatically creating standby database in a separate Availability Zone.
Amazon LightSail is very affordable.
Amazon LightSail plans are billed on an on-demand hourly rate, so you pay only for what you use.
For every Amazon LightSail plan you use, we charge you the fixed hourly price, up to the maximum monthly plan cost.

### AWS Elastic Beanstalk
AWS Elastic Beanstalk is the fastest and simplest way to get web applications up and running on AWS.
Developers simply upload their application code, and the service automatically handles all the details such as resource provisioning, load balancing, auto-scaling, and monitoring.
Elastic Beanstalk is ideal if you have a PHP, Java, Python, Ruby, Node.js, .NET, Go, or Docker web application.
Elastic Beanstalk uses core AWS services such as Amazon EC2, Amazon Elastic Container Service (Amazon ECS), Auto Scaling, and Elastic Load Balancing to easily support applications that need to scale to serve millions of users.
![image](https://github.com/nnhung232/AWS-CCP/assets/4153181/1ba3347e-e991-463a-a152-352289482672)

### AWS Batch
AWS Batch enables developers, scientists, and engineers to run hundreds of thousands of batch computing jobs easily and efficiently on AWS.
AWS Batch dynamically provisions the optimal quantity and type of compute resources (e.g., CPU or memory optimized instances) based on the volume and specific resource requirements of the batch jobs submitted.
With AWS Batch, you simply package the code for your batch jobs, specify their dependencies, and submit your batch job using the AWS Management Console, CLIs, or SDKs.
AWS Batch allows you to specify execution parameters and job dependencies, and facilitates integration with a broad range of popular batch computing workflow engines and languages (e.g., Pegasus WMS, Luigi, and AWS Step Functions).
AWS Batch efficiently and dynamically provisions and scales Amazon EC2 and Spot Instances based on the requirements of your jobs. AWS Batch provides default job queues and compute environment definitions that enable you to get started quickly.

## Auto Scaling and Elastic Load Balancing
### Amazon EC2 Auto Scaling
Amazon EC2 Auto Scaling automates the process of launching (scaling out) and terminating (scaling in) Amazon EC2 instances based on the traffic demand for your application.
Auto Scaling helps to ensure that you have the correct number of EC2 instances available to handle the application load.
Amazon EC2 Auto Scaling provides elasticity and scalability.
You create collections of EC2 instances, called an Auto Scaling group (ASG).
You can specify the minimum number of instances in each ASG, and AWS Auto Scaling will ensure the group never goes beneath this size.
You can also specify the maximum number of instances in each ASG, and the group will never go above this size.
A desired capacity can be configured, and AWS Auto Scaling will ensure the group has this number of instances.
You can also specify scaling policies that control when Auto Scaling launches or terminates instances.
Scaling policies determine when, if, and how the ASG scales and shrinks (on-demand/dynamic scaling, cyclic/scheduled scaling).
Scaling Plans define the triggers and when instances should be provisioned/de-provisioned.
A launch configuration is the template used to create new EC2 instances and includes parameters such as instance family, instance type, AMI, key pair, and security groups.
![image](https://github.com/nnhung232/AWS-CCP/assets/4153181/c57940ff-2a6b-4e18-84af-acf610f85e82)

### Amazon Elastic Load Balancing (ELB)
ELB automatically distributes incoming application traffic across multiple targets, such as Amazon EC2 instances, containers, and IP addresses.
ELB can handle the varying load of your application traffic in a single Availability Zone or across multiple Availability Zones.
ELB features high availability, automatic scaling, and robust security necessary to make your applications fault tolerant.

There are four types of Elastic Load Balancer (ELB) on AWS:
- Application Load Balancer (ALB) – layer 7 load balancer that routes connections based on the content of the request.
- Network Load Balancer (NLB) – layer 4 load balancer that routes connections based on IP protocol data.
- Classic Load Balancer (CLB) – this is the oldest of the three and provides basic load balancing at both layer 4 and layer 7 (not on the exam anymore).
- Gateway Load Balancer (GLB) – distributes connections to virtual appliances and scales them up or down (not on the exam).

### Application Load Balancer (ALB)
ALB is best suited for load balancing of HTTP and HTTPS traffic and provides advanced request routing targeted at the delivery of modern application architectures, including microservices and containers.
Operating at the individual request level (Layer 7), Application Load Balancer routes traffic to targets within Amazon Virtual Private Cloud (Amazon VPC) based on the content of the request.

### Network Load Balancer (NLB)
NLB is best suited for load balancing of TCP traffic where extreme performance is required.
Operating at the connection level (Layer 4), Network Load Balancer routes traffic to targets within Amazon Virtual Private Cloud (Amazon VPC) and is capable of handling millions of requests per second while maintaining ultra-low latencies.
Network Load Balancer is also optimized to handle sudden and volatile traffic patterns.
![image](https://github.com/nnhung232/AWS-CCP/assets/4153181/592c8455-c458-446c-b58c-251894a0f29a)


## AWS Database Services
Different Database Types
| Data Store |	When to Use |
| - | - |
| Database on EC2	| - Full control over instance and database <br> - Preferred DB not available under RDS |
| Amazon RDS	| - Need traditional relational database for OLTP <br> - Your data is well-formed and structured <br> - Existing applications requiring RDBMS |
| Amazon DynamoDB	| - Name/value pair data <br> - Unpredictable data structure <br> - In-memory performance with persistence <br> - High I/O needs <br> - Require dynamic scaling |
| Amazon RedShift	| - Data warehouse for large volumes of aggregated data <br> - Primarily OLAP workloads |
| Amazon Neptune	| - Relationships between objects are of high value | 
| Amazon ElastiCache	| - Fast temporary storage for small amounts of data <br> - Highly volatile data (non-persistent) |
| Amazon S3	| - Binary large objects (BLOBs) <br> - Static websites |

### Amazon Relational Database Service (RDS)
Amazon Relational Database Service (Amazon RDS) is a managed service that makes it easy to set up, operate, and scale a relational database in the cloud.
Relational databases are known as Structured Query Language (SQL) databases.
Non-relational databases are known as NoSQL databases.
RDS is an Online Transaction Processing (OLTP) type of database.

RDS features and benefits:
- SQL type of database.
- Can be used to perform complex queries and joins.
- Easy to setup, highly available, fault tolerant, and scalable.
- Used when data is clearly defined.
- Common use cases include online stores and banking systems.

Amazon RDS supports the following database engines:
- SQL Server.
- Oracle.
- MySQL Server.
- PostgreSQL.
- Aurora.
- MariaDB.

Aurora is Amazon’s proprietary database.
RDS is a fully managed service and you do not have access to the underlying EC2 instance (no root access).

The RDS service includes the following:
- Security and patching of the DB instances.
- Automated backup for the DB instances.
- Software updates for the DB engine.
- Easy scaling for storage and compute.
- Multi-AZ option with synchronous replication.
- Automatic failover for Multi-AZ option.
- Read replicas option for read heavy workloads.

A DB instance is a database environment in the cloud with the compute and storage resources you specify.

Encryption:
- You can encrypt your Amazon RDS instances and snapshots at rest by enabling the encryption option for your Amazon RDS DB instance.
- Encryption at rest is supported for all DB types and uses AWS KMS.
- You cannot encrypt an existing DB, you need to create a snapshot, copy it, encrypt the copy, then build an encrypted DB from the snapshot.

DB Subnet Groups:
- A DB subnet group is a collection of subnets (typically private) that you create in a VPC and that you then designate for your DB instances.
- Each DB subnet group should have subnets in at least two Availability Zones in each region.
- It is recommended to configure a subnet group with subnets in each AZ (even for standalone instances).

AWS Charge for:
- DB instance hours (partial hours are charged as full hours).
- Storage GB/month.
- I/O requests/month – for magnetic storage.
- Provisioned IOPS/month – for RDS provisioned IOPS SSD.
- Egress data transfer.
- Backup storage (DB backups and manual snapshots).

Scalability:
- You can only scale RDS up (compute and storage).
- You cannot decrease the allocated storage for an RDS instance.
- You can scale storage and change the storage type for all DB engines except MS SQL.

RDS provides multi-AZ for disaster recovery which provides fault tolerance across availability zones:
- Multi-AZ RDS creates a replica in another AZ and synchronously replicates to it (DR only).
- There is an option to choose multi-AZ during the launch wizard.
- AWS recommends the use of provisioned IOPS storage for multi-AZ RDS DB instances.
- Each AZ runs on its own physically distinct, independent infrastructure, and is engineered to be highly reliable.
- You cannot choose which AZ in the region will be chosen to create the standby DB instance.

Read Replicas – provide improved performance for reads:
- Read replicas are used for read heavy DBs and replication is asynchronous.
- Read replicas are for workload sharing and offloading.
- Read replicas provide read-only DR.
- Read replicas are created from a snapshot of the master instance.
- Must have automated backups enabled on the primary (retention period > 0).

![image](https://github.com/nnhung232/AWS-CCP/assets/4153181/0dc5dda4-4ce3-4d43-b592-a495fb99ea4e)

### Amazon DynamoDB
Amazon DynamoDB is a fully managed NoSQL database service that provides fast and predictable performance with seamless scalability.

Dynamo DB features and benefits:
- NoSQL type of database (non-relational).
- Fast, highly available, and fully managed.
- Used when data is fluid and can change.
- Common use cases include social networks and web analytics.

Push button scaling means that you can scale the DB at any time without incurring downtime.
SSD based and uses limited indexing on attributes for performance.
DynamoDB is a Web service that uses HTTP over SSL (HTTPS) as a transport and JSON as a message serialization format.
Amazon DynamoDB stores three geographically distributed replicas of each table to enable high availability and data durability.
Data is synchronously replicated across 3 facilities (AZs) in a region.

Cross-region replication allows you to replicate across regions:
- Amazon DynamoDB global tables provides a fully managed solution for deploying a multi-region, multi-master database.
- When you create a global table, you specify the AWS regions where you want the table to be available.
- DynamoDB performs all the necessary tasks to create identical tables in these regions and propagate ongoing data changes to all of them.

Provides low read and write latency.
Scale storage and throughput up or down as needed without code changes or downtime.
DynamoDB is schema-less.
DynamoDB can be used for storing session state.
Provides two read models.

Eventually consistent reads (Default):
- The eventual consistency option maximizes your read throughput (best read performance).
- An eventually consistent read might not reflect the results of a recently completed write.
- Consistency across all copies reached within 1 second.

Strongly consistent reads:
- A strongly consistent read returns a result that reflects all writes that received a successful response prior to the read (faster consistency).

Amazon DynamoDB Accelerator (DAX) is a fully managed, highly available, in-memory cache for DynamoDB that delivers up to a 10x performance improvement – from milliseconds to microseconds – even at millions of requests per second.

### Amazon RedShift
Amazon Redshift is a fast, fully managed data warehouse that makes it simple and cost-effective to analyze all your data using standard SQL and existing Business Intelligence (BI) tools.
RedShift is a SQL based data warehouse used for analytics applications.
RedShift is a relational database that is used for Online Analytics Processing (OLAP) use cases.
RedShift is used for running complex analytic queries against petabytes of structured data, using sophisticated query optimization, columnar storage on high-performance local disks, and massively parallel query execution.
RedShift is ideal for processing large amounts of data for business intelligence.
RedShift is 10x faster than a traditional SQL DB.

RedShift uses columnar data storage:
- Data is stored sequentially in columns instead of rows.
- Columnar based DB is ideal for data warehousing and analytics.
- Requires fewer I/Os which greatly enhances performance.

RedShift provides advanced compression:
- Data is stored sequentially in columns which allows for much better performance and less storage space.
- RedShift automatically selects the compression scheme.

RedShift uses replication and continuous backups to enhance availability and improve durability and can automatically recover from component and node failures.

RedShift always keeps three copies of your data:
- The original.
- A replica on compute nodes (within the cluster).
- A backup copy on S3.

RedShift provides continuous/incremental backups:
- Multiple copies within a cluster.
- Continuous and incremental backups to S3.
- Continuous and incremental backups across regions.
- Streaming restore.

RedShift provides fault tolerance for the following failures:
- Disk failures.
- Nodes failures.
- Network failures.
- AZ/region level disasters.

### Amazon ElastiCache
ElastiCache is a web service that makes it easy to deploy and run Memcached or Redis protocol-compliant server nodes in the cloud.
The in-memory caching provided by ElastiCache can be used to significantly improve latency and throughput for many read-heavy application workloads or compute-intensive workloads.
Best for scenarios where the DB load is based on Online Analytics Processing (OLAP) transactions.

The use cases for ElastiCache:
- Web session store:	In cases with load-balanced web servers, store web session information in Redis so if a server is lost, the session info is not lost, and another web server can pick it up
- Database caching:	Use Memcached in front of AWS RDS to cache popular queries to offload work from RDS and return results faster to users
- Leaderboards:	Use Redis to provide a live leaderboard for millions of users of your mobile app
- Streaming data dashboards:	Provide a landing spot for streaming sensor data on the factory floor, providing live real-time dashboard display

ElastiCache EC2 nodes cannot be accessed from the Internet, nor can they be accessed by EC2 instances in other VPCs.
Can be on-demand or reserved instances too (but not Spot instances).
ElastiCache can be used for storing session state.

There are two types of ElastiCache engine:
- Memcached – simplest model, can run large nodes with multiple cores/threads, can be scaled in and out, can cache objects such as DBs.
- Redis – complex model, supports encryption, master / slave replication, cross AZ (HA), automatic failover and backup/restore.

![image](https://github.com/nnhung232/AWS-CCP/assets/4153181/bccbaff0-ef6a-4691-9bdb-0fca8e497e0e)

### Amazon EMR
Amazon EMR is a web service that enables businesses, researchers, data analysts, and developers to process vast amounts of data easily and cost-effectively.
EMR utilizes a hosted Hadoop framework running on Amazon EC2 and Amazon S3.
Managed Hadoop framework for processing huge amounts of data.
Also support Apache Spark, HBase, Presto and Flink.
Most commonly used for log analysis, financial analysis, or extract, translate and loading (ETL) activities.

## AWS Application Integration Services
| Service	| What it does	| Example use cases |
| - | - | - |
| Simple Queue Service (SQS)	| Messaging queue; store and forward patterns	| Building distributed / decoupled applications |
| Simple Notification Service (SNS)	| Set up, operate, and send notifications from the cloud	| Send email notification when CloudWatch alarm is triggered |
| Step Functions	| Out-of-the-box coordination of AWS service components with visual workflow	| Order processing workflow
| Simple Workflow Service (SWF)	| Need to support external processes or specialized execution logic	| Human-enabled workflows like an order fulfilment system or for procedural requests |
| Amazon MQ	| Message broker service for Apache Active MQ and RabbitMQ	| Need a message queue that supports industry standard APIs and protocols; migrate queues to AWS |

### Amazon Simple Notification Service 
Amazon Simple Notification Service (Amazon SNS) is a web service that makes it easy to set up, operate, and send notifications from the cloud.
Amazon SNS is used for building and integrating loosely-coupled, distributed applications.
SNS provides instantaneous, push-based delivery (no polling).

SNS concepts:
- Topics – how you label and group different endpoints that you send messages to.
- Subscriptions – the endpoints that a topic sends messages to.
- Publishers – the person/alarm/event that gives SNS the message that needs to be sent.
![image](https://github.com/nnhung232/AWS-CCP/assets/4153181/c8d7ae2e-60b7-4ca5-a2a6-039922d1a055)
SNS usage:
- Send automated or manual notifications.
- Send notification to email, mobile (SMS), SQS, and HTTP endpoints.
- Closely integrated with other AWS services such as CloudWatch so that alarms, events, and actions in your AWS account can trigger notifications.

Uses simple APIs and easy integration with applications.
Flexible message delivery is provided over multiple transport protocols.
Offered under an inexpensive, pay-as-you-go model with no up-front costs.
The web-based AWS Management Console offers the simplicity of a point-and-click interface.
Data type is JSON.
SNS supports a wide variety of needs including event notification, monitoring applications, workflow systems, time-sensitive information updates, mobile applications, and any other application that generates or consumes notifications.

SNS Subscribers:
- HTTP.
- HTTPS.
- Email.
- Email-JSON.
- SQS.
- Application.
- Lambda.

SNS supports notifications over multiple transport protocols:
- HTTP/HTTPS – subscribers specify a URL as part of the subscription registration.
- Email/Email-JSON – messages are sent to registered addresses as email (text-based or JSON-object).
- SQS – users can specify an SQS standard queue as the endpoint.
- SMS – messages are sent to registered phone numbers as SMS text messages.

Topic names are limited to 256 characters.
SNS supports CloudTrail auditing for authenticated calls.
SNS provides durable storage of all messages that it receives (across multiple AZs).

### Amazon Simple Queue Service (Amazon SQS)
Amazon Simple Queue Service (SQS) is a distributed queue system.
Amazon SQS enables you to send, store, and receive messages between software components.
An Amazon SQS queue is a temporary repository for messages that are awaiting processing.
The SQS queue acts as a buffer between the component producing and saving data, and the component receiving the data for processing.
![image](https://github.com/nnhung232/AWS-CCP/assets/4153181/0ac853c1-2a98-4812-bf37-ff5e6cc9ee99)
This is known as decoupling / loose coupling and helps to enable elasticity for your application.
Amazon SQS is pull-based, not push-based (like Amazon SNS).

### Amazon Simple Workflow Service (Amazon SWF)
Amazon Simple Workflow Service (SWF) is a web service that makes it easy to coordinate work across distributed application components.
Amazon SWF is used for processing background jobs that have parallel or sequential steps.
You can think of Amazon SWF as a fully managed state tracker and task coordinator.
Use Amazon SWF if your app’s steps take more than 500 milliseconds to complete, you need to track the state of processing, or you need to recover or retry if a task fails.
With SWF you can create distributed asynchronous systems as workflows.
Tracks the state of your workflow which you interact and update via API.
Best suited for human-enabled workflows like an order fulfilment system or for procedural requests.

AWS recommends that for new applications customers consider AWS Step Functions instead of SWF.

### Amazon MQ
Amazon MQ is a managed message broker service for ActiveMQ.
Amazon MQ supports industry-standard APIs and protocols so you can migrate messaging and applications without rewriting code.
Amazon MQ provides cost-efficient and flexible messaging capacity.
Amazon MQ manages the administration and maintenance of ActiveMQ brokers and automatically provisions infrastructure for high availability.

### AWS Step Functions
AWS Step Functions can be used to coordinate the components of distributed applications as a series of steps in a visual workflow.
You can quickly build and run state machines to execute the steps of your application in a reliable and scalable fashion.

How it works:
  1. Define the steps of your workflow in the JSON-based Amazon States Language. The visual console automatically graphs each step in the order of execution.
  2. Start an execution to visualize and verify the steps of your application are operating as intended. The console highlights the real-time status of each step and provides a detailed history of every execution.
  3. AWS Step Functions operates and scales the steps of your application and underlying compute for you to help ensure your application executes reliably under increasing demand.
It is a managed workflow and orchestration platform.

## AWS Machine Learning Services

### AWS Rekognition
Add image and video analysis to your applications.
Identify objects, people, text, scenes, and activities in images and videos.
Processes videos stored in an Amazon S3 bucket.
Publish completion status to Amazon SNS Topic.
![image](https://github.com/nnhung232/AWS-CCP/assets/4153181/abf2c84f-e4ec-4844-9f39-feae2022728c)

### Amazon Transcribe
Add speech to text capabilities to applications.
Recorded speech can be converted to text before it can be used in applications.
Uses a deep learning process called automatic speech recognition (ASR) to convert speech to text quickly and accurately.

### Amazon Translate
Neural machine translation service that delivers fast, high-quality, and affordable language translation.
Uses deep learning models to deliver more accurate and more natural sounding translation.
Localize content such as websites and applications for your diverse users.

### Amazon Textract
Automatically extract printed text, handwriting, and data from any document.

Features:
- Optical character recognition (OCR).
- Identifies relationships, structure, and text.
- Uses AI to extract text and structured data.
- Recognizes handwriting as well as printed text.
- Can extract from documents such as PDFs, images, forms, and tables.
- Understands context. For example know what data to extract from a receipt or invoice.

### Amazon SageMaker
Helps data scientists and developers to prepare, build, train, and deploy high-quality machine learning (ML) models.

ML development activities including:
- Data preparation.
- Feature engineering.
- Statistical bias detection.
- Auto-ML.
- Training and tuning.
- Hosting.
- Monitoring.
- Workflows.

### Amazon Comprehend
Natural-language processing (NLP) service.
Uses machine learning to uncover information in unstructured data.
Can identify critical elements in data, including references to language, people, and places, and the text files can be categorized by relevant topics.
In real time, you can automatically and accurately detect customer sentiment in your content.

### Amazon Lex
Conversational AI for Chatbots.
Build conversational interfaces into any application using voice and text.
Build bots to increase contact center productivity, automate simple tasks, and drive operational efficiencies across the enterprise.

### Amazon Polly
Turns text into lifelike speech.
Create applications that talk and build entirely new categories of speech-enabled products.
Text-to-Speech (TTS) service uses advanced deep learning technologies to synthesize natural sounding human speech.

### Amazon Forecast
Time-series forecasting service.
Uses ML and is built for business metrics analysis.

### Amazon DevOps Guru
Cloud operations service for improving application operational performance and availability.
Detect behaviors that deviate from normal operating patterns.

Benefits:
- Automatically detect operational issues.
- Resolve issues with ML-powered insights.
- Elastically scale operational analytics.
- Uses ML to reduce alarm noise.


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
AWS works on a pay as you go model in which you only pay for what you use, when you are using it.
If you turn off resources, you don’t pay for them (you may pay for consumed storage).
There are no upfront charges, and you stop paying for a service when you stop using it.
Aside from EC2 reserved instances you are not locked into long term contracts and can terminate whenever you choose to.
Volume discounts are available so the more you use a service the cheaper it gets (per unit used).
There are no termination fees.
The three fundamental drivers of cost with AWS are: compute, storage, and outbound data transfer.
In most cases, there is no charge for inbound data transfer or for data transfer between other AWS services within the same region (there are some exceptions).
Outbound data transfer is aggregated across services and then charged at the outbound data transfer rate.
Free tier allows you to run certain resources for free.
Free tier includes offers that expire after 12 months and offers that never expire.

Pricing policies include:
- Pay as you go.
- Pay less when you reserve.
- Pay even less per unit when using more.
- Pay even less as AWS grows.
- Custom pricing (enterprise customers only).

Free services include:
- Amazon VPC.
- Elastic Beanstalk (but not the resources created).
- CloudFormation (but not the resources created).
- Identity Access Management (IAM).
- Auto Scaling (but not the resources created).
- OpsWorks.
- Consolidated Billing.

Fundamentally charges include:
- Compute.
- Storage.
- Data out.

### Amazon EC2 pricing
EC2 pricing is based on:
- Clock hours of server uptime.
- Instance configuration.
- Instance type.
- Number of instances.
- Load balancing.
- Detailed monitoring.
- Auto Scaling (resources created).
- Elastic IP addresses (charged if allocated but not used).
- Operating systems and software packages.

There are several pricing model for AWS services, these include:

On Demand:
- Means you pay for compute or database capacity with no long-term commitments of upfront payments.
- You pay for the computer capacity per hour or per second (Linux only, and applies to On-Demand, Reserved and Spot instances).
- Recommended for users who prefer low cost and flexibility without upfront payment or long-term commitments.
- Good for applications with short-term, spiky, or unpredictable workloads that cannot be interrupted.

Dedicated Hosts:
- A dedicated host is an EC2 servers dedicated to a single customer.
- Runs in your VPC.
- Good for when you want to leverage existing server-bound software licenses such as Windows Server, SQL Server, and SUSE Linux Enterprise Server.
- Also good for meeting compliance requirements.

Dedicated Instances:
- Dedicated Instances are Amazon EC2 instances that run in a VPC on hardware that’s dedicated to a single customer.
- Dedicated instances are physically isolated at the host hardware level from instances that belong to other AWS accounts.
- Dedicated instances may share hardware with other instances from the same AWS account that are not Dedicated instances.

Spot Instances:
- Purchase spare computing capacity with no upfront commitment at discounted hourly rates.
- Provides up to 90% off the On-Demand price.
- Recommended for applications that have flexible start and end times, applications that are only feasible at very low compute prices, and users with urgent computing needs for a lot of additional capacity.
- In the old model Spot instances were terminated because of higher competing bids, in the new model this does not happen, but instances still may be terminated (with a 2-minute warning) when EC2 needs the capacity back – note: the exam may not be updated to reflect this yet.

![image](https://github.com/nnhung232/AWS-CCP/assets/4153181/3e0e180d-43ef-4f12-992c-36a7b230669a)

Savings Plans:
- Commitment to a consistent amount of usage (EC2 + Fargate + Lambda); Pay by $/hour; 1 or 3-year commitment.

Reservations:
- Reserved instances provide significant discounts, up to 75% compared to On-Demand pricing, by paying for capacity ahead of time.
- Provide a capacity reservation when applied to a specific Availability Zone.
- Good for applications that have predictable usage, that need reserved capacity, and for customers who can commit to a 1 or 3-year term.

Reservations apply to various services, including:
- Amazon EC2 Reserved Instances.
- Amazon DynamoDB Reserved Capacity.
- Amazon ElastiCache Reserved Nodes.
- Amazon RDS Reserved Instances.
- Amazon RedShift Reserved Instances.

Reservation options include no upfront, partial upfront and all upfront.
Reservation terms are 1 or 3 years.

### Amazon Simple Storage Service (S3) Pricing
Storage pricing is determined by:
- Storage class – e.g., Standard or IA.
- Storage quantity – data volume stored in your buckets on a per GB basis.
- Number of requests – the number and type of requests, e.g., GET, PUT, POST, LIST, COPY.
- Lifecycle transitions requests – moving data between storage classes.
- Data transfer – data transferred out of an S3 region is charged.

Amazon Glacier pricing
- Extremely low cost and you pay only for what you need with no commitments of upfront fees.
- Charged for requests and data transferred out of Glacier.
- “Amazon Glacier Select” pricing allows queries to run directly on data stored on Glacier without having to retrieve the archive. Priced on amount of data scanned, returned, and number of requests initiated.

AWS Snowball Pricing
Pay a service fee per data transfer job and the cost of shipping the appliance.
Each job allows use of Snowball appliance for 10 days onsite for free.
Data transfer in to AWS is free and outbound is charged (per region pricing).
Amazon Relational Database Service (RDS) Pricing

RDS pricing is determined by:
- Clock hours of server uptime – amount of time the DB instance is running.
- Database characteristics – e.g. database engine, size, and memory class.
- Database purchase type – e.g. On-Demand, Reserved.
- Number of database instances.
- Provisioned storage – backup is included up to 100% of the size of the DB. After the DB is terminated backup storage is charged per GB per month.
- Additional storage – the amount of storage in addition to the provisioned storage is charged per GB per month.
- Requests – the number of input and output requests to the DB.
- Deployment type – single AZ or multi-AZ.
- Data transfer – inbound is free, outbound data transfer costs are tiered.
- Reserved Instances – RDS RIs can be purchased with No Upfront, Partial Upfront, or All Upfront terms. Available for Aurora, MySQL, MariaDB, Oracle and SQL Server.

### Amazon CloudFront Pricing
CloudFront pricing is determined by:
- Traffic distribution – data transfer and request pricing, varies across regions, and is based on the edge location from which the content is served.
- Requests – the number and type of requests (HTTP or HTTPS) and the geographic region in which they are made.
- Data transfer out – quantity of data transferred out of CloudFront edge locations.
There are additional chargeable items such as invalidation requests, field-level encryption requests, and custom SSL certificates.

### AWS Lambda Pricing
Pay only for what you use and charged based on the number of requests for functions and the time it takes to execute the code.
Price is dependent on the amount of memory allocated to the function.
Amazon Elastic Block Store (EBS) Pricing

Pricing is based on three factors:
- Volumes – volume storage for all EBS volumes type is charged by the amount of GB provisioned per month.
- Snapshots – based on the amount of space consumed by snapshots in S3. Copying snapshots is charged on the amount of data copied across regions.
- Data transfer – inbound data transfer is free, outbound data transfer charges are tiered.

### Amazon DynamoDB Pricing
Charged based on:
- Provisioned throughput (write).
- Provisioned throughput (read).
- Indexed data storage.
- Data transfer – no charge for data transfer between DynamoDB and other AWS services within the same region, across regions is charged on both sides of the transfer.
- Global tables – charged based on the resources associated with each replica of the table (replicated write capacity units, or rWCUs).
- Reserved Capacity – option available for a one-time upfront fee and commitment to paying a minimum usage level at specific hourly rates for the duration of the term. Additional throughput is charged at standard rates.

On-demand capacity mode:
- Charged for reads and writes
- No need to specify how much capacity is required
- Good for unpredictable workloads

Provisioned capacity mode:
- Specify number of reads and writes per second
- Can use Auto Scaling
- Good for predictable workloads
- Consistent traffic or gradual changes

### AWS Support Plans
There are four AWS support plans available:
- Basic – billing and account support only (access to forums only).
- Developer – business hours support via email.
- Business – 24×7 email, chat, and phone support.
- Enterprise – 24×7 email, chat, and phone support.
Enterprise support comes with a Technical Account Manager (TAM).
Developer allows one person to open unlimited cases.
Business and Enterprise allow unlimited contacts to open unlimited cases.

![image](https://github.com/nnhung232/AWS-CCP/assets/4153181/176759d4-9e67-469f-bb58-1472c3d1df1c)
![image](https://github.com/nnhung232/AWS-CCP/assets/4153181/99249a64-6cbc-418f-8b79-851197a25869)

### Resource Groups and Tagging
Tags are key / value pairs that can be attached to AWS resources.
Tags contain metadata (data about data).
Tags can sometimes be inherited – e.g. resources created by Auto Scaling, CloudFormation or Elastic Beanstalk.
Resource groups make it easy to group resources using the tags that are assigned to them. You can group resources that share one or more tags.

Resource groups contain general information, such as:
- Region.
- Name.
- Health Checks.

And specific information, such as:
- Public & private IP addresses (for EC2).
- Port configurations (for ELB).
- Database engine (for RDS).

### AWS Organizations and Consolidated Billing
AWS organizations allows you to consolidate multiple AWS accounts into an organization that you create and centrally manage.

Available in two feature sets:
- Consolidated Billing.
- All features.

Includes root accounts and organizational units.
Policies are applied to root accounts or OUs.

Consolidated billing includes:
- Paying Account – independent and cannot access resources of other accounts.
- Linked Accounts – all linked accounts are independent.

Consolidated billing has the following benefits:
- One bill – You get one bill for multiple accounts.
- Easy tracking – You can track the charges across multiple accounts and download the combined cost and usage data.
- Combined usage – You can combine the usage across all accounts in the organization to share the volume pricing discounts and Reserved Instance discounts. This can result in a lower charge for your project, department, or company than with individual standalone accounts.
- No extra fee – Consolidated billing is offered at no additional cost.

Limit of 20 linked accounts (by default).
One bill for multiple AWS accounts.
Easy to track charges and allocate costs.
Volume pricing discounts can be applied to resources.
Billing alerts enabled on the Paying account include data for all Linked accounts (or can be created per Linked account).
Consolidated billing allows you to get volume discounts on all your accounts.
Unused reserved instances (RIs) for EC2 are applied across the group.
CloudTrail is on a per account basis and per region basis but can be aggregated into a single bucket in the paying account.

Best practices:
- Always enable multi-factor authentication (MFA) on the root account.
- Always use a strong and complex password on the root account.
- The Paying account should be used for billing purposes only. Do not deploy resources into the Paying account.

### AWS Quick Starts
Quick Starts are built by AWS architects and partners to help you deploy popular solutions on AWS, based on AWS best practices for security and high availability.
These reference deployments implement key technologies automatically on the AWS Cloud, often with a single click and in less than an hour.
Leverages CloudFormation.

AWS Cost Calculators and Tools
- AWS Cost Explorer – enables you to visualize your usage patterns over time and to identify your underlying cost drivers.
- AWS Pricing Calculator – create cost estimates to suit your AWS use cases.

### AWS Cost Explorer
The AWS Cost Explorer is a free tool that allows you to view charts of your costs.
You can view cost data for the past 13 months and forecast how much you are likely to spend over the next three months.
Cost Explorer can be used to discover patterns in how much you spend on AWS resources over time and to identify cost problem areas.
Cost Explorer can help you to identify service usage statistics such as:
- Which services you use the most.
- View metrics for which AZ has the most traffic.
- Which linked account is used the most.

### AWS Pricing Calculator
AWS Pricing Calculator is a web-based service that you can use to create cost estimates to suit your AWS use cases.
AWS Pricing Calculator is useful both for people who have never used AWS and for those who want to reorganize or expand their usage.
AWS Pricing Calculator allows you to explore AWS services based on your use cases and create a cost estimate.

### AWS Cost & Usage Report
Publish AWS billing reports to an Amazon S3 bucket.

Reports break down costs by:
- Hour, day, month, product, product resource, tags.

Can update the report up to three times a day.
Create, retrieve, and delete your reports using the AWS CUR API Reference.

### AWS Price List API
Query the prices of AWS services.
Price List Service API (AKA the Query API) – query with JSON.
AWS Price List API (AKA the Bulk API) – query with HTML.
Alerts via Amazon SNS when prices change.

### AWS Budgets
Used to track cost, usage, or coverage and utilization for your Reserved Instances and Savings Plans, across multiple dimensions, such as service, or Cost Categories.
Alerting through event-driven alert notifications for when actual or forecasted cost or usage exceeds your budget limit, or when your RI and Savings Plans’ coverage or utilization drops below your threshold.
Create annual, quarterly, monthly, or even daily budgets depending on your business needs.
