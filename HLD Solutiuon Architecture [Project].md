High Level Design Solution Architecture
[Project]

Table of Contents

# Introduction 
## Document Purpose 
## Strategic Context and Management Summary 
## Scope 
## Project Timelines 
## [Company] Enterprise Architecture 
## Impact to Operating Model 
## Decommissioning 
# Baseline (AS-IS) Architecture 
## AS-IS Contextual Architecture 
## AS-IS Conceptual Architecture 
## AS-IS Logical Architecture 
## AS-IS Technical Architecture 
## AS-IS Data Architecture 
## AS-IS ETL Processes 
## AS-IS Technical Environments 
## AS-IS Network Architecture 
## AS-IS Error Architecture 
## AS-IS Security Architecture 
## AS-IS Post-Production Architecture 
# To-Be Solution Design 
## TO-BE Contextual Architecture 
## TO-BE Conceptual Architecture 
## TO-BE Logical Architecture 
# TO-BE InfrastructureArchitecture 
## Summary of TO-BE Infrastructure 
## TO-BE Physical Server and Client Device Architecture 
## TO-BE Technical Environments 
## TO-BE Storage Architecture 
# TO-BE Application Architecture 
## Client Management Framework Overview 
# TO-BE Information Architecture 
## Information Flows
## Business Intelligence 
## Data Interfaces 
## [PROJECT] Management Framework’s Database Design 
## Data Quality and Integrity 
# TO-BE Network Architecture 
## Network overview 
## Network Traffic Flows 
## Network Resilience 
## Network Connection Details 
## Network Services 
# TO-BE Security Architecture 
## Security Overview 
## Security Zones 
## Device Security 
# TO-BE Error Architecture 
## TO-BE Post-Production Architecture 
## Backup and Recovery 
## Disaster Recovery 
## Development and Test Environments 
# TO-BE Operations Architecture 
## Solution Dependencies 
## Business Process Dependencies 
## Operational Requirements 
# Solution Review and Assessment 
## Technology Stack Overview 
## Functional Requirements Mapping 
## Non-Functional Requirements Mapping 
## Assessment against Technology Compliance 
## Community Assessment 
## Assessment against IT principles 
## Assessment against Information principles 
## Exceptions from Group IT and GT&A principles 






# Introduction

## Document Purpose

## Strategic Context and Management Summary

## Scope

## Project Timelines

The following milestones and deleivery phases are envisaged in the course of this project:


End of Month | Deliverable
--- | ---
 |
 |


## [Company] Enterprise Architecture

## Decommissioning

### Decommissioning of the AS-IS system

### Decommissioning of the TO-BE system


# Baseline (AS-IS) Architecture

## AS-IS Contextual Architecture 

## AS-IS Conceptual Architecture 

## AS-IS Logical Architecture 

### Definition

### Server Technology

### Client Technology

### Support Technology

## AS-IS Technical Architecture

### Development Environment

### Test and UAT Environment

### Service-side Environment

### Client Environment


## AS-IS Data Architecture

### Database systems

### Data Schemas

## AS-IS ETL Processes

[Example]
There are 3 data loading processes that load external data into the client environment. The processes are described below. They are:

### Data set 1

### Data set 2

### Data set 3


## AS-IS Technical Environments

[Example Options:]
1. The DEV, UAT environments will be reused for the development and test, The existing PRODUCTION environment will be reused on cut-over.
2. New environments, in which case these need to be specified at the same level of details as the AS-IS.

### AS-IS Server Environments

### AS-IS Client Environment

The design of the DEV environment includes capacity for hosting the development of other development projects.One development workstation is required per developer.

Table: Physical Architecture: DEV-environment client definition

Utilisation:| Development Workstation, 1 off per developer
---|---
Location:| Development Centre

Device Description|Specification|Notes
---|---|---
Replication Required|No|
Operating System|Win11|
Patch level |Current|
Patch method|MS SCCM 20xx|
CPUs|xx|
Memory|xxGB|
NICs|xx|
VM Machine|No|
VM High Availability|N/A|
VM Anti-Affinity Rule|N/A|
VM Affinity Rule|N/A|
Applications:|Visual Studio 20xx|Enterprise License
"   |DotNet xx|
"   |Tortoise Subversion|Open-source Plug-In to Visual Studio
"   |SQL Server Express|
"   |IIS x.xx|


### AS-IS DEV Server Environment 

Figure: Development technical environment 


Utilisation:| Database Server
---|---
Location:| Development Centre

