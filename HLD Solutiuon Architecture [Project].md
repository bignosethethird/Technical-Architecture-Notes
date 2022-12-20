**High Level Design Solution Architecture:**

**[project]**

**Version: []**


[This template is based on a hypothetical system upgrade, which means that there is an AS-IS and a TO-BE aspect, so that the impact and business and technology can clearly be understood once this design is implemented. If this were to be a brand new system, there would not be an AS-IS section. The hypothetical design consists of a client-server project that consists of database servers, internet servers and development-support servers, with three environments: DEV, UAT+TEST and PROD, all on virtual networks. The servers are for now modelled as on premise VMs here, but could just as easily be applied to a cloud-based solution.]

[Note that the Version number and the Document Identity fields are both automatically updated when checked back into SharePoint]


**Document Details**

Document Identity:	[Unique Identifier that DocManagementSystem issues]

**Approvals**

|Role    |Name   |Title                       |Date|
|--------|-------|----------------------------|----|
|Originator|     |                            |    |
|APPROVER|       |SYSTEM DESIGN AUTHORITY     |    |
|APPROVER|	 |ASSISSTANT PROJECT MANAGER  |    |
|APPROVER|	 |SOFTWARE DEVELOPMENT MANAGER|    |
|APPROVER|       |SOFTWARE FUNCTIONAL MANAGER |    |
|REVIEWER|	 |QUALITY ASSURANCE           |    |
|Authoriser|     |                            |    |
|--------|-------|----------------------------|----|

**Distribution**

|Name|Copy|Number|
|---|---|---|
|  |  |   |
|  |  |  |
  
**Document Version History**

|Version|Date|Author|Details|
|---|---|---|---|
| | | | |
| | | | |

		
	
**Definitions and Abbreviations**

Acronym|Description
-----|---
AAA  |Authentication, Authorization and Auditing
API  |Application Programming Interface
BI   |Business Intelligence
BPM  |Business Process Management
CDM  |Common Data Model
CI   |Configurable Items
CICD |Continuous Integration and Continuous Deployment
COTS |Commercial Off The Shelf
CRUD |Create, Retrieve, Update, Delete
CSS  |Cascading Style Sheet
DAD  |Data Architecture Document
ESB  |Enterprise Service Bus
ETL/ELT|Extract, Transform, Load / Extract,, Load, Transform
GIT    |A better code control and versioning system
GraphQL|Hierarchical Graph Query Language
HLD    |High Level Design
HTML   |Hyper Text Mark-up Language
ICD    |Interface Control Document
IT     |Information Technology
JSON   |JavaScript Object Notation
MDM    |Master Data Management
MPP    |Massively Parallel Processes
MVP    |Minimum Viable Product
ReST   |Representational State Transfer
SAN    |Storage Area Network
SQL    |Structured Query Language
SSL    |Secure Sockets Layer
TOGAF  |The Open Group Architecture Framework
UML    |Unified Modelling Language
XML    |Extensible Mark-up Language

 
[To update these indexes, Right-click on each list and select “Update entire table”.]

**Table of Content**

