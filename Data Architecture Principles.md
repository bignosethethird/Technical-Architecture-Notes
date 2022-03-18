#	Data Architecture Principles
##	Data is a shared asset
_Rationale:_ Enterprises that start with a vision of data as a shared asset ultimately outperform their competition. Instead of allowing departmental data silos to persist, these enterprises ensure that all stakeholders have a complete view of the company, such as improved products and also improved business insights, by being able to correlate data from all systems and business functions. The result of this is better product design and improved corporate efficiency.
_Implications:_ The sharing of data with the organization between persons and processes must be controlled on a need-to-know basis, and good governance processes must exist for the request, issuance and revocation of access to the data. 
##	Provide the right interfaces for users to consume the data.
_Rationale:_ It is not realistic to put all data in one place to achieve the vision of data-driven products. In order for systems to benefit from a shared data asset, one needs to provide controlled yet usable interfaces that make it easy for systems and business users to consume that data. 
_Implications:_ The interfaces can be in the form of an OLAP interface for business intelligence, an SQL interface for data analysts or a real-time rest-ful API for systems. It is essential that the technical interfaces to the data are available to allow the systems to access required in a system-native way, and for business users to use the tools they know and are right for the job that they need to perform.
##	Ensure security and access controls.
_Rationale:_ The emergence of unified data platforms like Snowflake, Google BigQuery, Amazon Redshift, and map-reduce offerings (Hadoop et al) has necessitated the enforcement of data policies and access controls directly on the raw data, instead of in a web of downstream data stores and applications. 
_Implications:_ The emergence of new data security projects makes this approach to unified data security a reality, so consider using technologies that allow you to architect for security, and deliver broad self-service access, without compromising control.
##	Establish a common vocabulary.
_Rationale:_ By investing in an enterprise data hub, enterprises can now create a shared data asset for multiple consumers across a complex product supported by many vendors, or the business with its many departments. The arising ambiguity of the meaning of the data needs to be disambiguaged thorugh the use of an established common vocabulary. With a shared vocabulary, less time will be spent disputing, disambiguating or reconciling results and more time driving improved product output and business performance.
_Implications:_ It is critical that data users analyze and understand the purpose and content of the data in terms of a common vocabulary. System design, product catalogs, data warehouse dimensions, provider hierarchies and KPI definitions all need to be alligned to this common vocabulary, regardless of how users consume or analyze the data. 
##	Curate the data.
_Rationale:_ Systems and end-users can have a frustrating experience if data is not cleansed, incomplete or misaligned, which reduces the perceived and realized value of the system’s  underlying data. 
_Implications:_ By investing in processes that perform data curation, the organization has a better chance of realizing the value of its shared data assets.
##	Eliminate data copies and movement.
_Rationale: Every time data is moved there is an impact in either or all of these:_ cost, accuracy and time. 
_Implications:_ The fewer times data has to be moved, the better. Part of the promise of cloud data platforms and distributed file systems is a multi-structure, multi-workload environment for parallel processing of massive data sets. These data platforms scale linearly as workloads and data volumes grow. By eliminating the need for additional data movement, modern enterprise data architectures can reduce cost (time, effort, accuracy) and optimize its overall enterprise data agility.

 
#	Data Classification and Life-Cycle Policy
##	Introduction
This data classification policy details what precautions to take for protecting data with [company] and also within the customer's enterprise. This policy applies to all forms of data storage, data transport and everyone in the business.
###	Data ownership and stewardship
_All data must have an owner who is responsible for understanding the appropriate risks and implications of the owned data going awry. The data owner is responsible for assigning the classification level of the data and must ensure that it is consistently protected throughout its life cycle up to the point of where the data is destroyed:_ Data must be protected in a manner commensurate with its sensitivity, regardless of where the data resides, what electronic or printed form it is in, and what technology is used to handle the data. [company] is subject to strict regulatory compliance (PCIDSS, Data Protection Act, GDPR, etc..) and strict internal rules. Likewise, [company] customers have similar compliance rules that need to be adhered to, and also have a reasonable expectation that their data is treated with the utmost respect by system vendors.
##	Data Classifications