Device Description|Specification|Notes
---|---|---
Replication Required|No|
Operating System|W2K19SP1|
Patch level |Current|
Patch method|MS SCCM 20xx|
CPUs|xx|
Memory|xxGB|
NICs|xx|
VM Machine|No|
VM High Availability|N/A|
VM Anti-Affinity Rule|N/A|
VM Affinity Rule|N/A|
Applications:|SQL Server 20xx|Enterprise License
"   |DotNet xx|


Utilisation:| Version Control Server
---|---
Location:| Development Centre

Device Description|Specification|Notes
---|---|---
Replication Required|No|
Operating System|RedHat8.0|
Patch level |Current|
Patch method|RedHat YUM|
CPUs|xx|
Memory|xxGB|
NICs|xx|
VM Machine|No|
VM High Availability|N/A|
VM Anti-Affinity Rule|N/A|
VM Affinity Rule|N/A|
Applications:|GIT|Opensource License
"   |Apache Server|


## AS-IS Storage Architecture 

### AS-IS Storage Overview

This section describes the storage infrastructure in the architecture. Table xx shows a solution overview:

Table: Storage Overview

Requirement|Design
---|---
Storage Capacity|This has not been defined yet and is designed for worst-case - see below.
Performance|This has not been defined yet and is designed for worst-case: a high-performance tier-1 database storage is provided in case the project requires local search capability.
Data Growth|This has not been defined yet and is designed for worst-case
Archiving|There is no archiving in this trial. No requirements defined yet.
Data change rate %|Anticipated 1% daily change


### AS-IS DEV Environment Storage Architecture 

Table: DEV Storage Architecture

Server Node: PVUKxxxyyyIIS01 (Web server)
Local/SAN|OS/Bin/Data/Page|FS|Mapping|Tier|Size(GB)
---------|----------------|---|------|----|--------
SAN|OS|NTFS|C-drive|2|32
SAN|Page|NTFS|D-drive|2|8
SAN|Binaries|NTFS|E-drive|2|32
SAN|Data|NTFS|F-drive|2|32

Server Node: PVUKxxxyyyGIT01 (Version Control server)
Local/SAN|OS/Bin/Data/Page|FS|Mapping|Tier|Size(GB)
---------|----------------|---|------|----|--------
SAN|OS|XFS|/|2|32
SAN|Page|XFS|/swap|2|8
SAN|Binaries|XFS|/opt|2|32
SAN|Data|XFS|/var|2|128

Server Node: PVUKxxxyyySQL01 (Database server)
Local/SAN|OS/Bin/Data/Page|FS|Mapping|Tier|Size(GB)
---------|----------------|---|------|----|--------
SAN|OS|NTFS|C-drive|2|32
SAN|Page|NTFS|D-drive|2|8
SAN|Binaries|NTFS|E-drive|2|32
SAN|Application Data|NTFS|F-drive|2|32
SAN|DB Data|NTFS|F-drive|2|128
SAN|DB Log|NTFS|G-drive|1|32
SAN|DB TempDB|NTFS|H-drive|1|32
SAN|DB Backup|NTFS|I-drive|3|128
SAN|Fulltext Search|NTFS|J-drive|1|32

### AS-IS UAT Environment Storage Architecture 

Table: UAT Storage Architecture

Server Node: PVUKxxxyyyIIS02 (Web server)
Local/SAN|OS/Bin/Data/Page|FS|Mapping|Tier|Size(GB)
---------|----------------|---|------|----|--------
SAN|OS|NTFS|C-drive|2|32
SAN|Page|NTFS|D-drive|2|8
SAN|Binaries|NTFS|E-drive|2|32
SAN|Data|NTFS|F-drive|2|32

Server Node: PVUKxxxyyySQL02 (Database server)
Local/SAN|OS/Bin/Data/Page|FS|Mapping|Tier|Size(GB)
---------|----------------|---|------|----|--------
SAN|OS|NTFS|C-drive|2|32
SAN|Page|NTFS|D-drive|2|8
SAN|Binaries|NTFS|E-drive|2|32
SAN|Application Data|NTFS|F-drive|2|32
SAN|DB Data|NTFS|F-drive|2|128
SAN|DB Log|NTFS|G-drive|1|32
SAN|DB TempDB|NTFS|H-drive|1|32
SAN|DB Backup|NTFS|I-drive|3|128
SAN|Fulltext Search|NTFS|J-drive|1|32


### AS-IS PROD Environment Storage Architecture 

Table: UAT Storage Architecture

