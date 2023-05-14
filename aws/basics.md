# AWS - Basics

## IAM (Identity and Access Management)

- Service that helps you control access to **Resources**
- User attempt to perform **Actions** on resources (e.g. S3::CreateBucket)
- Authorization to perform an **Action** depends on a **Policy**
- There are also S3 Bucket Policies that are applied to **Principal** (person/application)
- References
	- https://www.youtube.com/watch?v=_ZCTvmaPgao

## S3 (Simple Storage Service)

- Buckets
	- Bucket name must be globally unique
	- It's like the top level directory.
- Objects: 
	- A file plus any metadata that describes the file
	- Every object in S3 is stored in a bucket
	- The object name is also referred as the object key
- Storage classes: reduce costs for infrequently accessed data
- References
	- https://www.youtube.com/watch?v=tfU0JEZjcsg
	- [S3 Bucket Policy](https://www.youtube.com/watch?v=gWAwqY76JQs)

## Lambda

## Glue

- **Serverless** data integration service
- Features:
    - **AWS Glue Data Catalog**: Centralized information about your datasets across multiple sources
    - **AWS Glue ETL**
    - **AWS Glue Studio**: Design ETL jobs in a visual interface
    - **AWS Glue DataBrew**: Visual data preparation tool for cleaning and normalize data
