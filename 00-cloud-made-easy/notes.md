Microservices => deployments are complex

- Amazon VPC, Cloud VPC, Azure Virtual Network: Your own isolated network in AWS cloud. Network traffic within a VPC is isolated (not visible) from all other Amazon VPCs. You control all the traffic coming in and going outside a VPC.
- Subnets - Each type of resource has its own access needs (public vs private)
- Addressing: IPv4 (Internet Protocol version 4 - numeric 32 bit) Example : 127.255.255.255 
	- IPv6 (Internet Protocol version 6 - alphanumeric 128 bit). Example : 2001:0db8:85a3:0000:0000:8a2e:0370:7334
	- Typically resources in same network use similar IP address to make routing easy
		- Example: Resources inside a specific network can use IP addresses from 69.208.0.0 to 69.208.0.15
	- A CIDR block consists of a starting IP address(69.208.0.0) and a range(/28). Quick Tip: 69.208.0.0/28 indicates that the first 28 bits (out of 32) are fixed. Last 4 bits can change => 2 to the power 4 = 16 addresses
	- VPC, Subnets are associated with CIDR blocks
	- Firewall Rules (Security Group, NSG) use CIDR blocks
- VM -> NAT Gateway (Cloud NAT, NAT Gateway in Azure also) -> Internet Gateway (AWS and Azure Don't need this - they have built-in internet gateway)  -> Internet
- Subnet <-> Internet Gateway <-> Internet (communication allowed both ways)
	- Each router has a set of rules that help it decide the path to the destination IP address
	- Route tables can be associated with VPCs and subnets
- NAT Gateway - allow instances in a private subnet to download software (WHILE denying inbound traffic from internet)
- NACL - stateless firewall at subnet level (In google cloud, Firewall Rules. In Azure, Azure Firewall )
- AWS Managed VPN (Traffic over internet - encrypted using IPsec protocol), Cloud VPN, Azure Virtual Private Network (VPN)
- AWS Direct Connect (DC) - Private dedicated network connection from on-premises to AWS (Cloud Interconnect, Azure ExpressRoute)

Storage
- Object Storage - S3, Azure Blob Storage, Cloud Storage
	- key-value, unlimited storage, REST API, text, binary, backup & archives, Staging data during on-premise to cloud database migration, Versioning, Event Notifications, 
	- Storage Classes (Standard/One-Zone-IA/Glacier, Hot/Cool/Archive, STANDARD/NEARLINE/COLDLINE/ARCHIVE) - Huge variations in access patterns
- Block Storage -  Azure Disks (Local SSDs), EBS (instance store), Persistent Disks (Local SSDs)
- File Storage - Azure Files, Cloud Filestore, EFS


Databases
- Unstructured Data vs Structured vs Semi Structured - Audio files, Video files, Binary files
- Fixed schema vs ACID vs latency vs volume of transactions vs scaling vs Complex queries

Relational database
- Do you want to manage the setup, backup, scaling, replication and patching of your relational databases? Or do you want to use a managed service?
- Structured Data, SQL, Strong schema (Primary Key, Foreign Key)
- You CANNOT SSH into database
- Typical upper limit - 64 TB
- Multi-AZ deployment (standby in another AZ) - maintenance easy - perform on standby and switch
- Read replicas (asynchronous replication, eventual consistency): Same AZ, Multi AZ (Availability+) Cross Region(Availability++) 
- Storage auto scaling, Automated backups (restore to point in time)
- Amazon RDS -  PostgreSQL, MySQL, MariaDB (Enhanced MySQL), Oracle Database, and SQL Server
- Azure Database for MySQL: Managed MySQL
- Azure Database for PostgreSQL: Managed PostgreSQL
- Cloud SQL (MySQL, PostgreSQL, and SQL Server)
- Global Database - Amazon Aurora, Azure SQL Database, Cloud Spanner

NoSQL
- Build from ground up as distributed databases
- Fast, scalable, distributed for any scale
- Automatically partitions data as it grows
- Automatic scaling (serverless) - Storage and Compute
- Single-digit millisecond response times
- Typical NoSQL databases trade-off "Strong consistency and SQL features" to achieve "scalability and high-performance"

Document Database - Amazon DynamoDB, Azure Cosmos DB SQL API & MongoDB API, Cloud Firestore (Datastore)
- Typically JSON
- Table > item(s),  Kind > Entity
- Other than the primary key, tables are schemaless
- Typically, information in one document would be stored in multiple tables, if you were using a relational database
- Secondary indexes are supported
- Eventually consistent

Key-Value - (Amazon DynamoDB, Azure Cosmos DB Table API, Azure Table Storage)
- Supports simple lookups - query by keys

Graph (n/w, fraud detection) - Amazon Neptune, Azure Cosmos DB Gremlin API

Column Family - Azure Cosmos DB Cassandra API, Cloud BigTable (NOT serverless.)
- large analytical and operational workloads
- IOT streams and real time analytics, financial data - transaction histories, stock prices etc

In-memory Databases - Amazon ElastiCache, Cloud Memorystore, Azure Cache
- Supports Redis and Memcached - Caching, session management, gaming leader boards, geospatial applications

Datawarehousing
relational, exponentially larger reads on the
databases compared to writes, Columnar data storage, High data compression, A single row of data might be stored across multiple nodes, query is distributed for execution

Redshift (Cluster - dynamically add and remove nodes)
Redshift Spectrum (Run SQL queries against datasets in Amazon S3 - Scale storage and compute independently, Eliminate expensive data transfers from S3 to data warehousing solutions)

Azure Synapse Analytics (Earlier called Azure SQL Data Warehouse)

Hadoop (Azure HDInsight, EMR)
- SSH access
- Runs on commodity servers with attached storage (Large clusters - thousands of nodes)
- HDFS vs Object Storage
Hadoop Distributed File System (HDFS): Primary data storage MapReduce: Write Java, Python, .. apps to process data
Enables massive parallelization
HIVE: Query using SQL
Apache Spark: How about processing in-memory?
Really fast: Can be up to 100 times faster than MapReduce (if you make sufficient memory available)
Supports Java, Python, R, SQL and Scala programming languages
Run data analytics, data processing and machine learning workloads
Has become very popular and is offered as a separate service in most cloud platforms!

Databricks (Azure Databricks): Web-based platform for working with Spark
Centralized platform for machine learning, streaming analytics and business intelligence workloads
Founded by the creators of Apache Spark
Automated cluster management


Amazon EMR - Elastic MapReduce


Streaming Data (Retain and replay data)
Kafka
Amazon Kinesis

Asynchronous Communication - Pull Model - SQS
Asynchronous Communication - Push Model - SNS


Data Lakes (Usual big data solutions are complex. How can we make collecting, analyzing (reporting, analytics, machine learning) and visualizing huge data sets easy?)
Typically retains all raw data (compressed)
Flexibility while saving cost
Perform ad-hoc analysis on demand
Analytics & intelligence services (even data warehouses) can directly read from data lake Azure Synapse Analytics, BigQuery(GCP) etc..
- Storage: Object Storage
- Querying: Hadoop (Amazon EMR) or Analytics services (Amazon Redshift, )


AWS CodeCommit - Private source control (Git) (Cloud Source Repositories, Azure DevOps Repositories)
AWS CodePipeline - Orchestrate CI/CD pipelines (Cloud Build)
AWS CodeBuild - Build and Test Code (application packages and containers)
AWS CodeDeploy - Automate Deployment (EC2, ECS, Elastic Beanstalk, EKS, Lambda etc)

Google Cloud Deployment Manager, Cloud Formation

Security (AWS Architect - 546, Google Cloud Architect - 383)


Release Management (Google Cloud Architect - 350)

Total Cost of Ownership(TCO) (Google Cloud Architect - 376)

Shared Responsibility Model (AZ-900 - 49)

Planning for High Availability - 379