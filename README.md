# Azure_Covid19_Analysis

This project analyses the No. of cases and Deaths due to covid 19 in year 2020 and transforms the Population data for further use.
The Azure Components used here are :

1. Azure Data Lake Storage Gen 2
2. Azure Blob Storage
3. Azure Data Factory
4. Azure DataBricks
5. Azure SQL Database
6. Azure Service Principal

### Pipeline for Ingesting ECDC data from https://github.com/SharadChoudhury/Azure_Covid19_Analysis/raw/ecdc/main

<img width="805" alt="Screenshot 2023-07-02 at 11 21 21 AM" src="https://github.com/SharadChoudhury/Azure_Covid19_Analysis/assets/65325622/b68992d0-64d4-469d-b81f-4b8c0e80ce77">

1. Implement a for-loop to fetch each file from https://github.com/SharadChoudhury/Azure_Covid19_Analysis/raw/ecdc/main using the ecdc_file_list.json
2. Store the ingested files in raw/ecdc folder in ADLS.


### Pipeline for Ingesting Population data from Blob Storage to Data Lake

<img width="810" alt="Screenshot 2023-07-02 at 11 34 41 AM" src="https://github.com/SharadChoudhury/Azure_Covid19_Analysis/assets/65325622/5cb1853d-4575-40e0-a570-2098756a040c">

1. Store the the raw population file in population_raw/BLOB in Azure Blob container
2. Implement a pipeline to fetch the raw file from the Blob container if it exists, then fetch its metadata and if the column count matches the required column count, then copy the file to ADLS.


### Pipeline for Processing Cases and Deaths data and storing the processed file in Data lake

<img width="1359" alt="Screenshot 2023-07-02 at 11 54 36 AM" src="https://github.com/SharadChoudhury/Azure_Covid19_Analysis/assets/65325622/30ae4cfd-1a46-4997-9ad5-5893da6c0904">

1. Create a dataflow to process the Cases and Deaths file as per the below requirements and store the processed sink file in ADLS.
   
<img width="700" alt="Screenshot 2023-07-02 at 7 54 11 PM" src="https://github.com/SharadChoudhury/Azure_Covid19_Analysis/assets/65325622/e5b7cb01-fbed-4f86-b8f9-0b12e19d692f">


### Pipeline for Processing Hospital admissions data and storing the processed file in Data lake

<img width="1353" alt="Screenshot 2023-07-02 at 12 08 09 PM" src="https://github.com/SharadChoudhury/Azure_Covid19_Analysis/assets/65325622/2867e178-0346-42dd-a2b0-582b1ed5d8da">

1. Create a dataflow to process the Hospital admissions file as per the below requirements and store the processed sink file in ADLS.

<img width="711" alt="Screenshot 2023-07-02 at 7 55 39 PM" src="https://github.com/SharadChoudhury/Azure_Covid19_Analysis/assets/65325622/cbee8e1d-41df-4de1-b73f-637bb934d7a9">


## Create a pipeline for transforming the population data using Databricks Pyspark Notebook

1. Create a ADF pipeline that runs the Databricks Notebook for population file transformation

   
## Create a Master pipeline that runs both the child pipelines : 1. Ingesting Population data, 2. Transforming Population data using Databricks 

<img width="633" alt="Screenshot 2023-07-02 at 8 03 12 PM" src="https://github.com/SharadChoudhury/Azure_Covid19_Analysis/assets/65325622/fd947e8c-8958-42c9-965d-1cf50b60a1f5">

1. This pipeline should get triggered when the blob for raw population file is created


## Create schemas for Cases and Deaths table, Hospital Admissions table in Azure SQL Database

1. Run SQL scripts in Azure SQL Database to create the table schemas in your database.


## Sqlize the processed Cases and Deaths file, Hospital Admissions file using the 

1. Create pipelines with Copy activity to copy the data from processed Cases and Deaths file, Hospital Admissions file to respective tables in the SQL database.
