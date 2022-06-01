## Pipelines 
Composed of the 
    1. Data Ingestion Pipeline
    2. Stream to S3 Pipeline 
        1. Raw data sink for backup, other data products 
        2. Data inserted into Kinesis Data Stream -> Lambda Triggers -> Inserted into S3 Bucket 
        3. Lambda is configured to read data for a time increment to limit the # of files written into the bucket 

    3. Stream to DynamoDB Piepline 
        1. Primary use case for transaction storage 
        2. Data inserted into Kinesis Data Stream -> Lambda Triggers -> DYnamoDB customer(invoice + customer)/invoice view(invoice + stock code)
        
    4. Visualization API 
    5. Redshift DWH pipeline 
    6. Batch Pipeline 

## Instructions 
1. Run docker build --tag=aws-lde-proj . to build the Docker image.
2. Run this with docker-compose up run 