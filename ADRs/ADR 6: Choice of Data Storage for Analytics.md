## ADR 6: Choice of Data Storage for Analytics
### Context
We need to determine the data storage solution for our analytics data, including data separation into raw, enriched, and curated forms.

### Decision
We will use Amazon S3 as the data lake for analytics, with separate buckets for raw, enriched, and curated data.

### Decision Rationale

+ Amazon S3 provides scalable and durable object storage.
+ It allows efficient data separation and management.
+ Integration with AWS analytics services simplifies data processing.

### Implications

+ Data pipelines for ETL processes must be developed.
+ Access controls and data governance need to be implemented.

### Dependencies

+ Integration with AWS analytics services like AWS Glue.
+ Implementation Details:
+ Create S3 buckets for raw, enriched, and curated data.
+ Define data ingestion and ETL pipelines.

### Monitoring and Testing

+ Monitor data ingestion, ETL processes, and data quality.
+ Test analytics processes for accuracy and performance.

### Open Issues

Defining data retention policies and access controls.
