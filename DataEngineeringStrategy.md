# Data Engineering Strategy
## Table of Contents
>[Vocabulary](#vocabulary-to-get-used-to)
>
>[General Process](#general-process)
>
>[Optimizing with AI](#optimizing-with-ai)
>
>[My Project at GBL](#my-project-at-gbl)
>
>[Other Important Considerations](#other-important-considerations)

## Vocabulary
- What is **data engineering**?

- What is **DevOps** and how does it differ from the '**waterfall**' development process?
- What is **CI/CD**?
- What does **ETL** stand for? What is an ETL pipeline?
- Difference between an **object/file/block**?
- What is **IoT** and what are some examples of these types of devices?

## General Process
### 1. Data Ingestion
- What is data ingestion?

- What is **batch mode** ingestion? What is streaming?
- What is a push model? What is a **pull model**?
### 2. Data Transformation
- What is data transformation?
- What are the general steps (give 5) in data transformation?
### 3. Data Storage
- What are some key things to consider when choosing your storage solution?

- What is **data temperature**? If data is accesed frequently, is it hot or cold?
- What are the various storage solutions? What is a **data lake**?
### 4. Data Serving
- What are some of the many ways data can be implemented?

- What tools turn processed data into clean analytics?
- Why is processed data so crucial for ML training?
- What is **reverse ETL**?
## Optimizing with AI
- What is a **RAG** LLM?

- What step in the process is simplified with **Synthia**? 
- What step in the process is simplified with **PandasAI**? 
- What step in the process is simplified with **FastAPI**, **Django**, or **Flask**?

## My Project at GBL
### disparate/siloed tabular data (found in a mixture of CSVs and actual databases) --> bring into a singular data lake (which will then have api endpoints to allows people to access it). How do I do that?
1. Choose your data lake technology:

    - AWS: S3 + Glue + Athena + API Gateway/Lambda  

    - Azure: Data Lake Storage Gen2 + Synapse + API Management

    - On-prem: Hadoop HDFS, MinIO, or Delta Lake (Databricks)

2. Ingest data from sources you have:

    - CSVs: Flat files

    - Databases: Likely MySQL, Postgres, or SQL Server

    - Ingest these using ETL tools or custom code:

        - For CSVs:
            - read them with Python (Pandas), Spark, or Airbyte/Fivetran.

            - Validate and clean (deduplication, formatting).

            - Upload to data lake (e.g., S3) with structured foldering:  

                ```
                s3://your-bucket/data/source_name/yyyy/mm/dd/file.csv
                ```

        - For Databases
            - Use ETL tools:

                - Airbyte (open-source)

                - Fivetran (managed)

                - Apache NiFi

                - Or write custom Python/SQLAlchemy + pandas scripts to extract → clean → upload to lake.

3. Normalize and Catalog the Data  
You want unified, queryable formats.

    - Convert data to Parquet or Delta Lake formats (efficient + columnar)

    - Register metadata/catalogs using:

        - AWS Glue Data Catalog

        - Apache Hive Metastore

        - DataHub / Amundsen (for data discovery)

5. Expose via APIs now that data is consolidated, cleaned, and queryable:

    - API Options
        - AWS: Lambda functions + API Gateway that query Athena or access S3 directly

        - Python:

            - Use FastAPI or Flask of Django

            - Connect to Presto/Trino/BigQuery to return results via REST

        - Query Use Case Example:

            ```
            @app.get("/sales/{region}")
            def get_sales(region: str):
                df = run_query(f"SELECT * FROM sales WHERE region = '{region}'")
                return df.to_dict(orient="records")
            ```

- Example Stack (if using AWS):  

    | Purpose	 | Tool                  |
    |------------|-----------------------|
    |Storage	 | S3                    |
    |ETL	     |AWS Glue               |
    |Query engine|	AWS Athena           |
    |API layer	 |FastAPI on Lambda      |  

### General idea:
- Raw Data (csv, json, pdf) goes through AWS Glue (ETL pipeline)

- Glue moves data to S3 bucket (or other data lake technologies). In this process, Python scripts can be run to clean individual datasets
- S3 bucket's data is made accessible with AWS Athena, which provides the API layer

## Other Important Considerations
### Flask, Django, and FastAPI Compared
#### Flask
-

-
-
#### Django
-

-
-
#### FastAPI
-

-
-

### Various Datalake possibilities
#### S3 Bucket
-

-
-
#### AWS DBS
-

-
-
#### PostgreSQL
-

-
-