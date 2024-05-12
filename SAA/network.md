#### You are designing an intrusion detection prevention (IDS/IPS) solution for a customer web application in a single VPC. You are considering the options for implementing IOS IPS protection for traffic coming from the Internet. Which of the following options would you consider? (Choose 2 answers)

- [ ] Implement IDS/IPS agents on each Instance running in VPC.
- [ ] Configure an instance in each subnet to switch its network interface card to promiscuous mode and analyze network traffic.
- [ ] Implement Elastic Load Balancing with SSL listeners in front of the web applications.
- [ ] Implement a reverse proxy layer in front of web servers and configure IDS/ IPS agents on each reverse proxy server.

#### How can the domain's zone apex, for example, 'myzoneapexdomain.com', be pointed towards an Elastic Load Balancer?

- [x] By using an Amazon Route 53 Alias record.
- [ ] By using an AAAA record.
- [ ] By using an Amazon Route 53 CNAME record.
- [ ] By using an A record.

> [!NOTE] 
>Route 53 is a web service for DNS. Here are the DNS record types which Route 53 supports:
>
>- alias(extension to DNS functionality)
>  - route traffic to selected **AWS resources**
>  - Route 53 responds to a DNS query only when the name of the alias record (such as acme.example.com) and the type of the alias record (such as A or AAAA) match the name and type in the DNS query.
>- A
>  - to a resource, such as a web server
>  - IPv4 address in dotted decimal notation.
>- AAAA
>  - to a resource, such as a web server
>  - IPv6 address in colon-separated hexadecimal format.
>- CNAME
>  - the name of the current record, such as acme.example.com, to another domain (example.com or example.net) or subdomain (acme.example.com or zenith.example.org).


#### You need to set up security for your VPC and you know that Amazon VPC provides two features that you can use to increase security for your VPC: Security groups and network access control lists (ACLs). You start to look into security groups first. Which statement below is incorrect in relation to security groups?

- [ ] A. Are stateful: Return traffic is automatically allowed, regardless of any rules.
- [x] B. Support addition of individual allow and deny rules in both inbound and outbound.
- [ ] C. Security Groups can be added or removed from EC2 instances in a VPC at any time.
- [ ] D. Evaluate all rules before deciding whether to allow traffic.

> [!NOTE]  
>Security groups
>- Act as a firewall for associated Amazon EC2 instances
>- controlling both inbound and outbound traffic at the instance level and supports "allow rules only".


#### A company runs a multi-tier web application that hosts news content. The application runs on Amazon EC2 instances behind an Application Load Balancer. The instances run in an EC2 Auto Scaling group across multiple Availability Zones and use an Amazon Aurora database. A solutions architect needs to make the application more resilient to periodic increases in request rates. Which architecture should the solutions architect implement? (Choose two.)

- [ ] A. Add AWS Shield.
- [ ] B. Add Aurora Replica.
- [ ] C. Add AWS Direct Connect.
- [ ] D. Add AWS Global Accelerator.
- [x] E. Add an Amazon CloudFront distribution in front of the Application Load Balancer.

> [!WARNING]
> 答案不確定是 B 還是 D，但有E

#### A recently acquired company is required to build its own infrastructure on AWS and migrate multiple applications to the cloud within a month. Each application has approximately 50 TB of data to be transferred. After the migration is complete, this company and its parent company will both require secure network connectivity with consistent throughput from their data centers to the applications. A solutions architect must ensure one-time data migration and ongoing network connectivity.
Which solution will meet these requirements?

- [ ] A. AWS Direct Connect for both the initial transfer and ongoing connectivity.
- [ ] B. AWS Site-to-Site VPN for both the initial transfer and ongoing connectivity.
- [x] C. AWS Snowball for the initial transfer and AWS Direct Connect for ongoing connectivity. Most Voted
- [ ] D. AWS Snowball for the initial transfer and AWS Site-to-Site VPN for ongoing connectivity.

>[!NOTE]
> - AWS Direct Connect 是用在資料中心和 VPC 之間建立專用私有連線
> - AWS snall ball Snowball 是一種高容量的數據傳輸裝置，通常用於大量數據的離線傳輸。

