## 10,000 Feet - GCP vs AWS vs Azure - Compute and Networking
| Question | AWS  | GCP | Azure|
|--|:--|:--|:--|
|How do you create Virtual Machines?|Amazon EC2 |Google Compute Engine (GCE)|Azure Virtual Machines|
|How do you attach permanent storage (block storage) with Virtual Machines?|Amazon EBS|Persistent Disk|Azure Disk Storage|
|How do distribute load among VMs?|Elastic Load Balancer|Cloud Load Balancing|Azure Load Balancer|
|How do you simplify setting up web applications?|AWS Elastic Beanstalk|Google App Engine|Azure App Service|
|How do you orchestrate containers?|Amazon EKS, Amazon ECS|Google Kubernetes Engine (GKE)|Azure Container Service (AKS)|
|How do you build serverless applications?| AWS Lambda| Cloud Functions|Azure Functions|
|How do you build private networks?|Amazon VPC|Cloud VPC|Azure Virtual Network|
|Private/Internal IP address connectivity across two virtual networks|VPC Peering|VPC Network Peering|Azure VNet Peering|
|Translations for internet connectivity for virtual networks|NAT Gateways|Cloud NAT|Azure Virtual Network NAT|
|Private Endpoint to access PaaS services from virtual networks|VPC endpoints (AWS PrivateLink)|Serverless VPC Access|Private Endpoint|
|How do you connect on premise with cloud? (Shared Connection over internet using IPsec)|AWS VPN|Cloud VPN|Azure VPN|
|How do you connect on premise with cloud? (Dedicated)|AWS Direct Connect|Cloud Interconnect|Azure Express Route|
|DNS management|AWS Route 53|Cloud DNS|Azure DNS|
|Content delivery network|CloudFront|Cloud CDN|Azure CDN|
|Debug Network Problems|VPC Flow logs|VPC Flow Logs|Azure Network Watcher|
|Petabyte- to exabyte-scale data transport solutions|Snowball, Snowball Edge, Snowmobile|Transfer Appliance|Azure Import/Export, Data Box|
---
## 10,000 Feet - GCP vs AWS vs Azure - Storage

<!-- .slide: class="tdfragment one40" -->
| Question | AWS  | GCP | Azure |
|--|:--|:--|:--|
|What is the Object storage solution?| Amazon S3|Cloud Storage|Azure Blob Storage|
|What is the Block storage solution?| Amazon EBS|Persistent Disk|Azure Disk Storage|
|What is the File storage solution?| Amazon EFS|Filestore|Azure Files|

---
## 10,000 Feet - GCP vs AWS vs Azure - Database

<!-- .slide: class="tdfragment one40" -->
| Question | AWS  | GCP | Azure | 
|--|:--|:--|:--|
| How do you create relational OLTP databases?|Amazon RDS (Amazon Aurora)|Cloud SQL, Cloud Spanner|Azure Database for MySQL and Azure Database for PostgreSQL, Azure SQL Database|
| What is the relational data warehouse solution?|Amazon Redshift|BigQuery|Azure Synapse Analytics|
| What are the NoSQL database options?|Amazon DynamoDB, Amazon DocumentDB|Datastore/Firestore, Cloud Bigtable|Azure Cosmos DB|
| How do you cache data from a database?| Amazon ElastiCache| Memorystore|Azure Cache|

---
## 10,000 Feet - GCP vs AWS - Others

<!-- .slide: class="tdfragment" -->

| Question | AWS  | GCP | Azure | 
|--|:--|:--|:--|
|What are the messaging services?|Amazon SNS, Amazon SQS|Cloud Pub/Sub|Azure Service Bus, Azure Storage Queues|
|How do you manage authentication and authorization to Cloud?|Amazon IAM|Cloud IAM|Azure Identity Management|
|How do you manage keys used for encrypting data?|AWS KMS|Cloud KMS|
|How do you automate deployment?|AWS CloudFormation, AWS Cloud Development Kit (AWS CDK)|Cloud Deployment Manager|Azure Deployment Manager, Azure Resource Manager (ARM) templates, Bicep|
|How do you monitor metrics around your applications|Amazon CloudWatch|Cloud Monitoring|Azure Monitor|
|How do you manage application and service logs?|Amazon CloudWatch Logs|Cloud Logging|Azure Monitor Logs|
|How do you trace requests across applications and services?|AWS X-Ray|Cloud Trace|Azure Monitor Application Insights Distributed Tracing|

---
## AWS - Regions and Availability Zones
| Region Code | Region  | Availability Zones | Availability Zones List |
|:--:|--|:--:|--|
| us-east-1   |  US East (N. Virginia)   | 6        | us-east-1a us-east-1b <BR/>us-east-1c  us-east-1d<BR/> us-east-1e us-east-1f      |
|  eu-west-2   |   Europe (London)     |   3     |  eu-west-2a eu-west-2b <BR/>eu-west-2c   |

- AWS provides **20+ regions** around the world
	- **Advantages** - High Availability, Low Latency and Adhere to government **regulations**
	- Choose region(s) based on - Users Location, Data Location, Regulatory and compliance needs
- Each AWS Region has at least two Availability Zones
	- **Isolated locations** in a Region	
	- **Increase availability** of applications in the same region

---
## GCP - Regions and Zones
| Region Code | Region  |  Zones | Zones List |
|:--:|--|:--:|--|
| us-west1   |  The Dalles, Oregon, North America   | 3        | us-west1-a <BR/>us-west1-b<BR/> us-west1-c      |
|asia-south1|Mumbai, India APAC|3|asia-south1-a, asia-south1-b <BR/>asia-south1-c|

- Regions in AWS = Regions in GCP
- Availability Zones in AWS = Zones in GCP
	- Three or more Zones in a Region (GCP)
