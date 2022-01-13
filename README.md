# AWS Cloud Practitioner Notes (CLF-C01)
✨
_Notes made while following the official course.
Could be used to prepare or to refresh your concepts in a single place instead of gobbling through the videos again even though they are fun. :p_
✨

**Server-Client model** - Distributing some task among the servers and the clients.
**Server example** - Elastic Cloud Compute, EC2. It is used to access the virtual servers.
EC2 runs on top of AWS managed servers using virtualization technologies.
We are not taking a whole host , but we are getting an instance of the host which are called Virtual Machines.
Hypervisor is running on it, which ensures the allocation of resources to be used as virtual machines.

**Multitenancy** - Sharing underlying hardware between virtual machines. Hypervisor coordinates this.

**Isolation** - Instances are not aware of other instances or the data they carry.

**Vertical Scaling** - Make the instances bigger/smaller whenever the need arises.

**Cloud computing** - On-demand IT resources with pay-as-you-go scheme.

**3 types of cloud deployment models:**
1) **Cloud-Based Deployment** - Migrate current applications or build everything in the cloud from ground-up.
2) **On-Premises Deployment** - Everything is kept on personal cloud storage/platforms but for better utilization
   and management, the applications are incorporated in the personal cloud. It is also called as
   private cloud deployment. It doesn't involve any resources that are stored in the cloud.
3) **Hybrid Deployment** - This connects cloud based resources to on-premises infrastructure. If the legacy IT
   applications are more suitable, then that won't be migrated to the cloud. It involves resources that are
   located in the cloud.

**Benefits:**
1) **Variable expense and not upfront expenses** - Upfront means the cost of data centers, physical servers and such
   whereas upfront expense in AWS is only the cost of the resources utilized.
2) **Flexibility in capacity**.
3) **More economies of scale = Less pay-as-you-go costs**. So, if more people are using, the average could go down
   and would be cheaper than it is.
4) **Increased speed and agility** - Access anything anytime or remove access. It is fast.
5) **Global deployment** - Whatever you deploy, can be available to the whole world in a matter of seconds.

**EC2 instances:**
EC2 instances are grouped into EC2 instances family and they differ in terms of their utilization and usability of
Computation, Memory and Networking.
1) **General purpose** - Example - GitHub, servers fulfilling HTTP/S requests.
2) **Compute optimized** - Example - Machine Learning model trainer servers.
3) **Memory optimized** - Example - Websites having hundreds or unstructured data in a single page, or 
   millions of structured data that needs to be shown efficiently. Or if there's huge data that is going to be used
   real-time, so they should be preloaded for faster access and thus, performance.
4) **Accelerated optimized** - Example - GeForce Now, Graphics processing (accelerators) is good for this instance because of the
   accelerator that is being used. They ensure that we get faster response to the graphics that is being depicted
   on screen (4K or 8K images processing in real-time). These are faster than CPUs. Other applications are
   pattern matching. The CUDA cores are benefited quite a lot by TensorFlow when it comes to Machine/Deep learning.
5) **Storage optimized** - Example - YouTube, where millions of people everyday upload videos.

**Pricing -**
1) **On-demand** - Recommended for short-term, irregular usage.
2) **EC2 savings plan** - Good for usage when there is a fixed limit to the computations being utilized. Saves upto 66%.
3) **Reserved instances** - These are billing discounts applied to on-demand instances. In this, we are buying a
   subscription for a long term (standard/convertible reserved). Either 1 or 3 year subscriptions are there.
4) **Spot instances** - This is useful when the services we require can withstand interruption or if the data is not critical.
   Whenever an instance becomes available, only then that can be used. Spot instances are unused EC2 computing
   capacity and offer cost saving of upto 90%.
5) **Dedicated hosts** - These are physical servers which are totally dedicated to our use. Most expensive.

**AWS Cost Explorer** - Tool that enables you to visualize, understand, and manage your AWS costs and usage over time.

**ROI** - Return On Investment is good when we choose the right instances.

**Amazon EC2 Auto Scaling** - Tool for scaling process to happen automatically.
Within Amazon EC2 Auto Scaling, you can use two approaches: dynamic scaling and predictive scaling.
1) **Dynamic scaling** responds to changing demand. 
2) **Predictive scaling** automatically schedules the right number of Amazon EC2 instances based on predicted demand.

**Amazon Lambda** - Serverless compute service, making the processes autonomous and taking care of scalability.

**3 configurations in Auto-Scaling** -
1) **Minimum capacity** - This number of instances should be on whenever started.
2) **Desired capacity** - If not mentioned, defaults to minimum.
3) **Maximum capacity** - Shouldn't cross this limit.

