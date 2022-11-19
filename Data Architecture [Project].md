Data Architecture:
[project] 


# Scope

## Identification

This [project] is a [functional description].

## Document Purpose 

The purpose of this Data Architecture Document (DAD) is to outline the data management principles and designs that underpin the [project]. Specifically it provides:

* A description of the contextual, conceptual and logical data models that holds the core information objects that support the intended application
* The high level approach used to exploit the data models in the targeted solution to achieve a seamless data flow and timely delivery, as described by the non-functional requirements
* An overview of all the transformations that the data will undergo
* Specifications of what constitutes acceptable data quality and the approaches that will be used to achieve that data quality
* A summary of all automation processes that relate to the initial data take-on, preparation, ongoing management, rationalization, cleansing and migrating of data
* An overview of reports (tabular and graphic) that will be produced as part of the overall solution, and a brief overview of any reporting tools used to produce these.
* An overview of the types of data analysis and data science-based business intelligence that will be performed on the data
* The high level design of how security is implemented at a data level, as opposed to the security at a network of application level
* A classification of what data into the enterprise’s data classification scheme
* Backing up and data vaulting strategies
* Recoverability strategies on loss of data

## Document Scope 

The DAD specifically presents the data-related aspects of the system

### 	Overview 

This DAD will: 

* Present the data-oriented design aspects and define them 
* Describe the Configurable Items (CI) being implemented
* Describe the software interfaces
* Describe the performance 
* Include design features and the architecture of the project
* Describe attributes of the data architecture that relate to non-functional requirements specified in the NFR:
** Security
** Safety
** Performance
** Data life cycle, from creation to disposal

## Intended Audience 

The target audience for this document includes business, technical and non-technical, governance, and project management stakeholders. Specific users of this document include solution architects, data architects, developers and test analysts. This DAD uses technical terms which should be understandable to the indicated audience.
 

# Data Architecture 

## Design Decisions

The table below identifies key design decisions that were specifically made regarding the data architecture in the [] product. These decisions were made in conjunction with SQEP individuals to ensure agreement across all contributors to the product stack, and complement the overall design set out in the HLD Solution Architecture.

|ID Number|Decision|
|---------|--------|
|DD-01||
|DD-02||

_Table 1 Data Architecture-specific decisions_

The design from the Solution Architecture HLD and the design decisions taken from Table 1 above are used to shape the data architecture below.

The decision rationale is based on the following:


### Limits of legacy database vs new database

[Describe limits in the legacy database that were relevant in choosing in choosing the new database, if any.]

Consider the following trade-offs:

Limit on horizontal scaling
Transactionability and ACID compliance
Database modelling and flexibility

### Benchmarking comparissons




### Choice of Database type and vendor






### Alterntive approches explored with legacy database 

[In the case of a database upgrade, what alternative remedies have been explored, and why were they not implemented instead?]

* Vertical server scaling by upgrading memory or processors
* Horizontal scaling by sharding the database or replicating to multiple read-only instances
* Disk I/O too slow, or too much Disk I/O instead of in-memory processing
* Possible database configuration changes considered
* Database tuning: Table design, indexed, compaction strategies, garbage collections, memory usage, stored procedure fine-tuning
* Storage partitioning schemes to physical storage devices
* Network tuning
* Cache the database front-end
* Expert and vendors consulted?


## Contextual Data Architecture

The contextual data model and data pipeline describes how data is mapped to the business activities to meet the business requirements and flows through the application [Ref. 1]. The sources of external data and internal data generation are described here too.




## Conceptual Data Architecture

### 	Overview

Here we enumerate the high-level data entities that support the application, and how they relate to one another in terms of their cardinality. 
[At this stage, row details are not included since they will be shown in the eventual data model.]




## Logical Data Architecture

### 	Overview

This section describes the data structures used where structured data is used in the application, e.g. normalised, dimensional, and hierarchical, key-value pairs, streamed data, time-series data and images and documents. Any pertinent characteristics in unstructured data used by the application are also enumerated here.

[Examples:]

Figure: Event Management database design

Figure: Content Management database design

Figure: Logging database design


## Physical Data Architecture

### 	Overview

This section describes the physical implementation of the databases, whether the databases is cloud-hosted or on premise hosted. This entails enumerations of the database management systems used in the application, data storages, file systems, directory structures, and any special features offered by the database system in use. Aspects such as table partitioning, data sharding, and other techniques used for distributing data are also described here. Furthermore, aspects of the physical data architecture that relate to disaster recovery (DR), backing up and restoring, and data vaulting and disposal are also described here. 