- Additional Geographical Groups in GCP:
	- **Multi-region Locations**: Two or more regions. Ex: United States, Europe, and Asia.
	- **Dual Regions**: Specific pair of regions. Ex: nam4 (Iowa and South Carolina), eur4 (Netherlands and Finland), asia1 (Tokyo and Osaka).

---
## Azure - Regions and Availability Zones

<!-- .slide: class="one20 lefttable" -->
| Region  | Availability Zones |
|--|:--:|--|
|(US) East US|3| 
|(Europe) West Europe|3|

- Regions in AWS = Regions in Azure
- Availability Zones in AWS = Availability Zones in Azure
- Additional Geographical Groups in Azure:
	- Azure regional pairs: Specific pair of regions. Ex: East Asia (Hong Kong) and Southeast Asia (Singapore), West India and South India

---
<!-- .slide: class="center" -->
# Compute

---
## EC2 vs GCE vs Azure VMs
<!-- .slide: class="image-right image-twenty one40" -->
![](./images/00-icons/gcp/compute-engine.png)
- In AWS, we use EC2 service to provision Virtual Instances
- In GCP, the corresponding service is GCE or Google Compute Engine 
	- **Google Compute Engine (GCE)** - Provision & Manage Virtual Instances
	- **Virtual Machines** - Virtual Instances in GCP
- In Azure, the corresponding service is Azure Virtual Machines
	- **Azure Virtual Machines** - Provision & Manage Virtual Instances
	- **Virtual Machines** - Virtual Instances in Azure

---
## 10,000 Feet - Virtual Machines in GCP and AWS

<!-- .slide: class="tdfragment" -->

| Feature | AWS  | GCP | Azure | 
|--|:--|:--|:--|
| Create Virtual Machines| Amazon EC2| Google Compute Engine (GCE) |Azure Virtual Machines |
| Choose Operating System and Software| AMI (Amazon Machine Image)| Image|VM image|
| Choose the right family of hardware (Generic or high memory or high compute)| Instance Family| Machine Family|VM Types|
| Choose the right quantity of hardware (2 vCPUs, 4GB of memory)| Instance Type| Machine Type|VM Sizes|
| Restrict inbound and outbound traffic| Security Groups| Firewall Rules|Network security group (NSG)|
| Attach Permanent Hard Disks (Block Storage)| Amazon EBS| Persistent Disks|Azure Disk Storage|

---
## IP Addresses - Virtual Machines

| Feature | AWS  | GCP |  Azure | 
|--|:--|:--|:--|
|Permanent Internal IP Address that does not change during the lifetime of an instance| Private IP Address| Internal IP Address|Private IP Address|
|Ephemeral External IP Address that changes when an instance is stopped| Public IP Address| External or Ephemeral IP Address|Public IP Address|
|Permanent External IP Address that can be attached to a VM|Elastic IP Address|Static IP Address|Static IP Address|

---
## Managing Virtual Machines

| Feature | AWS  | GCP | Azure | 
|--|:--|:--|:--|
|Templates to simplify creation of Virtual Machines|Launch Templates/ Configuration|Instance templates|- (ARM Templates)|
|Simplify creation of multiple Virtual Machines|Auto Scaling Group|Instance Groups|Virtual machine scale set|
|Physical hosts dedicated to one customer|EC2 Dedicated Hosts|Sole-tenant nodes|Azure Dedicated Hosts|
|Simplify management (software, OS patches etc) of 1000's of Virtual Machines|Systems Manager| VM Manager|Virtual Machine Manager (VMM) |

---
## Manage Costs for Virtual Machines

|Feature| Amazon EC2  | GCE |Azure VMs |
|--|--|--|--|
|Create cheaper, temporary instances for non critical workloads|Spot instances|Preemptible VMs|Spot VMs|
|Reserve compute instances ahead of time|Reserved instances|Committed use discounts|Reserved instances|
|Get discounts for using resources for long periods of time|None|Sustained use discounts|-|
|Budget Management|Budget alerts|Budget alerts|Budget alerts|
|Reserve based on monetary commitment ($100 per hour, for example)|AWS Savings Plans|-|-|

---
## AWS - Elastic Load Balancer
<!-- .slide: class="image-right image-forty" -->
![](images/aws/ec2/1-simple-elb.png)
- Distribute traffic across EC2 instances in one or more AZs in a single region
- **Managed service**:
	- AWS ensures that it is highly available
	- Auto scales to handle huge loads
	- Load Balancers can be **public or private**
- Types:
	- **Classic** Load Balancer ( OLD - Layer 4 and Layer 7)
	- **Application** Load Balancer (Layer 7 HTTP/HTTPS)
	- **Network** Load Balancer (High Performance - Layer 4 TCP/TLS and UDP)
	- **Gateway** Load Balancer (Deploy, scale, and run third-party virtual appliances)

---
## GCP - Cloud Load Balancing
- Distribute traffic across VM instances in one or more regions
- Single anycast IP
- **Managed service**:
	- Google Cloud ensures that it is highly available
	- Auto scales to handle huge loads
	- Load Balancers can be **public or private**
- Types:
	- External HTTP(S)
	- Internal HTTP(S)
	- SSL Proxy
	- TCP Proxy
	- External Network TCP/UDP
	- Internal TCP/UDP

---
## Azure Load Balancer
- Number of services for Load Balancing
- Options:
	- Azure Front Door: Global HTTP(S)
	- Traffic Manager: Global non-HTTP(S)
	- Application Gateway: Regional HTTP(S)
	- Azure Load Balancer: Regional	non-HTTP(S)
- You can combine these based on your use case - https://docs.microsoft.com/en-us/azure/architecture/guide/technology-choices/load-balancing-overview#reference-architecture-examples

