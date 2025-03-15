# Big Data ETL Pipeline with Azure & Databricks

## Overview
This project is an end-to-end data pipeline using Azure Data Lake Storage (ADLS), Azure Data Factory (ADF), Databricks, and Azure SQL DB to process order data from AWS S3.

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


