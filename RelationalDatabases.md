# Relational Databases
## Table of Contents
>[**Basic Vocabulary**](#introduction-to-relational-databases)
>
>[**RDMS**](#relational-database-management-systems)
>
>[**Database Architecture**](#database-architecture)
>
>[**Normalization**](#normalization--data-integrity)
>
>[**Security and Backups**](#security-and-backups)
>
>[**Data Engineering**](#data-engineering-considerations)

## Need-to-Know Vocab
- What's the difference between data, a data schema, and a database?
- What is an entity and what is an attribute?
- What makes a SQL databases "structured" and "relational"?

- What does a non-relational database like NoSQL do instead of making the data tabular? Why would someone use a non-relational database?
- What is the role of keys in relational databases? What are some attributes that a primary key must have?

## Relational Database Management Systems
- What are the most common RDBMSs used in the industry?

- How does PostgreSQL differ from MySQL or SQLite?
- When would you choose a specific RDBMS over another?
- How do entity relationship diagrams help employees manage databases?

| Feature / System      | **PostgreSQL**                    | **MySQL**                       | **SQLite**                 |
| --------------------- | --------------------------------- | ------------------------------- | -------------------------- |
| **Best For**          | Complex queries, extensibility    | Web apps, speed, simplicity     | Local apps, prototyping    |
| **SQL Compliance**    | Very high                         | Medium (some limitations)       | Medium                     |
| **Indexing Features** | Rich: B-Tree, GiST, GIN, BRIN     | Basic indexes                   | Limited                    |
| **Partitioning**      | Native partitioning support       | Limited (improving in 8.0+)     | Not supported              |
| **Replication**       | Built-in, streaming, logical      | Native replication              | Not built-in               |
| **Cloud Support**     | AWS RDS, GCP, Azure               | AWS RDS, GCP, Azure             | Used in mobile, local apps |
| **Extensibility**     | Highly extensible (e.g., PostGIS) | Less extensible                 | Not extensible             |
| **Community/Support** | Strong open-source community      | Massive community               | Minimal                    |


## Database Architecture
- What are the main components of a database architecture?

- What are single-tier, two-tier, and three-tier architectures?
## Normalization & Data Integrity
- What are the different normal forms (1NF, 2NF, 3NF, BCNF)?

- Why is normalization important?
- What types of constraints can be applied to a table?
## Security and Backups
- How do user roles and permissions work in an RDBMS?

- What are the different types of backups?
- What is the difference between logical and physical backups?
- What are common replication strategies?
- How do you ensure high availability?
## Data Engineering Considerations
- **What is an ETL pipeline and how is it implemented?**

- What are the differences between OLAP and OLTP?
- What is Change Data Capture (CDC) and how is it used?
- When should you use batch processing vs. streaming?
- What tools are used for orchestration and monitoring?