[Add your word processor's TOC link in here]

**List of Figures**

[Add your word processor's TOC link in here]

**List of Tables**

[Add your word processor's TOC link in here]
 

 
# Scope

##	Identification

This [project] is a [functional description].

## Document Purpose 

The purpose of this High Level Design (HLD) is to present the existing AS-IS solution or target estate against the new TO-BE solution, in terms of the application and technology architectures, in order to illustrate how the new solution will fit in the target estate or replace the existing solution and what the impact to peripheral systems already on the estate might be. The information and data architectures are covered in the Data Architecture Document – see Ref. 5. 
It also demonstrates how the solution complies with the prevailing core architectural principles and specifically points out any exception from these principles.

## Management summary

Specifically it provides:
•	A bird’s eye view of the system by describing the contextual, conceptual and logical breakdown of the solution. 
•	Changes or additions of business processes and workflows that are impacted by the introduction of this solution
•	A overview on changes to operational practices and identifies new required skills due to the resulting business changes and the introduction of new technologies that need to be supported or that the system’s users need to be become acquainted with.
•	A description of the application and software modules that are at the heart of the solution
•	Computational hardware, storage and other related system components (crypto-modules, CUDA processing units, AI processing devices, if used)
•	Networking and security , and their respective technical implementations
•	Failover prevention and disaster recovery strategies for this solutions

## Intended Audience 

The target audience for this document includes business, technical and non-technical, governance, and project management stakeholders. Specific users of this document include solution architects, data architects, developers and test analysts. This HLD uses technical terms which should be understandable to the indicated audience.
 
## Document Scope 

This HLD specifically presents the application- and technology-related aspects of the system. The scope of the solution is shown in Figure 1. 


## Enterprise Impact

[Describe what the impact to the peripheral systems would be after the deployment of this solution, e.g. what components will be adversely impacted, or made redundant and removed, or will require users to reskill]


# AS-IS Baseline Architecture 

[There is no need for this AS-IS section if there no existing solution that will be replaced or enhanced by the new solution]

This chapter describes the AS-IS architecture of the existing solution.

## AS-IS Contextual architecture

[Simple description of the business-context under which the solution currently operates.]

Figure: AS-IS Business-contextual architecture

## AS-IS Conceptual architecture

[Show and explant the current user operation in a workflow diagram. Swim lane diagrams with business area or system in each lane]

Figure: AS-IS Conceptual architecture

## AS-IS Logical architecture

[Show the application and computational components, network infrastructure, human interface components and storages currently in use in a figure and tables.]

Figure: AS-IS Logical architecture

### Component Definitions

[Explanation of the above figure, with brief summary of the technologies involved.]

Definition	Vendor	Explanation
		
Table 2 Component definitions and explanations

### Client technology

[Explanation with respect to the above figure, e.g. min browser spec, OS]

### Server technology

[Explanation with respect to the above figure]

### Support technology

[Describe how the AS-IS is supported – does it use VNC, XWindows, RDP, Skype screen share? Who is the current support team? How are software updates performed?]

## AS-IS Application Architecture

[Describe the applications and components in detail, and show their interfaces and how the end result of the business requirements are achieved.]

## AS-IS Technical Environments

[Describe the technical environments that are used to produce the AS-IS design, or are currently supporting the AS-IS design. If they were torn down after the development or deployment, indicate this.
Example Options:
1.	The DEV and the UAT environments will be reused for the development and test, the existing PRODUCTION environment will be reused on cut-over.
2.	New environments, in which case these need to be specified at the same level of details as the AS-IS.]

Environment	|Function	|Status
---|---|---
DEV|Development	|Mothballed
TEST	|Testing	|Mothballed
UAT	|User acceptance	|Mothballed
QA	|Quality Control 	|Mothballed
PROD	|Production	|Active

Table 3 Summary of AS-IS technical environments

###	AS-IS DEV (Development) environment
[Describe the development environment and how developers code on it. Any particular DevOps processes that are worth noting?]



###	AS-IS TEST/UAT/QA environment
[Describe the TEST and UAT environments in terms of servers and storages and network. Any particular DevOps processes that are worth noting, such as the application’s automatic promotion from DEV to TEST to UAT to QA]

###	AS-IS PROD (Production) environment
[Describe the PROD environment in terms of servers and storages and network.]

###	AS-IS Client environment
[Describe the technical aspects of the client – usually a device that support a thin-client interface such as a browser]

Item	Specification
Device	[Company]-Standard laptop
Operating system	Windows 7
Inputs	Mouse, keyboard, touchscreen, headset
Outputs	Graphical screen, printer
Programs	Edge Browser Version 9###10##6 (Official build) (64-bit)
Table 4 AS-IS Client specification


##	AS-IS Client Environments details

###	AS-IS DEV Client Environment

The design of the DEV client environment includes capacity for hosting the development of other development projects. One development workstation is required per developer.

Utilisation:|Development Workstation, 1 off per developer
Location:|Development Centre
Device Description	|Specification	|Notes
---|---|---
Replication Required|No	|
Operating System|Win11|	
Patch level	|Current|
Patch method|MS SCCM 20xx|
CPUs|xx|
Memory|xxGB|
NICs|xx|
VM Machine|No|
VM High Availability|N/A|
VM Anti-Affinity Rule|N/A|
VM Affinity Rule|N/A|
Applications:|Visual Studio 20xx|Enterprise License
 | |DotNet xx	
 | |Tortoise Subversion	Open-source Plug-In to Visual Studio
 | |SQL Server Express	
 | |IIS x.xx	
 
Table 5 Physical Architecture: DEV-environment client definition

###	AS-IS PROD Client Environment

The design of the production client environment includes capacity for hosting the application and other standard, peripheral support applications for communications and documentation.

Utilisation:	Standard issue laptop, 1 off per user
Location:	Operations Centre
Device Description	Specification	Notes
Replication Required	No	
Operating System	Win11	
Patch level	Current	
Patch method	MS SCCM 20xx	
CPUs	xx	
Memory	xxGB	
NICs	xx	
VM Machine	No	
VM High Availability	N/A	
VM Anti-Affinity Rule	N/A	
VM Affinity Rule	N/A	
Applications:	Standard apps	Enterprise License
Table 6 Physical Architecture: PROD-environment client definition

##	AS-IS Server Environments details

###	AS-IS DEV Server Environment

Utilisation:	Database server
Location:	Development Centre
Device Description	Specification	Notes
Replication Required	No	
Operating System	W2K19SP1	
Patch level	Current	
Patch method	MS SCCM 20xx	
CPUs	xx	
Memory	xxGB	
NICs	xx	
VM Machine	Yes	
VM High Availability	No	
VM Anti-Affinity Rule	No	
VM Affinity Rule	No	
Applications:	SQL Server 20xx	Enterprise License
	DotNet xx	
Table 7  Database & App server technical details

Utilisation:	Web server 
Location:	Development Centre
Device Description	Specification	Notes
Replication Required	No	
Operating System	W2K19SP1	
Patch level	Current	
Patch method	MS SCCM 20xx	
CPUs	xx	
Memory	xxGB	
NICs	xx	
VM Machine	Yes	
VM High Availability	No	
VM Anti-Affinity Rule	No	
VM Affinity Rule	No	
Applications:	IIS x.xx	Enterprise License
	DotNet xx	
Table 8  Web server technical details


Utilisation:	Version Control Server
Location:	Development Centre
Device Description	Specification	Notes
Replication Required	No	
Operating System	RedHat##	
Patch level	Current	
Patch method	Red Hat YUM	
CPUs	xx	
Memory	xxGB	
NICs	xx	
VM Machine	No	
VM High Availability	N/A	
VM Anti-Affinity Rule	N/A	
VM Affinity Rule	N/A	
Applications:	GIT	Open source License
	Apache Server	
Table 9  GIT Version Control server technical details

### AS-IS UAT/TEST/QA Server Environment

[Follow with the above DEV example]

### AS-IS PROD Server Environment

[Follow with the above DEV example. It is likely that the production environment will have 2 load-balanced web servers]

## AS-IS Storage Architecture

### AS-IS Storage Overview

This section describes the storage infrastructure in the architecture. Table 8 shows a solution overview:
Requirement	Design
Storage Capacity	This has not been defined yet and is designed for worst-case - see below.
Performance	This has not been defined yet and is designed for worst-case: a high-performance tier-1 database storage is provided in case the project requires local search capability.
Data Growth	This has not been defined yet and is designed for worst-case
Archiving	There is no archiving in this trial. No requirements defined yet.
Data change rate %	Anticipated 1% daily change
Table 10 Storage Overview
###	AS-IS DEV Environment Storage Architecture
This section describes the storage architecture for the DEV environment.
Server Node:	PVUKxxxyyyIIS01 (Web server)
Local/SAN	OS/Bin/Data/Page	FS	Mapping	Tier	Size(GB)
SAN	OS	NTFS	C-drive	2	32
SAN	Page	NTFS	D-drive	2	8
SAN	Binaries	NTFS	E-drive	2	32
SAN	Data	NTFS	F-drive	2	32
Table 11 DEV Web server storage mounts

Server Node:	PVUKxxxyyyGIT01 (GIT Version Control server)
Local/SAN	OS/Bin/Data/Page	FS	Mapping	Tier	Size(GB)
SAN	OS	XFS	/	2	32
SAN	Page	XFS	/swap	2	8
SAN	Binaries	XFS	/opt	2	32
SAN	Data	XFS	/var	2	128
Table 12 DEV Version Control server storage mounts

Server Node:	PVUKxxxyyySQL01 (Database server)
Local/SAN	OS/Bin/Data/Page	FS	Mapping	Tier	Size(GB)
SAN	OS	NTFS	C-drive	2	32
SAN	Page	NTFS	D-drive	2	8
SAN	Binaries	NTFS	E-drive	2	32
SAN	Application Data	NTFS	F-drive	2	32
SAN	DB Data	NTFS	F-drive	2	128
SAN	DB Log	NTFS	G-drive	1	32
SAN	DB TempDB	NTFS	H-drive	1	32
SAN	DB Backup	NTFS	I-drive	3	128
SAN	Fulltext Search	NTFS	J-drive	1	32
Table 13 DEV Database server storage mounts
###	AS-IS UAT Environment Storage Architecture
This section describes the storage architecture for the UAT environment.
Server Node:	PVUKxxxyyyIIS02 (Web server)
Local/SAN	OS/Bin/Data/Page	FS	Mapping	Tier	Size(GB)
SAN	OS	NTFS	C-drive	2	32
SAN	Page	NTFS	D-drive	2	8
SAN	Binaries	NTFS	E-drive	2	32
SAN	Data	NTFS	F-drive	2	32
Table 14 UAT Web server storage mounts

Server Node:	PVUKxxxyyySQL02 (Database server)
Local/SAN	OS/Bin/Data/Page	FS	Mapping	Tier	Size(GB)
SAN	OS	NTFS	C-drive	2	32
SAN	Page	NTFS	D-drive	2	8
SAN	Binaries	NTFS	E-drive	2	32
SAN	Application Data	NTFS	F-drive	2	32
SAN	DB Data	NTFS	F-drive	2	128
SAN	DB Log	NTFS	G-drive	1	32
SAN	DB TempDB	NTFS	H-drive	1	32
SAN	DB Backup	NTFS	I-drive	3	128
SAN	Fulltext Search	NTFS	J-drive	1	32
Table 15 UAT Database server storage mounts
###	AS-IS PROD Environment Storage Architecture
This section describes the storage architecture for the PROD (Production) environment.

Server Node:	PVUKxxxyyyIIS03 (Web server)
Local/SAN	OS/Bin/Data/Page	FS	Mapping	Tier	Size(GB)
SAN	OS	NTFS	C-drive	2	32
SAN	Page	NTFS	D-drive	2	8
SAN	Binaries	NTFS	E-drive	2	32
SAN	Data	NTFS	F-drive	2	32
Table 16 PROD Web server 1 storage mounts

Server Node:	PVUKxxxyyyIIS04 (Web server)
Local/SAN	OS/Bin/Data/Page	FS	Mapping	Tier	Size(GB)
SAN	OS	NTFS	C-drive	2	32
SAN	Page	NTFS	D-drive	2	8
SAN	Binaries	NTFS	E-drive	2	32
SAN	Data	NTFS	F-drive	2	32
Table 17 PROD Web server 2 storage mounts

Server Node:	PVUKxxxyyySQL03 (Database server)
Local/SAN	OS/Bin/Data/Page	FS	Mapping	Tier	Size(GB)
SAN	OS	NTFS	C-drive	2	32
SAN	Page	NTFS	D-drive	2	8
SAN	Binaries	NTFS	E-drive	2	32
SAN	Application Data	NTFS	F-drive	2	32
SAN	DB Data	NTFS	F-drive	2	128
SAN	DB Log	NTFS	G-drive	1	32
SAN	DB TempDB	NTFS	H-drive	1	32
SAN	DB Backup	NTFS	I-drive	3	128
SAN	Fulltext Search	NTFS	J-drive	1	32
Table 18 PROD Database server storage mounts


## AS-IS Network Architecture

[Show the AS-IS devices, how they are connected to the various networks in data centres, locations and clouds, and the information flow of the most pertinent types of transactions. 
Indicate what normal network traffic in production use is, and what support traffic is. 
Also indicate VNets and the network resilience design.]

### AS-IS DEV Hardware load balancing

There is no hardware load balancing in this environment.

### AS-IS UAT Hardware load balancing

There is no hardware load balancing in this environment.

### AS-IS PROD Hardware load balancing

There is hardware load balancing between the two web servers in this environment.

This is achieved on with an F5 network load balancer – see details in Network Architecture chapter.
Node	HLB Node	Port	Monitor Method	Server down landing page
PVUKxxxyyyIIS03	PVUKxxxyyyIIS05	80	Ping & HTTP Get every 5 seconds, timeout 16 seconds	TBA
PVUKxxxyyyIIS04		80	Ping & HTTP Get every 5 seconds, timeout 16 seconds	TBA
Table 19 PROD Hardware Load Balancing

### AS-IS Network Traffic – Client

Figure: Client network traffic steps between network components

Step	Description	Type	Impact
#		
#		
#		
#		

Table 20 Client network traffic Steps

### AS-IS Network Traffic – Operational and Support

Figure: Operational and Support network traffic Steps

Step	Description	Type	Impact
#		
#		
#		
#	

Table 21 Operational and Support network traffic Steps

### AS-IS Network Resilience

There is no network resilience.

### AS-IS Client Network Details

Figure: Test environment connected to the UAT server environment

DEV Environment
Client Id	Use Case	IP
#[test case set 1]	[aaa.bbb.ccc.ddd]
#[test case set 2]	[aaa.bbb.ccc.eee]
#[test case set 3]	[aaa.bbb.ccc.fff]
#[test case set 4]	[aaa.bbb.ccc.ggg]
Table 22 Test Client IP Configurations, specific details

Network Setting	Value
Gateway	x.x.6##6
Mask	25##5##5##40
DNS1	17#####03
DNS2	17#####03
Table 23 Test Client IP Configuration – common details
###	Server Network Connection Details

###.1	Network settings common to all environments

Network Device Description	IP Address
DNS	17#####03
DNS	17#####03
Citrix Terminal Server	17######7
Gateway Server	See Table 33.

Table 24  Server IP Configurations - Common
###.2	DEV Environment

Server Type	DNS Name	IP
DB	PVUKDEVKSKDB01.[DOMAIN].[Company].ORG	New
APP	PVUKDEVKSKAPP01.[DOMAIN].[Company].ORG	New
WEB	PVUKDEVKSKIIS01.[DOMAIN].[Company].ORG	New
SCM	TBA	New

Table 25 Server IP Configuration – DEV Server-specific

Server Type	IP	Mask	GW	VLAN
DB	17####7##80	25##5##5##40	17####7##77	343
APP	17####7##64	25##5##5##40	17####7##61	342
WEB	17####7##37	25##5##5##24	17####7##34	341

Table 26 DEV Server Gateways and VLAN

###.3	UAT Environment

Server Type	DNS Name	IP
DB	PVUKTSTKSKDB01.[DOMAIN].[Company].ORG	17####8##1/28
APP	PVUKTSTKSKAPP01.[DOMAIN].[Company].ORG	17####8##2/28
WEB	PVUKTSTKSKIIS01.[DOMAIN].[Company].ORG	17####8##3/27
Table 27 Server IP Configuration – UAT Server-specific
Server Type	IP	Mask	GW	VLAN
DB	17####7##80	25##5##5##40	17####7##77	346
APP	17####7##64	25##5##5##40	17####7##61	345
WEB	17####7##37	25##5##5##24	17####7##34	344

Table 28 UAT Server Gateways and VLAN

###.4	PRODUCTION Environment

Server Type	DNS Name	IP
DB	PVUKPRDKSKDB01.[DOMAIN].[Company].ORG	17####7##80/28
APP	PVUKPRDKSKAPP01.[DOMAIN].[Company].ORG	17####7##64/28
WEB	PVUKPRDKSKIIS01.[DOMAIN].[Company].ORG	17####7##37/27
Table 29 Server IP Configuration – PROD Server-specific
Server Type	IP	Mask	GW	VLAN
DB	17####7##80	25##5##5##40	17####7##77	349
APP	17####7##64	25##5##5##40	17####7##61	348
WEB	17####7##37	25##5##5##24	17####7##34	347
Table 30 PROD Server Gateways and VLAN

###	Client Network Connection Details
###.1	Configuration of Clients on the Network 

Client location	Name	Client Type	IP Address	Format	Patch Info
#				
#				
Table 31 Client IP Configuration - Specific settings

Network Setting	Value
Location Network	Class B. See first 2 octets of location IP in Table
Gateway	x.x.6##6
Mask	25##5##5##
DNS1	17#####05
DNS2	17#####05
VLAN	410
Proxy	sip-sysapp.ukdmz
Proxy Port	8080
Proxy user	[PROJECT]-allocated ID
Proxy password	[PROJECT]-generated
Table 32 Client IP Configuration – Common settings

Network Setting	Value
DNS1 Helper IP	17#####0
DNS2 Helper IP	17#####0
VLAN	410
Table 33  Remote Site Router Configuration

## AS-IS Error Architecture

[Describe error handling, logging, notifications, error severities, integration with the estate’s operational monitoring system]

## AS-IS Security Architecture

[Describe pertinent security features, such as encryption on the move and at rest, authentication mechanisms, access-controlled roles and allowed operations.]

## AS-IS Post-Go-Live Architecture

[Describe the support system in place for this solution, contact details to first line support of the respective vendors involved]
 
# TO-BE Solution Design
This section describes the TO-BE architecture of the future solution that will be applied.
##	TO-BE Contextual Architecture
[Simple description of the business-context under which the solution currently operates. Clearly indicate the changes if any between the AS-IS and the TO-BE versions.]

Figure: TO-BE Contextual architecture
###	TO-BE Conceptual Architecture

[Show and explain the current user operation in a workflow diagram. Swim lane diagrams with business area or system in each lane. Clearly indicate the changes if any between the AS-IS and the TO-BE versions.]


Figure: TO-BE Conceptual use case for ...
##	TO-BE Logical Architecture
[Show the application and computational components, human interface components and storages currently in use. Show in a figure. Clearly indicate the changes if any between the AS-IS and the TO-BE versions]

Figure: Logical architecture of the client solution
###	TO-BE Component Definitions

 [Explanation of the above figure, with brief summary of the technologies involved. Indicate the new or changed components.]

Definition	Vendor	Explanation
		
		
		
Table 34 Component definitions and explanations

### Client technology

[Explanation with respect to the above figure, e.g. min browser spec, OS, if different to the AS-IS ]

### Server technology

[Explanation with respect to the above figure, if different to the AS-IS]


### Support technology

[Describe how the TO-BE is supported if different to the AS-IS]

 
## TO-BE Technical Environments

 [Describe the technical environments that will be deployed, if they are different to the AS-IS. If they will be torn down after the development or deployment, indicate this. Example: 3 environments. Normally QA, TEST and UAT are separate environments]

[Describe the technical environments that are used to produce the AS-IS design, or are currently supporting the AS-IS design. If they were torn down after the development or deployment, indicate this.
Example Options:
1.	The DEV, UAT environments will be reused for the development and test, The existing PRODUCTION environment will be reused on cut-over.
2.	New environments, in which case these need to be specified at the same level of details as the AS-IS.]

Environment	Function	Status
DEV	Development	Active
UAT/TEST/QA	Test,QA,User Acceptance	Active
PROD	Production	Active
Table 35 Summary of TO-BE technical environments

### TO-BE DEV Environment

### TO-BE UAT Environment

### TO-BE PROD Environment


### TO-BE Client environment

[Describe the technical aspects of the client – usually a device that support a thin-client interface such as a browser]

Item	Specification
Device	[Company]-Standard laptop
Operating system	Windows 7
Inputs	Mouse, keyboard, touchscreen, headset
Outputs	Graphical screen, printer
Programs	Edge Browser Version 9###10##6 (Official build) (64-bit)
Table 36 AS-IS Client specification


##	TO-BE Client Environments details

###	TO-BE DEV Client Environment

The design of the DEV client environment includes capacity for hosting the development of other development projects. One development workstation is required per developer.

Utilisation:	Development Workstation, 1 off per developer
Location:	Development Centre
Device Description	Specification	Notes
Replication Required	No	
Operating System	Win11	
Patch level	Current	
Patch method	MS SCCM 20xx	
CPUs	xx	
Memory	xxGB	
NICs	xx	
VM Machine	No	
VM High Availability	N/A	
VM Anti-Affinity Rule	N/A	
VM Affinity Rule	N/A	
Applications:	Visual Studio 20xx	Enterprise License
	DotNet xx	
	GIT client	Open-source Plug-In to Visual Studio
	SQL Server Express	
	IIS x.xx	
Table 37 Physical Architecture: DEV-environment client definition

###	TO-BE UAT Client Environment

The design of the UAT client environment includes capacity for hosting the application and other standard, peripheral support applications for communications and documentation.
UAT testing will be conducted in a secure test environment by testers. Testing will commence following user training and completion of the relevant test plans.

Utilisation:	Standard issue laptop, 1 off per user
Location:	Secure Testing Centre
Device Description	Specification	Notes
Replication Required	No	
Operating System	Win11	
Patch level	Current	
Patch method	MS SCCM 20xx	
CPUs	xx	
Memory	xxGB	
NICs	xx	
VM Machine	No	
VM High Availability	N/A	
VM Anti-Affinity Rule	N/A	
VM Affinity Rule	N/A	
Applications:	Standard apps	Enterprise License
	GIT client	Open-source Plug-In to Visual Studio
	Test Console	Test management application
	Test system	System under test with apps and libs
Table 38 Physical Architecture: UAT-environment client definition


###	TO-BE PROD Client Environment

The design of the production client environment includes capacity for hosting the application and other standard, peripheral support applications for communications and documentation.

Utilisation:	Standard issue laptop, 1 off per user
Location:	Secure Operations Centre
Device Description	Specification	Notes
Replication Required	No	
Operating System	Win11	
Patch level	Current	
Patch method	MS SCCM 20xx	
CPUs	xx	
Memory	xxGB	
NICs	xx	
VM Machine	No	
VM High Availability	N/A	
VM Anti-Affinity Rule	N/A	
VM Affinity Rule	N/A	
Applications:	Standard apps	Enterprise License
	Test system	System under test with apps and libs
Table 39 Physical Architecture: PROD-environment client definition

##	TO-BE Server Environments details

###	TO-BE DEV Server Environment
This section lists the servers in the DEV environment. The code repository service is a shared service between other projects.

Utilisation:	Database Server
Location:	Development Centre
Device Description	Specification	Notes
Replication Required	No	
Operating System	W2K19SP1	
Patch level	Current	
Patch method	MS SCCM 20xx	
CPUs	xx	
Memory	xxGB	
NICs	xx	
VM Machine	Yes	
VM High Availability	No	
VM Anti-Affinity Rule	No	
VM Affinity Rule	No	
Applications:	SQL Server 20xx	Enterprise License
Table 40  Database server technical details

Utilisation:	Web server 
Location:	Development Centre
Device Description	Specification	Notes
Replication Required	No	
Operating System	W2K19SP1	
Patch level	Current	
Patch method	MS SCCM 20xx	
CPUs	xx	
Memory	xxGB	
NICs	xx	
VM Machine	Yes	
VM High Availability	No	
VM Anti-Affinity Rule	No	
VM Affinity Rule	No	
Applications:	IIS x.xx	Enterprise License
	DotNet xx	
Table 41  Web server technical details


Utilisation:	Version Control Server
Location:	Development Centre
Device Description	Specification	Notes
Replication Required	No	
Operating System	RedHat##	
Patch level	Current	
Patch method	Red Hat YUM	
CPUs	xx	
Memory	xxGB	
NICs	xx	
VM Machine	No	
VM High Availability	N/A	
VM Anti-Affinity Rule	N/A	
VM Affinity Rule	N/A	
Applications:	GIT	Open source License
	Apache Server	
Table 42  GIT Version Control server technical details


###	TO-BE UAT/TEST/QA Server Environment
[Follow the above DEV example]

###	TO-BE PROD Server Environment
[Follow the above DEV example. It is likely that the production environment will have 2 load-balanced web servers]


##	TO-BE Storage Architecture
###	TO-BE Storage Overview
This section describes the storage infrastructure in the architecture. Table 9 shows a solution overview:
Requirement	Design
Storage Capacity	This has not been defined yet and is designed for worst-case - see below.
Performance	This has not been defined yet and is designed for worst-case: a high-performance tier-1 database storage is provided in case the project requires local search capability.
Data Growth	This has not been defined yet and is designed for worst-case
Archiving	There is no archiving in this trial. No requirements defined yet.
Data change rate %	Anticipated 1% daily change
Table 43 Storage Overview
###	TO-BE DEV Environment Storage Architecture
This section describes the storage architecture for the DEV environment.
Server Node:	PVUKxxxyyyIIS01 (Web server)
Local/SAN	OS/Bin/Data/Page	FS	Mapping	Tier	Size(GB)
SAN	OS	NTFS	C-drive	2	32
SAN	Page	NTFS	D-drive	2	8
SAN	Binaries	NTFS	E-drive	2	32
SAN	Data	NTFS	F-drive	2	32
Table 44 DEV Web server storage mounts

Server Node:	PVUKxxxyyyGIT01 (GIT Version Control server)
Local/SAN	OS/Bin/Data/Page	FS	Mapping	Tier	Size(GB)
SAN	OS	XFS	/	2	32
SAN	Page	XFS	/swap	2	8
SAN	Binaries	XFS	/opt	2	32
SAN	Data	XFS	/var	2	128
Table 45 DEV Version Control server storage mounts

Server Node:	PVUKxxxyyySQL01 (Database server)
Local/SAN	OS/Bin/Data/Page	FS	Mapping	Tier	Size(GB)
SAN	OS	NTFS	C-drive	2	32
SAN	Page	NTFS	D-drive	2	8
SAN	Binaries	NTFS	E-drive	2	32
SAN	Application Data	NTFS	F-drive	2	32
SAN	DB Data	NTFS	F-drive	2	128
SAN	DB Log	NTFS	G-drive	1	32
SAN	DB TempDB	NTFS	H-drive	1	32
SAN	DB Backup	NTFS	I-drive	3	128
SAN	Fulltext Search	NTFS	J-drive	1	32
Table 46 DEV Database server storage mounts
###	TO-BE UAT Environment Storage Architecture
This section describes the storage architecture for the UAT environment.
Server Node:	PVUKxxxyyyIIS02 (Web server)
Local/SAN	OS/Bin/Data/Page	FS	Mapping	Tier	Size(GB)
SAN	OS	NTFS	C-drive	2	32
SAN	Page	NTFS	D-drive	2	8
SAN	Binaries	NTFS	E-drive	2	32
SAN	Data	NTFS	F-drive	2	32
Table 47 UAT Web server storage mounts

Server Node:	PVUKxxxyyySQL02 (Database server)
Local/SAN	OS/Bin/Data/Page	FS	Mapping	Tier	Size(GB)
SAN	OS	NTFS	C-drive	2	32
SAN	Page	NTFS	D-drive	2	8
SAN	Binaries	NTFS	E-drive	2	32
SAN	Application Data	NTFS	F-drive	2	32
SAN	DB Data	NTFS	F-drive	2	128
SAN	DB Log	NTFS	G-drive	1	32
SAN	DB TempDB	NTFS	H-drive	1	32
SAN	DB Backup	NTFS	I-drive	3	128
SAN	Fulltext Search	NTFS	J-drive	1	32
Table 48 UAT Database server storage mounts
###	TO-BE PROD Environment Storage Architecture
This section describes the storage architecture for the PROD (Production) environment.

Server Node:	PVUKxxxyyyIIS03 (Web server)
Local/SAN	OS/Bin/Data/Page	FS	Mapping	Tier	Size(GB)
SAN	OS	NTFS	C-drive	2	32
SAN	Page	NTFS	D-drive	2	8
SAN	Binaries	NTFS	E-drive	2	32
SAN	Data	NTFS	F-drive	2	32
Table 49 PROD Web server 1 storage mounts

Server Node:	PVUKxxxyyyIIS04 (Web server)
Local/SAN	OS/Bin/Data/Page	FS	Mapping	Tier	Size(GB)
SAN	OS	NTFS	C-drive	2	32
SAN	Page	NTFS	D-drive	2	8
SAN	Binaries	NTFS	E-drive	2	32
SAN	Data	NTFS	F-drive	2	32
Table 50 PROD Web server 2 storage mounts

Server Node:	PVUKxxxyyySQL03 (Database server)
Local/SAN	OS/Bin/Data/Page	FS	Mapping	Tier	Size(GB)
SAN	OS	NTFS	C-drive	2	32
SAN	Page	NTFS	D-drive	2	8
SAN	Binaries	NTFS	E-drive	2	32
SAN	Application Data	NTFS	F-drive	2	32
SAN	DB Data	NTFS	F-drive	2	128
SAN	DB Log	NTFS	G-drive	1	32
SAN	DB TempDB	NTFS	H-drive	1	32
SAN	DB Backup	NTFS	I-drive	3	128
SAN	Fulltext Search	NTFS	J-drive	1	32
Table 51 PROD Database server storage mounts

 
##	TO-BE Application Architecture
[Describe the applications that makeup the solution and their respective components in detail, and show their interfaces and how the end result of the business requirements are achieved.]

###	[AppName1] Overview

 
Figure 2 [Example application and its components]

[Example: Figure 2 is a Vendor-supplied representation of the logical architecture of the client-side application and applies to the product. The data flow on the client application is detailed in Figure xx - also a Vendor-supplied representation.]
Component	Description	Presentation layer	Business layer	Integration layer	System support layer
Device Executive					
Supervisor					
Monitor					
Downloader					
Event Logger					X
Table 52  Application Components for client

###	[AppName2] Overview

[Rinse and repeat for every application in the solution]

##	TO-BE Error Architecture
[Describe error handling, logging, notifications, error severities, integration with the estate’s operational monitoring system]
 
#TO-BE Network Architecture

[Show the TO-BE devices, how they are connected to the various networks in data centres, locations and clouds, and the information flow of the most pertinent types of transactions. 
Indicate what is normal network traffic in production use, and what is support traffic. 
Also indicate VNets and the network resilience design.]

##	Network Architecture Overview

Network Design	Required	Reason
Load Balancing	Yes	Required for webservers, although not currently used.
SSL Offloading	No	No encrypted traffic
Network Security	Yes	New client devices served by data-centre servers
Network Performance	No	Not anticipated
Network Resilience	Yes	Datacentre internal network resilience. Part of [Company] System standard pattern.
Non group-compliant IP Addressing	No	Use group-compliant IP addressing scheme for client devices and data centre devices
Table 53 Network Architecture Overview
##	Network Traffic
###	Network Traffic – Batch data update

[Example if batches are run:]
Figure xx shows the network traffic for daily data updates from the [Company] System data back-end to the client solution. This batch is scheduled to run daily at 06:00. Data take-on to all the client devices is completed by 07:00. The total data load per client device is in the region of 200K. This data is eventually distributed to each client.



Figure: Network flows for batch jobs

Flow	Route	Purpose	Type	Frequency	Volume
#Data centre	AbInitio server	Initiates data extraction process	Daily	5MB
#Data centre	Reference data update	ETL process	Daily	5MB
Table 54 Network traffic flows - Batch data update
No potential network bottlenecks are anticipated.
 Risk	Network	Route	Impact
#		
#		
Table 55 Potential bottlenecks - Batch data update

###	Network Traffic – Operational and Support
Operational and support traffic is anticipated to exist during standard operating hours in the standard location
Figure xx shows the network traffic.
Figure: Network flows for batch jobs
Flow	Route	Purpose	Type	Network	Frequency	Volume
#					
#					
#					
#					
#					
Table 56 Network traffic flows - Batch data update

No potential network bottlenecks are anticipated.

Risk	Network	Route	Impact
#		
#		
Table 57 Potential bottlenecks - Operational support
###	Network Traffic – Part Search and Cross reference
Figure xx shows the network traffic.
Figure: Network flows for batch jobs
Flow	Route	Purpose	Type	Network	Frequency	Volume
#					
#					
#					
#					
#					
Table 58 Network traffic flows – Part Search and cross reference
No potential network bottlenecks are anticipated.
Risk	Network	Route	Impact
#		
#		
Table 59 Potential bottlenecks - Part Search and cross reference
###	Network Traffic – Direct Client
Figure xx shows the client network traffic.
Figure: Network flows for client network traffic.
Flow	Route	Purpose	Type	Network	Frequency	Volume
#					
#					
#					
#					
#					
Table 60 Network traffic flows – client network traffic.
No potential network bottlenecks are anticipated.
Risk	Network	Route	Impact
#		
#		
Table 61 Potential bottlenecks - Client network traffic.
##	Network Resilience
[Example if the solution has network resilience]
The servers on all the environments are fully resilient. This is conceptually explained below in Figure xx.
Figure: Conceptual network resilience by interconnecting switches, firewalls and load balancers
##	Server Network Connection Details

###	Network settings common to all environments

Network Device Description	IP Address
DNS	[TBA]
DNS	[TBA]
Citrix Terminal Server	[TBA]
Gateway Server	[TBA]
Table 62  Server IP Configurations - Common
###	DEV Environment

Server Type	DNS Name	IP
DB	PVUKDEVKSKDB01.[DOMAIN].[Company].ORG	New
APP	PVUKDEVKSKAPP01.[DOMAIN].[Company].ORG	New
WEB	PVUKDEVKSKIIS01.[DOMAIN].[Company].ORG	New
SCM	TBA	New
Table 63 Server IP Configuration – DEV Server-specific

Server Type	IP	Mask	GW	VLAN
DB	[TBA]	25##5##5##40	[TBA]	343
APP	[TBA]	25##5##5##40	[TBA]	342
WEB	[TBA]	25##5##5##24	[TBA]	341
Table 64 DEV Server Gateways and VLAN

###	UAT Environment

Server Type	DNS Name	IP
DB	PVUKTSTKSKDB01.[DOMAIN].[Company].ORG	17####8##1/28
APP	PVUKTSTKSKAPP01.[DOMAIN].[Company].ORG	17####8##2/28
WEB	PVUKTSTKSKIIS01.[DOMAIN].[Company].ORG	17####8##3/27
Table 65 Server IP Configuration – UAT Server-specific
Server Type	IP	Mask	GW	VLAN
DB	[TBA]	25##5##5##40	[TBA]	346
APP	[TBA]	25##5##5##40	[TBA]	345
WEB	[TBA]	25##5##5##24	[TBA]	344
Table 66 UAT Server Gateways and VLAN

###	PRODUCTION Environment

Server Type	DNS Name	IP
DB	PVUKPRDKSKDB01.[DOMAIN].[Company].ORG	[TBA]/28
APP	PVUKPRDKSKAPP01.[DOMAIN].[Company].ORG	[TBA]/28
WEB	PVUKPRDKSKIIS01.[DOMAIN].[Company].ORG	[TBA]/27
Table 67 Server IP Configuration – PROD Server-specific
Server Type	IP	Mask	GW	VLAN
DB	[TBA]	25##5##5##40	[TBA]	349
APP	[TBA]	25##5##5##40	[TBA]	348
WEB	[TBA]	25##5##5##24	[TBA]	347
Table 68 PROD Server Gateways and VLAN

##	Client Network Connection Details
###	Configuration of Clients on the Network 

Client location	Name	Client Type	IP Address	Format	Patch Info
#				
#				
Table 69 Client IP Configuration - Specific settings

Network Setting	Value
Location Network	Class B. See first 2 octets of location IP in Table
Gateway	x.x.6##6
Mask	25##5##5##
DNS1	[TBA]
DNS2	[TBA]
VLAN	410
Proxy	[TBA]
Proxy Port	8080
Proxy user	[PROJECT]-allocated ID
Proxy password	[PROJECT]-generated
Table 70 Client IP Configuration – Common settings

Network Setting	Value
DNS1 Helper IP	[TBA]
DNS2 Helper IP	[TBA]
VLAN	410
Table 71  Remote Site Router Configuration
##	Network Services
###	Network File Shares
[Example given below:]
DEV Environment
Share	Shared from	Access
\PVUKDEVSKAPP01.[DOMAIN].[Company].ORG\[project]\in	F:\Data[project]\in	Everyone
\PVUKDEVSKAPP01.[DOMAIN].[Company].ORG\[project]\out	F:\Data[project]\out	Everyone
Table 72 Network File shares on DEV environment
UAT Environment
Share	Shared from	Access
\PVUKTSTKSKAPP01.[DOMAIN].[Company].ORG\[project]\in	F:\Data[project]\in	Everyone
\PVUKTSTKSKAPP01.[DOMAIN].[Company].ORG\[project]\out	F:\Data[project]\out	Everyone
Table 73 Network File shares on UAT environment
PRODUCTION Environment
Share	Shared from	Access
\PVUKPRDKSKAPP01.[DOMAIN].[Company].ORG\[project]\in	F:\Data[project]\in	Everyone
\PVUKPRDKSKAPP01.[DOMAIN].[Company].ORG\[project]\out	F:\Data[project]\out	Everyone
Table 74 Network File shares on PROD environment
Network services are consumed by the servers and the client devices, as detailed below:
Service	Reason	Details
DNS	Resilience and flexibility and future DR	[TBA], [TBA]
DHCP	No	
WINS	No	
NTP	Yes	TBA
AD	Yes	Domain: XXXX
SMTP	Yes, for SSRS report notification	TBA. Source email: noreply@[Company] System.com
Table 75 Server-side Network Services

Service	Reason	Details
DNS	Resilience and flexibility and future DR	[TBA], [TBA]
DHCP	No	
WINS	No	
NTP	Yes	TBA
AD	No	
SMTP	No	
Table 76 Client Network Services
##	Network Infrastructure
This section details the resulting network infrastructure
##	Conceptual network infrastructure
[Show where the solution is located on the various VLANs and  VNETs]
##	Logical network view
[Heavy-duty network implementations views if the project requires this.]
##0	Physical network view
[Heavy-duty network implementations views if the project requires this.]

##1	Switch-configuration context
[Heavy-duty network implementations views if the project requires this.]
 
#TO-BE Security Architecture
[Describe pertinent security features, such as encryption on the move and at rest, authentication mechanisms, access-controlled roles and allowed operations, requirements for firewall, security zones, and interfaces across these zones.]

##	Security Overview
This section explains how security and compliance is implemented for the solution.
Requirement	Implementation
Data Sensitivity Classification	Anonymous and not commercially sensitive
Business impact if information is disclosed	Negligible
Business impact if data is changed by adversary?	Significant
Implementation Approach?	Third-party application
Security operations	Sophos AV on each client and server
Logging of security events & data	Windows Event Logger, stored indeterminately
Table 77 Data Compliance

Requirement	Implementation
Electrical compliance	Yes
Desktop Support Compliance	Yes
Waste compliance	No
Data Protection Act	No
PCI DSS	No
Distance Selling Act	No
Disability Discrimination	No
Table 78 Legal Compliance

Requirement	Implementation
How will users authenticate to the system?	There is no user authentication on client devices. All users are treated as anonymous.
Is Active Directory to be used for authentication	No, as there is no user authentication.
How will users gain authorisation to the system and data?	Users are not required to view system data.
Are passwords transferred over the network in clear text?	No, as there is no user authentication.
Highlight any part of the system not based on the least privilege model?	None.
Table 79 Authentication, Authorisation and Access Control
##	Security Zones
Figure xx shows the solution’s security zones and trust boundaries that are implemented by means of firewalls and switches and corresponding network policies. No confidential data is transmitted between the security zones. The zones are:
Id	Security Zone	Description
A	Un-trusted External	Public network
B	Un-trusted Internal DMZ	Hosts the access gateway with strong policies
C	Trusted Internal DMZ	Citrix server farm for access servers in the Trusted Internal zones
D	Semi-trusted Internal: Location network	User network with restricted policies
E	Trusted internal: User-facing	Web server
F	Trusted internal: Application-facing
	Application and database server
G	Trusted internal: Enterprise Services	Product search (and other future services)
Table 80 Security Zones

Figure 2 shows security zones and how they are bound to each other:










 
###	Client Device Security
[Example, if the solution entails a dedicated client:]
###	Secure Client Enclosure
The client consists of a barebones-PC and touch screen enclosed in a steel cabinet. When closed, the steel cabinet prevents access to the PC.
The enclosure is secured with a barrel lock, of which there are only two keys. Both barrel keys are in the care of the deployment-location manager.
The client device does not have a mouse or a keyboard. It is also not possible to plug a mouse or a keyboard into the PC unless access is gained into the enclosure.
###	OS build on client devices
[Example for security of a simple embedded client device]
The base OS build for the client devices is one that has been accredited by [Company] System Desktop Support Services. All client devices are based on this build. The client devices are not registered on Active Directory.
The build features the following:
•	The build is based on the XXXX Operating System.
•	The client boots up into a default local user account without password authentication. The user account itself is, however, strongly password-protected. This account can only execute client-related processes. 
•	The client has a local administrator account which is password-protected with a strong password. 
•	The client boots up in a local user account and the [PROJECT] Application Launch service is started. This is responsible for launching client applications based on configuration settings.
•	There is no desktop screen or start bar on the screen. With no client application running, the screen displays a neutral grey. 
•	The only way to invoke any response from the device when no interactive application runs, is through the use of a plugged-in keyboard with the Ctrl-Alt-Del key combination.
•	No network port restrictions are in place.
•	The client devices are not part of the XXXX Active Directory (AD) domain.
•	
##	Servers on the network
[Example:] The servers are built according to the standard [Company] System build, which mandates certain levels of security.
They are virtual servers hosted on blade server housed in the Data Centre in a cage. Physical access to the data centre and the cage is controlled by security personnel.
All servers in all 3 environments are on the XXXXX Active Directory (AD) domain.
Remote Desktop Access is enabled and users that belong to the Remote Desktop Group can access the server desktop.
All services run as system service accounts.
##	Network Security
[Example:] Firewall policies ensure that: 
•	The UAT web server is the only server that can connect to the test client devices. 
•	Test Client devices can only access servers in the UAT environment.
 
#TO-BE Post-Production Architecture
[Describe the support system in place for this solution, contact details to first line support of the respective vendors involved, how to maintain the system, steps to take for self-recovery]

##	Backup and Restore
There is no back-up and recovery process in place for the DEV environment.
There is limited back-up and recovery process in place for the UAT environment.
The PRODUCTION environment has full backup capabilities.
##	System recovery
There is no system recovery. This is not a business-critical system.
##	Support Model
Support for [component x, component y] is entirely managed by the vendor of these components.
The remainder of this solution is supported by [Company] System's support team.
##	Application Codebase
The vendor manages the code base for the duration of this trial.
##	Backup and Recovery
In lieu of the fact this project is a trial, no backup has been implemented on any of the environments.
Requirement	Implementation
Backup Details	No local backups, no off-server backups, no off-site backups
Backup Schedule	None
Backup Durations	N/A
Backup Retention	None
Additional backup services	None
Recovery Services	None
Table 81 Backup and recovery design
##	Disaster Recovery
There is no DR implemented for this solution.
##	Development and Test Environments
Figure: UAT Testing Environment
#TO-BE Operations and Support Architecture
##	Solution Dependencies
The following list is a non-exhaustive list of applications and in-flight projects within the [Company] System estate that this projects is dependent on.
System/Project	Content	Interface	Comments	I/O
CSD	Product Search	Web service	Hosted on CSD server	
CSD	Image Retrieval	Web service	Hosted on CSD server	
				
Table 82 Projects that this project is dependent on
There are no applications or in-flight projects that are dependent on this project:
System/Project	Content	Interface	Comments	I/O
				
				
				
Table 83 Projects that are dependent on this project
##	Operational Requirements
This section provides an overview of the business processes affected by this solution in order to provide an understanding of the operational requirements and how the solution interacts with [Company] System's IT Operations.
Requirement	Implementation
Operational Requirements and Implementations
Monitor and alert service view	None
Partner Services	None.
Systems Management	Windows-based solution
Incident Management	L2 support provided by vendor
Change and Release Management	None. Responsibility of the vendor.
Capacity Management	None
Service Continuity	None
Solution Front-end:
Application Software Delivery	Ad-hoc, delivered by vendor
Client Asset Management	None
Security Auditing	None
Remote Control	MS Terminal Services and VNC
Solution Back-end:
Server Software Delivery	MS SCCM 20XX
	Red Hat YUM
Patch management	MS SCCM 20XX
	Red Hat YUM
Security Auditing	None
Remote Control	MS Terminal Services
	Linux VNC
	SSH Terminal
Anti-Malware	Sophos AV
	Linux Malware Detect
Table 84 Operational Requirements and Implementations
 
#Solution Review and Assessment
##	Technology Stack Overview
Technology	Description
SQL Server XXXX SP2
Version	XXXX
Decision Criteria	RDBMS storage required 98% availability
Options Considered	None. Specified by client
Impact of Technology Choice	None anticipated – the existing solution is SQL Server-based.
Microsoft .NET Framework
Version	X.X
Decision Criteria	None. Specified by client
Options Considered	None
Impact of Technology Choice	None anticipated – .NET is downward-compatible.
Windows Server O/S
Version	XXXX R2
Decision Criteria	None. Specified by client
Options Considered	None.
Impact of Technology Choice	None anticipated
Red Hat Server O/S
Version	Enterprise Edition ##
Decision Criteria	None. Specified by client
Options Considered	None.
Impact of Technology Choice	None anticipated
Table 85 Summary of all technologies used by the solution
##	Business Requirements Document Mapping
Ref.	Requirement	Solution implementation
BRD-1		[Paragraph cross-references]
BRD-2		[Paragraph cross-references]
Table 86 BRD Mapping
##	Functional Requirements Mapping
Ref.	Requirement	Solution implementation
FRS-1		[Paragraph cross-references]
FRS-2		[Paragraph cross-references]
Table 87 FRS Mapping
##	Non-Functional Requirements Mapping
Ref.	Requirement	Solution implementation
NFR-1		[Paragraph cross-references]
NFR-2		[Paragraph cross-references]
Table 88 NFR Mapping
##	Assessment against Technology Compliance
Criteria	RAG	Rationale
Servers and Devices
Complexity	Green	This is a repeatable solution being deployed
Technology	Green	Standard [Company] System application and on the roadmap
Volumetric	Green	An increase can be comfortably accommodated
Storage
Complexity	Green	This is a repeatable solution being deployed
Technology	Green	Standard [Company] System application and on the roadmap
Volumetric	Green	An increase can be comfortably accommodated
Network
Complexity	Green	This is a repeatable solution being deployed
Technology	Green	Standard [Company] System application and on the roadmap
Volumetric	Green	An increase can be comfortably accommodated
Infrastructure services
Complexity	Green	This is a repeatable solution being deployed
Technology	Green	Standard [Company] System application and on the roadmap
Volumetric	Green	An increase can be comfortably accommodated
Application services
Complexity	Green	This is a repeatable solution being deployed
Technology	Red	A non-standard [Company] System application and not on the roadmap
Volumetric	Green	An increase can be comfortably accommodated
Security
Complexity	Green	This is a repeatable solution being deployed
Technology	Green	Standard [Company] System application and on the roadmap
Volumetric	Green	An increase can be comfortably accommodated
Systems Management
Complexity	Green	This is a repeatable solution being deployed
Technology	Green	Standard [Company] System application and on the roadmap
Volumetric	Green	An increase can be comfortably accommodated
Table 89 Technology RAG status
##	Community Assessment
Question	Assessment	Comment
How will the project impact the energy usage of IT?	Increase	[Example: New virtual servers]
Will the project outcome impact the wider energy or fuel costs of [Company] System?	Increase	[Example: Business efficiencies will reduce overall energy costs]
If dedicated hardware, are there any energy management systems included in the product to ensure power savings?	Yes	[Example: Power Management is enabled that scales CPU clock cycles.]
Was energy usage a significant factor in the choice of the solution architecture?	No	[Example: Not specified by vendor]
Other environmental impacts:	Yes	[Example: Printing]
Table 90 Assessment against Community Assessment
##	Assessment against IT principles
IT Principles	RAG	Comment
Consistent Delivery
Establish common processes and systems worldwide		
Change the business process before changing the package		
Design for group repeatability – build once use many		
Centralise development and support		
Get it right first time
Create an agile environment able to respond to business and systems change		
One version of the truth – there will be one source for key business data		
Only IT does IT		
Automate complex jobs
Flexible & open inter-application data exchange to reduce complexity		
Where practical data should flow through systems, not be batched		
Create solutions that actively identify problems and fix them		
Understand the marketplace
Buy before build except where there is a competitive advantage		
Our systems are secure and legal		
Cost-effective solutions
We will use IT to reduce overall operating costs of the business		
Table 91 Assessment against IT principles

##	Assessment against Information principles

###	Integration Principles

Id|Principle to be met|RAG|Comment
#|Design for group repeatability||
#|Create an agile environment able to respond to business and systems change||
#|The Integration Layer is for integration||
#|Flexible and open exchange of data between applications to minimise application spaghetti||
#|Where practical data should flow through the systems, not be daily batches||
#|Supportability is vital||

.. and more	

Table 92 Assessment against Integration principles

###	Data Principles

Id	Principle to be met	RAG	Comment
#Corporate data is described in a [Company] System way.		
#Design for group repeatability		
10	One version of the truth		
11	Corporate data will be made readily available		
12	Data must be owned and managed throughout its life		
13	Data is clean and accurate		
14	Our data is Secure		
Table 93 Assessment against Data Principles

##	Exceptions from [Company]'s Technology & Data Architecture principles

Exception:	|EXP-1: [Design aspect]
---|---
Principle:|[Principle that was broken]
Description:|[How is this principle broken]
Justification:|[Why is this principle broken]
Recovery Plan:|[How, if ever, will this be remedied]

etc..