**EC2 Load Balancing** - All of the requests goes through one point and that is the load balancer, from where they are
are distributed among the resources so as not to put stress in a specific resource.

**Monolithic application** - Application containing a lot of tightly coupled components like databases, servers,
business logic, user interfaces and so on... If any one of the component fails, then all of it will fail.

**Microservices application** - Application components are loosely coupled and whevener a component fails, the other
still carry on the process of communicating with each other and without failing.

**Amazon Simple Queue Service (Amazon SQS)** - Allows us to send, receive and store messages between software components at any
volume. Data contained within the message is called Payload. These are protected.

**Amazon Simple Notification Service** (Amazon SNS) is a publish/subscribe service.
Using Amazon SNS topics, a publisher publishes messages to subscribers. One message to many.

**Serverless computing** - The server part is abstracted so no need to know how it works, that is being taken care of
by the environment which is managed by AWS.

If not ready for serverless computing, below mentioned can be preferable. They are docker based.

Orchesteration tools, to manage containerized applications -
**Amazon Elastic Container Service (ECS)**.
**Amazon Elastic Kubernetes Service (EKS)**.

**Container** - A package for the code, it has the configurations, dependencies or whatever is required to make it run.

**AWS EC2** - Everything done by or on AWS servers.
**AWS Lambda** - Don't want to manage underlying provisioning or servers, host short running functions, running
service oriented or event driven applications.
**AWS Fargate** - If we choose docker-based workloads on AWS and want the underlying servers or provisioning to be
managd by AWS. Here don't want underlying OS or even the instances. It is a serverless compute platform for
ECS/EKS which are orchesteration tools so choose one from them before using Fargate or any other.

**Availability zones** - Zones where the servers are present as the neighbouring places requires them, quite
demanding these places are.
An Availability Zone is a single data center or a group of data centers within a Region. Availability Zones
are located tens of miles apart from each other. This is close enough to have low latency (the time between
when content requested and received) between Availability Zones. However, if a disaster occurs in one part
of the Region, they are distant enough to reduce the chance that multiple Availability Zones are affected.

What regions to pick? There are 4 business factors.
1) **Compliance** - What rules should be followed, if something needs within a country, just choose the server there.
2) **Proximity** - How close to the customers we are.
3) **Feature and Availability**.
4) **Pricing**.

**Amazon Braket** - Quantum computing platform.

**Edge locations** - Caching the data closer to the customers. It uses a concept called CDN - Content Delivery Networks.
Helps to deliver whatever data is thereby giving low latency and high bandwidth.
**Amazon CloudFront** - CDN service, AWS Route 53 - DNS service, using AWS services in our own data center, so the
functionality is of AWS but the isolation is just within the organization - AWS Outposts.

**Regions** - Geographically isolated zones. They contains availability zones.
Edge location runs Amazon CloudFront.

In AWS, everything is an API.

Main tools to interact with AWS resources -
1) **AWS Management Console** - Browser based.
2) **AWS CLI** - More control.
3) **AWS SDKs**.

Other management tools -
**AWS Elastic Beanstalk** - With AWS Elastic Beanstalk, you provide code and configuration settings, and Elastic
Beanstalk deploys the resources necessary to perform the following tasks -
1) Adjust capacity
2) Load balancing
3) Automatic scaling
4) Application health monitoring.
5) AWS Configuration.

**AWS CloudFormation** - With AWS CloudFormation, you can treat your infrastructure as code. This means that you
can build an environment by writing lines of code instead of using the AWS Management Console to individually
provision resources.

**Amazon Virtual Private Cloud (VPC)**. Private subnet.
Amazon VPC - Our own private network in AWS. Allows us to define our own IP range for the AWS resources. We place
instances and ELBs inside of the VPCs, placing them not randomly but in subnets.

**Subnets** - Chunks of IP address in our VPC and it allows us to group our resources together.

**Internet gateway** - To enable some traffic to flow some system. It is like a doorway open to the public.

**Virtual private gateway** - To make a connection to some system privately. This resource is not for public.

**AWS Direct Connect** - Minimum latency and maximum security. It provides a physical line that connects our network
(data center) to AWS VPC.

Public subnets can access the internet gateway

**Security Group** - Stateful (has a memory, keeps information), Network ACL - Stateless (no memory).
Network ACL scans traffic. Incoming and outgoing, no matter if already scanned before.
EC2 instance is covered by security group, security group is covered by ACL.