#### An instance is launched into a VPC subnet with the network ACL configured to allow all inbound traffic and deny all outbound traffic. The instance’s security group is configured to allow SSH from any IP address and deny all outbound traffic. What changes need to be made to allow SSH access to the instance?

- [ ] The outbound security group needs to be modified to allow outbound traffic.
- [ ] The outbound network ACL needs to be modified to allow outbound traffic.
- [ ] Nothing, it can be accessed from any IP address using SSH.
- [ ] Both the outbound security group and outbound network ACL need to be modified to allow outbound
traffic.

> [!WARNING]
> 答案不確定是 B 還是 D，個人認為是 B 的原因是：security group 默認進的來就出得去，因為他有狀態紀錄；ACL 則沒有

#### HTTP Query-based requests are HTTP requests that use the HTTP verb GET or POST and a Query parameter named _____. 
- [x] A. Action 
- [ ] B. Value 
- [ ] C. Reset 
- [ ] D. Retrieve

#### What does a 'Domain' refer to in Amazon SWF?
- [ ] A security group in which only tasks inside can communicate with each other
- [ ] A special type of worker
- [x] A collection of related Workflows
- [ ] The DNS record for the Amazon SWF service
> [!NOTE]
> All the components of a workflow, such as the workflow type and activity types, must be specified to be in a domain. It is possible to have more than one workflow in a domain; however, workflows in different domains cannot interact with each other.


#### A company is building software on AWS that requires access to various AWS services. Which configuration should be used to ensure mat AWS credentials (i.e., Access Key ID/Secret Access Key combination) are not compromised(受到攻擊)?

- [x] Enable Multi-Factor Authentication for your AWS root account.
- [ ]  Assign an IAM role to the Amazon EC2 instance.
- [ ]  Store the AWS Access Key ID/Secret Access Key combination in software comments.
- [ ]  Assign an IAM user to the Amazon EC2 Instance.



#### Any person or application that interacts with AWS requires security credentials. AWS uses these credentials to identify who is making the call and whether to allow the requested access. You have just set up a VPC network for a client and you are now thinking about the best way to secure this network. You set up a security group called vpcsecuritygroup. Which following statement is true in respect to the initial settings that will be applied to this security group if you choose to use the default settings for this group?
- [ ] Allow all inbound traffic and allow no outbound traffic.
- [x] Allow no inbound traffic and allow all outbound traffic.
- [ ] Allow inbound traffic on port 80 only and allow all outbound traffic.
- [ ] Allow all inbound traffic and allow all outbound traffic.

>[!NOTE]
>[官網](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/default-custom-security-groups.html)
>
>The following are the default rules for a security group that you create:
>- Allows no inbound traffic
>- Allows all outbound traffic


#### You are creating a bastion host to allow SSH access to a set of EC2 instances in a private subnet within your organization's VPC. Which of the following should be done as part of configuring the bastion host? (Choose two.)
- [x] A. Ensure that the bastion host is exposed directly to the Internet.
- [ ] B. Place the bastion host within the private subnet.
- [x] C. Add a route from the bastion host IP into the private subnet into the subnet's NACLs.
- [ ] D. Ensure that the bastion host is within the same security group as the hosts within the private subnet.

#### Your company is setting up a VPN connection to connect its local network to an AWS VPC. Which of the following components are not necessary for this setup? (Choose two.)
- [x] A. A NAT instance
- [ ] B. A virtual private gateway
- [x] C. A private subnet in the AWS VPC
- [ ] D. A customer gateway
>[!NOTE]
>Site-to-site VPN connections require a virtual private gateway (on the AWS side) and a customer gateway (on the local side). A private subnet is optional, as is a NAT instance.


#### How would you enable encryption of your EBS volumes?
- [ ] A. Use the AWS CLI with the aws security command.
- [ ] B. Take a snapshot of the EBS volume and copy it to an encrypted S3 bucket.
- [x] C. Select the encryption option when creating the EBS volume.
- [ ] D. Encrypt the volume using the encryption tools of the operating system of the EC2 instance that has mounted the EBS volume
> [!NOTE]
> Amazon Elastic Block Store（EBS）是AWS提供的一種持久性塊存儲服務，用於將數據存儲在EC2實例上。

