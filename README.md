# Financial_analysis


## Solution Architecture
<img width="593" alt="image" src="https://github.com/user-attachments/assets/e44f460d-1840-4793-b97e-63d26e816075">

## ERD


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




