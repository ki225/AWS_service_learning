# Design Secure Architectures
## Domain1.1: Design Secure Access to AWS resources
To protect the cloud resources we build, the most important thing we should keep in mind is to protect own account(s). Most users might ignore this part, however, it will be a trouble if the account controlled by other bad guys.

To prevent this, we can use AWS IAM with the role-based access control strategy, and add MFA to the root account to improve the security. IAM users or IAM roles can only change their password in the beginning. The policies add by the root user can control what IAM user/group/role can do. Policies can be category as resource policy and identity policy. The first one decide which resource should be control, and the second one decide "who" can access the resources.

### security design strategy
- tracibility
- multiple AWS account
- enforce security standard
- automatically

## Domain1.2: Design secure workloads and applications
In most of the time, we use cloud services for building an application which is used by large amount of cutomers. The customers access it through the Internet, just like a student go home  through a road which connect the school and his house. However, if there is a path connect the this road and could guide anyone to a farm, the farmer should worry about his crop. One of the solution is to place a gate with lock in front of the farm, the other one is to hide the path to the farm.

Similarily, when we deploy the web server and website directly, anyone could access both of them through the Internet, so we have to use VPC to manage the networking part of our services. A VPC is build for an account, and it serves regionly.

- using endpoints is a better way to access the resources


### security design strategy
- security at every layer
- integrate secure services
- secure connection
  - some of the services can only connect to part of the resources
### associated services
- guardDuty
- macie
- cognito
- secret manager
- shield standard
- shield advanced

## Domain1.3: Determine appropriate data security controls
In this part, we will learn "encryption." Encryptions in SAA will be categorized as two types: rest and transmitted. The data is encrypting through another tunnel so that no one can get the data. 

In part of using encrypted key, the implementation of data replication, data backups and attaching policies for data access can also protect our data.

### key words
Before talk about encryption, some key words we should know are listed:
- plaintext 明文: data which is not encrypted, can be picture, video, text ...
- algorithm: a program to encrypt data with **plaintext + key**, finally generate a cyphertext
- key
  - symmetric
  - asymmetric
- cyphertext

### how to encrypted
- For data in rest
  - S3 encrypt
- For data in transit
  - aws certificate manager: store **SSL key**, not data key
  - S3 encrypt

### layered control
The more gates you set, the more secure the architecture will be. In every layer, we will use different secure control to achieve **protecting** and **detecting**

### cloud storage
- disaster recovery
  - low cost, low complexity
  - multiple AZ
- PRO 
- RTO
- backup
  - prriodically
  - continuously
  - way
    - dynamoDB backup, EFS backup
    - snapshot: EBS, RDS, Aurora...
    - socumentDB
    - S3 cross-region replication
    - AWS backup