Server Node: PVUKxxxyyyIIS03 (Web server)
Local/SAN|OS/Bin/Data/Page|FS|Mapping|Tier|Size(GB)
---------|----------------|---|------|----|--------
SAN|OS|NTFS|C-drive|2|32
SAN|Page|NTFS|D-drive|2|8
SAN|Binaries|NTFS|E-drive|2|32
SAN|Data|NTFS|F-drive|2|32

Server Node: PVUKxxxyyyIIS04 (Web server)
Local/SAN|OS/Bin/Data/Page|FS|Mapping|Tier|Size(GB)
---------|----------------|---|------|----|--------
SAN|OS|NTFS|C-drive|2|32
SAN|Page|NTFS|D-drive|2|8
SAN|Binaries|NTFS|E-drive|2|32
SAN|Data|NTFS|F-drive|2|32


Server Node: PVUKxxxyyySQL02 (Database server)
Local/SAN|OS/Bin/Data/Page|FS|Mapping|Tier|Size(GB)
---------|----------------|---|------|----|--------
SAN|OS|NTFS|C-drive|2|32
SAN|Page|NTFS|D-drive|2|8
SAN|Binaries|NTFS|E-drive|2|32
SAN|Application Data|NTFS|F-drive|2|32
SAN|DB Data|NTFS|F-drive|2|128
SAN|DB Log|NTFS|G-drive|1|32
SAN|DB TempDB|NTFS|H-drive|1|32
SAN|DB Backup|NTFS|I-drive|3|128
SAN|Fulltext Search|NTFS|J-drive|1|32

## AS-IS Network Architecture

### AS-IS DEV Hardware load balancing

There is no hardware load balancing in this environment. 

Table: Hardware Load Balancing
Node|HLB Node|Port|Monitor Method|Server down landing page
---|---|---|---|---
(Node 1)|(Node name)|80|Ping & HTTP Get every 5 seconds, timeout 16 seconds|TBA
(Node 2)|(Node name)|80|Ping & HTTP Get every 5 seconds, timeout 16 seconds|TBA

### AS-IS UAT Hardware load balancing

There is no hardware load balancing in this environment. 

Table: Hardware Load Balancing
Node|HLB Node|Port|Monitor Method|Server down landing page
---|---|---|---|---
(Node 1)|(Node name)|80|Ping & HTTP Get every 5 seconds, timeout 16 seconds|TBA
(Node 2)|(Node name)|80|Ping & HTTP Get every 5 seconds, timeout 16 seconds|TBA


### AS-IS PROD Hardware load balancing

There is hardware load balancing between the two web servers in this environment. 

Table: Hardware Load Balancing
Node|HLB Node|Port|Monitor Method|Server down landing page
---|---|---|---|---
PVUKxxxyyyIIS03|PVUKxxxyyyIIS05|80|Ping & HTTP Get every 5 seconds, timeout 16 seconds|TBA
PVUKxxxyyyIIS04|PVUKxxxyyyIIS05|80|Ping & HTTP Get every 5 seconds, timeout 16 seconds|TBA

### AS-IS Network Traffic – Client

Figure: Client network traffic Steps

Table: Client network traffic Steps

Step | Description | Type | Impact
--- | --- | --- | --- 
1 |  |  | 
2 |  |  | 
3 |  |  | 
4 |  |  | 

### AS-IS Network Traffic – Operational and Support

Figure: Operational and Support network traffic Steps

Table: Operational and Support network traffic Steps

Step | Description | Type | Impact
--- | --- | --- | --- 
1 |  |  | 
2 |  |  | 
3 |  |  | 
4 |  |  | 

### AS-IS Network Resilience

There is no network resilience.

### AS-IS Client Network Details

Figure: Test environment connected to the UAT server environment

Table: Test Client IP Configurations, specific details

Client Id|Use Case|IP address
---|---
1|[test case set 1]|aaa.bbb.ccc.ddd
2|[test case set 1]|aaa.bbb.ccc.eee
3|[test case set 1]|aaa.bbb.ccc.fff
4|[test case set 2]|aaa.bbb.ccc.ggg
5|[test case set 2]|aaa.bbb.ccc.hhh

Table: Test Lab Client IP Configuration – common details

Network Setting|Value
---|---
Gateway|x.x.64.16
Mask|255.255.255.240
DNS1|172.21.7.103
DNS2|172.22.7.103

### AS-IS DEV Server Network Details

### AS-IS UAT Server Network Details

### AS-IS PROD Server Network Details


## AS-IS Error Architecture

## AS-IS Security Architecture 