By default, all the traffic requests are **allowed** in **AWS ACL**.
By default, all the traffic requests are **denied** in **AWS NetworkGroup**.

**Route 53** - DNS. Translation service, names into IP.
Its routing policies -
1) Latency-based routing.
2) Geolocation DNS.
3) Geoproximity routing.
4) Weighted round robin.

**CDN (Content Delivery System)** - A network that delivers edge content to its users based on their geographic location.

In block storage, only data which is modified is changed so there's no overwriting of the whole data.
In object storage, each object has data, metadata and a key (identifier).

**Instance store** - It is a temporary block-level storage location for the instances. Whenever the instance is deleted, the
temporary storage is also deleted.
It is physically attached to the host computer for an EC2 instance.

**Amazon Elastic Block Store (Amazon EBS)** - It is a service that provides block-level storage volumes for EC2
instances.

**Steps to create EBS volume** - We define configurations (volume size and type) and provision it. Then we can attach
it to instances.
EBS data persists so even if the instances are deleted, the data stays.

**EBS snapshot** - An EBS snapshot is an incremental backup. This means that the first backup taken of a volume
copies all the data. For subsequent backups, only the blocks of data that have changed since the most recent
snapshot are saved.

**Amazon S3 (Simple Storage Service)** - It provides us with object-level storage. It stores data as objects in basket.

2 factors to consider when taking Amazon S3 -
1) How often do we plan to retrieve the data.
2) How available we need the data to be.

S3 types -
1) **S3 Standard** - Intended for data that needs to be accessed frequently. Data is stored in minimum of 3
availability zones.
2) **S3 Standard-Infrequent Access (S3-IA)** - Intended for data that needs to be accessed infrequently but whenever it is
needed, it should be delivered quickly. Data is stored in minimum of 3 availability zones. Cheaper than Standard.
3) **S3 One Zone-Infrequent Access (S3 Zone One-IA)** - Data is stored in of 1 availability zone.
4) **S3 Intelligent-Tiering** - It automatically categorizes the data and put them to their recommended tiers. Good
for use when the data usage or access pattern is unknown.
5) **S3 Glacier** - Low-cost storage designed for data archiving. The data can be retrieved in minutes or hours.
6) **S3 Glacier Deep Archive** - Data can be retrieved within 12 hours.

**S3 vs EBS** - If we need to only update certain data and not whole, EBS is the right choice else it is S3.

**File Storage** - It is like object-level storage but the data is organized, as in file systems.
It is good to use if large number of resources or services are making use of that data.

**EBS (Elastic Block System)** - Stores data in single availability zone.
**EFS (Elastic File System)** - Stores data across multiple availability zones.

**Amazon Relational Database Service (RDS)** - AWS service of using relational database on cloud. Amazon RDS
is a managed service that automates tasks such as hardware provisioning, database setup, patching, and backups.

**Supported database engines** -
1) Amazon Aurora
2) PostgreSQL.
3) MySQL
4) MariaDB
5) Oracle Database
6) Microsoft SQL Server

**Amazon Aurora** - It is an enterprise-class relational database. It is compatible with MySQL and PostgreSQL
relational databases. It is up to five times faster than standard MySQL databases and up to three times
faster than standard PostgreSQL databases.
Amazon Aurora helps to reduce your database costs by reducing unnecessary input/output (I/O) operations,
while ensuring that your database resources remain reliable and available. Consider Amazon Aurora if your
workloads require high availability. It replicates six copies of your data
across three Availability Zones and continuously backs up your data to Amazon S3.

**Amazon DynamoDB** - It is non-relational, key-value database service. It delivers single-digit millisecond performance at any scale.

**Amazon Redshift** - It is a data warehousing service that you can use for big data analytics.
It offers the ability to collect data from many sources and helps you to understand relationships and
trends across your data.

**AWS Database Migration Service (AWS DMS)** - It enables you to migrate relational databases, non-relational
databases, and other types of data stores.

1) **Amazon DocumentDB** - Supports MongoDB workloads.
2) **Amazon Neptune** - It is a graph database service. Usage in recommendation engines, fraud detection and knowledge
graphs etc.
3) **Amazon Quantum Ledger Database (Amazon QLDB)** - It is a ledger database service. You can use Amazon QLDB to
review a complete history of all the changes that have been made to your application data.
4) **Amazon Managed Blockchain** - It is a service that you can use to create and manage blockchain networks with
open-source frameworks.
5) **Amazon ElastiCache** - Amazon ElastiCache is a service that adds caching layers on top of your databases to help
improve the read times of common requests. It supports two types of data stores: Redis and Memcached.
6) **Amazon DynamoDB Accelerator (DAX)** - It is an in-memory cache for DynamoDB.
It helps improve response times from single-digit milliseconds to microseconds.

