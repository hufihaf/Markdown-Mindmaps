# Data Lakehouse Strategy and Implementation with Cloud Services
## Table of Contents
>[Vocabulary](#vocabulary)
>
>[Data Warehouse](#data-warehouse)
>
>[Data Lake](#data-lake)
>
>[Data Lakehouse](#data-lakehouse)
>
>[AWS Implementation](#how-to-implement-with-aws)
>
>[Azure Implementation](#how-to-implement-with-azure)
>
>[My Project](#my-project)

## Vocabulary
- What is **structured/unstructured/semi-structured data**?

- What is **ETL/ELT**?
- What are **SQL queries**?
- What is the difference between **blocks** and **objects**? What happens when you change either?
- What is an **API**? 
- What is **Amazon S3** capable of? How do you differentiate it from **Amazon EBS** or **EFS**?
- What is **schema-on-write / schema-on-read**?

## Data Warehouse
- What data **format(s)** exist in a data warehouse?

- How would you **transform** your data into that format?
- What data warehouse services are provided by **AWS/Azure/GCP**?
- What are **drawbacks** of the data warehouse strategy?
- What is the **main strength** that a data warehouse has over a data lake?
- Why is this strategy no longer the **industry default**?
    - Consider cost, modern data formats, compatability with ML models and ML model training, 
- Again, what is **schema-on-write** and what is **block storage**?

## Data Lake
- What data **format(s)** exist in a data warehouse?

- At what point is the data **transformed**, if at all?
- What data lake services are provided by **cloud service providers**?
- What is the **main strength** of a data lake over a data warehouse?
- Again, what is **schema-on-read**?
- Why is this option **cheaper**?

## Data Lakehouse
- What **problems** does a Lakehouse architecture solve?

- How do you implement a Lakehouse in **AWS/Azure/GCP**?
- How does a Lakehouse work **under the hood**?
- In a lakehouse, what **formats** are structured datasets put in?
- What services can you use to make the data queryable?

## How to implement with AWS
1. Create an S3 Bucket and make three zones for raw data, cleaned data, and curated data.

2. Set up a database in AWS Glue.
3. Setup Apache Iceberg as your table format.
- schema evolution, partition pruning, and ACID transactions to Parquet your data in S3.
4. Create Iceberg tables with Amazon Athena
5. Ingest data into the raw file storage. Use AWS Glue to transform certain datasets and write them to the curated Iceberg tables
6. Query the data with Amazon Athena, or use Amazon QuickSite with dashboards

## How to implement with Azure
1. Create an Azure Data Lake Storage Gen2 (organize raw, bronze, silver, gold files)

2. Use Azure Databricks (not really sure how this works).
3. Create data tables
4. Query with SQL and Python
5. Connect to PowerBI.

## My Project
- My data is entirely unstructured.

- I have a lot of data from a variety of sources. I need this data centralized and accesible with APIs. 
- An AWS Datalake is the best option here.
- 6/30/25 -> set up the S3 bucket. failed to set up API ingestion (no permissions).
- 7/1/25 -> API key and address from sam.gov and data.gov gathered. Need to gain permissions still. Requested access to Athena and QuickSight services in order to get the output layer going. On second note, it doesn't seem that my project domain extends to visualization - I just need that API layer (Athena). Does this API layer work with PowerBI? -> Yes, just need Open Database Connectivity (ODBC) driver installed on PowerBI. 