## AS-IS Post-Production Architecture  


# To-Be Solution Design 

## TO-BE Contextual Architecture 

Figure: TO-BE Contextual architecture

## TO-BE Conceptual Architecture 

Figure: TO-BE Conceptual use case for ...

Figure: TO-BE Conceptual use case for ...

## TO-BE Logical Architecture 

Figure: Logical architecture of the client solution

### TO-BE Client Logical Architecture

### TO-BE Client Physical Architecture

# TO-BE Infrastructure Architecture

## TO-BE Summary of TO-BE Infrastructure

Figure: Infrastructure Overview

## TO-BE Technical Environments

### TO-BE DEV Environment

### TO-BE UAT Environment

### TO-BE PROD Environment


# TO-BE Application Architecture

## Client Management Framework Overview


Figure: Client Management Framework architecture (server-side and client)

Figure xx is a Vendor-supplied representation of the logical architecture of the client-side application and applies to the product search as well as the wine advisor client devices. The data flow on the client application is detailed in Figure xx - also a Vendor-supplied representation.

Note:	A future review session is planned with the vendors to better understand the components’ functions that constitute the application.  

Table: Application Components
Component
Description
Client Application Presentation layer
(See above note)
Client Application Business & Application layer

[PROJECT] Device Executive

Supervisor

iMonitor

iDownloader

Event Logger

iLauncher

Optional pre-processors



Figure: Client application architecture


Figure: Product Search & - Advisor data flow


Figure: Application integration



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

# TO-BE Network Architecture

## Network overview

### Netowrk Architecture Overview

Table: Network Architecture Overview

Network Design|Required|Reason
---|---|---
Load Balancing|Yes|Required for webservers, although not currently used.
SSL Offloading|No|No encrypted traffic
Network Security|Yes|New client devices served by data-centre servers
Network Performance|No|Not anticipated
Network Resilience|Yes|Datacentre internal network resilience. Part of [Company] standard pattern.
Non group-compliant IP Addressing|No|Use group-compliant IP addressing scheme for client devices and data centre devices

## Network Traffic Flows

### Network Traffic – Batch data update

[Example if batches are run]

Figure xx shows the network traffic for daily data updates from the [Company] data back-end to the client solution. This batch is scheduled to run daily at 06:00. Data take-on to all the client devices is completed by 07:00. The total data load per client device is in the region of 200K. This data is eventually distributed to each client.


Figure: Network flows for batch jobs

Table: Network traffic flows - Batch data update

Flow|Route|Purpose|Type|Network|Frequency|Volume
----|-----|-------|----|-------|---------|------
1|Scheduler|AbInitio server|Initiates data extraction process|XML|Data centre network|Daily|Negligible
2|ETL server|Reference data update|ETL process|XML|Data centre network|Daily|Negligible

No potential network bottlenecks are anticipated.

Table: Potential bottlenecks - Batch data update

Risk|Network|Route|Impact
----|-------|-----|------
1|||
2|||

### Network Traffic – Operational and Support

Operational and support traffic is anticipated to exist during standard location operating hours.

Figure xx shows the network traffic.

Figure: Network flows for batch jobs

Table: Network traffic flows - Batch data update

Flow|Route|Purpose|Type|Network|Frequency|Volume
----|-----|-------|----|-------|---------|------
1||||||
2||||||
3||||||
4||||||
5||||||

No potential network bottlenecks are anticipated.

Table: Potential bottlenecks

Risk|Network|Route|Impact
----|-------|-----|------
1|||
2|||

### Network Traffic – Operational and Support

Figure xx shows the network traffic.

Figure: Network flows for batch jobs

Table: Network traffic flows - Batch data update

Flow|Route|Purpose|Type|Network|Frequency|Volume
----|-----|-------|----|-------|---------|------
1||||||
2||||||
3||||||
4||||||
5||||||

No potential network bottlenecks are anticipated.

Table: Potential bottlenecks

Risk|Network|Route|Impact
----|-------|-----|------
1|||
2|||

### Network Traffic – Part Search and Cross reference

Figure xx shows the network traffic.

Figure: Network flows for batch jobs

Table: Network traffic flows - Batch data update

Flow|Route|Purpose|Type|Network|Frequency|Volume
----|-----|-------|----|-------|---------|------
1||||||
2||||||
3||||||
4||||||
5||||||

No potential network bottlenecks are anticipated.

Table: Potential bottlenecks

Risk|Network|Route|Impact
----|-------|-----|------
1|||
2|||