**Security** - There's a shared security model in AWS. It is responsible for some stuff and the people/organization using
AWS is responsible for some.
In simple words...
AWS - Security of the cloud, example - software, networking, database, regions, storage...
We - Security in the cloud, example - data of customers, encryption (server, client), OS/firewall configurations...

**AWS Identity and Access Management (IAM)** - It enables you to manage access to AWS services and resources securely.
IAM gives you the flexibility to configure access based on your company’s specific operational and security needs.
Features -
1) IAM users, groups, and roles
2) IAM policies
3) Multi-factor authentication

**IAM users** - An IAM user is an identity that you create in AWS. It represents the person or application that
interacts with AWS services and resources. It consists of a name and credentials.
**IAM Groups** - Helps us to give permission to users at a group level, at-once-to-all.
**IAM Roles** - An IAM role is an identity that you can assume to gain temporary access to permissions. Abandon all
current permission and have another permission.

**IAM policies** - It is a document that allows or denies permissions to AWS services and resources. For example,
you can allow users to access all of the Amazon S3 buckets within your AWS account, or only a specific bucket.

**AWS Organizations** - It is used to consolidate and manage multiple AWS accounts, within a central location. The
permissions are centrally controlled by using SCPs (Service Control Policies).
To categorize them even more which have similar business/security settings, called as OUs (Organizational Units).

**SCP** - It enable you to place restrictions on the AWS services, resources, and individual API actions that
users and roles in each account can access.

There are some standards that needs to be followed and to keep track of them, there's a service called Artifact.
**AWS Artifact** - It is a service that provides on-demand access to AWS security and compliance reports and
select online agreements. AWS Artifact consists of two main sections: AWS Artifact Agreements and AWS Artifact.
Reports.

**AWS Artifact Agreements** - An agreement with AWS regarding your use of certain types of information throughout
AWS services.
Different types of agreements are offered to address the needs of customers who are subject to specific regulations,
such as the Health Insurance Portability and Accountability Act (HIPAA).

**AWS Artifact Reports** - This is a report that is needed by development teams to better understand the rules and
regulations they should follow, or their responsibilities.
It provides compliance reports from 3rd party auditors and they test and verify if AWS is compliant with a variety
of global, regional, and industry-specific security standards and regulations.

**AWS Shield** for protection against DDoS, it comes with 2 levels of protection -
a) AWS Shield Standard - Free.
b) AWS Shield Advanced - Paid.
It comes with AWS WAF.

**Encryption at rest** - Encryption for data which is stored.
**Encryption in transit** - Encryption for data which is transmitting.

**AWS Key Management Service (AWS KMS)** - It enables us to perform encryption operations through the use of
cryptographic keys. A cryptographic key is a random string of digits used for locking (encrypting) and unlocking
(decrypting) data. You can use AWS KMS to create, manage, and use cryptographic keys. You can also control the use
of keys across a wide range of services and in your applications.

**AWS WAF** - It is a web application firewall that lets you monitor network requests that come into your web applications. 
AWS WAF works together with Amazon CloudFront and an Application Load Balancer.
AWS WAF works in a similar way to block or allow traffic. However, it does this by using a web access control list
(ACL) to protect your AWS resources.
If a request came from one of the blocked IP addresses that you have specified in the web ACL, it is denied access.

**Amazon Inspector** - It helps to improve the security and compliance of applications by running automated security
assessments. It checks applications for security vulnerabilities and deviations from security best practices,
such as open access to Amazon EC2 instances and installations of vulnerable software versions.
It is like an anti-virus program or anti-malware or anti-threat-anything program.

**Amazon GuardDuty** - It is a service that provides intelligent threat detection for your AWS infrastructure and
resources. It identifies threats by continuously monitoring the network activity and account behavior within your
AWS environment.
It continuously analyzes data from multiple AWS sources, including VPC Flow Logs and DNS logs.

**Amazon CloudWatch** - It is a web service that enables you to monitor and manage various metrics and configure alarm
actions based on data from those metrics.
CloudWatch uses metrics to represent the data points for your resources. AWS services send metrics to CloudWatch.
It then uses these metrics to create graphs automatically that show how performance has changed over time.

