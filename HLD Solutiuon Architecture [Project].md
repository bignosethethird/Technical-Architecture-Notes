---
title: "Non-functional Requirements"
output: "Non-functional Requirements.pdf"
---

# Non-functional Requirements


**[project]**

**Document Id: [Use SharePoints Document Id]**

**Version: [Use SharePoints Document Versioning]**



*[This template is based on a hypothetical system upgrade, which means that there is an AS-IS and a TO-BE aspect, so that the impact and business and technology can clearly be understood once this design is implemented. If this were to be a brand new system, there would not be an AS-IS section. The hypothetical design consists of a client-server project that consists of database servers, internet servers and development-support servers, with three environments: DEV, UAT+TEST and PROD, all on virtual networks. The servers are for now modelled as on premise VMs here, but could just as easily be applied to a cloud-based solution.]*

This document is written in GitHub-standard Markdown scripts and uses the following plugins for viewing the correctly-rendered output in Visual Code's Mark Down Preview:

- *"Mermaid" for various diagram types*
- *"GraphViz" DOT diagram notation for other diagram types not supported by Mermaid*


Note that the Version number and the Document Identity fields should be set up in your word processor to automatically update when this document is checked back into SharePoint, or whatever doument management system you are using.
Remove all comment sections in italics before final presentation. ]*


**Document Details**

Document Identity:	*[Unique Identifier that your Document Management System had issue this document]*



**Approvals**

|Role      |Name   |Title                       |Date|
|----------|-------|----------------------------|----|
|Originator|       |SOLUTION ARCHITECT          |    |
|Approver  |       |SYSTEM DESIGN AUTHORITY     |    |
|Approver  |	   |ASSISSTANT PROJECT MANAGER  |    |
|Approver  |	   |SOFTWARE DEVELOPMENT MANAGER|    |
|Approver  |       |SOFTWARE FUNCTIONAL MANAGER |    |
|Reviewer  |	   |QUALITY ASSURANCE           |    |
|Authoriser|       |ENTERPRISE ARCHITECT        |    |


**Distribution**

|Name|Copy|Number|
|----|----|------|
|  |  |  |
|  |  |  |
  


**Document Version History**

|Version|Date|Author|Details|
|-------|----|------|-------|
|       |    |      |       |
|       |    |      |       |
|       |    |      |       |



**Concepts**

*[A list of concepts that are referred to in this this document. Remove superflous ones.]*

Concepts|Description
--------|------------
Latency |How fast the system responds to a single request. Lower latency means that a user experiences snappier performance. 
Throughput|A measure of how many requests an application can simlutaneously handle in a given period. Higher throughput menas that more clients can make requets before the system performance degrades.
Performance Dilmemma|Optimizing for lower latency can degrade throughput and the other around too. Maximize throughput with acceptable latency at a reasonable cost.
	
**Definitions and Abbreviations**

*[A list of useful acronyms and abbreviations that are referred to in this this document. Remove superflous ones.]*

Acronym|Description
-------|------------
AAA    |Authentication, Authorization and Auditing
API    |Application Programming Interface
BI     |Business Intelligence
BPM    |Business Process Management
CBOR   |Concise Binary Object Representation, based on JSON
CDM    |Common Data Model
CI     |Configurable Items
CICD   |Continuous Integration and Continuous Deployment
CORS   |Cross Origin Resource Sharing
COTS   |Commercial Off The Shelf
CQRS   |Command and Query Responsibility Segregation of read and write operations
CRUD   |Create, Retrieve, Update, Delete
CSS    |Cascading Style Sheet
DAD    |Data Architecture Document
ESB    |Enterprise Service Bus
ETL    |Extract, Transform, Load of batched data
ELT    |Extract,,Load, Transform of streamed data
gRPC   |Cross-platform, high-performance network protocol
GIT    |A better code control and versioning system
GraphQL|Hierarchical Graph Query Language
HLD    |High Level Design
HMAC   |Hash-based Message Authentication Code
HTML   |Hyper Text Mark-up Language
ICD    |Interface Control Document
IT     |Information Technology
JSON   |JavaScript Object Notation for schemaless data interchange
MDM    |Master Data Management
MPP    |Massively Parallel Processes
MVP    |Minimum Viable Product
RCS    |Rich Communication Service, successor to SMS
ReST   |Representational State Transfer
RPO    |Recovery Point Objective
RTO    |Recovery Time Objective
SAN    |Storage Area Network
SQL    |Structured Query Language
SSL    |Secure Sockets Layer
TOGAF  |The Open Group Architecture Framework
UML    |Unified Modelling Language
XML    |Extensible Mark-up Language
Zero Trust|Assumption that every interface can be a hostile threat

 
*[To update these indexes, Right-click on each list and select “Update entire table”.]*

**Table of Content**

