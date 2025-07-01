# Data Engineering in AWS
## The S3 Bucket
- what is object-level storage?

- how do you set up an API / SQL layer for the S3 bucket?
- what are bucket lifecycle rules?
- how do you process data in a bucket?

### Methods of ingesting data into a bucket
- manually through AWS management console

- AWS CLI -> great for scripting, getting a lot of data on a machine into a bucket
- SDK (Python) -> libraries like boto3 allow for scripting files into the bucket, provided that you have the key, location, etc.
- **REST API** -> to set this up, you just need to create a presigned url (Python boto3 is able to do this), which requires that you generate a key. Make the url temporarily accessible (for security), then share it to a client that has the data -> they use the url in this command:
    ```
    curl -X PUT -T "file.txt" "<url>" 
    ```
- **AWS DataSync** -> transfer data from on-prem to S3 quickly -> set up agent which connects to the S3. Give agent a source and a destination (can be NFS, SMB, or EFS). 
- B.N. -> If the data is spread across multiple API's, we could just set up a Lambda function for each API (or make some sort of handler) and point them all to the S3 bucket to ingest.

### Between Ingestion and Storage -> Processing
- Critical step -> we do not want duplicate, mysterious, inconsistent data.

- Solution = put data in same format, schema (if possible), clean the data, flatten the data (Athena), partition the data (naming it well), add tags, and perhaps compress.
- How? -> AWS Glue can do the entire thing. Lambda can too, but you'll have to write the code yourself (may be necessary... again - we need to see the data).

### Data output
- Handled by the Athena service