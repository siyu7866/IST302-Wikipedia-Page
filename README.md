# IST302-Wikipedia-Page
Cloud database provides users database service that is built, deployed and delivered through a cloud platform-as-a-service. Whether it is a relational or non-relational database (structured or unstructured), it permits backend users, organizations, and applications to store, manage and retrieve data from a private, public or hybrid cloud computing infrastructure platform. Popular cloud platforms cloud providers include Amazon Web Service, Microsoft Azure, Google Cloud Platform, Red Hat (IBM), Oracle, etc.

In October 2014, Amazon Web Services offered a relational database built for the cloud called Amazon Aurora and can be used with MySQL and PostgreSQL. Amazon Aurora is faster than standard MySQL and standard PostgreSQL databases. It provides security, availability, and reliability with lower cost and open-source databases.

== Overview ==
Cloud database provides users database service that is built, deployed and delivered through a cloud platform-as-a-service. Whether it is a relational or non-relational database (structured or unstructured), it permits backend users, organizations, and applications to store, manage and retrieve data from a private, public or hybrid cloud computing infrastructure platform<ref> Rouse, M., Sheldon, R., & Shore, J. (2017, February). What is cloud database? - Definition from WhatIs.com. Retrieved November 7, 2019, from https://searchcloudcomputing.techtarget.com/definition/cloud-database.
</ref>. Popular cloud platforms cloud providers include Amazon Web Service, Microsoft Azure, Google Cloud Platform, Red Hat (IBM), Oracle, etc.

Over the years, many companies are trying to migrate their databases into cloud databases. Migrate to cloud databases, especially relational databases, is a strategic way to help manage valuable resources and databases in an efficient manner<ref>Why You Should Move Your Database To The Cloud. (2016, May 2). Retrieved November 7, 2019, from https://micoresolutions.com/moving-database-to-cloud/.</ref>. The cloud providers in the market have been in the race of reduced complexity while delivering a higher level of programming and increased overall effectiveness for the databases.

As mentioned above, Cloud can support relational and non-relational database. However, in this report,  we will focus on relational database only. So what is a relational database?
Relational is a type of database that stores and provides access to data points that has relationship between them<ref>What is a relational database? (n.d.). Retrieved November 13, 2019, from https://www.oracle.com/database/what-is-a-relational-database/.</ref>. The values are stored and organized as a set of tables with columns and rows. The rows in the table represent a collection of related values of one object or entity. Each row in a table could be marked with a unique identifier called a primary key, and rows among multiple tables can be made related using foreign keys<ref>Carter, J. (1995). The relational database. Retrieved from https://aws.amazon.com/relational-database/.</ref>. 

In October 2014, Amazon Web Services offered a relational database built for the cloud called Amazon Aurora and can be used with MySQL and PostgreSQL<ref>Barr, J. (2014, November 14). Amazon Aurora – New Cost-Effective MySQL-Compatible Database Engine for Amazon RDS. Retrieved November 13, 2019, from https://aws.amazon.com/blogs/aws/highly-scalable-mysql-compat-rds-db-engine/.</ref>. According to its website<ref>Amazon Aurora. (n.d.). Retrieved November 13, 2019, from https://aws.amazon.com/rds/aurora/.</ref>, Amazon Aurora is cost-effectiveness at 1/10th cost of commercial-grade databases, its use cases include Enterprise Applications, Software as a Service (SaaS) Application, Web and Mobile Gaming. Amazon Aurora is faster than standard MySQL and standard PostgreSQL databases. It provides security, availability, and reliability with lower cost and open-source databases <ref>Barr, J. (2014, November 14). Amazon Aurora – New Cost-Effective MySQL-Compatible Database Engine for Amazon RDS. Retrieved November 13, 2019, from https://aws.amazon.com/blogs/aws/highly-scalable-mysql-compat-rds-db-engine/.</ref>.

