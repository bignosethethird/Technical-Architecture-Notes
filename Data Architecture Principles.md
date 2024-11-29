# Data Architecture Principles

Data Architecture is both an art form and a science for connecting, manageing and democratizing data to enable automation, self-service reporting, data-led decision-making and the creation of new business opportunities.

##  Data is a shared asset

_Rationale:_ 

Enterprises that start with a vision of data as a shared asset ultimately outperform their competition. Instead of allowing departmental data silos to persist, these enterprises ensure that all stakeholders have a complete view of the company, such as improved products and also improved business insights, by being able to correlate data from all systems and business functions. The result of this is better product design, improved corporate efficiency and better business decisions.

_Implications:_ 

- Data decmocratization should make the data available to those that should be able to access it.
- The sharing of data with the organization between persons and processes must be controlled on a need-to-know basis, and good governance processes must exist for the request, issuance and revocation of access to the data. 
- Access and understanding of data makes for better business decisions
- Inaccessible data has no inherent value.

##  Provide the right interfaces for users to consume the data.

_Rationale:_ It is not realistic to put all data in one place to achieve the vision of data-driven products. In order for systems to benefit from a shared data asset, one needs to provide controlled yet usable interfaces that make it easy for systems and business users to consume that data. 

_Implications:_ The interfaces can be in the form of an OLAP interface for business intelligence, an SQL interface for data analysts or a real-time rest-ful API for systems. It is essential that the technical interfaces to the data are available to allow the systems to access required in a system-native way, and for business users to use the tools they know and are right for the job that they need to perform.

##  Ensure security and access controls.

_Rationale:_ The emergence of unified data platforms like Snowflake, Google BigQuery, Amazon Redshift, and map-reduce offerings (Hadoop et al) has necessitated the enforcement of data policies and access controls directly on the raw data, instead of in a web of downstream data stores and applications. 
_Implications:_ The emergence of new data security projects necessitates a unified security-oriented approach, so consider using technologies that allow you to architect for security, and deliver broad self-service access, without compromising control.

##  Establish and maintain a common vocabulary.

_Rationale:_ By investing in an enterprise-wide data approach - likely in the form of an enterprise data hub, enterprises can now create a shared data asset for multiple consumers across a complex product supported by many vendors, or the business with its many departments. The arising ambiguity of the meaning of the data needs to be disambiguaged thorugh the use of an established common vocabulary. With a shared vocabulary, less time will be spent disputing, disambiguating or reconciling results and more time driving improved product output and business performance.

_Implications:_ It is critical that data users analyze and understand the purpose and content of the data in terms of a common vocabulary. System design, product catalogs, data warehouse dimensions, provider hierarchies and KPI definitions all need to be alligned to this common vocabulary, regardless of how users consume or analyze the data. 

## Data must be trustworthy

### Store data securely

###  Curate the data.

By investing in processes that perform data curation, the organization has a better chance of realizing the value of its shared data assets, and is able to collaborate with 

_Rationale:_ Systems and end-users can have a frustrating experience if data is not cleansed, incomplete or misaligned, which reduces the perceived and realized value of the system’s underlying data. 
_Implications:_ 

Typical data problems:

- Dirty data
- Incomplete data
- Inconsistent data
- Uncatalogued data
- Non-compliance of regularatory standards
- Data of unverified provenance

##  Eliminate data copies and movement.

_Rationale: Every time data is moved there is an impact in either or all of these:_ cost, accuracy and time. 

_Implications:_ The fewer times data has to be moved, the better. Part of the promise of cloud data platforms and distributed file systems is a multi-structure, multi-workload environment for parallel processing of massive data sets. These data platforms scale linearly as workloads and data volumes grow. By eliminating the need for additional data movement, modern enterprise data architectures can reduce cost (time, effort, accuracy) and optimize its overall enterprise data agility.

 
# Data Life-Cycle Policy based on its Classification

##  Introduction

This data classification policy details what precautions to take for protecting data with Succession Wealth and also within the customer's enterprise. This policy applies to all forms of data storage, data transport and everyone in the business.

### Data ownership and stewardship

- All data must have an owner who is responsible for understanding the appropriate risks and implications of the owned data going awry. 
- The data owner is responsible for assigning the sensitivity classification level of the data and must ensure that it is consistently protected throughout its life cycle up to the point of where the data is destroyed.
- Data must be protected in a manner commensurate with its sensitivity classification, regardless of where the data resides, what electronic or printed form it is in, and what technology is used to handle the data.

Data Sensitivity Classification is described in the the document "Data Classification Policy".



 # Implementation steps

 - Understand the goals for implementing a data governance regime, guided by policies and how the business consumes the data
 - Build a data governance team consisting of data owners / stewards / SMEs and continually engage with them
 - Install the right tools and processes to support the data governance initiative
 