### Network Traffic – Direct Client

Figure xx shows the network traffic.

Figure: Network flows for batch jobs

Table: Network traffic flows - Batch data update

Flow|Route|Purpose|Type|Network|Frequency|Volume
----|-----|-------|----|-------|---------|------
1||||||
2||||||
3||||||
4||||||
5||||||

No potential network bottlenecks are anticipated.

Table: Potential bottlenecks

Risk|Network|Route|Impact
----|-------|-----|------
1|||
2|||


## Network Resilience

[Example if the solution has network resillience]

The servers on all the environments are fully resilient. This is conceptually explained below in Figure xx.

Figure: Conceptual network resilience by intgerconnecting switches, firewalls and load balancers

## Network Connection Details

### Server Network Configuration

Table: Server IP Configurations - Common

Network Device Description|IP Address
--------------------------|----------
DNS|172.21.7.103
DNS|172.22.7.103
Citrix Terminal Server|172.21.80.37
Gateway Server|See Table 38.

Table: Server IP Configuration - Server-specific

**DEV Environment**

Server Type|DNS Name|IP
-----------|--------|---
DB|PVUKDEVKSKDB01.UKROI.[COMPANY].ORG|New
APP|PVUKDEVKSKAPP01.UKROI.[COMPANY].ORG|New
WEB|PVUKDEVKSKIIS01.UKROI.[COMPANY].ORG|New
SCM|TBA|New

**UAT Environment**

Server Type|DNS Name|IP
-----------|--------|---
DB|PVUKTSTKSKDB01.UKROI.[COMPANY].ORG|172.21.181.61/28
APP|PVUKTSTKSKAPP01.UKROI.[COMPANY].ORG|172.21.181.62/28
WEB|PVUKTSTKSKIIS01.UKROI.[COMPANY].ORG|172.21.181.63/27

**PRODUCTION Environment**

Server Type|DNS Name|IP
-----------|--------|---
DB|PVUKPRDKSKDB01.UKROI.[COMPANY].ORG|172.21.177.180/28
APP|PVUKPRDKSKAPP01.UKROI.[COMPANY].ORG|172.21.177.164/28
WEB|PVUKPRDKSKIIS01.UKROI.[COMPANY].ORG|172.21.176.137/27

 
Table: Server Gateways and VLAN

DEV Environment

Server Type|IP|Mask|GW|VLAN
-----------|---|---|---|---
DB||||
APP||||
WEB|||||


UAT Environment

Server Type|IP|Mask|GW|VLAN
-----------|---|---|---|---

DB|172.21.177.244|255.255.255.240|172.21.177.241|353
APP|172.21.177.228|255.255.255.240|172.21.177.225|352
WEB|172.21.177.201|255.255.255.240|172.21.177.198|350

PRODUCTION Environment

Server Type|IP|Mask|GW|VLAN
-----------|---|---|---|---
DB|172.21.177.180|255.255.255.240|172.21.177.177|349
APP|172.21.177.164|255.255.255.240|172.21.177.161|348
WEB|172.21.176.137|255.255.255.224|172.21.176.134|347

### Client Network Configuration

Table: Client IP Configuration - Specific settings

Client location Id|Name|Client Type|IP Address|Format|Patch Info
------------------|----|-----------|----------|------|----------
1|||||
2|||||

Table: Client IP Configuration – Common settings

Network Setting|Value
---|---
Location Network|Class B. See first 2 octets of location IP in Table 
Gateway|x.x.64.16
Mask|255.255.255.0
DNS1|172.21.7.205
DNS2|172.22.7.205
VLAN|410
Proxy|sip-sysapp.ukdmz
Proxy Port|8080
Proxy user|[PROJECT]-allocated ID
Proxy password|[PROJECT]-generated

Table: Remote Site Router Configuration

Network Setting|Value
---|---
DNS1 Helper IP|172.21.7.90
DNS2 Helper IP|172.22.7.90
VLAN|410

## Network Services

### Network File Shares

[Example]

Table: Network File shares on each environment

DEV Environment

Share|Shared from|Access
---|---|---
\\PVUKDEVSKAPP01.UKROI.[COMPANY].ORG\[project]\in|F:\Data\[project]\in|Everyone
\\PVUKDEVSKAPP01.UKROI.[COMPANY].ORG\[project]\out|F:\Data\[project]\out|Everyone

UAT Environment

