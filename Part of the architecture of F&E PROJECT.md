# F&E DATA ENGINEERING PROJECT

1	**INTRODUCTION**

This project involves building a scalable data pipeline to support a commercial dashboard for a pharmaceutical company's Neurology and Immunology (NI) business. The data engineering tasks include:

Data Ingestion: Collect data from sources like IQVIA RxDynamics, SAP, and Salesforce, and store it in AWS S3.
Data Processing: Use AWS Glue and AWS Lambda for ETL processes, including file validation, transformation, and loading into AWS Redshift.
Data Storage: Build a data warehouse on Redshift using a Star Schema for efficient querying and reporting.
Data Integration: Combine data from multiple sources into a unified format for analysis.
Data Quality: Implement validation checks and monitor data quality using AWS CloudWatch.
Automation: Automate ETL pipelines with event-driven triggers and scheduling.
Accessibility: Connect processed data to Tableau for dashboard creation and ensure role-based access control (RBAC).
Scalability: Design a serverless, scalable architecture using AWS services.
Security: Encrypt data, manage access with AWS IAM, and ensure compliance with regulations.
Monitoring: Use CloudWatch for pipeline performance tracking and issue resolution.
The outcome is a robust data infrastructure that enables real-time insights, supports 15 Tableau dashboards, and drives data-driven decision-making for the pharmaceutical company.

2 **AWS SERVICES USED IN THE PROJECT** :

1. Data Storage
AWS S3 (Simple Storage Service):
Used for storing raw and processed data files (e.g., CSV, XLS).
Acts as a data lake for archival and backup purposes.

2. Data Processing
AWS Glue:
Fully managed ETL service for data extraction, transformation, and loading.
Handles file validation, format conversion (e.g., XLS to CSV), and data cataloging.

AWS Lambda:
Serverless compute service for event-driven data processing.
Triggers ETL jobs and performs lightweight transformations.

3. Data Warehousing
AWS Redshift:
Fully managed data warehouse for storing and querying structured data.
Supports the Star Schema for efficient analytics and reporting.

4. Monitoring and Logging
AWS CloudWatch:
Monitors ETL jobs, Lambda functions, and Redshift performance.
Provides alerts for failures or performance bottlenecks.

5. Security and Access Management
AWS IAM (Identity and Access Management):
Manages user permissions and role-based access control (RBAC).
Ensures secure access to AWS resources.
AWS KMS (Key Management Service):
Used for encrypting data at rest and in transit.

6. Infrastructure as Code (IaC)
Terraform:
Deploys and manages AWS infrastructure (e.g., S3 buckets, Glue jobs, Redshift clusters).
Ensures repeatable and version-controlled infrastructure setup.

7. Data Visualization Integration
Tableau:
Connected to AWS Redshift for creating interactive dashboards.
Publishes dashboards on the Tableau Server for stakeholder access.

With the foundational data engineering framework in place, the next critical phase is the 

3 **APPLICATION ARCHITECTURE**

Application architecture refers to the design and structure of the FE Project. It defines how the different components of the application interact with each other, how data flows between them, and how they collectively fulfill the application’s functional and non-functional requirements.

3.2	Solution Overview:
This document presents the solution architecture for the data analytics project serving the Fertility and Endo department. The aim is to provide valuable insights on medications and enable better business/client decisions.

3.3	Application Layers:
The solution is designed as a data value chain, starting with dataset ingestion, followed by data processing and storage. Downstream, data visualization is implemented to offer UpToDate, consistent, and reliable data visualization for end-users.

                                                Application Architecture