According to Werner Vogels’s blog, a CTO of Amazon.com, in 2019, their Amazon Aurora development team wins the 2019 Association for Computing Machinery’s (ACM) Special Interest Group on Management of Data (SIGMOD) Systems Award <ref>Vogels, W. (2019, July 4). Amazon Aurora development team wins the 2019 ACM SIGMOD Systems Award*. Retrieved November 7, 2019, from https://www.allthingsdistributed.com/2019/07/aurora-sigmod-award.html.</ref>. The Amazon Aurora architectural innovation is a good example of the cloud-native relational database. Aurora has been used by many companies and organizations with various backgrounds and in different industries. The following table contains some of the companies and organizations’ feedbacks about Amazon Aurora and how they use it <ref>Amazon Aurora Customers. (n.d.). Retrieved November 13, 2019, from https://aws.amazon.com/rds/aurora/customers/.</ref>:
{| class="wikitable"
|-
! Company/Organization 
! Feedbacks 
|-
| row1cell1
| "We’re moving much of our on premise database workload, currently MySQL, Sybase, Oracle, and Microsoft SQL Server to Aurora or RDS. Aurora also plays an integral role in our data lake strategy, along with Redshift and S3, as we build out our new advanced analytic platform. Data behind our ASU Alexa skill and ASU mobile app benefits from Amazon Aurora's scalability and high performance as enormous concurrent student users during the school year creates new peak loads each season. And, we see Amazon Aurora Serverless as a next step in our cloud maturity to help us improve development agility while reducing costs on infrequently used systems, to further optimize our overall infrastructure operations."
|-
| row 2 cell 1
| “At Choice Hotels, we process millions of requests every day for guests looking to stay at our properties. Transaction volume has grown over 300 percent in the last three years, and sets new daily records every summer. To accommodate this growth, we undertook a significant challenge and developed the first new global reservation system from a hotel company in over 30 years, and built it on AWS. Leveraging Amazon Aurora and other AWS services allowed us to both exceed our performance requirements and lower our costs.”
|-
| row3cell3
| “Dow Jones’ first legacy on-prem database to Aurora migration was a high-profile workload that plays a critical role in engaging and retaining our customers. We were an early adopter of Aurora and the AWS Database Migration Service, which we’re utilizing to move data from our legacy on-prem environment to Aurora. The migration allowed us to replace a legacy platform with performance challenges that required 400k in DBA staff to manage, with $1M in licensing costs annually, to a cloud-based, highly scalable and resilient solution. It uses a 1TB Aurora cluster with 200 transactions per second, along with replication to another region for high availability and disaster recovery. By moving much of the operational overhead to AWS, and eliminating the need to manage storage completely, Aurora frees up funds for innovation.”
|}

== Amazon Aurora  Performance Optimization ==
Amazon Aurora with MySQL compatibility; performance optimization works for database consolidation. The dimensions that are important include the size of the tables, the number of tables, and the utilization of the database. While working across these dimensions optimization .
=== Optimizing for large tables ===

EX of USE: If you’re in the ad tech, IoT, or consumer applications space, you typically split the database of a large homogeneous application into many shards, each containing a subset of the data. With Aurora, you might not do away with sharing entirely, but you consolidate into fewer shards to reduce operational overhead. (define: highlighted)

Description: Amazon Aurora stores data using 16 KiB pages (KiB = kibibyte is a multiple of the unit byte for quantities of digital information; binary prefix kibi means 2 power of 10, or 1024, 1 KiB = 1024 bytes). Pages are grouped into tablespaces, which act as containers for tables and the associated indexes. By default, Aurora uses a separate tablespace for each table, or for each partition of a table if the table is partitioned. 

Performance Optimization Approach

* Partitions are tool to mitigate performance decreases in large tables. Each partition is stored in a separate tablespace by default, it contains the clustered index, secondary index, and external pages for specific subset of data, as determined by the partitioning expression.
* Indexes
=== Optimizing for number of tables ===

Larger numbers of tables are also an outcome of consolidation. This outcome is common in SaaS applications that require tenant isolation, where each tenant usually has their own database, or set of tables. Multiple tenants of this type are packed together on fewer and larger Aurora clusters to reduce operational cost per tenant.

 

EX of USE:

 

Description:

 

Performance Optimization Approach

 

Larger numbers of tables are also an outcome of consolidation. This outcome is common in SaaS applications that require tenant isolation, where each tenant usually has their own database, or set of tables. Multiple tenants of this type are packed together on fewer and larger Aurora clusters to reduce operational cost per tenant.

Optimizing for utilization of the database –

Utilization of the consolidated database workload increases across a number of metrics, including higher numbers of concurrent connections.
* A description of the performance optimization approach.
* A comparison of the selected software to RDBMS' approach to optimization, including both strengths and weaknesses.
{| class="wikitable"
|-
| 
| RDBMS' approach to optimization (Oracle)
| Aurora with MySQL
|-
| Characteristics
|
| Has maximum limits, storage capacity of 64TB, this represents the upper limit of how large a table could be as well.
|-
| Strengths
| 
| MySQL-compatible database engine, Aurora MySQL inherits many characteristics;
|-
| Shared Characters
| Table partitioning mechanism is Local/Global indexes
| Table partitioning mechanism is different then Oracles (Limited, there is no direct equivalents for Local/Global but by using child and parent table creation it behaves similarly)
|-
| Weaknesses
| 
| MySQL inheriting influences how much consolidation happens.
|}
== Architecture, Data Storage, and Access ==
Oracle Real Application Clusters (Oracle RAC) is considered a standard as one of the most advanced and capable technologies for enabling a highly available and scalable relational database. It relies on a private cloud architecture. Oracle Rac uses Amazon Aurora can serve as a powerful and flexible alternative to Oracle RAC for certain applications. Both Oracle RAC and Amazon Aurora are designed to provide increased availability and performance scalability, but they approach these goals from very different directions using different architectures:

* Oracle RAC uses an intricate end-to-end software stack developed by Oracle—including Oracle Clusterware and Grid Infrastructure, Oracle Automatic Storage Management (ASM), Oracle Net Listener, and the Oracle Database itself—combined with enterprise-grade storage that enables a shared-everything database cluster technology.
* Amazon Aurora simplifies the database technology stack by using AWS ecosystem components to transparently enable higher availability and performance for MySQL and PostgreSQL databases.

=== Oracle RAC Architecture ===
When comparing relational databases, Oracle RAC is a major differentiating feature when compared to other relational database technologies. Oracle RAC is the technology that allows an Oracle database to provide increased levels of availability and performance benefits.

Oracle RAC is an Active database cluster, where multiple Oracle database servers (running Oracle Database instances) access a shared storage device that contains a single set of disk-persistent database files. This architecture is considerably different from what you usually find in a non-Oracle database cluster. Instead of each database node having its own dedicated storage, all the database nodes coordinate and share access to the same physical disks.

All the database nodes coordinate with one another using both a dedicated network-based communication channel (known as the cluster interconnect) and a set of disk-based files.

Public access to the cluster (from incoming applications, SQL queries, users, etc.) is performed using a set of SCAN IPs that are used to load-balance incoming sessions. In addition, each RAC cluster node has its own physical and virtual IP addresses that can be used to open a connection directly to a specific node.

=== Amazon Aurora Architecture ===
Aurora extends MySQL and PostgreSQL in two major ways:

* Adding enhancements to the MySQL/PostgreSQL database kernel itself to improve performance (concurrency, locking, multithreading, etc.)
* Using the capabilities of the AWS ecosystem for greater high availability, disaster recovery, and backup/recovery functionality.

Aurora adds these enhancements without affecting the database optimizer and SQL parser. This means that these changes are completely transparent to the application. By provisioning an Aurora cluster with MySQL compatibility then any MySQL-compatible application can function.

When comparing the Amazon Aurora architecture to Oracle RAC, you can see major differences in how Amazon chooses to provide scalability and increased high availability in Aurora. These differences are due mainly to the existing capabilities of MySQL/PostgreSQL and the strengths that the AWS backend can provide in terms of networking and storage.

Instead of having multiple read/write cluster nodes access a shared disk, an Aurora cluster has a single primary node (“master”) that is open for reads and writes and a set of replica nodes that are open for reads with automatic promotion to primary (“master”) in case of failures. Whereas Oracle RAC uses a set of background processes to coordinate writes across all cluster nodes, the Amazon Aurora Master writes a constant redo stream to six storage nodes, distributed across three Availability Zones in an AWS Region. The only writes that cross the network are redo log records, not pages.

Each Aurora cluster can have one or more instances which serve different purposes:

* At any given time, a single instance functions as the primary (“master”) that handles both writes and reads from applications.
* In addition to the primary (“master”), up to 15 read replicas can be created, which are used for two purposes:
** For performance and read scalability: as read-only nodes for queries/report-type workloads.
** For high availability: as failover nodes in case the master fails. Each read replica can be located in one of the three Availability Zones that hosts your Aurora cluster. A single Availability Zone can host more than one read replica.
=== Comparing Features of Oracle and Aurora ===
{| class="wikitable"
|-
! Feature
! Oracle RAC
! Amazon Aurora
|-
| Storage
| Usually enterprise-grade storage + ASM
| Aurora Storage Nodes: Distributed, Low Latency, Storage Engine Spanning Multiple AZs
|-
| Cluster Type
| 	
Active/Active
* All nodes open for R/W
| Active/Active
* Primary node open for R/W
* Replica nodes open for reads
|-
| Cluster virtual IPs
| R/W load balancing: SCAN IP
| 	
R/W: Cluster endpoint <br/>
+ <br/>
Read load balancing: Reader endpoint
|-
| Transaction (write) TTR from node failure
| Typically 0–30 seconds

| Typically < 30 Seconds
|-
| Max number of cluster nodes
| Theoretical maximum is 100, but smaller clusters (2 – 10 nodes) are far more common
| 15
|- 
| Provides built-in read scaling
| Yes
| Yes
|-
| Provides built-in write scaling
| Yes (with limitations*)
| No
|- 
| Data loss in case of node failure
| No data loss
| No data loss
|-
| Operational complexity
| Requires database, IT, network and storage expertise
| Provided as a cloud-solution
|-
| Scale-up nodes
| Difficult with physical hardware, usually requires to replace servers
| Easy using the AWS UI/CLI
|-
| Scale-out cluster
| Provision, deploy, and configure new servers, unless you pre-allocate a pool of idle servers to scale-out on
| Easy using the AWS UI/CLI
|-
| Database engine
| Oracle
| MySQL or PostgreSQL
|}