Share|Shared from|Access
---|---|---
\\PVUKTSTKSKAPP01.UKROI.[COMPANY].ORG\[project]\in|F:\Data\[project]\in|Everyone
\\PVUKTSTKSKAPP01.UKROI.[COMPANY].ORG\[project]\out|F:\Data\[project]\out|Everyone

PRODUCTION Environment

Share|Shared from|Access
---|---|---
\\PVUKPRDKSKAPP01.UKROI.[COMPANY].ORG\[project]\in|F:\Data\[project]\in|Everyone
\\PVUKPRDKSKAPP01.UKROI.[COMPANY].ORG\[project]\out|F:\Data\[project]\out|Everyone


Network services are consumed by the servers and the client devices, as detailed below:

Table: Server-side Network Services

Service|Reason|Details
---|---|---
DNS|Resillience and flexibility and future DR|172.21.7.103, 172.22.7.103
DHCP|No|
WINS|No|
NTP|Yes|TBA
AD|Yes|Domain: XXXX
SMTP|Yes, for SSRS report notification|TBA. Source email: noreply@[company].com


Table: Client Network Services

Service|Reason|Details
---|---|---
DNS|Resillience and flexibility and future DR|172.21.7.103, 172.22.7.103
DHCP|No|
WINS|No|
NTP|Yes|TBA
AD|No|
SMTP|No|


## Network Infrastructure

This section details the resulting network infrastructure

### Conceptual network infrastructure

### Logical network view

### Physical network view

### Switch-configuration context



# TO-BE Security Architecture

## Security Overview

This section explains how security and compliance is implemented for the solution.

Table: Data Compliance

Requiment|Implementation
---------|--------------
Data Sensitivity Classification|Anonymous and not commercially sensitive
Business impact if information is disclosed|Negligeable
Business impact if data is changed by adversary?|Significant
Implementation Approach?|Third-party application
Security operations|Sophos AV on each client and server
Logging of security events & data|Windows Event Logger, stored indeterminately

Table: Legal Compliance

Requiment|Implementation
---------|--------------
Electrical compliance|Yes
Desktop Support Compliance|Yes
Waste compliance|No
Data Protection Act|No
PCI DSS|No
Distance Selling Act|No
Disabilit Discrimination|No

Table: Authentication, Authorisation and Access Control

Requiment|Implementation
---------|--------------
How will users authenticate to the system?|There is no user authentication on client devices. All users are treated as anonymous.
Is Active Directory to be used for authentication|No, as there is no user authentication.
How will users gain authorisation to the system and data?|Users are not required to view system data.
Are passwords transferred over the network in clear text?|No, as there is no user authentication.
Highlight any part of the system not based on the least privilege model?|None.

## Security Zones

Figure xx shows the solution’s security zones and trust boundaries that are implemented by means of firewalls and switches and corresponding network policies. No confidential data is transmitted between the security zones. The zones are:

Table: Security Zones

Security Zone|Description
Un-trusted External|Public network
Un-trusted Internal DMZ|Hosts the access gateway with strong policies
Trusted Internal DMZ|Citrix server farm for access servers in the Trusted Internal zones
Semi-trusted Internal: Location network|User network with restricted policies
Trusted internal: User-facing|Web server
Trusted internal: Application-facing|Application and database server
Trusted internal: Enterprise Services|Product search (and other future services)

Figure xx shows security zones and how they are bound to each other:

Figure: Solution's Security Zones

## Client Device Security

[Example, if the solution entails a dedicated client:]

### Secure Client Enclosure

The client consists of a barebones-PC and touch screen enclosed in a steel cabinet. When closed, the steel cabinet prevents access to the PC. 

The enclosure is secured with a barrel lock, of which there are only two keys. Both barrel keys are in the care of the deployment-location manager.

The client device does not have a mouse or a keyboard. It is also not possible to plug a mouse or a keyboard into the PC unless access is gained into the enclosure. 

### OS build on client devices

The base OS build for the client devices is one that has been accredited by [Company] Desktop Support Services.
All client devices are based on this build. The client devices are not registered on Active Directory.

The build features the following:

    • The build is based on the XXXX Operating System.

    • The client boots up into a default local user account without password authentication. The user account itself is, however, strongly password-protected. This account can only execute client-related processes. 

    • The client has a local administrator account which is password-protected with a strong password. 

    • The client boots up in a local user account and the [PROJECT] Application Launch service is started. This is responsible for launching client applications based on configuration settings.

    • There is no desktop screen or start bar on the screen. With no client application running, the screen displays a neutral grey. 

    • The only way to invoke any response from the device when no interactive application runs, is through the use of a plugged-in keyboard with the Ctrl-Alt-Del key combination.

    • No network port restrictions are in place.

    • The client devices are not part of the XXXX Active Directory (AD) domain.