### 	Vendor choices

[Describe the choice of vendor based on technical capability to meet the data requirements for this application.]



### 	Data Volumetrics

Table 2 lists the estimated data traffic for the database in a typical production setting. This is useful when determining storage design and network design, and ultimately in the database design where incoming streamed data could possibly get lost if it can’t handle the influx.

|Operation|Transactions per Minute (TPM)|Data volume per transaction in KB|Data volume per second (KB/s)|
|---------------------------------------|---------------------------------|-----------------------------|
|Insert|... KB/s|||
|Select|... KB/s|||
|Update|... KB/s|||
|Delete|... KB/s|||

Table 2 Estimated Data traffic

### 	Physical tablespaces on the server

[Example: The back-end RDBMS is SQL Server 20XX SP2 and is hosted by [Company] in its data centre. The database holds configurations, user metrics and client content. The full-text search function is reserved for in the design but is not currently used.]

The tables below show the physical database architecture for all environments, where only one tablespace is used. There is no partitioning of any data tables.

Database Instance: [PROJECT]

Database: APPDB

|Storage|Mount|Size GB|%Growth|
|-------|-----|-------|-------|
|Data Tablespace 1|G:|||
|Indexes Tablespace 1|H:|||
|Data Log Tablespace 1|I:|||
|Table Partitions	|None|N/A|N/A|
|Full-Text Search data	|K:|1G||
|Full-Text Search indexes|K:|1G||

Table 3 Application database server mount points

Database:	REPORTDB	

|Storage|Mount|	Size GB|%Growth|
|-------|-----|--------|-------|
|Data	Tablespace 1|G:|TBA||
|Indexes Tablespace 1|H:|TBA||
|Data Log Tablespace 1|I:|TBA||
|Table Partitions|None|N/A|N/A|
|Full-Text Search data|K:|TBA||
|Full-Text Search indexes|K:|TBA||

Table 4 Report Database server mounts  

Database:	TEMPDB	
|Storage|Mount|Size GB|%Growth|
|-------|-----|-------|-------|
|Temp Data|J:|TBA||
|Temp Indexes|J:|TBA||

Table 5 TempDB server mount points

### 	Data Storage Design

[This section describes the storage for:

1.	Structured data in the relational database:

* Table spaces on the RDBMS, if more that the default
* SAN Data tiering used for each table space on the RDBMS

2.	Unstructured data (documents, audio, images, video) typically makes for 80% of enterprise data. 

3.	Non-relational databases a.k.a. “no-SQL” databases, e.g. key-value stores, graph databases, document stores, column stores

4.	File systems for heterogeneous files.]

[Example for RDBMS storage:]

Server Node:	PVUKxxxyyySQL01 (Database server)

|Local/SAN|OS/Bin/Data/Page|FS|Mapping|Tier|Size(GB)|
|---------|----------------|--|-------|----|--------|
|SAN|OS|NTFS|C-drive|2|32|
|SAN|Page|NTFS|D-drive|2|8|
|SAN|Binaries|NTFS|E-drive|2|32|
|SAN|Application Data|NTFS|F-drive|2|32|
|SAN|DB Data|NTFS|G-drive|2|128|
|SAN|DB Indexes|NTFS|H-drive|2|32|
|SAN|DB Log|NTFS|I-drive|1|32|
|SAN|DB TempDB|NTFS|J-drive|1|32|
|SAN|DB Backup|NTFS|J-drive|3|128|
|SAN|Fulltext Search|NTFS|K-drive|1|32|

Table 6 DEV Database server storage mounts

### 	Initial Data Take-on

This solution does not require and initial data take-on.

### 	Storage Volumetrics

Storage per schema and anticipated growth per annum


### 	Data Storage scalability

[Statement on storage scalability, based on future-proofing requirements in the NFR.]


### 	Data Replication

[Describe the primary database and secondary database integration, role reversal scenarios, physical locations, connectivity, expected network latency
Is the replication synchronous (wait for the replication to complete before committing the transaction) or asynchronous (data is written to the secondary database after it is already committed on the primary server)?]


### 0	High Availability

[Examples are Oracle RAC, High Availability via storage design, and servers on a clustered file system.]


### 1	Distributed System Design

