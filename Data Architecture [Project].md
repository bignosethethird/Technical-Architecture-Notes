

# TO-BE Information Architecture

## TO-BE Information Flows in Application

Figure: Information Flow

The information flows are summarized in Table xx and described in detail below.

Table: Information flows

Ref|Source|Destination|Description|Frequency|Size
---|------|-----------|-----------|---------|----
1|Client servers|Client|Client content data deployment|Daily|TBA
2|Client|Client servers|Performance data|Operational|TBA
3|ODS|Client servers|Parts availability update|Daily|200KB
4|Product Search|Client servers|Real-time parts search data|Operational|TBA

### Master Data Management

There is no MDM requirement for this project. There are no MDM issues that arise from the implementation of this stage of the project.

### The Value of Created Information

At present, the information created by this application is limited to the following:

Table: Created information

Ref|Information|Description|Level of detail|Usage
---|-----------|-----------|---------------|-----
1|User Interactions|Every user action is logged|Location and user-action level|Usage analysis
2|Client system|All system events|Timestamp|Perf. analysis

### Data Ownership

All data on this solution is owned by [Company].

## Information Flows – Product Search Client

TBA

## Information Flows – Direct Client

TBA

## Business Intelligence

TBA

### Business Performance Monitoring  

TBA

### Business Activity Monitoring

TBA

### Modelling

There is no What-If scenario modeling requirement for this project.

### Data Mining

There is no data mining requirement for this project. It is expected that requirements will eventually emerge. All the necessary components are in place to implement this. The current infrastructure is anticipated to be able to adequately cope with the implementation of these requirements. 

### Reporting (Pre–defined)

There is no pre-built business reporting requirement for this project. However, there is a reporting function that currently delivers performance reports for the purpose of support.

### Reporting (Ad-hoc)

There is no ad-hoc business reporting requirement for this project. However, there is a reporting function that is able to deliver this, should it be required in the future.

## Data Interfaces

### Data Interface #1: [Example]

### Data Interface #2: [Example]

## [PROJECT] Application Database Design

[Repeat this section if thereare multiple databases]

### Metadata Model

Figure: Client Application Metadata Model

Table: Metadata CRUD

Entity|Description|CRUD|Sourced from / Mastered by
------|-----------|----|--------------------------
Client|Determines content to be displayed|R|Content
Users|Authenticates support users|R|Client
Logging|Logs events|C|Client & Content


### Initial Data Take-on

This solution does not require and initial data take-on.

### Data Partner Services

No data is directly provided by other third-party data partners.

### Logical Database Design


Figure: Event Management database design


Figure: Content Management database design


Figure: Logging database design


### Physical Data Architecture

The back-end RDBMS is SQL Server 20XX SP2 and is hosted by [Company] in its data centre. The database holds configurations, user metrics and client content. The full-text search function is reserved for in the design but is not currently used.

Table: Database Architecture for all environments

**Database Instance:.\[PROJECT]**

Database:|APPDB|Mount point|Size GB|%Growth
---------|-----|-----------|-------|-------
|Data|G:|1G|
|Indexes|G:||
|Data Log|H:|
Table Partitions|None|N/A|N/A
|Full-Text Search data|K:|1G|
|Full-Text Search indexes|K:|1G|

Database:|REPORTDB|Mount point|Size GB|%Growth
---------|-----|-----------|-------|-------
|Data|G:|1G|
|Indexes|G:||
|Data Log|H:|
Table Partitions|None|N/A|N/A
|Full-Text Search data|K:|1G|
|Full-Text Search indexes|K:|1G|


Database:|TEMPDB|Mount point|Size GB|%Growth
---------|-----|-----------|-------|-------
|Temp Data|I:|1G|
|Temp Indexes|I:||


## Data Quality and Integrity

There are no explicit data quality or integrity requirements.

### Reconciliation

No data on this application needs to be reconciled.

### Data Quality Controls

There are no checking mechanisms that verify data quality

### Recovery

It is not possible to recover poor-quality data.