### Servers on the network

[Example:]
The servers are built according to the standard [Company] build, which mandates certain levels of security. 

They are virtual servers hosted on blade server housed in the Data Centre in a cage. Physical access to the data centre and the cage is controlled by security personnel.

All servers in all 3 environments are on the XXXXX Active Directory (AD) domain.

Remote Desktop Access is enabled and users that belong to the Remote Desktop Group can access the server desktop.

All services run as system service accounts.

### Network Security

[Example:]
Firewall policies ensure that:
    * The UAT web server is the only server that can connect to the test client devices. 
    * Test Client devices can only access servers in the UAT environment.


# TO-BE Error Architecture



# TO-BE Post-Production Architecture 

## Backup and Restore

There is no back-up and recovery process in place for the DEV environment.

There is limited back-up and recovery process in place for the UAT environment.

The PRODUCTION environment has full backup capabilities.

## System recovery

There is no system recovery. This is not a business-critical system.

## Support Model

Support for [component x, component y] is entirely managed by the vendor of these components.

The remainder of this solution is supported by [Company]'s support team.

### Application Codebase

The vendor manages the code base for the duration of this trial.




## Backup and Recovery
In lieu of the fact this project is a trial, no backup has been implemented on any of the environments.

Table: Backup and recovery design
Requirement
Implementation
Backup Details
No local backups, no off-server backups, no off-site backups
Backup Schedule
None.
Backup Durations
N/A
Backup Retention
None.
Additional backup services 
None.
Recovery Services
None.

## Disaster Recovery
There is no DR implemented for this solution.


## Development and Test Environments

Figure: UAT Testing Environment




# TO-BE Operations and Support Architecture

## Solution Dependencies

The following list is a non-exhaustive list of applications and in-flight projects within the [COMPANY] estate that this projects is dependent on.

Table: Projects that this project is dependent on

System/Project|Content|Interface|Comments|I/O
--------------|-------|---------|--------|---
CSD|Product Search|Web service|Hosted on CSD server|
CSD|Image Retrieval|Web service|Hosted on CSD server|
||||

There are no applications or in-flight projects that are dependent on this project:

Table: Projects that are dependent on this project

System/Project|Content|Interface|Comments|I/O
--------------|-------|---------|--------|---
||||
||||
||||


## Operational Requirements

This section provides an overview of the business processes affected by this solution in order to provide an understanding of the operational requirements and how the solution interacts with [Company]'s IT Operations.

Table: Operational Requirements and Implementations

Requirement|Implementation
-----------|--------------
Monitor and alert service view|None
Partner Services|None. 
Systems Management|Windows-based solution
Incident Management|L2 support provided by vendor
Change and Release Management|None. Responsibility of the vendor.
Capacity Management|None
Service Continuity|None
**Solution Front-end:**||
Application Software Delivery|Ad-hoc, delivered by vendor
Client Asset Management|None
Security Auditing|None
Remote Control|MS Terminal Services and VNC
**Solution Back-end:**||
Server Software Delivery|MS SCCM 20XX
"|Red Hat YUM
Patch management|MS SCCM 20XX
"|Red Hat YUM
Security Auditing|None
Remote Control|MS Terminal Services 
"|Linux VNC
"|SSH Terminal
Anti-Malware|Sophos AV
"|Linux Malware Detect

# Solution Review and Assessment

## Technology Stack Overview

Table: Summary of all technologies used by the solution

Technology|Description
---|---
**SQL Server XXXX SP2**|
Version|XXXX
Decision Criteria|RDBMS storage required 98% availability
Options Considered|None. Specified by client
Impact of Technology Choice|None anticipated – the existing solution is SQL Server-based.
**Microsoft .NET Framework**|
Version|X.X
Decision Criteria|None. Specified by client
Options Considered|None
Impact of Technology Choice|None anticipated – .NET is downward-compatible.
**Windows Server O/S**|
Version|XXXX R2
Decision Criteria|None. Specified by client
Options Considered|None. 
Impact of Technology Choice|None anticipated 
**Red Hat Server O/S**|
Version|Enterprise Edition 8.5
Decision Criteria|None. Specified by client
Options Considered|None. 
Impact of Technology Choice|None anticipated 


## Business Requirements Document Mapping

Table: BRD Mapping
Ref.|Requirement|Solution implementation
---|---|---
BRD-1||[Paragraph cross-references]
BRD-2||[Paragraph cross-references]