[Aspects of the distributed system design are considered here, if any. Possible server distribution approaches are data sharding a.k.a. fragmentation (each server holds a range of data e.g. geographic unit), multiple servers on a clustered file system, data replication at the storage level, e.g. on storage area networks (SANs) and on many cloud offerings.] 


## Data Interfaces

[This section describes the high-level technical interfaces, data pipelines and user interfaces between the data stores, the applications, the middle-ware and the users. It demonstrates how data can safely, speedily and readily be accessed by these components, and transferred in bulk between them. Any bespoke data services that are used for connectivity are described separately. The detailed technical descriptions for all data interfaces are described in the Interface Control Document (ICD). See Ref. 11.]

## Data Services

[This section describes the data services that exist to access the data from the application. Such services can either be via a function library such as ODBC, JDBC or DBLIB, web services such as ReSTful API or GraphQL, or vendor-bespoke data services as offered in the latest generation of data architectures like Snowflake and Kafka. Also for consideration here are any inter-database service procedure interfaces (SPIs).]



## Information Architecture

[This section describes and classifies the types of information that this application treats, the provenance of the information and the peripheral systems that intend to consume the information.]

### 	AS-IS Information Classes

[Include this section if there is a change in the information classes]


### 	TO-BE Information Classes

[Example of data sets and the respective security classifications. Also indicate what type of operations will be performed to these data sets.]

|Data Type|Source / Mastered by|Security Class|CRUD|
|---------|--------------------|--------------|----|
|User Data|LDAP|Confidential|R|
|Process Events|Application|Internal|CR|
|Parts Data|....|Secret|R|
|Search results|...|Secret|C|
||||

Table 7 TO-BE Information architecture summary


### 	AS-IS Information Flows

[Include this section if there is a change in the information flow in the solution]

### 	TO-BE Information Flows

[Example Figure of information flow between components]

 
The information flows are summarized and described in below in Table 4.
Ref	Source	Destination	Description	Frequency	Size

# Client servers	Client	Client content data deployment	Daily	TBA

# Client	Client servers	Performance data	Operational	TBA

# ODS	Client servers	Parts availability update	Daily	200KB

# Part number Search	Client servers	Real-time parts search data	Operational	TBA
Table 8 Information flows

## Data Partner Services

No data is directly provided by other third-party data partners.
 

# The Processing and Computation of data

## Introduction

Computation on the database itself are, for example, in-flight string manipulations, calculations, aggregations, execution of stored procedures. Other data based computations are performed on other external devices, such as data science-oriented operations, and machine learning (ML) and artificial intelligence (AI) operations such as pattern and image recognitions. As the size of the data grows, the capability of the database management system should also grow, and so should the computational data capability grow. 

The following processes are performed on the data pipeline:

•	Data cleansing
•	Data enrichment
•	General data processing


### 	Data cleansing

No data on this application needs to have any incoming data to be cleansed.

### 	Data enrichment

No data on this application needs to have any incoming data to be enriched.

### 	Reconciliation

No data on this application needs to be reconciled.

### 	General data processing

No further data processes to be performed on the data.

### 	Data Computation scalability

[Statement on computation scalability on the database itself (in-flight string manipulations, calculations, aggregations, stored procedures), based on future-proofing requirements in the NFR.]

This section described how the computational ability of the installed system is allowed to grow as the needs for this increase. 

Possible approaches are:

* Vertical scaling: add more ram, processor cores, clock-speed, 
* Horizontal scaling: add more servers that run massively parallel processes (MPP), or run a map-reduce strategy. Describe how load balancing works and how the resources are negotiated. 
* Elastic scaling in the cloud: The cloud vendor will combine vertical and horizontal scaling approaches and will employ its own approach to resource allocation and load balancing.


## Distributed System Design for Computability

[Aspects of the distributed computation design are considered here, if any. Possible distributed computation approaches are the distributed Spark database or the Apache Impala distributed computation model. The now dated MapReduce approach, as offered by Hadoop et al is also a candidate for making the computational aspects of a database distributed. AI and ML operations can be farmed out to Cloud providers] 

 
# Data Security Architecture

## Introduction

Authentication, authorization and auditing (AAA) are the three pillars of data architecture security. This chapter describes each of these aspects from a high level point of view.

## Authentication 

[Discuss the type of authentication in use by users and processes: Either Password, LDAP, SSL, PPK, API bearer token, SSO, etc…]

This method by which either a user confirms its identity is performed using multi-factor authentication. 

This method by which either a client process confirms its identity is performed using an SSL certificate.

## Authorization