**AWS CloudTrail** - It records API calls for the account. It includes identity of API caller, time of call, source IP
address of caller. This is like breadcrumbs, taking logs of actions being performed.
Also to know if followed the widely accepted industry standards of deployment, maintenance and monitoring.

**CloudTrail Insights** - It is optional to enable it and this feature allows CLoudTrail to detect unusual API activities.

**AWS Trusted Advisor** - It is like the suggestions in code editor. It scans in real-time or inspects the AWS environment
and then gives recommendations in accordance with best AWS practices.
It compares its findings in 5 categories -
a) Cost optimization
b) Performance
c) Security
d) Fault tolerance
e) Service limits.

Which service enables you to review the security of your Amazon S3 buckets by checking for open access permissions?
- AWS Trusted Advisor.

Free AWS tiers -
1) Always free - 3.2 million seconds of compute time, 25GiB DynamoDB storage and 1 million free requests.
2) 12 months free - 12 months free after initial sign-up date to AWS.
3) Trials - It starts from the date we activate a particular service.

**Amazon Lightsail** - A service which enables us to run virtual private servers. It is like Lambda but it is not serverless.

**AWS Pricing Calculator** - It calculates an estimate for the use cases of AWS services (🔗: https://calculator.aws/#/)

**===========================================================================================**

Below are notes I made after doing some practice tests and these are abstract notes, you'd understand better after studying basic concepts.
**🔗**: **https://www.awsboy.com/aws-practice-exams/practitioner/**
(A very good website where you can do mock tests online and for free after creating an account **😃**)

**Lambda** - compute service serverless, run code w/o provisioning servers, compute service which makes easy for us to
build quick response apps. No need of running dedicated server for the services to be responsive.

**EC2 and Lightsail** - compute services.

S3 bucket restrict access to individual objects - **ACL**.

Edge locations series + CDN content - **Distribution**.

We need to optimize appliation using **RDS**.

**Bucket policies** - Control entire bucket contents.
CloudFormation template - **YAML and JSON**.
Building environments with - (Code - **CloudFormation**) & (GUI - **Management Console**).

**Glacier key components** - Access Policy, Archive and Vault (Grouping archives).

**Application Load Balancer** - Listeners, Targets and Target Groups.

Dashboards -
	**AWS Personal Health Dashboard** - Personalized performance and availability information.
	**AWS Service Health Dashboard** - General performance and availability information.
	**Trusted Advisor** - Cost, security, fault tolerance, performance.
	**CloudWatch** - Alert based on metrics, like cost threshold.

**VPC** - Networking and Delivery. Attach Internet Gateway for public subnet.

**S3** - Good for flat files (photos, docs).

**Object URL structure** - https > bucket name > dot > region endpoint > slash > object name.

**Round Robin is used in** -
	The Classic uses a Round-Robin strategy for TCP listeners only.
	The ALB 1st selects a target based on the routing rule, then uses a Round-Robin strategy to select a node.

**QuickSight** - Audit information, making reports with pictorial or chart related demonstration.
No need to copy to another zone for multiple instances.

**Lightsail** - PaaS, to host our stuff like apps.

**CodeDeploy** - installing/updating applications on EC2.

**CodeCommit** - share program codes securely.
Backup and Restore > Pilot Light > Warm Standby > Multi Site => **Multi Site** is the best choice for fast data recovery.

**OpsWork** - Sharing software comfiguration to other instances.

**Read replicas** - Optimizing responsiveness of accessing file.

**Rekognition** - Computer vision.

**Right sizing** - Which EC2 appropriate for our workload.

**Cloud9** - Share realtime development environment.

**EBS snapshots** - Customer responsibility.

**Quick Start** - Automated reference deployments for key workloads.

**S3 intelligent tiering** - For frequent and infrequent access.

**Systems Manager** - group AWS resources across different AWS Regions
	by application and then collect for monitoring.

**Resource tags** - Can be edited or removed at any time.

**EFS (Elastic File System)** - For shared file access.


DynamoDB + S3 + SNS + Lambda - **Serverless services**.

**Snowball** - Transfer petabyte-scale data.

**Beanstalk** - AWS cloud service helps in quick deployment of resources which can make
	use of different programming languages such as .Net and Java.

**Route 53** - TTL (Time To Live), DR is triggered.

**Decoupling applications** - SQS.

**S3** - Besst to store static content store, photos and videos.

**WAF** comes with - Shield (DDoS protection: Distributed Denial of Service).

**Machine Image** - To spin up EC2 instances on the AWS cloud.

 👩‍💻 Good Luck!) 👨‍💻

- Neeraj Mishra (nmcnemis@gmail.com).
