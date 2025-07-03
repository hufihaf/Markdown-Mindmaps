# Data Lakehouse Strategy and Implementation with Cloud Services
## Table of Contents
>[**Vocabulary**](#vocabulary)
>
>[**Data Warehouse**](#data-warehouse)
>
>[**Data Lake**](#data-lake)
>
>[**Data Lakehouse**](#data-lakehouse)
>
>[**Data Engineering in AWS**](#data-engineering-in-aws)
>
>[**Azure Data Engineering**](#azure-data-engineering)
>
>[]()

## <span style="color:orange">Vocabulary</span>
- What is **structured/unstructured/semi-structured data**?

- What is **ETL/ELT**?
- What are **SQL queries**?
- What is the difference between **blocks** and **objects**? What happens when you change either?
- What is an **API**? 
- What is **Amazon S3** capable of? How do you differentiate it from **Amazon EBS** or **EFS**?
- What is **schema-on-write / schema-on-read**?

## <span style="color:orange">Data Warehouse</span>
- What data **format(s)** exist in a data warehouse?

- How would you **transform** your data into that format?
- What data warehouse services are provided by **AWS/Azure/GCP**?
- What are **drawbacks** of the data warehouse strategy?
- What is the **main strength** that a data warehouse has over a data lake?
- Why is this strategy no longer the **industry default**?
    - Consider cost, modern data formats, compatability with ML models and ML model training, 
- Again, what is **schema-on-write** and what is **block storage**?

## <span style="color:orange">Data Lake</span>
- What data **format(s)** exist in a data warehouse?

- At what point is the data **transformed**, if at all?
- What data lake services are provided by **cloud service providers**?
- What is the **main strength** of a data lake over a data warehouse?
- Again, what is **schema-on-read**?
- Why is this option **cheaper**?

## <span style="color:orange">Data Lakehouse</span>
- What **problems** does a Lakehouse architecture solve?

- How do you implement a Lakehouse in **AWS/Azure/GCP**?
- How does a Lakehouse work **under the hood**?
- In a lakehouse, what **formats** are structured datasets put in?
- What services can you use to make the data queryable?

## <span style="color:orange">Data Engineering in AWS</span>
### <span style="color:darkred">The S3 Bucket</span>
- what is object-level storage?

- how do you set up an API / SQL layer for the S3 bucket?
- what are bucket lifecycle rules?
- how do you process data in a bucket?

#### <span style="color:green">Methods of ingesting data into a bucket</span>
- manually through AWS management console

- AWS CLI -> great for scripting, getting a lot of data on a machine into a bucket
- SDK (Python) -> libraries like boto3 allow for scripting files into the bucket, provided that you have the key, location, etc.
- **REST API** -> to set this up, you just need to create a presigned url (Python boto3 is able to do this), which requires that you generate a key. Make the url temporarily accessible (for security), then share it to a client that has the data -> they use the url in this command:
    ```
    curl -X PUT -T "file.txt" "<url>" 
    ```
- **AWS DataSync** -> transfer data from on-prem to S3 quickly -> set up agent which connects to the S3. Give agent a source and a destination (can be NFS, SMB, or EFS). 
- B.N. -> If the data is spread across multiple API's, we could just set up a Lambda function for each API (or make some sort of handler) and point them all to the S3 bucket to ingest.

#### <span style="color:green">Between Ingestion and Storage -> Processing</span>
- Critical step -> we do not want duplicate, mysterious, inconsistent data.

- Solution = put data in same format, schema (if possible), clean the data, flatten the data (Athena), partition the data (naming it well), add tags, and perhaps compress.
- How? -> AWS Glue can do the entire thing. Lambda can too, but you'll have to write the code yourself (may be necessary... again - we need to see the data).

#### <span style="color:green">Data output</span>
- Handled by the Athena service

## <span style="color:orange">Azure Data Engineering</span>
### <span style="color:darkred">Main Storage Service: Data Lake Storage Gen2 (ADLS)</span>
- Microsoft equivalent of the S3 Bucket -> object level storage that is heavily compatible with other tools

### <span style="color:darkred">Data Ingestion with Multiple API's</span>
- set up the hierarchy in the ADLS (preferrably one file for each API?)

- fetch data with an Azure function (like Lambda)
    - one function for each API seems to be the SOP. Pipe the data to the appropriate "file" in the ADLS.
- you would also use Azure functions to process the data -> they do not have an AWS Glue equivalent. perhaps each API function could pipe the data into this one processor function to reduce complexity.
- I should research **Azure Data Factory** (might be another way to process our data)

## Necessary Step Before Any Storage: ETL
- for our project, we need to parse tables out of pdf's

- a few python libraries exist that can help, namely:
    - **camelot / tabula / pdfplumber** have similar capabilities. Which should we use?
    - **PyMuPDF** has more granular control, in case the previous do not work (not automatic).