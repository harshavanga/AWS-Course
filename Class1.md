## Assignment 1

### 1. What is OLAP and OLTP?

Data is stored and processed using two different types of data management systems: OLAP and OLTP. Both are used to store new data and query already-existing data. 
Businesses use OLAP for analytical processing of historical data and transactional processing of real-time transactional data. 

OLAP:

OLAP, short for Online Analytical Processing, is a system tailored for in-depth data analysis and reporting, particularly suited for complex datasets. It excels in processing aggregated data, facilitating tasks such as report generation, intricate data analysis, and trend identification crucial for business insights.
- In terms of data formatting, OLAP systems employ multidimensional models, where various dimensions represent distinct data attributes, and the values denote measures at the intersections of these dimensions.
- Regarding data architecture, OLAP prioritizes data reading over writing, emphasizing analytical functions over transactional operations. While availability isn't a top priority, the focus lies on efficient data retrieval for analytics purposes.Performance-wise, OLAP systems typically involve longer processing times ranging from minutes to hours.
-  Data updates are scheduled daily, weekly, or monthly, depending on system requirements.Storage and computational demands are significant as OLAP serves as a centralized data repository. Storage needs span from terabytes to petabytes, with computational resources primarily dedicated to data-intensive read operations.
-  OLAP serves as a crucial tool for analyzing data sourced from OLTP systems. It enables tasks like identifying popular products for inventory planning and predicting customer behavior based on purchasing trends, among other business-centric analyses.


OLTP:

OLTP, or Online Transaction Processing, is geared towards the swift processing of transactional data with immediate updates. Its primary function is to manage database transactions such as order processing, customer account management, and inventory updates.
- In OLTP systems, data is structured in a single dimension and stored within relational databases. Each row represents a specific instance, while columns denote attributes associated with those instances.
- Data architecture in OLTP systems emphasizes prioritizing write operations to efficiently handle high-frequency and high-volume transactional data while upholding data integrity. For instance, in cases where simultaneous purchases of the same product occur, the system considers chronological order, prioritizing the fulfillment of the first customer's order if stock is limited.
- Ensuring availability is paramount, achieved through the maintenance of multiple data backups. Performance-wise, OLTP systems excel in rapid processing, typically achieving processing times in milliseconds or less. Real-time updates ensure the accuracy and consistency of data.
-  Storage requirements for OLTP systems typically range in gigabytes, as data may be periodically transferred to OLAP systems for deeper analysis. These systems also demand significant computational resources to efficiently handle transactional processing.
- Examples of OLTP usage encompass real-time transaction processing, dynamic updates of inventory levels, and the management of customer accounts including rewards and returns.

### 2. Differences between OLAP and OLTP

|OLAP|OLTP|
|:---|:---|
|Analyze aggregated data, generate reports, identify trends for business intelligence|Process database transactions in real-time, manage orders, accounts, inventory|
|Multidimensional data models|Unidimensional, relational databases|
|Prioritizes data read operations, availability not as critical|Prioritizes data write operations, availability crucial|
|Longer processing times (minutes to hours), less frequent updates|Faster processing times (milliseconds or less), real-time updates|
|Centralized data store, compute-intensive data reads	|Gigabytes storage, significant computational resources|
|Analyzing data for inventory budgeting, predicting customer behavior|Processing orders, updating inventory levels|

### 3. Normal Forms:

Normalization is the process of organizing data into separate tables/entities and establishing relationships between them using unique identifiers. This practice is crucial for safeguarding data against anomalies during insertion, update, and deletion, thereby ensuring data integrity and consistency. There are four main normal forms (NFs) in database normalization:

**First Normal Form (1NF)**:
Attributes/column values must be atomic and not contain repeating groups.
Values within attributes should be of the same type.
Attributes must be unique.
The order of attributes should not matter.
Each row must be uniquely identifiable, requiring a primary key.

**Second Normal Form (2NF)**:
The database must adhere to 1NF requirements.
Each non-key attribute should depend on the entire primary key (in the case of a composite primary key), avoiding partial dependencies.

**Third Normal Form (3NF)**:
The database must satisfy 1NF and 2NF criteria.
None of the non-key attributes should depend on other non-key attributes, eliminating transitive dependencies.
BCNF is a stricter version of 3NF.
Every attribute in a table should depend solely on the key, known as the whole key, without any other dependencies.

**Fourth Normal Form (4NF)**:
The database must meet the requirements of 1NF, 2NF, 3NF, and BCNF.
It should not contain any multivalued dependencies, where an attribute's value depends on multiple values from other attributes.


### 4. Dimension vs Fact Tables

**Dimension Table**:
Dimensions refer to distinct entities within the dataset, such as customers, orders, time, and products. Each of these entities is represented by individual tables known as dimension tables.

**Fact Table**:
Fact tables store measures derived from the dimensions. These measures are stored in a centralized fact table.

Types of Dimensions:

Static Dimension:
A dimension that remains constant over time, such as gender or status.

Slowly Changing Dimension (SCD):
This type of dimension table experiences gradual changes over time, though not frequently. For instance, the address of a customer may change in the future. SCDs can be categorized into three types: Type 1 (no historical data retained), Type 2 (complete historical data maintained with start and end dates to determine validity), and Type 3 (limited history stored, often just the current and previous records).

Conformed Dimension:
A dimension that can be shared across multiple fact tables, such as a place or time dimension.

Degenerate Dimension:
When a dimension is present directly within the fact table instead of being referenced through a dimension table, it is termed a degenerate dimension.

Junk Dimension:
This dimension combines unrelated, small dimensions into a single dimension to simplify data management.



### 5. Snowflake and Star Schemas

**Star Schema**:
The star schema is a straightforward type of data warehouse schema, visually resembling a star. It comprises a central fact table surrounded by dimension tables. Data retrieval involves a single join between the dimension and fact tables. In this schema, dimension tables may not necessarily be normalized.

**Snowflake Schema**:
The snowflake schema expands upon the star schema by incorporating additional dimensions, resulting in a structure reminiscent of a snowflake. Here, the fact table is encircled by dimension tables, which in turn are surrounded by further dimension tables. Retrieving data from dimensions and fact tables requires multiple joins. Notably, the dimension tables in this schema are normalized, leading to their division into multiple dimension tables.