---
## Compute
<!-- .slide: class="image-right image-ten" -->

|Category|AWS|GCP|Azure|
|:--:|--|--|--|
|IAAS|Amazon EC2| Google Compute Engine|Azure VMs|
|PAAS|AWS Elastic Beanstalk|App Engine|Azure App Service|
|CAAS - Kubernetes|Amazon EKS|Google Kubernetes Engine|Azure Kubernetes Service, Azure Red Hat OpenShift|
|CAAS - Custom|Amazon ECS|||
|CAAS - Serverless|AWS Fargate|Cloud Run|Azure Container Instances|
|FAAS - Serverless |AWS Lambda|Cloud Functions|Azure Functions|
|VMWare|VMware Cloud on AWS|VMware Engine|Azure VMware Solution|

---
<!-- .slide: class="center" -->
# App Engine
---

## AWS Elastic BeanStalk
- **Simplest way** to deploy and scale your web application in AWS
	- Provides end-to-end web application management
		- Programming languages (Go, Java, Node.js, PHP, Python, Ruby)
		- Application servers (Tomcat, Passenger, Puma)
		- Docker containers (Single and Multi Container Options)
		- **No usage charges** - Pay only for AWS resources you provision
		- **Features**: Load Balancing, Auto scaling and Managed Platform updates
		- Multiple Release Options
			- **All at once** – Deploy V2 to all existing instances in a SINGLE batch.
			- **Rolling** – Deploy V2 to existing instances in multiple batches.
			- **Rolling with additional batch** – Launches a new batch with V2 first. Each batch with V2 will replace existing instances with V1 deployed. 
			- **Immutable** – Second ASG created with V2.
			- **Traffic splitting** – Canary testing approach. Deploy V2 to few new instances. Send a portion of traffic to V2 (While serving majority of users from V1). 
			- **(ADDITIONAL OPTION) BLUE GREEN with SWAP URL** - Create New Environment with V2 instances. Test them. SWAP URL of V1 environment with V2 environment. One time switch!
---

## App Engine
<!-- .slide: class="image-right image-twenty" -->
![](./images/00-icons/gcp/app-engine.png)
- **Simplest way** to deploy and scale your applications in GCP
	- Provides end-to-end application management
- Supports:
	- Go, Java, .NET, Node.js, PHP, Python, Ruby using pre-configured runtimes
	- Use custom run-time and write code in any language
	- Connect to variety of Google Cloud storage products (Cloud SQL etc)
- **No usage charges** - Pay for resources provisioned
- **Features**:
	- Automatic load balancing & Auto scaling
	- Managed platform updates & Application health monitoring
	- Application versioning
	- Traffic splitting

---
## Azure App Service
<!-- .slide: class="image-right image-thirty" -->
![](./images/aws/cloud-2-PAAS.png)
- Fully managed platform for building, deploying and scaling your web apps
	- Also supports REST APIs, and mobile back ends
- Natively supports .NET, .NET Core, Node.js, Java, Python and PHP
- Choose App Service plan: defines a set of compute resources for a web app
- Features:
	- Automated Deployment and management
	- Auto Scaling
	- Built in Load Balancing

---
## App Engine vs AWS Elastic Beanstalk vs App Service
|Feature|AWS Elastic Beanstalk| App Engine|Azure App Service|
|--|:--|:--|:--|
|Recommended for| Simple Web Apps and Batch Apps|Simple Web Apps and Batch Apps (For simple microservices)|Simple Web Apps|
|Quick Database Integration|Amazon RDS, Amazon DynamoDB| Firestore, Cloud SQL|Azure Cosmos DB MongoDB, Azure SQL Database, Azure Database for MySQL|
|Batch Programs|Worker Tier with SQS integration|Asynchronous task queues - Pub Sub|NA (Recommended Service: Azure Batch)|
|Hierarchy|Application > Application version > Environment| Application > Service > Version|App Service > Web App, API App, or Mobile App|
|Run Containers| Yes| Yes (App Engine flexible)|Yes|
|New Releases|Rolling updates, blue/green deployment (using Swap URL)|Rolling updates, blue/green deployment|Blue/green deployment(Using deployment slots)|

---
<!-- .slide: class="center" -->
# Container Orchestration

---
## Amazon Web Services - Container Orchestration
![](./images/aws/ecs.png) 
<!-- .slide: class="image-right image-thirty" -->
- Microservices are built in multiple languages (Go, Java, Python, JavaScript, etc)
- Containers simplify deployment of microservices:
	- Step I : Create a self contained Docker image 
		- Application Runtime (JDK or Python), Application code and Dependencies 
	- Step II : Run it as a container any where 
		- Local machine OR Corporate data center OR Cloud
- How do you manage 1000s of containers?
	- **Elastic Container Service (ECS)** - Fully managed service for container orchestration
		- **Step I** : Create a Cluster (Group of one or more EC2 instances)
		- **Step II**: Deploy your microservice containers
	- **AWS Fargate**: Serverless ECS. DON'T worry about EC2 instances.
	- **Cloud Neutral**: Kubernetes 
		- AWS - AWS Elastic Kubernetes Service (EKS)

---
## Google Kubernetes Engine (GKE) 
<!-- .slide: class="image-right image-twenty" -->
![](./images/00-icons/gcp/kubernetes-engine.png)
- **Managed** Kubernetes service
	- Provides all important container orchestration features:
		- **Auto Scaling**
		- **Service Discovery**
		- **Load Balancer**
		- **Self Healing**
		- **Zero Downtime Deployments**
- Provides **Pod and Cluster Autoscaling**
- Enable **Cloud Logging** and **Cloud Monitoring** with simple configuration
- Uses **Container-Optimized OS**, a hardened OS built by Google

