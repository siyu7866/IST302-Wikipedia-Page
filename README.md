# IST302-Wikipedia-Page
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