#### Which of the following must a security group have when you create it? (Choose two.)
- [ ] A. At least one inbound rule
- [x] B. A name
- [x] C. A description
- [ ] D. At least one outbound rule

#### Which of the following are default rules on a default security group, such as the one that comes with the default VPC? (Choose two.)
- [x] A. Outbound: 0.0.0.0/0 for all protocols allowed
- [ ] B. Inbound: 0.0.0.0/0 for all protocols allowed
- [x] C. Outbound: ::/0 for all protocols allowed
- [ ] D. Inbound: ::/0 for all protocols allowed

> [!NOTE]
> 0.0.0.0/0 is IPv4, ::/0 is IPv6

####  Which of the following are parts of a security group rule? (Choose two.)
- [x] A. A protocol
- [ ] B. A subnet
- [ ] C. An instance ID
- [x] D. A description

####  Which of the following describes client-side encryption for S3 bucket data?
- [x] A. You encrypt and upload data to S3, managing the encryption process yourself.
- [ ] B. You encrypt and upload data to S3, allowing AWS to manage the encryption process.
- [ ] C. You request AWS to encrypt an object before saving it to S3.
- [ ] D. You encrypt an object, but AWS uploads and decrypts the object.

> [!NOTE]
> client-side 就是讓客戶自己維護服務的安全性


#### Which of the following are valid steps in enabling client-side encryption for S3? (Choose two.)
- [ ] A. Download the AWS CLI and SSH to your S3 key store.
- [x] B. Use a KMS-managed customer master key.
- [x] C. Download an AWS SDK for encrypting data on the client side.
- [ ] D. Turn on bucket encryption for the target S3 buckets.


#### What type of replication will your Multi-AZ RDS instances use?
- [ ] A. Offline replication
- [x] B. Synchronous replication
- [ ] C. Push replication
- [ ] D. Asynchronous replication

> [!NOTE]
> In an Amazon RDS Multi-AZ deployment, Amazon RDS automatically creates a primary database (DB) instance and synchronously replicates the data to an instance in a different AZ.
> 
> [官網](https://www.google.com/url?sa=t&source=web&rct=j&opi=89978449&url=https://aws.amazon.com/rds/features/multi-az/&ved=2ahUKEwjWq7fHkIWGAxXkmlYBHZcqC9wQFnoECA4QAw&usg=AOvVaw0hKuaPUyMuq2YWK54-CYDG)

#### You want to provide maximum protection against data in your S3 object storage being deleted accidentally. What steps should you take? (Choose two.)
- [x] A. Enable versioning on your S3 buckets.
- [x] B. Turn on MFA Delete on your S3 buckets.
- [ ] C. Enable versioning in CloudWatch's S3 API.
- [ ] D. Remove IAM permissions for deleting objects for all users.

> [!NOTE]
> Versioning in Amazon S3 is a means of keeping multiple variants of an object in the same bucket.
> 
> [官網](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Versioning.html)


#### What types of data are encrypted when you create an encrypted EBS volume? (Choose two.)
- [x] A. Data at rest inside the volume
- [x] B. Data moving between the volume and the attached instance
- [ ] C. Data inside S3 buckets that store the encrypted instance
- [ ] D. Data in an EFS on instances attached to the volume

> [!NOTE]
> When you create an encrypted EBS volume and attach it to a supported instance type, the following types of data are encrypted: Data at rest inside the volume. All data moving between the volume and the instance. All snapshots created from the volume.
>
> [Amazon EBS encryption](https://www.google.com/url?sa=t&source=web&rct=j&opi=89978449&url=https://docs.aws.amazon.com/ebs/latest/userguide/ebs-encryption.html&ved=2ahUKEwjuzrvOlIWGAxUYdvUHHdVMBcQQFnoECBUQAw&usg=AOvVaw1-gk50DqOaWxOXx3pGtA6E)

#### How can you access the private IP address of a running EC2 instance?
- [ ] A. http://169.254.169.254/latest/user-data/
- [ ] B. http://169.254.169.254/latest/instance-data/
- [x] C. http://169.254.169.254/latest/meta-data/
- [ ] D. http://169.254.169.254/latest/ec2-data/