---
## Azure Container Orchestration - AKS and Service Fabric
![](./images/02-architecture/container-orchestration.png) 
<!-- .slide: class="image-right image-fifty" -->
- Using a Container Orchestrator:
	- 1: Create a Cluster
	- 2: Deploy & Orchestrate Microservices
- Azure Services:
	- Azure Kubernetes Service: Managed Kubernetes Service
	- Azure Service Fabric: Microsoft's container orchestrator

---
<!-- .slide: class="center" -->
# Google Cloud Functions

---
## Going Serverless with AWS Lambda
<!-- .slide: class="image-right image-ten" -->
![](./images/aws/00-icons/lambda.png) 
![](./images/aws/00-icons/apigateway.png) 
![](./images/aws/00-icons/dynamodb.png) 
- **Serverless** - ** Don't worry about servers. Focus on building your app**
	- Remember: **Serverless does NOT mean "No Servers"**
	- **Serverless for me**:
		- You don't worry about infrastructure
		- Flexible scaling and automated high availability
		- Pay for use NOT FOR SERVERS
	- **You focus on code** and the cloud managed service takes care of all that is needed to scale your code to serve millions of requests!
- **AWS Lambda** - Write and Scale Your Business Logic
	- Supports Node.js (JavaScript), Java, Python, Go,  C# and more..
	- Don't worry about servers or scaling or availability
	- Pay for Use: Number of requests, Duration of requests and Memory Configured
		- Free tier - 1M free requests per month
	- Integrates with AWS X-Ray(tracing), AWS CloudWatch (monitoring and logs)

---
## Cloud Functions
<!-- .slide: class="image-right image-ten" -->
![](./images/00-icons/gcp/functions.png)
- **Run code in response to events**
	- Write your business logic in  Node.js, Python, Go, Java, .NET, and Ruby
	- **Don't worry** about servers or scaling or availability (only worry about your code)
- **Pay only for what you use**
	- Number of invocations
	- Compute Time of the invocations
	- Amount of memory and CPU provisioned
- **Time Bound** - Default 1 min and MAX 60 minutes (2nd gen) for HTTP functions
- **Each execution runs in a separate instance**
	- No direct sharing between invocations


---
## Azure Functions
![](./images/azure/00-icons/functions.png) 
- You don't worry about servers or scaling or availability
- You only worry about your code
- You pay for what you use 
	- Number of requests
	- Duration of requests
	- Memory consumed
- Supports C#, Python, JavaScript, Typescript and Java

---
## AWS Lambda vs Cloud Functions vs Azure Functions
 
|Feature | AWS Lambda | Cloud Functions  | Azure Functions|
|--|--|--|--|
|Memory|upto 10 GB| upto 16 GB|upto 16 GB|upto 14 GB|
|Max Runtime|15 minutes|9 minutes|230 seconds for HTTP triggered function|
|Pricing|1ms increments <BR/>Based on memory provisioned| 100ms increments<BR/>Based on memory provisioned|per-second vCPU-s and GB-s consumption|
|Trigger| Very wide variety |   HTTP, Cloud Storage, Pub/Sub, Cloud Firestore, Firebase, Cloud Logging|Queue, Timer, Event Grid, HTTP, ..|
|Exposing REST API| API Gateway or something else| HTTP Trigger|HTTP Trigger|
|Logging|Amazon CloudWatch|Cloud Logging|Azure Monitor Logs|

---
<!-- .slide: class="center" -->
# Encryption

---
## AWS - KMS and Cloud HSM
<!-- .slide: class="image-right image-five" -->
![](./images/aws/00-icons/kms.png)
![](./images/aws/00-icons/cloudhsm.png) 

- Generate, store, use and replace your keys(symmetric & asymmetric)
- **KMS**: Multi-tenant Key Management Service
	- **KMS** integrates with all storage and database services in AWS
	- Define key usage permissions (including **cross account** access)
	- **Automatically rotate master keys** once a year 
- **CloudHSM**: **Dedicated** **single-tenant** HSM for regulatory compliance
	- (Remember) AWS KMS is a Multi-tenant service

---
## Cloud KMS vs AWS KMS
<!-- .slide: class="image-right image-twenty" -->
![](./images/00-icons/gcp/kms.png) 
- **Cloud KMS** is very similar to **AWS KMS**
	- Create and manage **cryptographic keys** (symmetric and asymmetric)
	- **Control their use** in your applications and GCP Services
	- Provides an API to encrypt, decrypt, or sign data
	- Use existing cryptographic keys created on premises
	- **Integrates with almost all GCP services** that need data encryption:
		- Google-managed key: No configuration required
		- Customer-managed key: Use key from KMS
		- Customer-supplied key: Provide your own key
- **Cloud HSM**: FIPS 140-2 Level 3 certified HSMs (Similar to AWS CloudHSM)

--- 
## Azure Encryption services (similar to KMS)
- Key Vault
- Provides security solution and works with other services by providing a way to manage, create, and control encryption keys stored in hardware security modules (HSM).
- Azure Dedicated HSM
- https://docs.microsoft.com/en-us/azure/dedicated-hsm/faq#how-do-i-decide-whether-to-use-azure-key-vault-or-azure-dedicated-hsm-

---
<!-- .slide: class="center" -->
# Storage

---
## Storage

