# AWS Certified Cloud Practitioner Official Practice Question Set (CLF-CO2-English)

#### A company is hosting a static website from a single Amazon S3 bucket.  Which AWS service will achieve lower latency and high transfer speeds?
- [ ] : Elastic Beanstalk is a service to deploy and scale web applications and services developed with common programming languages on automatically deployed infrastructure with capacity management, load balancing, auto scaling, and monitoring. Elastic Beanstalk makes it easier to provision and support an application. Elastic Beanstalk does not reduce website latency.
- [ ] : DAX is used to reduce response times from a DynamoDB table from single-digit milliseconds to microseconds. DynamoDB tables cannot host static websites.
- [ ] : DNS web service. 
- [x] : CloudFront is a web service that speeds up the distribution of your static and dynamic web content, such as .html, .css, .js, and image files, to your users. Content is cached in edge locations. Content that is repeatedly accessed can be served from the edge locations instead of the source S3 bucket.

#### A company is moving all of their development activities to AWS. The company wants a solution to store and manage their developers' source code. Which AWS coding service will meet this requirement?
- [ ] :  CodeArtifact is a managed artifact repository service that stores and shares software that is ready for deployment. CodeArtifact is not a source code management service.
- [ ] : CodeBuild is a service that helps users to automatically compile source code, run unit tests, and produce software packages that are ready for deployment. CodeBuild is not a code management service.
- [ ] : CodePipeline is a service that manages the movement of code between the individual services. CodePipeline is not a source code storage service.
- [x] : CodeCommit is a source code version control service. CodeCommit helps users store and manage developers' source code in AWS.

#### Which credential components are required to gain programmatic access to an AWS account? (Select TWO.)
- [x] : Programmatic access requires an access key ID and a secret access key that can be assigned to an AWS user.
- [ ] : A primary key is a feature used in **database management**. It does not grant AWS account access.
- [x] : Programmatic access requires an access key ID and a secret access key that can be assigned to an AWS user.
- [ ] : A user ID is used for **IAM security credentials**, but not for programmatic access.
- [ ] : A secondary key is a feature used in **database management**. It does not grant AWS account access.

> [!NOTE]
> Programmatic access 授予程式設計存取權
> 
> 使用者想要與 AWS Management Console 之外的 AWS 互動，則需要程式設計存取權。

#### What is the MINIMUM AWS Support plan that provides technical support through phone calls?
- [ ] : 
- [ ] :
- [ ] :
- [x] :

#### Which AWS service identifies security groups that allow unrestricted access to a user's AWS resources?
- [x] : Trusted Advisor checks security groups for rules that allow unrestricted access to a resource. Unrestricted access increases opportunities for malicious activity, such as hacking, denial-of-service attacks, or loss of data. 
- [ ] : AWS Config **continuously monitors and records changes** to your AWS resources, but it does not identify security groups that allow unrestricted access.
- [ ] : CloudWatch is a monitoring service that collects and tracks metrics for AWS resources. It does not identify security groups that allow unrestricted access.
- [ ] : CloudTrail provides an audit record of API calls. It does not identify security groups that allow unrestricted access.

#### Which tasks are the customer's responsibility according to the AWS shared responsibility model? (Select TWO.)
- [ ] : AWS provides Lambda as a service. The customer does not have to patch the operating system.
- [ ] :  AWS provides Amazon RDS as a service. AWS manages patches for the Amazon RDS engine. The customer can choose a time window to install patches.
- [ ] : AWS does not allow access to data centers. A customer can take a virtual tour of a data center to understand the security measures and controls. Customers cannot visit data centers in person.
- [x] : AWS provides AWS Identity and Access Management (IAM) as a service. The customer defines IAM users and the access policies that apply to those users
- [x] : The customer determines access permissions to S3 buckets that the customer owns.  

#### A company wants to create a learning application for students. The learning application must give students the option to choose a button to have the text read out loud to them. Which AWS machine learning service will meet this requirement?
- [ ] : Amazon Transcribe is a service that uses machine learning to convert **audio data to text**. 
- [x] : Amazon Polly is a machine learning service that converts **text to speech**.
- [ ] : Amazon Translate is a machine learning language translation service.
- [ ] : Amazon Textract is a machine learning service that can extract text from scanned documents.

#### What are benefits of using the AWS Cloud for companies with customers in many countries around the world? (Select TWO.)
- [x] : The use of Regions around the world will improve an application's global performance and reduce latency for users.
- [ ] : Amazon Translate does not provide automatic translation of third-party website interfaces.
- [x] 
- [ ] : Amazon Comprehend is a natural language processing (NLP) service that uses machine learning to find insights and relationships in text. Amazon Comprehend does not translate text.
- [ ] : A load balancer accepts incoming traffic from clients and routes requests to its registered targets (such as EC2 instances) in one or more Availability Zones. 

#### A user deploys an Amazon RDS DB instance in multiple Availability Zones. This strategy involves which pillar of the AWS Well-Architected Framework?
- [ ] 
- [x] 
- [ ] 
- [ ] 