*[Add your word processor's TOC link in here - it should look something like this, which is generated in MD using the "Auto Markdown TOC" by Hunter Tran:]*
*[To update these indexes, Right-click on each list and select “Update entire table”.]*

<!-- TOC -->
- [Background](#background)
- [Issues and Assumptions](#issues-and-assumptions)
  - [ASM-1:	Enterprise Monitoring System](#asm-1%09enterprise-monitoring-system)
  - [ASM-2:	Message-based protocol](#asm-2%09message-based-protocol)
  - [ASM-3:	Data Backups](#asm-3%09data-backups)
- [Non Functional Requirements](#non-functional-requirements)
  - [Access Management & Security](#access-management--security)
  - [Operating Environments](#operating-environments)
  - [System Availability](#system-availability)
  - [Data Management](#data-management)
  - [User Interface Non-Functional Requirements](#user-interface-non-functional-requirements)
  - [Internationalization](#internationalization)
- [Performance, Capacity, Scalability](#performance-capacity-scalability)
  - [Hardware Non-functional Requirements](#hardware-non-functional-requirements)
  - [Monitoring, Deployment and Support](#monitoring-deployment-and-support)
- [Appendix A  Disaster Recovery Levels](#appendix-a--disaster-recovery-levels)
- [Appendix B  Agreed Issue Resolution Times](#appendix-b--agreed-issue-resolution-times)
<!-- /TOC -->






# Background

It is the intent to []. This document describes the non-functional requirements to achieve this.

# Issues and Assumptions	

### ASM-1:	Enterprise Monitoring System	

Assumption: No enterprise-wide application monitoring solution exists in Succession Wealth.
Consideration: This is currently being investigated. For the purposes of this NFR, it is assumed that the NAGIOS solution will eventually be accepted as the tool of choice.

### ASM-2:	Message-based protocol	

Assumption: No enterprise-wide cross-platform message-based protocol exists at Succession Wealth.

### ASM-3:	Data Backups

Assumption: In the apparent absence of an enterprise architecture mandate for data backups, data retention, data restoring and data vaulting, this doc defines these issues.
Consideration: Data management-related procedures will be amended once these mandates are finalized

# Non Functional Requirements


*[Use this templated table for documenting an NFR]*

|### NFR-x|Non- functional Requirement Name||
|-----|--------------------------------|---|
|     |                                ||
|**Source:**|**Owner:**|**Priority:**|
|*[source]* |*[owner]* |*[priority]*|
|**Description:**|
|*[description]*|
|**Benefits:**|
| *[benefits]*|
|**Comments or suggested solutions:**|
|*[comments]*|
|**Related requirements:**|
| *[related]*|


## Access Management & Security

### NFR-1: User Base

Description:


* There are approx. [] users
* The breakdown of user classes that are supported is:

  * 80% are basic users

  * 18% are supervisors

  * 1% are managers

  * 1% are engineers

* The number of users is expected to grow by 5% per annum

### NFR-3: User Authentication

### NFR-6: Security Audit

### NFR-7: Network Security

Description:


* Public Private key-pairs are used as the primary form of remote access authentication.

* Where this is not possible or feasible, password authentication is used. 

* Passwords are encrypted at all times and appear at no time in clear text, whether it be in storage, during network transport or during user entry time.

* Files are transferred using a secure channel, like Secure Shell (SSH)

* Outgoing IP address and port restrictions are in force, such that it can only communicate with its back office servers on the absolutely minimum required ports.

* Incoming IP address and port restrictions are in force, such that only back office servers, and IP addresses from system administrators and engineers can axcc

## Operating Environments 

### NFR-12: Physical Location - client devices



### NFR-13: Physical Location – back-end devices


### NFR-14: Client Operating Environment

Description:


* Enclosure rating: IP ??

* Operational temperature range: +5°C to +45°C


### NFR-15: Device Security

Description:

Unauthorized removal of the device should be prevented is as far as possible.


The device must remain movable on the counter so that the counter underneath it can be cleaned.

## System Availability

### NFR-16: System Availability (SA) / Standard usage hours

Description:


* Standard usage is 7 days per week, 8:00 to 20:00, with regional and seasonal variations and exceptions.

Uptime calculation based on 10 minutes downtime per week:

$$(System Availability – Acceptable Downtime)/( System Availability) * 100 %$$

e.g.

$$(12x60x365 – 10*52)/( 12x60x365) * 100 = 99.8 %$$

### NFR-17: Backup of client devices

Description:


* An hourly, local data backup is performed to a backup partition on the device
### NFR-18: Backup of Back-end system

Description:


* A daily data backup to tape is performed 

### NFR-19: System Uptime - Client devices

Description:


* 10 minutes accepted downtime per week per client device

* Required system uptime based on this is 99.8%

### NFR-20: System Uptime – Back-end

Description:


* 10 minutes accepted downtime per month per back office server

* Required system uptime based on 10 minutes acceptable downtime per month is 99.95%

Calculation: 

(System Availability – Acceptable Downtime)/( System Availability) * 100 %
e.g. (12x60x365 – 10*12)/( 12x60x365) * 100 = 99.95%

### NFR-21: Planned Outages outside System Availability – Client devices

Description:

- Outages can be planned for the 1* hour period from 20:00 to 08:00 the next day.
- Outages are scheduled to start before 00:00 
- Outages are scheduled to not last longer than * hours
- Outages are planned such that the outage can be returned to the last known point of operation, should the remedial work not be successful. Where practical, a spare device with the data and configuration duplicated to it should be on hand.
- The duration of backing out of a planned outage must not last longer than * hours.
- A system stabilization period is of * hours is required after backing out of a planned outage, to ensure that the outage back out has successfully returned the system to the last known point of operation.

Benefits:
This ensures that remedial work on devices is undertaken in a structured and safe manner that will not hinder the business. Sufficient time is mandated to return a system to it previous working state. Therefore, outages must be planned to commence at 20:00 and be completed at 00:00. If the remedial work is not completed by then, the outage must be backed out from immediately, so allowing sufficient time to test for a successful outage back out. 

### NFR-22: Planned Outages outside System Availability – Back-end

Description:

- Outages can be planned for the 1* hour period from 20:00 to 08:00 the next day.
- Outages are scheduled to start before 00:00 
- Outages are scheduled to not last longer than * hours
- Outages are planned such that the outage can be returned to the last known point of operation, should the remedial work not be successful. Where practical, a spare device with the data and configuration duplicated to it should be on hand.
- The duration of backing out of a planned outage must not last longer than * hours.
- A system stabilization period is of * hours is required after backing out of a planned outage, to ensure that the outage back out has successfully returned the system to the last known point of operation.

Benefits:

This ensures that remedial work on devices is undertaken in a structured and safe manner that will not hinder the business. Sufficient time is mandated to return a system to it previous working state. Therefore, outages must be planned to commence at 20:00 and be completed at 00:00. If the remedial work is not completed by then, the outage must be backed out from immediately, so allowing sufficient time to test for a successful outage back out. 

### NFR-23: Unplanned Outages of the client devices

Description:

- Unplanned outages of client devices during the system availability window are tolerated if:
◦ The number of outaged client devices is less than 25% of the total client devices (i.e. no more than * in * client devices are outaged)
◦ The basic functionality of weighing, price determination and printing of labels is possible on the other (non-outaged) client devices
◦ Hygiene regulations are not contravened or extra steps can be taken to cross-use client devices

The business impact for unplanned outages is:

- Up to x hour: No significant business impact
- Up to xx hours: Possible loss of revenue due to price adjustments and other data not reaching the Client devices, and longer customer waiting times 
- Up to xxx hours: Loss of user productivity and definite loss if store revenue


### NFR-24: Unplanned Outages of the Back Office

Description:


* Unplanned outages of middleware during the system availability window are tolerated if:
** The basic client device functionality of weighing, price determination and printing of labels is possible
** A manual and paper-based process can temporarily replace parts of the business process where necessary (e.g. updating of product prices on the client device itself)

The business impact for unplanned outages is:

* Up to x hour: No business impact

* Up to xx hours: Possible loss of revenue due to ...

* Up to xxx hours: Loss of user productivity as manual processes would need to be invoked

### NFR-25: Business Continuity Requirements – Client devices

Description:


* Recovery Point Objective (RPO) of * hour, i.e. data loss of one hour’s worth of transactions on a client device is tolerated. 

* Recovery Time Objective (RTO) of * hours for data loss, i.e. the time to restore the system to operational state is constrained to no more than * hours, during which time the client device is not available. This includes the restoring of backed-up transaction data and backed-up configuration data via a remote process.

* Recovery Time Objective (RTO) of 1* hours for complete client device system loss, i.e. the time to restore the entire system due to catastrophic storage failure by an on-site engineer. This does not include the time to restore any data.


### NFR-26: Business Continuity Requirements – Back Office

Description:


* Recovery Point Objective (RPO) of 0 minutes, i.e. no data loss is tolerated. 

* Recovery Time Objective (RTO) of * hours for data loss, i.e. the time to restore the system to operational state is constrained to no more than * hours, during which time the back office system is not available. This includes the restoring of backed-up transaction data and backed-up configuration data via a remote process.

* Recovery Time Objective (RTO) of * hours for complete back office system loss, i.e. the time to restore the entire system due to catastrophic storage failure. This does not include the time to restore any data.
Benefits:

### NFR-27: Disaster Recovery Requirements – Client devices

Description:


* Refer to Appendix A  Disaster Recovery Levels: Level * DR is required, i.e. the Client devices should be recovered within * week (7 days) 


### NFR-28: Disaster Recovery Requirements – Back Office

Description:


* Refer to Appendix A  Disaster Recovery Levels: Level * DR is required, i.e. the Back office should be recovered within 2* hours


### NFR-30: System Integration

Description:


* Client devices and Back Office application are integrated through the use of an enterprise-based, cross-platform, message-based protocol
Benefits:

Comments / Suggested Solutions: 
Currently, no enterprise cross-platform message-based protocol exists at Succession Wealth


### NFR-31: Technology choices – Client devices


### NFR-32: Technology choices – Back office

### NFR-33: Integration Technology – Complimentary systems

Description:


* Where complimentary systems are not able to support an enterprise messaging service or other service oriented approach (due to legacy or support issues), system integration is effected by data integration.

* Data integration is performed through an enterprise-wide ETL tool.


## Data Management

### NFR-34: Data Backup 

Description:


* A daily incremental backup of the configuration of each client device is made to the back office.

* A daily full database on the back office is backed to tape

Benefits:

Comments / Suggested Solutions: 

There is no need to back up data from the Client devices, as their data is primarily sourced from the back office database. Transaction data generated on the Client devices is immediately replicated to the back office. Instrumentation and log data does not need to be backed up.


### NFR-35: Data Backup Retention

Description:


* Backup retention of client device configuration data on the back office server is 1* months.

* Tape backup retention of back office server data is 1* months


### NFR-36: Data Restore

Description:


* A client device configuration is restored from the back office server to a target client device within an hour.

* A tape backup is restored to the back office server data within an hour

### NFR-37: Data Vaulting

Description:


* Backup tapes from over 1* months ago are vaulted

* A vaulted backup can be restored with in 2* hours

### NFR-38: Data Synchronization – Client devices

Description:


* Transaction and configuration data is synchronized between client device and Back Office

* The client device is fully data synchronized with the back office within 60 seconds of completion of booting with the back office

* Transactions are synchronization at the earliest possible opportunity

* The number of stored transactions on the client device - synchronized or not – is not limited.
5 The client device attempts a final synchronization on power down.

### NFR-39: Data Growth

Description:


* The number of counter products is expected to grow by 5% per annum. This is mainly predicated by the introduction of new types of counters, e.g. pizza counters. As a result, the number of users in each store is expected to grow by ca. 5% per annum

* The number of sites are expected to grow by 5% per annum

### NFR-40: Data Storage Capacity – Client devices

Description:


* Store all counter products for the region

* Store all transactions

* Store all event, instrumentation and audit history

### NFR-41: Data Storage Capacity – Back office

Description:


* Store all counter products for the region

* Store all transactions

* Store all event, instrumentation and audit history

* Store backups of all Client devices configuration

### NFR-42: Data Security – Client devices

Description:


* Time card Id’s only of users who have used a particular client device are held in data

* Name details are removed from the Client devices database when a user has not accessed the client device after * months.

* No corporate sensitive or confidential data is held on the Client devices

### NFR-43: Data Security – Back office

Description:


* The back office server holds confidential and sensitive data

* Policies are in place to prevent unauthorised piecemeal access to the data

* Policies are in place to prevent unauthorised bulk copying of all the data

## User Interface Non-Functional Requirements

### NFR-44: Mode of Interaction

Description:


* All operations that are possible for Basic, Supervisor and Manager-class of users can be executed through the touch screen.

* Engineering functions are performed either remotely from a standard PC or through a plugged-in keyboard and optional mouse.

### NFR-45: User Interface Look and Feel

Description:


* Follows the corporate Succession Wealth style guide

* Appeals to all ages, young and old (i.e. has a conservative look)

* Available user options are displayed as images with supporting text

* Basic-class operations can be performed by users with no prior experience or knowledge of the client device of the selected language

### NFR-46: User Interface Clarity and Ease of Use

Description:


* Ease of use criteria applies to Basic, Supervisor and Manager-class of users. The requirement breakdown of typical operations is:
◦ 80% of typical operations are performed within a * screen-deep hierarchy (e.g. selecting product, weight, print label)
◦ 15% of typical operations are performed within a * screen-deep hierarchy (e.g. selecting category, selecting product, weight, print label)
◦ 5% of remaining operations are performed within a * screen-deep hierarchy (e.g. set configuration, change PIN, etc.)

* No screens within screens, i.e. no dialog boxes.

* A clear, backing-out option is present on each screen.

### NFR-47: User Interface Response time – Data Entry

Description:


* Provide tactile user feedback within 0.* seconds of a user action with an audible sound or other tactile feedback (i.e. vibrating touch screen)

* Provide visual user feedback within 0.* seconds of a user keyboard action, i.e. a typed character must display within 0.* second.

* Allow the typing of a new character within 0.* seconds of the last character typed, i.e. a user should be able to enter up to 5 characters with * second.

### NFR-48: User Interface Response time – Screen change

Description:


* The client device needs to start displaying the response within 0.8 seconds on a user action that requires a new screen or dialog to be rendered

* The data-complete rendering of a new screen or dialog must be competed within * seconds.

### NFR-49: User Interface Mode change

Description:


* A mode change on a user interface occurs when a user is required to change the type of operation on the device. The identified modes of operation are:
◦ Weighing
◦ Configuration
◦ Administration
◦ Exception handling

* Each mode of operation is clearly identifiable on the display

* A mode change is displayed on a new screen

## Internationalization

### NFR-51: Geographical Locations

Description:

1. Countries of deployment:

* UK

### NFR-52: Time Zones

Description:

1. The default time zone is BST/GMT
2. A client device is set to its respective time zone through the engineering function
3. All time zones are supported
4. The client device updates automatically between daylight-saving modes
5. The client device synchronizes its local time with an NTP time server on at least once a day
6. The NTP time service is hosted on the back office server
7. The back office server synchronizes its local time with an enterprise NTP time server or a public NTP time server (pool.ntp.org) at least once a day


### NFR-53: Multi-lingual User Interface

Description:


* UTF-8 text display is supported

* All text strings are stored in a separate repository. A text string repository exists for each supported language and contains translations of all strings that relate to weighing and configuration operations.

* Text strings that relate to administrative operations are not translated and therefore remain in English only, albeit that they are also in the text string repository.

* A string, for which a non-English translation does not exist, defaults to the English text.

Benefits:

Avoids the hard-coding of strings in code and allows extensibility
Comments / Suggested Solutions: 
It is not necessary to translate administration strings to other languages as general support language is English.

### NFR-54: Multi-cultural User Interface

Description:

1. Locales are selectable from an administration-level function
2. The choice of locale selects an appropriate virtual keyboard layout
3. Each locale is supported by a particular virtual keyboard layout (some locales share the same virtual keyboard layout)
4. The following locales are supported:

* EN (UK & EI)
Benefits:

Comments / Suggested Solutions: 
Locales are normally set up once only on client device deployment

# Performance, Capacity, Scalability

*[The objective of setting the performance is to find the right balance between latency and throughput at an acceptable cost]*

### NFR-56: Transactional Performance

Description:

* Perform at least one operation once every 5 seconds, i.e. it should be possible for an operator or automated product feeding machine to process 1* items in a minute.

### NFR-57: Transactional Capacity

Description:


* No more than one item at a time can be processesed

* Up to xx client devices on a site can simultaneously perform the operation

### NFR-58: Scalability in the Enterprise

Description:


* Up to xxx client devices in the enterprise are initially supported during the operational window

* The number of client devices is expected to grow by 5% per year per store

* The number of sites in the UK is expected to grow by 5% per annum

* At least 10,000 client devices in a region are supportable during the operational window

### NFR-59: Role Changes – Client devices

Description:

1. A configuration switch allows the client device to change roles for operating between the following operational areas:

* xxx

* yyy

* zzz

Benefits:

Better workload sharing and better resource (client devices) sharing

### NFR-60: Configurability – Client devices

Description:

1. Parameters related to the general behaviour of the Client devices are configurable by Supervisors, Store Managers or Engineers.
2. Configuration values can be summarized in a visible report that is locally and remotely viewable.
3. All configuration changes are auditable
Benefits:

* Better code management

* Better configuration error resolution

## Hardware Non-functional Requirements

### NFR-61: Peripheral support

Description:


* The client device supports the following MANDATORY peripherals:

* Label Printer

* User-facing touch screen

* Barcode scanner

* The client device supports the following OPTIONAL peripherals:

* External mouse and keyboard

### NFR-62: Device Accuracy

Description:


* Accuracy better than 0.05g/g (5%)

### NFR-63: Device Range

Description:


* client devices to have range of at least 10g to 5,000g

### NFR-64: Hardware Reliability

Description:


* Mean time between failures / Mean time to failure (MTBF/MTTF) of at least 50,000 hours. 

The MTBF/MTTF is calculated as follows:
MTBF = (Sum of failure-free periods of operations) / 
(Number of failure-based interruptions)


### NFR-65: Client devices Hardware Longevity

Description:


* New Client devices have an expected total minimum lifetime of 10 years

* Currently-existing Client devices that have this project deployed on them have an expected lifetime of at least 5 years from the point of deployment

* Spares for the all types of deployed Client devices should remain available for their lifetimes.


### NFR-66: Hard Drive Replacement Regime

Description:


* S.M.A.R.T. hard-drive protocol is enabled in the BIOS of all client devices.

* Hard drives are replaced when their accumulated operating hours have exceed their respective manufacturer’s states MTBF

* S.M.A.R.T. hard-drive protocol is monitored and reported on, on a daily basis so that premature failure can be identified in a timely manner and dealt with in advance.

* Old hard drives should be replaced, when necessary, with new SSD drives.

Benefits:

- Avoid loss of business continuity.
- Keeps performance optimal

Comments / Suggested Solutions:

SSD drives typically have a MTBF of 1,000,000 hours (100 years), as opposed to MBTF’s ranging from 50,000 hours (5 years) to 300,000 hours. Their cost is on parity with their spinning-platter equivalents. SSD disks also have better seek times.


### NFR-67: Cabling to the client device

Description:


* Cables that lead to the weighing, printing and display equipment do not dislodge or tear out of their plugs during thorough cleaning

* Cables are kept to a minimal length, i.e. no bundling or coiling of cables


### NFR-68: Power Cycles

Description:


* The client device can operate continuously and uninterrupted for 2* hours throughout its lifetime

* Total power cycles in lifetime of a client device: 10,000

* When UPS is not present, instant power-off is possible with no loss of integrity of stored data
Benefits:

Comments / Suggested Solutions: 

Most client devices are in fact never turned off. 


### NFR-69: Power Saving Mode * - Sleep

Description:


* The client device should go into power saving mode after 20 minutes of no user activity on the user interface or scanner. This duration is configurable. 

* The client device should return from power saving mode within 5 seconds, on user activity on the user interface or scanner (but not the client device).

* Loss of power causes the UPS-powered graceful shutdown, as described further below.

* During power saving mode 1, the following happens:
◦ A screen saver runs
◦ All background processes continue to run
◦ Any current transactions are cancelled / rolled back

Comments / Suggested Solutions: 

Most client devices are in fact never turned off. 

### NFR-70: Power Saving Mode * - Hibernation

Description:


* The client device should go into power saving mode after * hour of no user activity on the user interface or scanner. This duration is configurable. 

* The client device should return from power saving mode within 10 seconds on user activity on the user interface or scanner (but not the client device).

* Loss of power causes the UPS-powered graceful shutdown, as described further below.

* During power saving mode 2, the following happens:
◦ The screen blanks completely
◦ Background processes run slower
◦ The current user session is terminated (i.e. a user needs to log in again)
◦ Any current transactions are cancelled / rolled back

Benefits:

Significant power savings are anticipated


### NFR-71: Power failure - Client devices

### NFR-71: Power failure - Client devices

Description:


* Loss of power switches the client device UPS mode.

* The UPS is able to support the touch screen, barcode scanner and printer for a minimum of 5 minutes of normal operation. This duration is configurable.

* After this period expires, the device powers down gracefully, as described further below
Benefits:

Comments / Suggested Solutions: 

Assuming batteries 2,100 mAH at 10.8V, it can supply 100W of power for 15 minutes.


### NFR-72: Power-up Cycle - Client devices

Description:


* Power-up can be manually initiated by any user. This can either be done by:
• Momentarily depressing the power button at the back of the (current model) touch screen
• A remote engineering command that sends a Wake On Lan (WOL) command to the network port’s MAC address

* The client device is fully powered up within 60 seconds

* Data synchronization and other housekeeping functions ensue after boot completion

* On a previously non-graceful power-down, housekeeping functions include disk journal checking
5 Every 180 days, the disk is checked for consistency after boot completion
6 All significant power-up events are written to the log
7 The client application starts up after boot completion
Benefits:

Comments / Suggested Solutions: 
It is not clear how the BIOS responds to mains power being applied when the device is already powered down – either the device will power up, or it will wait for one of the above actions to power-up the device


### NFR-73: Power-down Cycle – Client devices

Description:


* Power-downs can be manually initiated by any user. This can either be done by:
• Momentarily depressing the power button at the back of the (current model) touch screen
• A button on the touch screen, some levels deep
• A remote engineering command

* A graceful power-down is attempted on each power down, which synchronizes any outstanding data, writes disk journals and shuts down drivers

* The device only makes one attempt to synchronize outstanding transaction data. If it fails to do this, then it continues with the remainder of the shutting down process.

* All significant power-down events are written to the log
Benefits:

Comments / Suggested Solutions: 


### NFR-74: Electrical Standards

Description:


* client device complies to the following electrical standards
◦ BS EN 60335: Specification for safety of household and similar electrical appliances
◦ BS EN 61000-6-3,4: Electromagnetic compatibility. Generic emission standard.
◦ BS EN 61000-6-1,2: Electromagnetic compatibility. Generic immunity standard


## Monitoring, Deployment and Support

### NFR-75: Monitoring of Events – Client devices

Description:


* An enterprise application monitoring system monitors each deployed client device and their related back office applications.

* The applications are monitored for the following:
• Exceptions
• Current status: On-line / Off line / Sleep mode / Hibernation mode 
• Current logged on user, if any
• Security breach attempts

Benefits:

Comments / Suggested Solutions: 

The solution may entail deploying a monitoring agent on each device that needs to be monitored. 
At present, no enterprise solution exists in Succession Wealth. A well-known cross-platform solution is the NAGIOS product.

### NFR-76: Alerting of Events

Description:


* A support user can set a selection of monitored events or thresholds, for which an alert can be received.

* The alert can be received via one or more of the following:
• Email
• Office communicator
• SMS

Benefits:

Comments / Suggested Solutions:

At present, no enterprise solution exists for alerting of monitored events in Succession Wealth. A well-known cross-platform solution is the NAGIOS product. It is assumed that Succession Wealth has a dedicated SMS gateway.

### NFR-75: Monitoring of Events – Client devices

### NFR-77: Reporting of Events

Description:


* Daily reports are generated for all the Client devices

* The report shows the time line of all the activities and monitored events on a selected client device

* The reports are presented over a browser.

Benefits:

Comments / Suggested Solutions:

It is assumed that the enterprise solution of choice for reporting is SSRS 2008.

### NFR-75: Monitoring of Events – Client devices

### NFR-78: Country-wide Dashboard of Client devices States

Description:


* A near real-time dashboard displays status of all availability (On-line / Off line) and status (User logged in / Sleep mode / Hibernation mode) 

* Update interval is * minute

Benefits:

Comments / Suggested Solutions: 

It is assumed that the enterprise solution of choice for reporting is SSRS 2008.
A well-known cross-platform solution for managing heartbeat is the NAGIOS product

### NFR-79: Instrumentation – Client devices

Description:


* All significant processes on the client devices are performance instrumented. This specifically includes: 
◦ O/S performance and loading
◦ Database performance 
◦ Network performance
◦ User interface response times

Benefits:

Performance optimization
Error resolution

### NFR-80: Instrumentation – Back Office

Description:


* All significant processes on back office are performance instrumented. This specifically includes: 
◦ O/S performance and loading
◦ Database performance 
◦ Network performance


### NFR-81: Event logging

Description:


* All significant events are logged to a local log file. This specifically includes:
◦ Power cycles
◦ User log on and log off
◦ Hardware detection - insertion and removal and details
◦ All exceptions

* A process exists to clean up old log files older than 30 days

Benefits:

Comments / Suggested Solutions: 

The event logs are used for monitoring

### NFR-82: Transaction Audit

Description:


* A full audit trial of all transactions is locally maintained on the client device

* A process exists to clean up old audit files older than 30 days

### NFR-83: Diagnostic Tools

Description:


* A diagnostic tool is available on the client device with which support and engineering can get an overview of the status of the client device to aid issue resolution. The diagnostic uses event and instrumentation data, in conjunction with transaction and security audit data.

* The diagnostic overview is locally visible on the client device

* The diagnostic overview is remotely viewable, where possible

* The diagnostic overview is printable as a report to a series of labels on the printer

Benefits:

Speeds up issue resolution

Comments / Suggested Solutions: 


### NFR-84: Remote Access Management Tool

Description:


* A support tool manages remote access to all remote Client devices on the estate. 

* The security requirements that relate to this are described in Error: Reference source not found Error: Reference source not found

* It allows the selection of a specific remote client device in the hierarchical tree, based on the following hierarchy:
◦ Country
◦ Store

* The support tool allows the selection of a specific remote client device by searching for the following criteria:
◦ A match on a partial client device DNS name
◦ A match on a partial user name who is logged on

* The support tool allows the selection of a specific remote client device by explicit entering:
• Full PC DNS name
• Full PC IP address

Benefits:

Speeds up issue resolution


### NFR-85: Remote Access – Client devices

Description:


* Remote access to the operator screen through an open source graphical desktop sharing system

* Remote access to the O/S shell with no interruption to the graphical operation and no operator interaction* 

* Bi-directional remote file transfer with no interruption to the graphical operation and no operator interaction4
Benefits:

Comments / Suggested Solutions: 
Succession Wealth is currently using VNC as a remote desktop sharing system. It is only secure if it is tunnelled over SSH. Other equally secure possibilities exist.


### NFR-86: Remote Deployment of System rebuild

Description:


* The system rebuild, including O/S, is remotely deployed to all target devices with no manual local intervention.

* The system rebuild does not require hardware upgrades
Benefits:
Keep hardware costs to minimum.
Comments / Suggested Solutions: 
There is a possibility that machines with 128MB may be upgraded to 512MB where the performance improvement that this will deliver is necessary, although this enhancements is not mandatory to achieve the general project objectives. 


### NFR-87: Registration of new Client devices in the Enterprise

Description:


* A new client device is registered to the enterprise in a single operation

* This operation establishes the necessary data couplings with the back office servers and network couplings in order for the following facilities to function:
• Monitoring
• Event Logging
• Daily event reporting
• Real-time dashboard reporting
• User authentication
• Connection to the respective back office server
• Remote access 
• Engineering functions

### NFR-88: Remote Deployment of Patches

Description:


* All patches can be remotely deployed and don’t require user interaction at the target device

* These functions are performed over a secure channel
Benefits:

Comments / Suggested Solutions: 
Succession Wealth’s deployment tool of choice is SCCM for Windows-devices, which offers limited support for non-Windows platforms. Other deployment tools are used in the Succession Wealth enterprise, such as WaveLink for Windows Mobile devices. Because the proposed solution is Linux-based, a Linux-based software deployment system is used.


### NFR-89: Modularity of software

Description:


* The application is based on a framework that allows the addition and removal of software modules without having to recompile any part of the framework. 

* Each functional area is hosted in a separate module 

* The modules deployed can be listed on each client device

* A central database of deployed modules on each client device is maintained
Benefits:
Allows the plugging-in of different weighing rule-sets that apply to various countries that the client devices are deployed in. Other region-specific or store-model-specific modules can also be deployed.

### NFR-90: Remote Engineering functions

Description:


* It is possible to execute all available engineering functions remotely

* These functions are performed over a secure channel that is authenticated as described in Error: Reference source not found Error: Reference source not found


### NFR-91: Application Code Base

Description:


* The code base is source-controlled through a central repository

* Patches are deployed through the use of packages

* System builds are built out of the source control repository

* Patch packages are built out of the source control repository
5 It is possible to check what code changes relate to which issue that was addressed, i.e. code is only ever checked in against an issue identifier
Benefits:
Traceability of who changed what code when and for what reason
Comments / Suggested Solutions: 
Succession Wealth currently uses ClearQuest and ClearCase, but these two systems operate independently of one another, i.e. it is not possible to demonstrate which software changes relate to which IR and vice versa.

### NFR-92: Change Management

Description:


* Change management is performed with the combined use of the issue management system and source control management system

* An incremental release-numbering system is used to identify releases and patches.

* The release number is tagged to the version control system for code traceability


### NFR-93: Operational Support Model

Description:


* First Line of support: sites Help Desk (SHD): 6:00– 19:30 BST MON-FRI, 8:00 -17:30 SAT, 9:00 – 17:00 SUN.

* Second Line of support: sites support operations (SSO): 2* hours, take over first line support during out of hours. 

* Third Line of support: 9:00-17:00 BST, on call out of hours


### NFR-94: Self-remedy by Users

Description:


* Users are not expected nor trained to remedy issues with the client device, other than ensuring power is connected to the device. 

* All other hardware issues of Client devices are taken care of by the client device retailers, who use service engineers that repair the devices on site.


### NFR-95: Issue Escalation Model

Description:


* All issues are initially reported to the First Line of support, except when out of hours, when issues are reported to Second Line of support

* First Line passes issues that can’t be resolved to Second Line.

* Second Line passes issues that can’t be resolved to Third Line.

* Agreed total issue resolution times are described in Appendix B  Agreed Issue Resolution Times

* Where issues cannot be remedied, they are optionally escalated to the weekly Air Traffic Control conference. 

2.1* Training Requirements

### NFR-96: Support Training

Description:


* A technical support manual is provided that describes the client devices system from the O/S level upwards.

* The support documentation includes a Frequently Encountered Issues section with corresponding remedies


### NFR-97: User Training – Client devices

Description:


* Teaching the basic user function to staff with no prior computer skills should take no longer than * hours. A user training manual accompanies this course.

* Teaching the supervisor user functions to staff with no prior computer skills should take no longer than an additional * hours. A user training manual accompanies this part of the course.

* Teaching the manager user functions to staff with no prior computer skills should take no longer than an additional * hours. A user training manual accompanies this part of the course.


### NFR-98: Engineer Training – Client devices

Description:


* A self-read technical support manual is provided to augment engineering staff’s existing, technical knowledge of the system.

2.1*  Legal Requirements

### NFR-100: Open Source Software Licensing

Description:


* Where open-source components are used and subsequently modified, the changes need to be publicized in accordance with the open-source license

### NFR-101: Accessibility

Description:


* All weighing-based operations (touch screen operation, label printing initialization, label application) are performed by a single touch / button-press operation at a time

* It is possible to operate the touch screen without actual skin contact, i.e. prosthetic limb can actuate controls on the touch screen


# Appendix A  Disaster Recovery Levels

| |Level 1|Level 2|Level 3|Level 4|Level 5|
|---|---|---|---|---|---|
|Recovery Time Objective|Recovery within 8 hour window|Recovery within 2* hour window|Recovery within * week|Recovery within * month|No Recovery required|
|Recovery Point Objective|||||None|
|Hardware Requirements|Dedicated hardware should exist in DR site and be of similar specification.|Hardware should exist in DR site.  Some hardware will be required to receive and process database logs shipped from the primary site. On DR this should be supplemented from other environments to limit the amount of dedicated hardware. Typically the Test, Patch, and UAT environments should make way for recovery.|Test, Patch and UAT environments may be used for recovery or a hardware provider should be asked to supply equipment at short notice.|Test, Patch and UAT environments may be used for recovery or a hardware provider should be asked to supply equipment at short notice.|None|
|Replication of Data|Data should be replicated between the primary Data Centre and DR site in near real-time.|Data should be replicated between the primary Data Centre and DR site in near real-time.|Data should be replicated between the primary Data Centre and DR site once a day or a mechanism should exist for restoration of data.|Restoration of data from backup device.|None|

# Appendix B  Agreed Issue Resolution Times

TBA.
