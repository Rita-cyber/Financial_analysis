# Financial_analysis
## Data Source
The pipeline pulls daily time series data from the Alpha Vantage API, specifically focusing on open, close, high, low prices, and volume. The API provides reliable and well-structured financial data suitable for aggregation and analysis.

API Endpoint: https://www.alphavantage.co/query?function=TIME_SERIES_DAILY
Frequency: Daily data refreshes
## Technologies
### Azure DataFactory: Used for orchestration and scheduling
### Azure Databricks: Employed for ETL transformations to handle and process data efficiently
### Azure SQL: Database to store raw and aggregated tables with custom stored procedures for financial analysis
### SQL: Used for creating tables, views, and procedures for data aggregation
### Python: Core language for scripting and data manipulation


## Solution Architecture

![image](https://github.com/user-attachments/assets/97a4eb8f-85e3-4075-aa55-e2e055ca8584)

# Data Pipeline Flow

![image](https://github.com/user-attachments/assets/93b2a32c-9127-48a9-be36-5491e297fa83)



## Pipeline Workflow
Extract:
Using extract.py, the pipeline fetches daily time series data from the Alpha Vantage API.
Load:
Transformed data is loaded into PostgreSQL tables using load.py.
Aggregation:
aggregate tables are created in postgress to using stored SQLprocedures
Aggregated tables are generated in PostgreSQL using stored procedures and SQL scripts in stored_procedures.sql.

# ERD Schema
![Gold_Fintech_erd-erd](https://github.com/user-attachments/assets/be0381de-572c-4fa3-8bb5-0f192ad0af9e)


## Data Pipeline Flow

<img width="661" alt="image" src="https://github.com/user-attachments/assets/4454ff22-50d5-44a2-ab38-d241c99b7c02">


![image](https://github.com/user-attachments/assets/bb6821e7-1f69-45e3-8e2b-3b5bc9748eea)


<img width="941" alt="image" src="https://github.com/user-attachments/assets/62c82fb7-17b9-49be-a66e-6e51fd8fe829">

## Error Handling

@concat(
    activity('Ingest_azureblob').output?.Error?.Message, 
    ' | ', 
    activity('extract_transform').output?.Error?.Message, 
    ' | ', 
    activity('load_azuresql').output?.Error?.Message
)

<img width="946" alt="image" src="https://github.com/user-attachments/assets/f222b048-3a7b-4b11-a201-e30868143162">

## Azure Logic Apps
Click on use sample payload to generate schema and paste the below json in it

{"pipelineName": "",
  "RunId":"",
  "ErrorMessage" :""
    }

<img width="425" alt="image" src="https://github.com/user-attachments/assets/a59e6b94-70a8-4721-adda-7443454f70b6">










# Error Handling in Azure Data Factory
![image](https://github.com/user-attachments/assets/60d22b24-69dc-40d8-9e43-c67215126d2c)


# Deployed to Live Mode

![image](https://github.com/user-attachments/assets/9ff7612f-3ec8-47d8-a08a-eb76a940cae8)






