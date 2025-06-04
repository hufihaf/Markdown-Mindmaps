# Relational Databases
## Table of Contents
>[]()
>
>[]()
>
>[]()
>
>[]()
>
>[]()
>
>[]()
>
>[]()
>
>[]()
>
>[]()
>
>[]()
>
>[]()
>
>[]()

## Introduction to Relational Databases
- How is data organized in relational databases?

- What is the role of keys in relational databases?
- What is a primary key and why is it important?
- What is a foreign key?
- What is a schema in a database?

## Relational Database Management Systems (RDBMSs)
- What are the most common RDBMSs used in the industry?

- How does PostgreSQL differ from MySQL or SQLite?
- When would you choose a specific RDBMS over another?

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


## SQL: Structured Query Language
- What is CRUD?

## Database Architecture
- What are the main components of a database architecture?

- What roles do the SQL engine, parser, optimizer, and executor play?
- What is the function of the storage engine and buffer pool?
- How do single-tier, two-tier, and three-tier architectures differ?
## Normalization & Data Integrity
- What are the different normal forms (1NF, 2NF, 3NF, BCNF)?

- Why is normalization important?
- What types of constraints can be applied to a table?
## Indexes, Views, and Transactions
- What are the different types of indexes?

- How do views work and when should you use them?
- What are transactions and what are the ACID properties?
## Security and Permissions
- How do user roles and permissions work in an RDBMS?

- What are the SQL commands to grant or revoke permissions?
- What methods are used to secure data at-rest and in-transit?
## Performance Tuning & Optimization
- How do you analyze and optimize SQL queries?

- What is the purpose of EXPLAIN/EXPLAIN ANALYZE?
- What is table partitioning and vacuuming?
## Backups, Recovery & Replication
- What are the different types of backups?

- What is the difference between logical and physical backups?
- What are common replication strategies?
- How do you ensure high availability?
## Data Engineering Considerations
- What is an ETL pipeline and how is it implemented?

- What are the differences between OLAP and OLTP?
- What is Change Data Capture (CDC) and how is it used?
- When should you use batch processing vs. streaming?
- What tools are used for orchestration and monitoring?