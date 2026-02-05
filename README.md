# AWS Glue ETL Pipeline – CSV to Parquet

## Overview
This project demonstrates an end-to-end ETL pipeline using AWS Glue and PySpark.
Raw CSV data is ingested into Amazon S3, transformed using AWS Glue, and stored
as optimized Parquet files for analytics.

## Architecture
CSV → S3 (Raw) → AWS Glue ETL (PySpark) → S3 (Processed Parquet) → Athena

## AWS Services Used
- Amazon S3
- AWS Glue (Crawler + ETL Job)
- AWS Glue Data Catalog
- Amazon Athena
- IAM

## ETL Logic
- Read raw CSV data from S3 using Glue Data Catalog
- Apply schema enforcement using Glue transformations
- Convert CSV to Parquet format with Snappy compression
- Write processed data back to S3

## Sample Athena Query
```sql
SELECT customer_id, SUM(amount) 
FROM processed_sales 
GROUP BY customer_id;# aws-glue-etl-sales
## What I Learned
- Designed an end-to-end ETL pipeline on AWS
- Used AWS Glue with PySpark for data transformation
- Worked with Glue Crawlers and Data Catalog
- Converted CSV data into Parquet for optimized analytics
- Queried processed data using Amazon Athena
