# Data Architecture Principles

# Data is ashared asset

Enterprises that start with a vision of data as a shared asset ultimately outperform their competition. Instead of allowing departmental data silos to persist, these enterprises ensure that all stakeholders have a complete view of the company, such as a 360-degree view of customer insights along with the ability to correlate valuable data signals from all business functions, including manufacturing and logistics. The result of thos type of data intelligence is improved corporate efficiency.

# Provide the right interfaces for users to consume the data.

Putting data in one place isn't enough to achieve the vision of a data-driven organization. In order for people (and systems) to benefit from a shared data asset, one needs to provide the interfaces that make it easy for users to consume that data. This might be in the form of an OLAP interface for business intelligence, an SQL interface for data analysts, a real-time API for targeting systems, or an R language interface for data scientists. In the end, it's about letting your people work in the tools they know and are right for the job they need to perform.

# Ensure security and access controls.

The emergence of unified data platforms like Snowflake, Google BigQuery, Amazon Redshift, and Hadoop has necessitated the enforcement of data policies and access controls directly on the raw data, instead of in a web of downstream data stores and applications. The emergence of data security projects like Apache Sentry makes this approach to unified data security a reality. Look to technologies that allow you to architect for security, and deliver broad self-service access, without compromising control.

# Establish a common vocabulary.

By investing in an enterprise data hub, enterprises can now create a shared data asset for multiple consumers across the business. However, it's critical data users analyze and understand the purpose and content of the data in terms of a common vocabulary. Product catalogs, fiscal calendar dimensions, provider hierarchies and KPI definitions all need to be alligned to this common vocabulary, regardless of how users consume or analyze the data. Without this shared vocabulary, you'll spend more time disputing or reconciling results than driving improved performance.

# Curate the data.

Without proper data curation on self-serve data access and writing to raw data on cloud-based data platforms like S3, data lakes, GCP nand Hadoop, which includes modeling important relationships, cleansing raw data and curating key dimensions and measures, ­end users can have a frustrating experience-which will vastly reduce the perceived and realized value of the underlying data. By investing in core functions that perform data curation, you have a better chance of realizing the value of the shared data asset.

# Eliminate data copies and movement.

Every time data is moved there is an impact; cost, accuracy and time: the fewer times data has to be moved, the better. Part of the promise of cloud data platforms and distributed file systems is a multi-structure, multi-workload environment for parallel processing of massive data sets. These data platforms scale linearly as workloads and data volumes grow. By eliminating the need for additional data movement, modern enterprise data architectures can reduce cost (time, effort, accuracy, increase "data freshness" and optimize overall enterprise data agility.