Authorization is the process that grants users or processes various levels of access to data, to carry out specific actions on data, i.e. create, retrieve, update and delete (CRUD), and also under which operational situations these authorizations apply, e.g. which use-cases, rules for specific environments. This may also be coupled with execution rights to specific programs that operate on the data.

### 	Access control for data take-on

[Describe how to connect to for the various use-cases (e.g. engineer, admin, and operator) that will perform production operations]
[Roles and privileges to perform data take on]

|Use case|Role Name|Privileges|Data Entities|
|--------|---------|----------|-------------|
|||||

			
Table 9 Access privileges for data take-on


### 	Access control in production

[Roles and privileges to perform production operations for each use case]

|Use case|Role Name|Privileges|Data Entities|
|--------|---------|----------|-------------|
|||||
			
Table 10 Access privileges in production time


### 	Access control for application and database support

[Often in simple applications, the following is the case:
There are no specific Roles and privileges for database support at the application level. 
The standard  SA account for SQL Server RDBMS and the “sysdba” account for the Oracle RDBMS used.]

|Use case|Role Name|Privileges|Data Entities|
|--------|---------|----------|-------------|
|SQL Server|SA|System|All application and system tables and views|
|Oracle|Sysdba|system|All application and system tables and views|
|||||
	
Table 11 Access privileges for support


### 	Access control for development and testing 

[Roles and privileges for database development]

|Use case|Role Name|Privileges|Data Entities|
|--------|---------|----------|-------------|
|Schema designer||||
|SQL Coder||||
|Unit Tester||||

Table 12 Access privileges for database development and testing

## Auditing

The following database-related events are logged to an audit with timestamped user identifier or process identifier in order to provide a complete trace:

* All DDL changes
* All changes to static configuration and reference data
* All warnings and errors
* Backups and restores
* Shut-downs and restores of the database management system
* User log-ins and log-outs
* Process connects and disconnects

The audit log in the case is a table called “audit”. 

The audit log can be viewed through a SQL development tool and manually-written SQL queries.

The audit log can only be truncated by the database administrator.

 

# Data Visualisation, Reporting and Deep Insights

## Introduction

This section described all data visualisation and reporting techniques used in the application. It is possible that some operational data is also copied to a data warehouse (a dimensional model) for deeper analysis by a self-service business intelligence (BI) tool and machine learning (ML) by data scientists, in which case the mapping between business area and BI domains will also appear here.


## Data Mining

There is no data mining requirement for this project. It is expected that requirements will eventually emerge. All the necessary components are in place to implement this. The current infrastructure is anticipated to be able to adequately cope with the implementation of these requirements.

## Reporting (Pre–defined)

There is no pre-built business reporting requirement for this project. However, there is a reporting function that currently delivers performance reports for the purpose of support.

## Reporting (Ad-hoc)

There is no ad-hoc business reporting requirement for this project. However, there is a reporting function that is able to deliver this, should it be required in the future.

 

# Batch Processes

## Introduction
This chapter lists the batch processes that are run on the database, which perform the following types for functions: 

* Function 1
* Function 2
* Etc…

The batches are controlled by the [SQL Server AT Server, CRON job, Windows AT job, Oracle DBMS_JOB, Airflow, etc…] scheduler.


## Batch Process: 

[State purpose, schedule]

## Batch Process: 

[State purpose, schedule]

 

# Data Backup and Restoring 

## Introduction

[Backup Schedule, what data, to where is it backed up]

 

# Data Disposal Life-cycle

## Data Housekeeping Cycle

[Describe what data can be safely be removed from the immediate production environment.]

## Creation

[How much data is likely to be created in the course of the housekeeping cycle]

## Deletion

[What much data can safely be removed in the course of the housekeeping cycle]


## Archiving and Vaulting

[What much data needs to be archived in the course of the housekeeping cycle, and how to retrieve it whenever needed]. 

 

# Error Architecture

This chapter describes the error handling pattern that is employed across all application components and database stored procedures. Error conditions that arise from the faults on the database are listed in Appendix B Data Error Codes. 

## Local Exception Handling 

[Confirm that the following is to be achieved:
All application code that invokes database procedures should have full exception handling. 
All database stored procedures should have full exception handling]

## Error Logging Strategy

[Describe the error logging strategy, and how the critical log entries are relayed to the application operation dashboard and / or integrated into the enterprise logging service, as described in the solution architecture HLD.]
 
# Data Governance

