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

## AWS CloudTrail
## AWS Resource for Security Support
### Amazon Inspector
### AWS Report Abuse

# Technology
## Deployment and Operating in the AWS
### On premise & Hybrid
- Snowball
- Storage Gateway
- DNS


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

## AWS Direct Connect (DX)
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

## AWS Global Accelerator
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