|Type|AWS|GCP|Azure|
|:--:|:--|:--|:--|
|Persistent Block storage|Amazon Elastic Block Store|Persistent Disk|Azure Disk Storage|
|Ephemeral Block storage|Instance Store|Local SSDs|Ephemeral OS disks|
|Object storage|Amazon S3 (Simple Storage Service)|Cloud Storage|Azure Blob Storage|
|Infrequent Access Object Storage|Amazon S3 - Standard-IA, One Zone-IA|Cloud Storage - Nearline and Coldline classes|Azure Cool Blob Storage tier|
|Archival Object Storage|Amazon Glacier|Cloud Storage - Archive class|Azure Blob Storage archive access tier|
|File storage|Amazon Elastic File System|Filestore|

---
<!-- .slide: class="center" -->
# Object Storage - Cloud Storage

---
## Object Storage in AWS - Amazon S3
![](./images/aws/00-icons/s3.png)
<!-- .slide: class="image-right image-twenty" -->
- **Most popular, very flexible & inexpensive** storage service
- Store large objects using a **key-value** approach
	- Objects are stored in buckets:
		- Bucket names are **globally unique** and used as part of object URLs 
			- Can contain ONLY lower case letters, numbers, hyphens and periods
		- Unlimited objects in a bucket
- Provides REST API to access and modify objects
- Provides **unlimited storage**:
	- Objects are **replicated in a single region (across multiple AZs)**
- **Store all file types** - text, binary, backup & archives:
	- Media files and archives
	- Application packages and logs
	- Backups of your databases or storage devices
	- Staging data during on-premise to cloud database migration

---
## Amazon S3 - Important Features
![](./images/aws/00-icons/s3.png)
<!-- .slide: class="image-right image-ten" -->
- Amazon S3 Versioning(**Optional** - Enabled at bucket level):
	- Protects against **accidental deletion**
- How do you save costs and **move files between storage classes**?
	- Solution: S3 Lifecycle configuration
	- Two kinds of actions:
		- **transition** actions (one storage class to another)
		- **expiration** actions (delete objects) 
- **Different kinds of data** can be stored in Amazon S3
	- Huge variations in **access patterns**
	- **Trade-off** between access time and cost
	- **S3 storage classes** help to optimize your costs while meeting access time needs
		- Designed for durability of **99.999999999%(11 9’s)**

---
## Amazon S3 Storage Classes

|Storage Class|Scenario|
|--|:--|:--|
|Standard|Frequently accessed data|
|Standard-IA|Long-lived, infrequently accessed data (backups for disaster recovery)|
|One Zone-IA|Long-lived, infrequently accessed, non-critical data (Easily re-creatable data - thumbnails for images)|
|Intelligent-Tiering|Long-lived data with changing or unknown access patterns|
|Glacier|Archive data with retrieval times ranging from minutes to hours|
|Glacier Deep Archive|Archive data that rarely, if ever, needs to be accessed with retrieval times in hours|
|Reduced Redundancy (Not recommended)|Frequently accessed, non-critical data|

