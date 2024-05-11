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



