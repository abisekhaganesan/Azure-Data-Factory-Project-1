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
      ~ create Dataset from Factory Resource in Azure DataFactory Author for source, destination and filename.
      ~ Source Dataset should contain a linked Service, create one for HTTP. specify the base url and set Parameter for Relative URL.
      ~Destination Dataset should contain a linked Service For Azure Data Lake Gen 2. and specify the File path to azure storage account "raw" to store the date on cloud. also set parameter value to get save each file from git.

---- Refer **1.Git Source to Azure Data Lake Gen 2 - SS ** ----