## Functional Requirements Mapping

Table: FRS Mapping
Ref.|Requirement|Solution implementation
---|---|---
FRS-1||[Paragraph cross-references]
FRS-2||[Paragraph cross-references]

## Non-Functional Requirements Mapping
Table: NFR Mapping
Ref.|Requirement|Solution implementation
---|---|---
NFR-1||[Paragraph cross-references]
NFR-2||[Paragraph cross-references]

## Assessment against Technology Compliance

Table: Technology RAG status

Criteria|RAG|Rationale
---|---|---
**Servers and Devices**||
Complexity|Green|This is a repeatable solution being deployed
Technology|Green|Standard [Company] application and on the roadmap
Volumetric|Green|An increase can be comfortably accommodated
**Storage**||
Complexity|Green|This is a repeatable solution being deployed
Technology|Green|Standard [Company] application and on the roadmap
Volumetric|Green|An increase can be comfortably accommodated
**Network**||
Complexity|Green|This is a repeatable solution being deployed
Technology|Green|Standard [Company] application and on the roadmap
Volumetric|Green|An increase can be comfortably accommodated
**Infrastructure services**||
Complexity|Green|This is a repeatable solution being deployed
Technology|Green|Standard [Company] application and on the roadmap
Volumetric|Green|An increase can be comfortably accommodated
**Application services**||
Complexity|Green|This is a repeatable solution being deployed
Technology|Red|A non-standard [Company] application and not on the roadmap
Volumetric|Green|An increase can be comfortably accommodated
**Security**||
Complexity|Green|This is a repeatable solution being deployed
Technology|Green|Standard [Company] application and on the roadmap
Volumetric|Green|An increase can be comfortably accommodated
**Systems Management**||
Complexity|Green|This is a repeatable solution being deployed
Technology|Green|Standard [Company] application and on the roadmap
Volumetric|Green|An increase can be comfortably accommodated

## Community Assessment

Question|Assessment|Comment
---|---|---
How will the project impact the energy usage of IT?|Increase|New virtual servers
Will the project outcome impact the wider energy or fuel costs of [Company]?|Increase|Business efficiencies will reduce overall energy costs
If dedicated hardware, are there any energy management systems included in the product to ensure power savings?|Yes|Power Management is enabled that scales CPU clock cycles.
Was energy usage a significant factor in the choice of the solution architecture? |No|Not specified by vendor
Other environmental impacts:|Yes|Printing

## Assessment against IT principles

Group IT Principles | RAG | Comment / Exception
---|---|---
**Consistent Delivery**||
Establish common processes and systems worldwide||
Change the business process before changing the package||
Design for group repeatability – build once use many||
Centralise development and support||
**Get it right first time**||
Create an agile environment able to respond to business and systems change||
One version of the truth – there will be one source for key business data||
Only IT does IT||
**Automate complex jobs**||
Flexible & open inter-application data exchange to reduce complexity||
Where practical data should flow through systems, not be batched||
Create solutions that actively identify problems and fix them||
**Understand the marketplace**||
Buy before build except where there is a competitive advantage||
Our systems are secure and legal||
**Cost-effective solutions**||
We will use IT to reduce overall operating costs of the business||


## Assessment against Information principles


Integration Principles

Id|Principle to be met|RAG|Comment
---|---|---|---
1|Design for group repeatability||
2|Create an agile environment able to respond to business and systems change||
3|The Integration Layer is for integration||
4|Flexible and open exchange of data between applications to minimise application spaghetti||
5|Where practical data should flow through the systems, not be daily batches||
6|Supportability is vital||
7|Our data is secure||

Data Principles

Id|Principle to be met|RAG|Comment
---|---|---|---
8|Corporate data is described in a [Company] way.||
9|Design for group repeatability ||
10|One version of the truth||
11 |Corporate data will be made readily available||
12|Data must be owned and managed throughout its life||
13|Data is clean and accurate||
14|Our data is Secure||


## Exceptions from [Company] Technology & Data Architecture principles

Exception: | EXP-1: [Design aspect]
---|---
Principle: |  [Principle that was broken]
Description: |  [How is this principle broken]
Justification: |  [Why is this principle broken]
Recovery Plan: |  [How, if ever, will this be remedied]

Exception: | EXP-2: [Design aspect]
---|---
Principle: |  [Principle that was broken]
Description: |  [How is this principle broken]
Justification: |  [Why is this principle broken]
Recovery Plan: |  [How, if ever, will this be remedied]

