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

5 INTEGRATION ARCHITECTURE 

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

<img width="610" alt="Image" src="https://github.com/user-attachments/assets/a39603be-9cad-4ef1-b040-16bc0959a0af" />

### Basic ETL
In the Basic ETL pattern, we conduct file validation, extract data from CSV files, and load it into the Redshift staging area.
In the Basic ETL pattern, we conduct file validation, extract data from CSV files, and load it into the Redshift staging area.![image](https://github.com/user-attachments/assets/caa1f5a4-e4b1-4eb7-bffa-fece697a93e7)


![Image](https://github.com/user-attachments/assets/0b65f1b7-d116-4b40-b20c-a60f575903f2)

If you decide to include this, you should also talk a bit about why you chose the architecture and tools you did for this project.

## Prerequisites

Directions or anything needed before running the project.

- Prerequisite 1
- Prerequisite 2
- Prerequisite 3

## How to Run This Project

Replace the example step-by-step instructions with your own.

1. Install x packages
2. Run command: `python x`
3. Make sure it's running properly by checking z
4. To clean up at the end, run script: `python cleanup.py`

## Lessons Learned

It's good to reflect on what you learned throughout the process of building this project. Here you might discuss what you would have done differently if you had more time/money/data. Did you end up choosing the right tools or would you try something else next time?

## Contact

Please feel free to contact me if you have any questions at: LinkedIn, Twitter
