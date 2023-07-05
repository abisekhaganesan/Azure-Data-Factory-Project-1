# adf_adb_project1

# Simplifying Data Processing in Azure Cloud with Data Factory and SQL

In this repo, I've documented one of the real world 'AZURE Data Engneering' example on how to use Azure Data Factory to extract data from various online storage systems (Here I've used Git repo) and store it in Azure Data Lake Gen 2. Once the data is extracted from the source and stored in Data Lake, we will use Azure SQL to store and process the data.

# Required Resource 
1. Azure Subscription
2. Azure Data Factory
3. Storage Account - Data Lake Gen 2
4. Azure SQL Database

# Achitecture of the Example


![image](https://github.com/abisekhaganesan/adf_adb_project1/assets/60116728/d632dfc9-65c7-48c4-8b30-5bf8ec0bc9d7)


# Step 1: Extract data from Git(source) to Azure Data Lake(Destination)
      ~ create Dataset from (Factory Resource) in Azure DataFactory (Author) for source, destination and filename.
      ~ Source Dataset should contain a linked Service, create one for HTTP. specify the base url and set Parameter for Relative URL.
      ~Destination Dataset should contain a linked Service For Azure Data Lake Gen 2. and specify the File path to azure storage account "raw" to store the date on cloud. also set parameter value to get save each file from git.

---- Refer [**1.Git Source to Azure Data Lake Gen 2 - SS**](https://github.com/abisekhaganesan/adf_adb_project1/tree/main/1.Git%20Source%20to%20Azure%20Data%20Lake%20Gen%202%20-%20SS) ----


# Step 2: Transfer data from Azure Data Lake(Source) to Azure SQL Database(Destination)
      ~ create Dataset Azure Data Lake(Source) with same linked service and another dataset for Azure SQL Database(Destination) by creating new linked service to access the sql database.
      ~ Specify the Linked service of azure sql database and table name which has the schema to store the data.
      ~ To Transfer data internally from azure to azure resource we need to use Data Flows option.
      ~ Add source in dataflow to add azure data lake dataset(which is now our source dataset), set json setting as "Document per line".
      ~ Meanwhile create a table schema for extracted data to store in sql. --- https://github.com/abisekhaganesan/adf_adb_project1/blob/main/2.Azure%20Data%20Lake%20to%20Azure%20SQL%20Database%20-%20SS/Table%20Schema.txt
      ~ And Projected their datatype values in source Dataflow.
      ~ Create a Derived Column to store date values.
      ~ Add Sink to Dataflow to sink the gathered data into the Azure sql database. Also do Mannual mapping to map column names from source to sql table schema.

----- Refer [**2.Azure Data Lake to Azure SQL Database - SS**] (https://github.com/abisekhaganesan/adf_adb_project1/tree/main/2.Azure%20Data%20Lake%20to%20Azure%20SQL%20Database%20-%20SS) -----
