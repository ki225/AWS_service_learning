## Design Secure Architectures
### Q1
A reporting application runs on Amazon EC2 instances behind an Application Load Balancer. The instances run in an Amazon EC2 Auto Scaling group across multiple Availability Zones. For complex reports, the application can take up to 15 minutes to respond to a request. A solutions architect is concerned that users will receive HTTP 5xx errors if a report request is in process during a scale-in event.

What should the solutions architect do to ensure that user requests will be completed before instances are terminated?

<img src="img/mock-SAA-C03-01/s1.png">


### A1
- [ ] : Incorrect. If an EC2 instance were removed from the target group during a scale-in process, the EC2 instance would fail (or would be unhealthy if it were checked). An Application Load Balancer would stop routing requests to that target and would choose a new healthy target.
  - see [Sticky Sessions for Your Application Load Balancer](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/sticky-sessions.html)
- [ ] : Incorrect. An increase of the instance size likely would increase the speed of processing. However, this solution does not directly ensure that instances that process a request are unaffected by scale-in actions. A more suitable solution would be to use deregistration delay.
  -  [see Deregistration Delay.](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-target-groups.html#deregistration-delay)
- [ ] : Incorrect. Amazon EC2 Auto Scaling cooldown periods help you prevent Auto Scaling groups from launching or terminating additional instances before the effects of previous activities are apparent.
  - see [Scaling Cooldowns for Amazon EC2 Auto Scaling](https://docs.aws.amazon.com/autoscaling/ec2/userguide/Cooldown.html)
- [x] : Correct. By default, the Application Load Balancer waits 300 seconds before the completion of the deregistration process, which can help in-flight requests to the target become complete. To change the amount of time that the Application Load Balancer waits, update the deregistration delay value.



### Q2
A company has strict data protection requirements. A solutions architect must configure security for a VPC to ensure that backend Amazon RDS DB instances cannot be accessed from the internet. The solutions architect must ensure that the DB instances are accessible from the application tier over a specified port only.

Which actions should the solutions architect take to meet these requirements? (Select TWO.)
### A2
- [x] : Correct. A private subnet is one component to use to secure the database tier. Internet traffic is not routed to a private subnet. When you place DB instances in a private subnet, you add a layer of security.
  - [routing](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Scenario2.html#VPC_Scenario2_Routing)
- [ ] : Incorrect. An elastic network interface is a logical networking component in a VPC that represents a virtual network card. The use of an elastic network interface would not meet the requirements in the scenario.
  - [Elastic network interfaces](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-eni.html)
- [ ] : Incorrect. Shield provides protection against DDoS attacks. Shield cannot be a target of routes in a route table. The use of Shield would not meet the requirements in the scenario.
  - [aws shield](https://docs.aws.amazon.com/waf/latest/developerguide/shield-chapter.html)
- [ ] : Incorrect. Direct Connect provides a dedicated connection to your AWS environment. The use of Direct Connect would not meet the requirements in the scenario.
  - [Direct Connect](https://aws.amazon.com/directconnect/features/)
- [x] : Correct. Security groups can restrict access to the DB instances. Security groups provide access from only the application tier on only a specific port.
  - [SG](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_SecurityGroups.html#VPCSecurityGroups)

### Q6
A company uses one AWS account to run production workloads. The company has a separate AWS account for its security team. During periodic audits, the security team needs to view specific account settings and resource configurations in the AWS account that runs production workloads. A solutions architect must provide the required access to the security team by designing a solution that follows AWS security best practices.

Which solution will meet these requirements?
### A6
- [ ] : This solution does not follow the security best practice of using roles to delegate permissions.
  - [ Require Human Users to Use Federation with an Identity Provider to Access AWS Using Temporary Credentials](https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html#bp-users-federation-idp)
- [x] : This solution follows security best practices by using a role to delegate permissions that consist of least-privilege access.
- [ ] : The assignment of administrative privileges to a user violates security best practices and the principle of least privilege.
- [ ] : This solution does not follow the security best practice of using roles to delegate permissions.


### Q9
A company is investigating services to manage vulnerability scans in Amazon EC2 instances and container images that the company stores in Amazon Elastic Container Registry (Amazon ECR). The service should identify potential software vulnerabilities and categorize the severity of the vulnerabilities.

Which AWS service will meet these requirements?


### A9
- [ ] : [Amazon GuardDuty](https://aws.amazon.com/guardduty/features/) is a threat detection service that continuously monitors for malicious activity and anomalous behavior. It does not scan for vulnerabilities.
- [ ] : You can use [Patch Manager](https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-patch.html) to apply patches for operating systems and applications. This does not satisfy the requirement to scan EC2 instances and containers for vulnerabilities.
- [ ] : Amazon [Inspector](https://aws.amazon.com/inspector/features) removes the operational overhead that is necessary to configure a vulnerability management solution. Amazon Inspector works with both EC2 instances and container images in Amazon ECR to identify potential software vulnerabilities and to categorize the severity of the vulnerabilities.
- [ ] : AWS [Config](https://aws.amazon.com/config/) is a service that gives you the ability to assess, audit, and evaluate the configurations of your AWS resources. It does not scan for vulnerabilities or network exposures.

### Q11
A company runs its website on Amazon EC2 instances behind an Application Load Balancer that is configured as the origin for an Amazon CloudFront distribution. The company wants to protect against cross-site scripting and SQL injection attacks.

### A11
- [ ] : Shield Advanced protects against DDoS attacks. Shield Advanced does not protect against cross-site scripting or SQL injection.
- [ ] : With Firewall Manager, you can manage AWS WAF, Shield Advanced, and other AWS services. Shield Advanced protects against DDoS attacks. Shield Advanced does not protect against cross-site scripting or SQL injection.
- [ ] : With Firewall Manager, you can manage AWS WAF, AWS Shield Advanced, and other AWS services. Firewall Manager is a managed service that is not installed on EC2 instances.
- [x] : AWS WAF can detect the presence of SQL code that is likely to be malicious (known as SQL injection). AWS WAF also can detect the presence of a script that is likely to be malicious (known as cross-site scripting).


### Q19
A company is developing a new mobile version of its popular web application in the AWS Cloud. The mobile app must be accessible to internal and external users. The mobile app must handle authorization, authentication, and user management from one central source.

Which solution meets these requirements?
### A19
- [ ] : An [IAM role](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles.html) is an IAM entity that is assumable by an IAM user. An IAM role has permissions policies that define what the entity can and cannot do. However, an IAM role does not control access to an application.
- [ ] : You can use [IAM users](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_users.html) and [groups](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_groups.html) to control who is authenticated and authorized to use an AWS service. However, users and groups do not control access to an application.
- [x] : [Amazon Cognito](https://docs.aws.amazon.com/cognito/latest/developerguide/what-is-amazon-cognito.html) provides authentication, authorization, and user management for your web and mobile apps. Users can sign in directly with a user name and password, or through a trusted third party.
- [ ] : You can use AWS STS to create and provide trusted users with temporary security credentials that can control access to your AWS resources. However, **AWS STS does not control access to an application.**

### Q20
Which components are required to build a site-to-site VPN connection to AWS? (Select TWO.)

### A20
- [ ] : An internet gateway is attached to a VPC to allow traffic from the internet to flow into or out of the VPC. A VPN connection does not flow through an internet gateway. The internet gateway is designed to allow traffic from the open internet, not an encrypted VPN connection.
- [ ] : A NAT gateway provides a way for private Amazon EC2 instances to send requests to the internet. A NAT gateway does not give you the ability to create an encrypted site-to-site VPN connection.
- [x] : A customer gateway is required for the VPN connection to be established. A customer gateway device is set up and configured in the customer's data center.
- [ ] : [API Gateway](https://docs.aws.amazon.com/zh_tw/apigateway/latest/developerguide/welcome.html) is a fully managed service for developers to create, publish, maintain, monitor, and secure APIs at any scale. APIs act as the front door for applications to use to access data, business logic, or functionality from backend services. However, API Gateway is not necessary for the implementation of a VPN connection.
- [x] : A virtual private gateway is attached to a VPC to create a site-to-site VPN connection to AWS. You can accept private encrypted network traffic from an on-premises data center into your VPC without the need to traverse the open public internet.


## Design Resilient Architectures

### Q3
A company is designing a disaster recovery (DR) architecture for an important application on AWS. The company has determined that the recovery time objective (RTO) is 5 minutes with a minimal running instance capacity to support the application in the AWS DR site. The company needs to minimize costs for the DR architecture.

Which DR strategy will meet these requirements?

<img src="img/mock-SAA-C03-01/s3.png">

### A3
- [x] : This solution meets the requirement for an RTO of 5 minutes with a minimal running instance. The instances run at a low capacity and can scale within minutes.
- [ ] : This solution would not meet the requirement for a minimal running instance. The instances are stopped.
- [ ] : Because this is an active-active environment, this solution would address the requirement for an RTO within minutes. The services are already running at full capacity within that time. However, this solution costs more than is necessary to meet the company's requirements.
- [ ] : This solution would not meet the requirement for a minimal running instance. The instances would need to be created, and backup and restore strategies take hours to run.




### Q4
A company needs to look up configuration details about how a Linux-based Amazon EC2 instance was launched.

Which command should a solutions architect run on the EC2 instance to gather the system metadata?

### A4
- [x] : The only way to retrieve instance metadata is to use the link-local address, which is 169.254.169.254.
  - [Retrieve Instance Metadata](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instancedata-data-retrieval.html)
- [ ] : The use of localhost will not work because this solution checks an IP address of 127.0.0.1. Metadata is not available through the use of the localhost name.
- [ ] : The format for the link-local address is 169.254.169.254.
- [ ] : Instance metadata is not available through 192.168.x.x.

### Q17
A company asks a solutions architect to implement a pilot light disaster recovery (DR) strategy for an existing on-premises application. The application is self contained and does not need to access any databases.

Which solution will implement a pilot light DR strategy?
### A17
- [ ] : This is a backup and restore DR strategy. Backup and restore DR strategies typically have the lowest cost but highest recovery time. A solution that manually rebuilds the hosting infrastructure on AWS could take hours.
- [x] : This is a pilot light DR strategy. This solution recreates an existing application hosting environment in an AWS Region. This solution turns off most (or all) resources and uses the resources only during tests or when DR failover is necessary. RPO and RTO are usually 10s of minutes. A pilot light strategy simplifies recovery at the time of a disaster because the core infrastructure requirements are all in place. A pilot light strategy also minimizes the ongoing cost of DR by minimizing the active resources.
- [ ] : This is a warm standby DR strategy. This solution recreates an existing application hosting environment in an AWS Region. This solution serves a portion of live traffic. With this DR strategy, RPO and RTO are usually a few minutes. However, costs are higher because this solutions runs resources continuously.
- [ ] : This is a backup and restore DR strategy. Backup and restore DR strategies typically have the lowest cost but highest recovery time. A solution that manually rebuilds the hosting infrastructure on premises and downloads the data that a company has backed up could take hours or days.

### Q16
An application runs on two Amazon EC2 instances behind a Network Load Balancer. The EC2 instances are in a single Availability Zone.

What should a solutions architect do to make this architecture more highly available?
### A16
- [ ] : [VPC peering](https://docs.aws.amazon.com/vpc/latest/peering/what-is-vpc-peering.html) will provide connectivity to the other Availability Zone. However, VPC peering does not ensure high availability because the EC2 instances are still in one Availability Zone.
- [ ] : The replacement of the Network Load Balancer with an Application Load Balancer provides no additional availability. Both load balancers are inherently highly available. However, the EC2 instances would be highly available only if they extended across two Availability Zones.
- [ ] : Failover routing requires a primary destination and a secondary (failover) destination. No failover destination is specified in this solution. In addition, this approach does not ensure high availability because the EC2 instances are still in one Availability Zone.
  - [Configuring DNS failover](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/dns-failover-configuring.html)
- [x] : This solution extends the EC2 instances across multiple Availability Zones and automatically adds capacity when additional capacity is needed.




## Design High-Performing Architectures

### Q5
A media company is designing a new application for graphic rendering. The application requires up to 400 GB of storage for temporary data that is discarded after the frames are rendered. The application requires approximately 40,000 random IOPS to perform the rendering.

What is the MOST cost-effective storage option for this rendering application?
### A5
- [x] : Storage optimized instances are designed for workloads that require high, sequential read and write access to very large datasets on local storage. These instances are optimized to provide applications with tens of thousands of low-latency, random IOPS. The instance store has no additional cost.
  - [instance store](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/InstanceStorage.html#instance-store-volumes)
- [ ] :  Provisioned IOPS SSD (io1 or io2) EBS volumes can deliver more than the 40,000 IOPS that are required in the scenario. However, this solution is not as cost-effective as an instance store because Amazon EBS adds cost to the hourly instance rate. This solution provides persistence of data beyond the lifecycle of the instance, but persistence is not required in this use case.
- [ ] : Throughput Optimized HDD (st1) EBS volumes are engineered to maximize the throughput of data that can be sent to and from a volume, not the random IOPS. Consequently, this solution does not meet the IOPS requirement. Additionally, Amazon EBS adds cost to the hourly instance rate. This solution provides persistence of data beyond the lifecycle of the instance, but persistence is not required in this use case.
- [ ] : Amazon S3 (object storage) is not the most suitable solution for rapidly changing data that is required for the scratch volume space. Block storage is appropriate for the read/write functionality to work smoothly.

### Q10
A company is deploying a new database on a new Amazon EC2 instance. The workload of this database requires a single Amazon Elastic Block Store (Amazon EBS) volume that can support up to 20,000 IOPS.

Which type of EBS volume meets this requirement?
### A10
- [ ] : A Throughput Optimized HDD EBS volume is an HDD-backed storage device that is limited to 500 IOPS for each volume.
- [ ] : A Provisioned IOPS SSD EBS volume provides up to 64,000 IOPS for each volume.
- [ ] : A General Purpose SSD EBS volume is limited to 16,000 IOPS for each volume.
- [ ] : A Cold HDD volume provides low-cost magnetic storage that defines performance in terms of throughput rather than IOPS. Cold HDD volumes are a good fit for large, sequential cold-data workloads.



## Design Cost-Optimized Architectures


### Q7
A company is developing a chat application that will be deployed on AWS. The application stores the messages by using a key-value data model. Groups of users typically read the messages multiple times. A solutions architect must select a database solution that will scale for a high rate of reads and will deliver messages with microsecond latency.

Which database solution will meet these requirements?
### A7
- [ ] : Aurora is a relational database (not a key-value database). Aurora is not likely to achieve microsecond latency consistently.
  - [Aurora](https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/CHAP_AuroraOverview.html)
- [ ] : DynamoDB is a NoSQL database that supports key-value records. DAX delivers response times in microseconds. 
- [ ] : [What is Amazon ElastiCache for Memcached?](https://docs.aws.amazon.com/AmazonElastiCache/latest/mem-ug/WhatIs.html)
- [ ] :  Neptune is a graph database that is optimized for working with highly connected data. Neptune is not optimized for simple key-value data.


### Q8
A company that processes satellite images has an application that runs on AWS. The company stores the images in an Amazon S3 bucket. For compliance reasons, the company must replicate all data once a month to an on-premises location. The average amount of data that the company needs to transfer is 60 TB.

What is the MOST cost-effective way to transfer this data?
### A8
- [x] : The base price covers the device and 10 days of usage at the on-premises location. If the company returns the device within a week, the company pays the base price and the price for data transfer out of AWS.
- [ ] : There is no cost advantage if the company copies all the data to another S3 bucket that uses S3 Standard-IA storage. The company could transfer the data directly from the original S3 bucket. This solution is not the most cost-effective option because the additional replication increases the cost.
- [ ] : There is no cost advantage if the company copies all the data to another S3 bucket that uses S3 Standard-IA storage. The company could transfer the data directly from the original S3 bucket. This solution is not the most cost-effective option because the additional replication increases the cost.
- [ ] : Data transfer to CloudFront is free of cost, but data transfer of 60 TB from CloudFront to an on-premises location incurs a cost. This option would cost approximately twice as much as the option to use the AWS Snowball Edge Storage Optimized device.



### Q12
A company has an on-premises application that exports log files about users of a website. The log files range from 20 GB to 30 GB in size. A solutions architect has created an Amazon S3 bucket to store the files. The files will be uploaded directly from the application. The network connection experiences intermittent failures, and the upload sometimes fails. The solutions architect must design a solution that resolves this issue. The solution must minimize operational overhead.

Which solution will meet these requirements?
### A12
- [ ] :  S3 Transfer Acceleration facilitates quicker uploads by using edge locations to copy data into Amazon S3. Because the network has intermittent failures, you should use multipart upload to increase resiliency and avoid upload restarts.
- [ ] : S3 Lifecycle policies cannot transfer files from EC2 block storage to Amazon S3.
- [x] : You can use a multipart upload to upload larger files, such as the files in this scenario. If transmission of any part fails, you can retransmit that part without affecting other parts.
- [ ] : A solution that uploads to two Regions simultaneously requires additional operational overhead. Multipart upload is a more efficient solution to increase resiliency and avoid upload restarts.

### Q13
A company is transitioning its Amazon EC2 based MariaDB database to Amazon RDS. The company has already identified a database instance type that will meet the company's CPU and memory requirements. The database must provide at least 40 GiB of storage capacity and 1,000 IOPS.

Which storage configuration for the Amazon RDS for MariaDB instance is MOST cost effective?
### A13
- [ ] : Magnetic storage does not support IOPS as a configurable parameter.
- [x] : General Purpose SSD (gp3) includes 3,000 IOPS at no additional cost independent of volume size.
- [ ] : General Purpose SSD (gp2) IOPS are dependent on volume size at a rate of 3 IOPS/GB. Provisioning 334 GiB of storage on gp2 to achieve the required IOPS would be more expensive than using 50 GiB of gp3.
- [ ] : 50 GiB of Provisioned IOPS storage with 1,000 IOPS would be more expensive than 50 GiB of General Purpose SSD (gp3) storage.
 
### Q14
A company is deploying a new application that will consist of an application layer and an online transaction processing (OLTP) relational database. The application must be available at all times. However, the application will have unpredictable traffic patterns. The company wants to pay the minimum for compute costs during these idle periods.

Which solution will meet these requirements MOST cost effectively?
### A14
- [ ] : EC2 burstable instances offer burstable capability without scaling. However, this solution does not minimize cost during the periods of inactivity and is not the most cost-effective option. Additionally, an Amazon Redshift database is not the most suitable solution for OLTP. Amazon Redshift is specifically designed for online analytic processing (OLAP).
- [ ] : Although infrastructure as code (IaC) helps with availability, this solution does not meet the requirement of always being available. Additionally, this solution offers no way to keep the database data after the database is deleted.
- [ ] : With this solution, at least one instance and a database will run during the periods of inactivity. This solution does not minimize cost during the periods of inactivity. This solution is not the most cost-effective option.
- [x] : When Amazon ECS uses Fargate for compute, it incurs minimal costs when the application is idle. Aurora Serverless also incurs no compute costs when it is idle.

### Q15
A company needs to maintain data records for a minimum of 5 years. The data is rarely accessed after it is stored. The data must be accessible within 2 hours.

Which solution will meet these requirements MOST cost-effectively?
### A15
- [ ] : This solution is not the most cost-effective solution. Amazon S3 is a more cost-effective solution if there is not a requirement for a file system.
- [ ] : This solution is not the most cost-effective solution because it requires the use of Amazon EBS in addition to Amazon S3.
- [ ] : The storage of the data in an S3 bucket provides a cost-effective initial location for the data. However, S3 Standard-IA is not the most cost-effective storage class to meet the requirements in the scenario. The S3 Glacier storage class is designed for low-cost data archiving.
- [x] : The storage of the data in an S3 bucket provides a cost-effective initial location for the data. S3 Glacier Instant Retrieval is the most cost-effective archival storage solution that meets the requirement of a 2-hour retrieval time.

### Q18
A company has an application that runs on a large general purpose Amazon EC2 instance type that is part of an EC2 Auto Scaling group. The company wants to reduce future costs associated with this application. After the company reviews metrics and logs in Amazon CloudWatch, the company notices that this application runs randomly a couple of times a day to retrieve and manage data. According to CloudWatch, the maximum runtime for each request is 10 minutes, the memory use is 4 GB, and the instances are always in the running state.

Which solution will reduce costs the MOST?
### A18
- [ ] : This solution would keep the EC2 instance in the running state 24 hours a day. This solution would not reduce costs.
- [ ] :  Lambda is a fully managed service that would automatically scale when necessary and would be highly available. A solution that deploys the application as a Lambda function reduces costs the most.
- [ ] : This solution would not reduce costs because this solution would still require EC2 instances to be in the running state beyond the run duration of each request.
- [ ] : This solution would not be appropriate because the request times are unpredictable. This solution would create scenarios where the application would not be available because instance launches are not correctly scheduled. This solution would also incur unnecessary costs because the company would be charged on an hourly basis for the EC2 instances instead of on the basis of exact runtimes.








