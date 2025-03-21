# Big Data ETL Pipeline with Azure & Databricks

## Overview
This project is an end-to-end data pipeline using Azure Data Lake Storage (ADLS), Azure Data Factory (ADF), Databricks, and Azure SQL DB to process order data from AWS S3.

![Data Flow_Architecture](https://github.com/Lovepreet12a/adf-databricks-etl/blob/main/Data%20Flow%20Architecture.png)

![Data Pipeline Flow](https://github.com/Lovepreet12a/adf-databricks-etl/blob/main/pipeline_image.png)


## Technologies Used
- **Azure Data Lake Storage (ADLS) Gen2**
- **Azure Data Factory (ADF)**
- **Azure Key Vault (AKV)**
- **Databricks (PySpark)**
- **Azure SQL Database**
- **Power BI**

## Data Flow
1. Data arrives from AWS S3 to `order_items` folder in ADLS.
2. ADF triggers when a new file lands in `Landing/`.
3. ADF copies the file from AWS S3 to ADLS.
4. ADF runs a Databricks notebook for validation and transformation.
5. Invalid data moves to `Discard/`; valid data moves to `Staging/`.
6. Databricks processes the data using lookup tables in Azure SQL.
7. The final aggregated data is written to Azure SQL for Power BI visualization.


## Contributing
If you'd like to contribute, please fork the repository and submit a pull request.
