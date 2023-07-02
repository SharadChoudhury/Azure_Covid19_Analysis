# Azure_Covid19_Analysis

This project analyses the No. of cases and Deaths due to covid 19 in year 2020 and transforms the Population data for further use.
The Azure Components used here are :
1. Azure Data Lake Storage Gen 2
2. Azure Blob Storage
3. Azure Data Factory
4. Azure DataBricks

### Pipeline for Ingesting ECDC data from https://github.com/SharadChoudhury/Azure_Covid19_Analysis/raw/ecdc/main 
<img width="805" alt="Screenshot 2023-07-02 at 11 21 21 AM" src="https://github.com/SharadChoudhury/Azure_Covid19_Analysis/assets/65325622/b68992d0-64d4-469d-b81f-4b8c0e80ce77">

### Pipeline for Ingesting Population data from Blob Storage to Data Lake
<img width="810" alt="Screenshot 2023-07-02 at 11 34 41 AM" src="https://github.com/SharadChoudhury/Azure_Covid19_Analysis/assets/65325622/5cb1853d-4575-40e0-a570-2098756a040c">

### Pipeline for Processing Cases and Deaths data and storing the processed file in Data lake
<img width="1359" alt="Screenshot 2023-07-02 at 11 54 36 AM" src="https://github.com/SharadChoudhury/Azure_Covid19_Analysis/assets/65325622/30ae4cfd-1a46-4997-9ad5-5893da6c0904">

### Pipeline for Processing Hospital admissions data and storing the processed file in Data lake
<img width="1353" alt="Screenshot 2023-07-02 at 12 08 09 PM" src="https://github.com/SharadChoudhury/Azure_Covid19_Analysis/assets/65325622/2867e178-0346-42dd-a2b0-582b1ed5d8da">