Data governance is essentially an agreed decision-making model that determines who can do what with which data and what methods to use. The points raised here sets the agreed decision-making framework...

## Introduction

This chapter details the rules used for effective data governance on the application. Here, the personnel or staff-roles of the responsible data owner, data quality stewardship, compliance, retention, disposal and security are enumerated and described. The finer aspects of data treatment to optimize data quality are also described here, e.g. data cleansing, standardisation, categorisation, enrichment, rationalization and any required encryptions.

## Data Quality

### Data quality overview

This section describes the processes used to ensure that the requisite data quality, as specified in the non-functional requirements (NFR), is achieved. In particular, it identifies the data stores that holds the “single source of truth”, highlights special cases where the data needs to be duplicated, how incomplete data is identified and remedied, and the identification and remediation process for any data redundancies.

## Static and Reference data
The maintenance of static and reference data is the responsibility of the data owner. This data rarely changes but it is important to keep it up to date, and to keep a history of the changes to this data.

Reference data sets held by the application are:

* [Glossary, Abbreviations, ISO country codes, ISO currency codes, exchange rates, etc…]

* [Describe the processes to update reference data]

* [Describe how the change history of static and reference data is stored and audited]

## Data lineage

[Data lineage lays out the history of data and all its transformation from creation to consumption and can tell us who owned the data at a given point in time.
Describe for which data entities data lineage is maintained and how the lineage information is held.]

### Data Cleansing and Standardization

[Describe which data entities are cleansed, what aspects are cleansed, and to what format the relevant data is standardised.]

### Categorisation of data

[Describe how the data that is stored and generated by the application would be categorized for possible use in enterprise-wide data lakes and analytics]

### Data Enrichment processes

[Describe what data entities would be subject to any data enrichment processes. This may entail the completion of empty fields in rows, for example in data entities such as addresses, engineering parts, supplier details. I can also entail the categorization and linking of rows in each data entity.]

### Data Rationalization and Master Data Management

[Describe the processes used to identify missing data and duplicate in entities’ data hierarchy.
Example: 
There is no MDM requirement for this project. There are no MDM issues that arise from the implementation of this stage of the project.]

## Data Value

[Describe the value of data that is created within the solution.
Example:
At present, the information created by this application is limited to the following:]

|Ref|Information|Description|Level of detail|Usage|
|---|-----------|-----------|---------------|-----|
|1|User Interactions|Every user action is logged|Location and user-action level|Usage analysis|
|Client system|All system events|Timestamp|Perf. analysis|

Table 13 Created information

## Data ownership and stewardship

[Enumerate which corporate entities owns which data.
Example:  All data on this solution is owned by COMPANY Systems.]

[Enumerate who the data stewards with COMPANY are and what their responsibilities are:]

|Ref|Role|Person(s)|Contact details|
|---|----|---------|---------------|
|1|Data owner||||
|2|Data quality steward, business domain A|||
|3|Data quality steward, business domain B|||
|4|Data protection officer|||

Table 14 Data governance roles

## General Data Protection Regulation (GDPR)

[Even if no personal data is held on the databases, then the data breach reporting process needs to be described.]

### Geographical scope of GDPR

[Describe the geographical scope(s) of the applicable GDPR in use here. The scopes and details of compliancy regulations of the many GDPRs varies by geographical region, but in general they all aim to achieve the same goals.]

### Data breach and reporting process

[Describe how a data breach in this application could conceivably be detected]
[In addition to the standard data breach reporting process within COMPANY Maritime Systems, state any additional reporting steps required for this application.]

### Privacy incident, data complaint and subject data request handling

[Processes should exist so that it is possible to respond in a timely manner to requests about the lineage and lifecycle of private data, and to react to data complaints.]

### Implementation of GDPR

Here we describe how the guiding principles of the GDPR are adhered to in the [appname] application’s data architecture, which are:

|GDPR Principle|Description and Cross-references|
|--------------|--------------------------------|
|Lawfulness, transparency and fairness||
|Purpose of limitation||
|Data minimisation||
|Accuracy||
|Storage limitation||
|Confidentiality and integrity||

Table 15 GDPR principles implementation 
 
# Database Provisioning and Deployment

This chapter describe any special steps to provision or install the RDBMS, and specific configuration that is required on the RDBMS and what data is required to prime the database before the application can be open


This appendix lists the application-specific error codes that can arise from data-specific error conditions.

# Error Codes	Message	Explanation / Remedy
		
Table 16 Data Error Codes