THE FOLLOWING NEEDS TO ALLIGNED WITH [company]’S POLICIES AND DATA CLASSIFICATIONS:
###	Public
_Description:_ This data may be freely disseminated outside the organisation without potential harm. 
_Accessible by:_ Available to the general public and for distribution outside of [company].
_Data Breach Impact:_ None.
Examples:
*	Product and service brochures sanctioned for public consumption
*	Advertisements sanctioned for public consumption
*	Job opening announcements
*	Press releases
*	Financial results releases
Network Data Transfer Policy:
*	No special handling required
*_	Email to External accounts:_ No special handling required
*_	Email to Internal accounts:_ No special handling required
Transfer via removable storage devices:
*	No special handling required
Storage:
*_	All electronic data:_ No special handling required
*_	Printed material:_ No special handling required
Data Disposal:
*_	All electronic data:_ No special handling required
*_	Printed material:_ No special handling required
###	Internal
_Description:_ This classification applies to all other data that does not clearly fit into the other classifications.
_Accessible by:_ Intended for use only within [company].
_Data Breach Impact:_ Unauthorised disclosure, modification or destruction of this data is not expected to seriously or adversely impact the organisation, its employees, or its business partners. 
Examples:
*	Company telephone directory
*	Employee training materials
*	Internal policy manuals
Network Data Transfer Policy:
*_	Network:_ No special handling required
*_	Email to External accounts:_ No special handling required
*_	Email to Internal accounts:_ No special handling required
Transfer via removable storage devices:
*	No special handling required
Storage:
*_	All electronic data:_ Reasonable precautions to restrict access to internal staff
*_	Printed material:_ No special handling required
Data Disposal:
*_	All electronic data:_ No special handling required
*_	Printed material:_ Paper shredding. Paper recyling allowed.
###	Confidential
_Description:_ This classification applies to data that is intended solely for use within [company]. Data that is considered private is included in this classification, as well as data covered by data protection legislation and Payment Card Industry standards.
_Accessible by:_ Access should be limited to a need to know basis as required by staff to do their job, and would not be released externally except for regulatory or legal compliance.
_Data Breach Impact:_ Unauthorised disclosure could adversely impact the organisation, its employees and business partners. 
_Examples:_ 
*	Product and service brochures of confidential projects
*	Employee Human Resources data
*	Source code
*	Design specification documents
*	Financial data
*	Purchasing data
*	Vendor contracts
*	Customer data in bulk.
Network Data Transfer Policy:
*	SSH or SSL¬encrypted channel
*_	Email to External accounts:_ Should only be emailed externally on a need to know basis
*_	Email to Internal accounts:_ No special handling required
Transfer via removable storage devices:
*	Access to the storage device should be password¬protected
Storage:
*_	Active electronic data:_ Processing systems must be resistant to unauthorised access
*_	Vaulted electronic data:_ In a lockable enclosure
*_	Printed material:_ In a lockable enclosure
Data Disposal:
*_	All electronic data:_ Secure deletion process such as DBAN.
*_	Printed material:_ Paper shredding. Paper recyling allowed.
###	Secret
_Description:_ This classification applies to the most sensitive business data that is intended strictly for use within the organisation.
_Accessible by:_ Access is limited to as few persons as possible and on a need to know basis. As this data is very sensitive it should be closely controlled from creation to destruction.
_Data Breach Impact:_ Unauthorised disclosure could seriously and adversely impact the organisation, its shareholders, employees and its business partners. 
_Examples:_ 
*	National security and defence
*	Corporate merger and acquisition documents
*	Corporate level strategic plans
*	Litigation strategy
*	HR issues
Network Data Transfer Policy:
*	SSH or SSL-encrypted channel
*_	Email to External accounts:_ Data must be in an encrypted file
*_	Email to Internal accounts:_ Should only be emailed externally on a need to know basis
*_	Transfer via removable storage devices:_ Must be encrypted
Storage:
*_	Active electronic data:_ There should not be any secret data on any processing systems
*_	Vaulted electronic data:_ In a lockable enclosure
*_	Printed material:_ In a lockable enclosure
Data Disposal:
*_	All electronic data:_ Secure deletion process such as DBAN.