== Other Consideration ==

=== Overview of technical aspects of the data management system ===

==== Backup and Recovery ====
A data management system’s backup and recovery is crucial that protect the database’s accessibility and accuracy.

==== Security ====
A data management system’s security is a broad area that encapsulates managing issues ranging from legal, ethical policy to specific system related.<ref> Instructor Insight #10 [Class Handout]. Claremont, CA: Claremont Graduate University, IST 302.</ref>

The aim of security is to protect against the following:

* Loss of Confidentiality
* Loss of Integrity
* Loss of Availability

== Description of Amazon Aurora’s approach to the mentioned technical considerations ==

=== Backup and Recovery ===
This is a technical aspect that AWS has incorporated into Aurora’s barebone design to be reliable, durable, and fault tolerate through the following features:

- Storage Auto-Repair ensures no data is lost even amidst of disk failure with multiple copies of the data in three availability zones. Aurora immediately repairs a segment when the disk volume fails using the other copies, so there is no need to do a manual point-in-time recovery.

- Survivable Cache Warming enhances the data access performance by “warming” the buffer cool cache with the pages of known common queries. Implementing this when the database is starting up or after a failure, user can access common used data more readily.

- Crash Recovery imposes the database to recover from a crash almost instantaneously by performing crash recovery asynchronously on parallel threads so the database remains available for the user even right after a crash. <ref> [https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/Aurora.Overview.StorageReliability.html “Amazon Aurora Storage and Reliability”]. Retrieved November 1, 2019 </ref>

Aurora offers the option for the master user to set the length of the backup retention period from 1 to 35 days. So within the set days, a backup can be restored at any time, with no impact on the database service.<ref> [https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/disaster-recovery-resiliency.html “Resilience in Amazon Aurora”]. Retrieved November 1, 2019 </ref>

=== Security ===
This is a technical aspect highestly prioritized at AWS.

==== Confidentiality ====
With the nature of the database being cloud-based. AWS has third party auditors regularly test and verify the effectiveness of their cloud security, and Aurora is listed as an AWS services in Scope by Compliance Program. Therefore, Aurora is currently in compliance with the following certifications / requirements / standards:<ref> [https://aws.amazon.com/cn/compliance/programs/ “AWS Compliance Programs”].  Retrieved November 1, 2019</ref>

* CSA: Cloud Security Alliance Controls
* ISO 9007: Global Quality Standard
* ISO 27001: Security Management Controls
* ISO 27017: Cloud Specific Controls
* ISO 27018: Personal Data Protection
* PCI DSS Level 1: Payment Card Standards
* SOC 1: Audit Control Reports
* SOC 2: Security, Availability & Confidentiality Report
* SOC 3: General Controls Report

With the nature that database’s security is also deemed by its users, user’s  requirements, and related laws and regulations, Aurora offers the following customizations to meet each unique entity’s security and compliance objectives.

* Run Aurora in Amazon Virtual Private Cloud to have complete control over the virtual networking environment from IP address range, subnets, routing and access control lists.
* Use AWS Identity and Assess Management (IAM) to grant user permissions and level of access.
* Use Secure Socket Layer (SSL) or Transport Layer Security (TLS) connections
* Use Amazon Aurora encryption which is the industry standard AES-256

==== Integrity ====
Aurora empowers its users against improper modification of information through these following Identity and Access Management functionalities:

* Can set up multi-factor authentication (MFA) for each created account
* Can setup API and user activity logging with AWS CloudTrail
* Can use advanced managed security services such as Amazon Macie

==== Availability ====
Aurora promises high availability for its users to be able to always access their database amidst of planned maintenances, failures, and disruptions through the followings factors:

* architecture with separate of storage and compute
* store copies of the data across multiple availability zones in a single AWS region. Aurora will synchronously replicate to six storage nodes, so eliminating I/O freezes, minimizing latency spikes during backups.

=== Comparison of Aurora’s to RDBMS' approach to the technical considerations ===
Aurora is also a relational database engine running on Amazon Relational Database Service (RDS).

== References ==
{{reflist}}
