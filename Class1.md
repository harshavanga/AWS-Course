Assignment 1

1. What is OLAP and OLTP?

Data is stored and processed using two different types of data management systems: OLAP and OLTP. Both are used to store new data and query already-existing data. 
Businesses use OLAP for analytical processing of historical data and transactional processing of real-time transactional data. 

OLAP:
OLAP, short for Online Analytical Processing, is a system tailored for in-depth data analysis and reporting, particularly suited for complex datasets. It excels in processing aggregated data, facilitating tasks such as report generation, intricate data analysis, and trend identification crucial for business insights.
In terms of data formatting, OLAP systems employ multidimensional models, where various dimensions represent distinct data attributes, and the values denote measures at the intersections of these dimensions.
Regarding data architecture, OLAP prioritizes data reading over writing, emphasizing analytical functions over transactional operations. While availability isn't a top priority, the focus lies on efficient data retrieval for analytics purposes.Performance-wise, OLAP systems typically involve longer processing times ranging from minutes to hours. Data updates are scheduled daily, weekly, or monthly, depending on system requirements.Storage and computational demands are significant as OLAP serves as a centralized data repository. Storage needs span from terabytes to petabytes, with computational resources primarily dedicated to data-intensive read operations. OLAP serves as a crucial tool for analyzing data sourced from OLTP systems. It enables tasks like identifying popular products for inventory planning and predicting customer behavior based on purchasing trends, among other business-centric analyses.
