# Data Lake Implementation in AWS and Azure

## <span style="color:darkgray">Basic High Level Data Lake Architecture</span>

### <span style="color:gray">Object Storage</span>
- object level storage 

- accesible via APIs and HTTPS
- rich metadata on objects
- cheap
- main purpose is to read, not to write (WORM)
- integratable with analytical tools
### <span style="color:gray">Data Ingestion (In)</span>
- source identification -> APIs, files, databases, etc.

- batch vs. streaming vs. manual
    - scheduled, IoT, uploads/scripts, respectively
### <span style="color:gray">Data Lake Zones</span>
- Bronze / Silver/ Gold "Buckets" -> really zones within the lake

- What happens to data ingested into bronze bucket?
- What is in the gold bucket? What is special about it?
- ETL pipeline
### <span style="color:gray">ELT Pipeline (Out)</span>
- similar to process above

- what do you want to do with the data pulled
- can be a replacement for the bucket process entirely
## <span style="color:darkgray">AWS Implementation vs Azure Implementation, Organized from SaaS to IaaS</span>
<table>
<tr>
<th>
    <span style="color:orange">AWS</span>
</th>
<th>
<span style="color:#0096FF">Azure</th>
</th>
</tr>

<tr>
<td>

- Storage - Amazon S3
- Query Engine - Athena / Spark with Amazon EMR / Trino
- ETL/ELT - AWS Step Functions with Glue / Apache NiFi (ingest) with Apache Spark (transform)
</td> 

<td>

- Storage - ADLS Gen2
- Query Engine - Azure Synapse Serverless SQL / Trino
- ETL/ELT - Azure Data Factory / Apache Spark or Databricks
</td>
</tr>
</table>

## <span style="color:darkgray">Unique Strengths of Each</span>
<table>
    <tr>
        <th>
            <span style="color:orange">AWS</span>
        </th>
        <th>
            <span style="color:#0096FF">Azure</th>
    </tr>
<tr>
<td>  

- Amazon Kinesis simplifies real-time data ingestion

- AWS Lake Formation centralizes the data lake governance into one console. You can also make security controls here.
</td>   
<td>

- Azure Synapse Analytics streamlines the SQL setup and the ETL pipelines into one UI

- Data Factory is a visual ETL tool
- Direct allows one to link data lake to Power BI very easily
        </td>
    </tr>
</table>

## <span style="color:darkgray">Check Out [PDF ETL](PDF_Ingestion_Techniques.md)</span>