---
## Cloud Storage
<!-- .slide: class="image-right image-twenty" -->
![](./images/00-icons/gcp/storage.png)
- Very similar to Amazon S3
- Serverless: Autoscaling and infinite scale
- Provides REST API to access and modify objects
	- Also provides CLI (gsutil) & Client Libraries (C++, C#, Java, Node.js, PHP, Python & Ruby)
- **Store all file types** - text, binary, backup & archives:
- Objects are stored in buckets
	- Bucket names are **globally unique**
	- Unlimited objects in a bucket
	- Each bucket is associated with a project
	- Max object size is **5 TB**
		- BUT you can store unlimited number of such objects
- Buckets can be in a Region, Multi Region or Dual Region

---
## Cloud Storage - Storage Classes - Comparison

| Storage Class |Name | Minimum Storage duration| Typical Monthly availability|Use case|
|--|--|--|--|--|
|Standard|STANDARD| None | > 99.99% in multi region and dual region, 99.99% in regions| Frequently used data/Short period of time|
| Nearline storage|NEARLINE |30 days | 99.95% in multi region and dual region, 99.9% in regions|Read or modify **once a month** on average|
| Coldline storage| COLDLINE|90 days| 99.95% in multi region and dual region, 99.9% in regions|Read or modify **at most once a quarter**|
| Archive storage |ARCHIVE|365 days| 99.95% in multi region and dual region, 99.9% in regions|**Less than once a year**|

---
## Features across Storage Classes
<!-- .slide: class="image-right image-twenty" -->
![](./images/00-icons/gcp/storage.png)
- Important to Remember: Unlike AWS, most features are the same across storage classes
- **Low** latency (first byte typically in tens of milliseconds)
- **Unlimited** storage 
	- Autoscaling (No configuration needed)
	- **NO minimum** object size
- Same APIs across storage classes
- High durability (99.999999999% annual durability)
- **Committed SLA** is 99.95% for multi region and 99.9% for single region for Standard, Nearline and Coldline storage classes
	- No committed SLA for Archive storage

---
## Azure Blob Storage
<!-- .slide: class="image-right image-twenty" -->
![](./images/azure/00-icons/storage.png) 
- **Azure Blob Storage**: Object storage in Azure
- **Structure**: Storage Account > Container(s) > Blob(s)
- Store massive volumes of unstructured data
	- **Store all file types** - text, binary, backup & archives:
		- Media files and archives, Application packages and logs
		- Backups of your databases or storage devices
- **Three Types of Blobs**
	- Block Blobs: Store text or binary files (videos, archives etc)
	- Append Blobs: Store log files (Ideal for append operations)
	- Page Blobs: Foundation for Azure IaaS Disks (512-byte pages up to 8 TB)
- **Azure Data Lake Storage Gen2**: Azure Blob Storage Enhanced
	- Designed for enterprise big data analytics (exabytes, hierarchical)
	- Low-cost, tiered storage, with high availability/disaster recovery

---
## Azure Blob Storage - Access Tiers
<!-- .slide: class="image-right image-twenty" -->
![](./images/azure/00-icons/storage.png) 
- **Different kinds of data** can be stored in Blob Storage
	- Media files, website static content
	- Backups of your databases or storage devices
	- Long term archives
- Huge variations in **access patterns**
- Can I pay a cheaper price for objects I access less frequently?
	- **Access tiers**
		- **Hot**: Store frequently accessed data
		- **Cool**: Infrequently accessed data stored for min. 30 days
		- **Archive**: Rarely accessed data stored for min. 180 days
			- Lowest storage cost BUT Highest access cost
			- Access latency: In hours
			- To access: **Rehydrate** (Change access tier to hot or cool) OR 
				- Copy to another blob with access tier hot or cool
		- You can **change access tiers** of an object **at any point in time**

---
<!-- .slide: class="center" -->
# Networking 
---
## Amazon VPC (Virtual Private Cloud) and Subnets
<!-- .slide: class="image-right image-ten" -->
![](./images/aws/00-icons/vpc.png) 
- **VPC(Virtual Private Cloud)** - Your **own isolated network** in AWS cloud
	- Network traffic within a VPC is isolated (not visible) from all other Amazon VPCs
	- You **control all the traffic** coming in and going outside a VPC
	- **(Best Practice)** Create AWS resources **in a VPC**
		- Secure resources from unauthorized access AND 
		- Enable secure communication between your cloud resources
		- Each VPC is created in a Region 
- **Subnet** - **Separate public resources from private resources** in a VPC
	- **Create different subnets** for public and private resources
		- Resources in a public subnet **CAN** be accessed from internet
		- Resources in a private subnet **CANNOT** be accessed from internet
		- BUT resources in public subnet can talk to resources in private subnet
		- Each Subnet is created in an Availability Zone 
		- VPC - us-east-1 => Subnets - AZs us-east-1a or us-east-1b or ..
- Users can 
	- Select IP address range 
	- Add/update address ranges
	- Configure route tables & network gateways.

---
## Azure Virtual Network (Vnet) and Subnets
- Azure Virtual Network is similar to AWS VPC
- Subnet in AWS is also called Subnet in Azure
- You can create your own custom Vnets and subnets
	- You can create different types of resources in different subnets
	- You can setup Virtual network peering between Vnets to connect different Vnets

---
## Google Cloud VPC (Virtual Private Cloud) and Subnets

<!-- .slide: class="image-right image-twenty" -->
![](./images/00-icons/gcp/vpc.png)

- VPC and Subnets in GCP are very similar to AWS:
	- Default VPCs are provided with default subnets
	- You can create your own custom VPCs and subnets
	- You can create different types of resources in different subnets
	- You can use VPC flow logs to debug problems
	- You can setup peering between VPCs to connect different VPCs
	- You can create Shared VPCs to share resources across multiple GCP projects or AWS accounts
- However, it is important to note the differences:
	- In AWS, VPCs are regional and Subnets belong to an Availability Zone
		- However, in GCP VPCs are global and Subnets belong to specific region
	- There are significant differences in default VPCs and subnets configuration
		- In GCP, default VPCs are created per project
			- Each default VPC has multiple subnets - one in each region

---
<!-- .slide: class="center" -->
# Organizing Resources
---
## Organizing Resources
- Azure: Account > Management group > Subscriptions > Resource groups > Resources
- Google Cloud: Organization (or Account) > Folders > Projects > Resources
- AWS: AWS Organization > AWS Account(s) > Resources
- Key things to remember:
	- Google Cloud Projects and Azure Subscriptions can be moved to different owner (Account or Organization). However, AWS resources are tied to an AWS Account.
	- A Google Cloud project is conceptually similar to the Azure subscription, in terms of billing, quotas, and limits.
		- However, from a functional perspective, a Google Cloud project is more like a resource group in Azure. It's a logical unit that cloud resources are deployed to.

---
## Organizing Resources in AWS
<!-- .slide: class="image-right image-twenty" -->
![](./images/aws/00-icons/organizations.png) 

- Where do we create resources in AWS?
	- In an AWS Account!
	- By default, you will be billed per AWS Account!
- What if you want to create resources for multiple environments?
	- One of the recommended approaches is to create separate AWS accounts
		- Each AWS account provides natural security, access and billing boundaries
		- Create **AWS Organization** to organize accounts into Organizational Units (OU)
			- Consolidated bill for AWS accounts
		- Use **AWS Resource Access Manager** to share AWS resources:
			- Share AWS Transit Gateways, Subnets, AWS License Manager configurations etc

---
## Resource Hierarchy in GCP
<!-- .slide: class="image-right image-sixty" -->
![](./images/02-architecture/resource-hierarchy-overview.png)
source: (https://cloud.google.com)
- **Well defined hierarchy**:
	- Organization > Folder > Project > Resources
- **Resources** are created in projects
- A **Folder** can contain multiple projects
- **Organization** can contain multiple Folders


## Azure Resource Hierarchy

<!-- .slide: class="image-right image-thirty" -->
![](./images/azure/rbac-scope-no-label.png)
(https://docs.microsoft.com/)

- **Hierarchy**: Management Group(s) > Subscription (s) > Resource Group (s) > Resources
	- **Resources**: VMs, Storage, Databases
	- **Resource groups**: Organize resources by grouping them into Resource groups
	- **Subscriptions**: Manage costs for resources provisioned for different teams or different projects or different business units
	- **Management groups**: Centralized management for access, policy, and compliance across multiple subscriptions
- **Remember**:
	- No hierarchy in resource groups BUT management groups can have a hierarchy

---
## Resource Groups

<!-- .slide: class="image-right image-twenty" -->
![](./images/azure/dev-and-qa.png)

- **Resource Group**: Logical container for resources
	- Associated with a single subscription
	- Can have multiple resources
		- (REMEMBER) A resource can be associated with one and only one resource group
	- Can have resources from multiple regions
	- Deleting it deletes all resources under it
- **Subscriptions**: Subscription links Azure Account to its resources
	- You need a Subscription to create resources in Azure
	- An Azure Account can have multiple subscriptions and multiple account administrators
- **Management Groups**: Allows you to manage access, policies, and compliance across multiple subscriptions
	- Group subscriptions into **Management Groups**
	- All subscriptions & resources under a Management Group inherit all constraints applied to it
	- (REMEMBER) You can create a hierarchy of management groups

---
## Relational Databases
<!-- .slide: class="image-right image-fifty" -->
![Database](./images/aws/relational-schema.png)
- This was the **only option** until a decade back!
- Most **popular (or unpopular)** type of databases
- **Predefined schema** with tables and relationships
- Very **strong transactional** capabilities
- Used for 
	- OLTP (Online Transaction Processing) use cases and
	- OLAP (Online Analytics Processing) use cases

---
## Relational Database - OLTP (Online Transaction Processing)
<!-- .slide: class="image-right image-twenty" -->
![](./images/00-icons/gcp/sql.png)
![](./images/00-icons/gcp/spanner.png) 
- Applications where **large number of users make large number of small transactions** ( small reads & updates)
	- **Use cases**: Most traditional applications, ERP, CRM, e-commerce, banking applications
- **Popular databases**: MySQL, Oracle, SQL Server etc
- Recommended AWS Services
	- **Amazon RDS** (Relational Database Service) - (Amazon Aurora, PostgreSQL, MySQL, MariaDB (Enhanced MySQL), Oracle Database, and SQL Server)
		- Amazon Aurora Provides "Global Database" option
- Recommended GCP Services: 
	- **Cloud SQL** : Supports PostgreSQL, MySQL, and SQL Server for regional relational databases (upto a few TBs)
	- **Cloud Spanner**: Unlimited scale (multiple PBs) and 99.999% availability for global applications with horizontal scaling
- Recommended Azure Services: 
	- **Azure SQL Database**: Managed Microsoft SQL Server
	- **Azure Database for MySQL**: Managed MySQL
	- **Azure Database for PostgreSQL**: Managed PostgreSQL

---
## Relational Database - OLAP (Online Analytics Processing)
<!-- .slide: class="image-right image-twenty" -->
![](./images/00-icons/gcp/bigquery.png) 
- Applications allowing users to **analyze petabytes of data**
	- **Examples** : Reporting applications, Data ware houses, Business intelligence applications, Analytics systems
	- **Sample application** : Decide insurance premiums analyzing data from last hundred years
	- Data is consolidated from multiple (transactional) databases
- Recommended AWS Managed Service: **Amazon Redshift**
- Recommended GCP Managed Service: **BigQuery**
- Recommended Azure Managed Service: **Azure Synapse Analytics**

---
## NoSQL Databases
<!-- .slide: class="image-right image-ten" -->
![](./images/00-icons/gcp/datastore.png)
![](./images/00-icons/gcp/big-query.png)
- **New approach** (actually NOT so new!) to building your databases
	- NoSQL = not only SQL
	- Flexible schema
		- Structure data **the way your application needs it**
		- Let the schema evolve with time
	- Horizontally scale to petabytes of data with millions of TPS
- **NOT a 100% accurate generalization** but a great starting point:
	- Typical NoSQL databases trade-off "Strong consistency and SQL features" to achieve "scalability and high-performance"
- **AWS Managed Services**:Amazon DynamoDB & Amazon DocumentDB
- **Google Managed Services**: Cloud Firestore (Datastore) &  Cloud BigTable
- **Azure Managed Service**: Azure Cosmos DB (MongoDB, Cassandra, Gremlin,.. APIs)

---
## Cloud Firestore (Datastore) vs Cloud BigTable
<!-- .slide: class="image-right image-ten" -->
![](./images/00-icons/gcp/datastore.png)
![](./images/00-icons/gcp/big-query.png)
- **Cloud Datastore** - Managed serverless NoSQL document database
	- Provides ACID transactions, SQL-like queries, indexes
		- Designed for transactional mobile and web applications
	- Firestore (next version of Datastore) adds:
		- Strong consistency
		- Mobile and Web client libraries
	- Recommended for small to medium databases (0 to a few Terabytes)
- **Cloud BigTable** - Managed, scalable NoSQL wide column database
	- NOT serverless (You need to create instances)
	- Recommend for data size > 10 Terabytes to several Petabytes
	- Recommended for large analytical and operational workloads:
		- NOT recommended for transactional workloads (Does NOT support multi row transactions - supports ONLY Single-row transactions)

---
## In-memory Databases
<!-- .slide: class="image-right image-twenty" -->
![](./images/00-icons/gcp/memorystore.png) 
- **Retrieving data from memory is much faster than retrieving data from disk**
- In-memory databases like Redis deliver microsecond latency by storing **persistent data in memory**
- Recommended AWS Managed Service 
	- **Amazon ElastiCache** (Redis and Memcached)
- Recommended GCP Managed Service 
	- **Memorystore** (Redis and Memcached)
- Recommended Azure Managed Service 
	- **Azure Cache** (Redis)
- **Use cases** : Caching, session management, gaming leader boards, geospatial applications

---
## Databases

| Type |AWS  | GCP | Azure |
|--|:--|:--|:--|
|RDBMS|Amazon Relational Database Service, Amazon Aurora|Cloud SQL, Cloud Spanner|Azure Database for MySQL and Azure Database for PostgreSQL, Azure SQL Database|
|NoSQL|Amazon DynamoDB, Amazon DocumentDB|Datastore/Firestore, Cloud Bigtable|Azure Cosmos DB|
|In-memory|Amazon ElastiCache|Memorystore|Azure Cache|
|Data warehouse|Amazon Redshift|BigQuery|Azure Synapse Analytics|
|Migration of databases|Database Migration Service|Database Migration Service|Database Migration Service|Database Migration Service|
---
## Synchronous vs Asynchronous Communication
<!-- .slide: class="image-right image-fifty" -->
![](./images/aws/02-Queuing/0-SQS-00.png)
![](./images/aws/02-Queuing/0-SQS-01.png)
![](./images/aws/02-Queuing/3-SNS.png)

- Synchronous Communication:
	- What if your logging service goes down?
		- Will you applications go down too?
	- What if there is high load?
		- Log Service unable to handle and goes down
- Asynchronous Communication:
	- Create a queue or a topic
		- Your applications put the logs on the queue
		- Picked up when the logging service is ready
	- Good example of decoupling!
	- (Possible) Multiple logging service instances reading from the queue!
- Two Types:
	- Pull based
	- Push based
---

|Producer Consumer (using Pull)|Simple Queue Service (SQS)|Cloud Pub/Sub|Queue Storage, Azure Service Bus|
|Publish Subscribe (Push)|Simple Notification Service (SNS)|Cloud Pub/Sub|Azure Service Bus|
|Real-time data ingestion service (event-driven systems and streaming analytics)|Amazon Kinesis|Cloud Pub/Sub|Azure Event Hubs|
---
## AWS - Amazon SQS and Amazon SNS
<!-- .slide: class="image-right image-thirty" -->
![](./images/aws/02-Queuing/0-SQS-01.png)
![](./images/aws/02-Queuing/3-SNS.png)
- Pull Based: **Amazon SQS**
	- Producers put messages. Consumers poll on queue.
		- Only one of the consumers will successfully process a message
	- Standard Queue 
		- Unlimited throughput
		- BUT NO guarantee of ordering (Best-Effort Ordering) 
		- and NO guarantee of exactly-once processing
	- FIFO (first-in-first-out) Queue
		- First-In-First-out Delivery, Exactly-Once Processing
		- BUT throughput is lower 
- Push Based: **Amazon SNS**
	- 1: Create an SNS Topic
	- 2: Subscribers can register for a Topic
	- 3: When an SNS Topic receives an event notification (from publisher), it is broadcast to all Subscribers

---
## Messaging in GCP - Pub/Sub
<!-- .slide: class="image-right image-ten" -->
![](./images/00-icons/gcp/pub-sub.png)
- Reliable, scalable, fully-managed asynchronous messaging service
- Backbone for **Highly Available** and **Highly Scalable** Solutions
	- Auto scale to process billions of messages per day
	- Low cost (Pay for use)
- Supports push and pull message deliveries
- Pub/Sub does NOT guarantee message ordering 
	- BUT there are mitigation options --enable-message-ordering
- Pub/Sub does NOT guarantee exactly-once delivery
	- Applications can handle duplicate messages

---
## Pub/Sub - Sending and Receiving a Message
<!-- .slide: class="image-right image-forty" -->
![](./images/02-Architecture/00-pubsub-messageflow.png)
- Publisher sends a message to Topic
- Message **individually** delivered to each and every subscription
	- Subscribers can receive message either by:
		- Push: Pub/Sub sends the message to Subscriber
		- Pull: Subscribers poll for messages
- Subscribers send acknowledgement(s)
- Message(s) are removed from subscriptions message queue
	- Pub/Sub ensures the message is retained **per subscription** until it is acknowledged

---
## DevOps

| Feature | AWS  | GCP | Azure|
|--|:--|:--|:--|
|CI/CD|CodeDeploy, CodeCommit, CodePipeline|Cloud Build|Azure DevOps|
|Monitoring|Amazon CloudWatch|Cloud Monitoring|Azure Monitor|
|Logging|Amazon CloudWatch Logs|Cloud Logging|Azure Monitor Logs|
|Audit logging|AWS CloudTrail|Cloud Audit Logs|Azure platform logs (Resource logs, Activity log, Azure AD logs)|
|Debugging|AWS X-Ray|Cloud Debugger|Azure Monitor Application Insights Snapshot Debugger|
|Performance tracing|AWS X-Ray|Cloud Trace|Azure Monitor Application Insights Distributed Tracing|
|How do you automate deployment?|AWS CloudFormation, AWS SAM, AWS Cloud Development Kit (AWS CDK)|Cloud Deployment Manager|Azure Deployment Manager, Azure Resource Manager (ARM) templates, Bicep|


---
## Others

| Feature | AWS  | GCP | Azure|
|--|:--|:--|:--|
|Multi-cloud|Amazon EKS Anywhere, Amazon ECS Anywhere|Anthos|Azure Arc|
|Container registry|Amazon Elastic Container Registry (ECR)|Artifact Registry|Azure Container Registry|
|Business intelligence|Amazon QuickSight|Looker|Microsoft Power BI|
|Apache Hadoop|Amazon Elastic MapReduce (EMR)|Dataproc|HDInsight|
|API management|Amazon API Gateway|API Gateway,Apigee API Management|Azure API Management|
|Cost management|AWS Budgets|Cost Management|Cost Management|
|Online data transfers from on-premise to cloud|AWS Storage Gateway|Storage Transfer Service|Azure Migrate|
|Web application firewall|AWS WAF|Google Cloud Armor|Azure WAF|
|Discover, classify, and protect data|Amazon Macie|Cloud Data Loss Prevention|Azure Information Protection|
|Store secrets|AWS Secrets Manager|Secret Manager|Azure Key Vault|