![Image](https://github.com/user-attachments/assets/70304476-b5be-4854-bd78-9840a3685f20)

 
3.4 IBOND APPLICATION LAYER 

The IBOND application layer is a data retrieval system built in the AWS Cloud architecture. It retrieves specific defined objects from Salesforce directly, allowing easy access and data manipulation on the cloud layer. The FE project utilizes this pre-built system to integrate existing data and load it into AWS Redshift for later binding with other FE patient data sets.

                                                IBOND Application Layer
![Image](https://github.com/user-attachments/assets/0b65f1b7-d116-4b40-b20c-a60f575903f2)

4 INTEGRATION ARCHITECTURE 

The integration architecture phase is a critical step in the IT project lifecycle, focusing on designing a cohesive framework to integrate systems, applications, and data sources. The goal is to enable seamless communication, data exchange, and interoperability across disparate systems.

For data ingestion, the project adopts the ETL (Extract, Transform, Load) architecture pattern, with three defined ETL workflows:

Advanced ETL:
Validates files, converts XLS to CSV, extracts and transforms data, and loads it into the Redshift staging area and multidimensional model.

Intermediary ETL:
Validates files, extracts data from CSV, and loads it into the Redshift staging area and multidimensional model.

Basic ETL:
Validates files and extracts data from CSV, loading it into the Redshift staging area.

This structured approach ensures efficient data integration, supporting the project's goal of delivering actionable insights through a unified data pipeline.

### ADVANCED ETL 

This pattern involves file validation, converting files from XLS to CSV format, extracting data from CSV files, transforming it, loading it into the Redshift staging area, and finally loading it into the Redshift multidimensional model.

  <img width="610" alt="Image" src="https://github.com/user-attachments/assets/48cf8a25-96f5-4679-8602-28e079e3e380" />

## Intermediary ETL 

In the Intermediary ETL pattern, we perform file validation, extract data from CSV files, load it into the Redshift staging area, and then load it into the Redshift multidimensional model.

<img width="638" alt="Image" src="https://github.com/user-attachments/assets/4bb8a1ef-449d-47ea-b2df-ef5fc003156f" />

5	 Patterns (Solution Architecture Attributes):

   Star Schema The solution will adopt the Star schema for the data architecture of the data warehouse. 
The Star schema is a data modeling technique used in data warehousing and business intelligence (BI) systems. It has a simple and intuitive structure that resembles a star shape when visualized. In the Star schema, the central entity known as the "fact table" contains the primary measures or metrics of interest, such as sales revenue or product quantities. 

The fact table is surrounded by multiple related dimension tables, providing descriptive attributes about the measures. Key characteristics of the Star schema:

Fact Table: Holds numerical or quantitative data representing business metrics and contains foreign keys for establishing relationships with dimension tables. 

Dimension Tables: Provide descriptive attributes associated with the measures in the fact table, such as time, geography, product, customer, etc., and contain primary keys connecting to the fact table. 

Denormalized Structure: Star schemas are denormalized, simplifying query processing and improving performance for reporting and analysis tasks. 	One-to-Many Relationships: Relationships between the fact table and dimension tables are typically one-to-many.

Simplicity and Performance: The star schema offers simplicity and ease of use for data analysis, with efficient queries due to the flat structure and reduced joins. The Star schema design facilitates efficient querying and reporting for BI and analytical purposes, allowing users to navigate and analyze data along different dimensions intuitively.


The data modeling phase is crucial in the software development life cycle, specifically in database design. It involves creating a conceptual representation of the data to be stored and managed. Key aspects of the data modeling phase for the NI Project include:

1.	Conceptual Data Model: Focuses on business requirements and high-level data entities using Entity-Relationship (ER) diagrams.
2.	Logical Data Model: Refines the conceptual model into a detailed structure independent of specific technology.
3.	Normalization: Eliminates data redundancy and improves data integrity through normalization.
4.	Physical Data Model: Transforms the logical model into a specific structure for the target database management system (DBMS).
5.	Data Modeling Tool: Utilizes specialized software tools like Oracle SQL Developer for creating, visualizing, and managing data models.

The output of the data modeling phase is a well-defined and documented data model serving as a blueprint for efficient database design and maintenance throughout the FE project lifecycle.

                                                        Logical Data Modeling
 
<img width="711" alt="Image" src="https://github.com/user-attachments/assets/f48770f7-b784-4270-be50-4320186b2683" />

**Conclusion
**
In summary, the data architecture phase focuses on designing the structure, organization, storage, and management of data assets within an organization. It ensures that data is efficiently collected, stored, integrated, secured, and governed to support business objectives and enable effective data-driven decision-making.





## Prerequisites and technology capacity specs

Infrastructure architecture involves designing and planning the technology infrastructure that supports an organization's IT systems and operations. It entails creating a blueprint for the hardware, software, networks, storage, and other components needed to build a strong and scalable IT infrastructure.

<img width="747" alt="Image" src="https://github.com/user-attachments/assets/a7871b70-52f4-44b7-b7af-cafd71b1551b" />

First script to consume data from sharepoint file
1. Key Functionality
The script performs the following tasks:
1. Authenticate with SharePoint:
    * Retrieves an access token using OAuth 2.0 client credentials flow.
    * Uses the access token to interact with the SharePoint REST API.
2. Retrieve Files from SharePoint:
    * Lists all files in a specified SharePoint folder (pickup_folder_path).
3. Download and Upload Files:
    * Downloads each file from the SharePoint folder.
    * Uploads the downloaded file to a specified Amazon S3 bucket (trg_bucket).
4. Archive Files in SharePoint:
    * Moves each file from the pickup folder to an archive folder in SharePoint.
    * The archive folder path includes the current date to organize archived files.
5. Error Handling:
    * Handles errors during authentication, file retrieval, download, upload, and archiving.
    * Logs errors and returns appropriate status codes.
  