#### A company needs to monitor and receive alerts about AWS Management Console sign-in events that involve the AWS account root user. Which AWS service can the company use to meet these requirements?
- [x] : CloudWatch monitors your AWS resources and the applications that you run on AWS in real time. You can use CloudWatch with AWS CloudTrail to monitor and receive alerts about console sign-in events that involve the AWS account root user.
- [ ] : use AWS Config to assess, audit, and evaluate the configurations of your AWS resources.
- [ ] : Trusted Advisor for real-time guidance to help you provision your resources according to AWS best practices.
- [ ] :

#### A company wants to establish a consistent and private connection from the company's on-premises data center to the AWS Cloud. Which AWS service will meet these requirements?
- [ ] :
- [ ] :
- [x] :
- [ ] :

#### A user needs to automatically discover, classify, and protect sensitive data stored in Amazon S3. Which AWS service can meet these requirements?
- [ ] : Amazon Inspector is an automated security assessment service that helps improve the security and compliance of applications deployed on Amazon EC2 instances. 
- [x] : **Macie is an automated security assessment service that helps improve the security and compliance of applications deployed on AWS.**
- [ ] : GuardDuty is a threat detection service that continuously monitors for malicious activity and unauthorized behavior to protect your AWS accounts and workloads.
- [ ] : Secrets Manager helps you protect secrets needed to access your applications, services, and IT resources. 

#### How does AWS charge for AWS Lambda usage once the free tier has been exceeded? (Select TWO.)
- [x] :
- [ ] :
- [x] :
- [ ] :
- [ ] :

#### A company requires a relational database on AWS that records new customer orders from a website. Which AWS service or feature will meet this requirement?
- [ ] : improves the performance of your users’ network traffic by up to 60%.
- [ ] : NoSQL database 
- [x] : Aurora is a MySQL- and PostgreSQL-compatible relational database built for the cloud. Aurora combines the performance and availability of traditional enterprise databases with the simplicity and cost-effectiveness of open source databases.
- [ ] : Amazon EBS by itself is not a relational database. You can use Amazon EBS with Amazon EC2 for both throughput- and transaction-intensive workloads at any scale.

#### A company has an on-premises Linux-based server with an Oracle database that runs on it. The company wants to migrate the database server to run on an Amazon EC2 instance in AWS. Which service should the company use to complete the migration?
- [ ] :  AWS DMS can be used to migrate data from an on-premises **database to a database** in AWS. However, AWS DMS does not migrate the actual server to an EC2 instance.
- [ ] :  Migration Hub is a service that **helps plan and track application migrations**. Migration Hub does not perform system migrations.
- [x] : AWS MGN is an automated lift-and-shift solution. This solution can migrate physical servers and any databases or applications that run on them to EC2 instances in AWS.
- [ ] : Application Discovery Service collects information about the usage and configuration of on-premises servers to help plan a migration to AWS. Application Discovery Service does not actually perform migration operations.

#### What are the advantages of deploying an application with Amazon EC2 instances in multiple Availability Zones? (Select TWO.)
- [x] :
- [ ] :
- [ ] : The best option to serve users with low latency across Regions is to launch another EC2 instance **in the second Region** that is closer to the user's location.
- [x] : If you host all your instances in a single location that is affected by a failure, none of your instances would be available. Availability Zones are designed for physical redundancy and to provide resilience with uninterrupted performance.
- [ ] : two EC2 instances that run in the same Availability Zone or in different Availability Zones will not change the overall load of the application.

#### Which AWS service allows customers to purchase unused Amazon EC2 capacity at an often discounted rate?
- [ ] : Reserved Instances reserve some capacity for your use at any time. Reserved Instances can sometimes give you a discount. However, this **capacity is not unused capacity**.
- [ ] : On-Demand Instances are the **default purchase option** and are immediately available. On-Demand Instances are not discounted.
- [ ] : Dedicated Instances run in VPCs on hardware dedicated to that individual customer and **are often used** when there are licensing or compliance constraints. Dedicated Instances are not discounted.
- [x] :

#### A company requires an encrypted connection between the company's on-premises servers and AWS. The connection must use the company's existing internet connection. Which solution will meet these requirements?
- [ ] : AWS Direct Connect 透過標準乙太網路光纖纜線，將您的內部網路連結至某個 AWS Direct Connect 位置。纜線的一端連接到您的路由器，而另一端連接到 AWS Direct Connect 路由器。
- [ ] : Amazon Connect is an omnichannel cloud contact center. Amazon Connect helps you provide customer service at a low cost. Amazon Connect uses an omnichannel design to provide a seamless experience across voice and chat for your customers and agents. Amazon Connect does not provide a network connection.
- [ ] :
- [x] : Site-to-Site VPN creates an encrypted network path between your on-premises network and your AWS Cloud network. This connection between your on-premises network and your AWS Cloud network uses the internet. 

#### Each department within a company has its own independent AWS account and its own payment method. The company needs to centralize departmental governance and consolidate payments. How can the company achieve these objectives by using AWS services or features?
- [ ] : AWS Cloud Map creates and maintains a map of backend services. 
- [x] : Organizations provides centralized governance and billing for an AWS environment, including multiple accounts.
- [ ] : OpsCenter provides a central location for IT professionals to **view, investigate, and resolve operational work items**.
- [ ] : This solution consolidates the billing in a report, but it will work only for the **individual accounts** (without cross-account billing).