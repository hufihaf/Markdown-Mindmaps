# Azure Data Engineering
## Main Storage Service: Data Lake Storage Gen2 (ADLS)
- Microsoft equivalent of the S3 Bucket -> object level storage that is heavily compatible with other tools

## Data Ingestion with Multiple API's
- set up the hierarchy in the ADLS (preferrably one file for each API?)

- fetch data with an Azure function (like Lambda)
    - one function for each API seems to be the SOP. Pipe the data to the appropriate "file" in the ADLS.
- you would also use Azure functions to process the data -> they do not have an AWS Glue equivalent. perhaps each API function could pipe the data into this one processor function to reduce complexity.
- I should research **Azure Data Factory** (might be another way to process our data)