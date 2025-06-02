# Azure Functions Integration – Blob Storage & SQL Database (Python)

Video Demo:  https://youtu.be/3TTTXeQMjIA 


This project includes two Azure Functions built in Python using Visual Studio Code:

- `blob_function/`: Writes data to Azure Blob Storage.
- `sql_function/`: Inserts records into Azure SQL Database.

---

## 🔧 Prerequisites

- Python 3.9+
- Azure CLI
- VS Code with Azure Functions, Python, and Azure Tools extensions
- Azure Subscription

---

## 🚀 1. Blob Storage Function (HTTP → Blob)

### Steps

Tutorial Link : https://learn.microsoft.com/en-us/azure/azure-functions/functions-add-output-binding-storage-queue-vs-code?pivots=programming-language-python&tabs=isolated-process 

1. Create Azure Function and connect it to the Azure storage.
2. Add `AzureWebJobsStorage` to `local.settings.json`.
3. Add `blob` output binding.
4. Trigger via HTTP POST with `{ "name": "file.txt", "content": "..." }`.

---

## 🗃️ 2. SQL Database Function (HTTP → SQL Table)

### Steps

Tutorial Link : https://learn.microsoft.com/en-us/azure/azure-functions/functions-add-output-binding-azure-sql-vs-code?pivots=programming-language-python 


1. Create Azure SQL Database (serverless).
2. Create `dbo.ToDo` table:
   ```sql
   CREATE TABLE dbo.ToDo (
     Id UNIQUEIDENTIFIER PRIMARY KEY,
     [order] INT NULL,
     title NVARCHAR(200) NOT NULL,
     url NVARCHAR(200) NOT NULL,
     completed BIT NOT NULL
   );

3. Copy ADO.NET connection string → update password.
4. Add SqlConnectionString to local.settings.json.
5. Use sql output binding with generic_output_binding.
6. Trigger via HTTP POST with { "name": "Sample Task" }.

## 🗃️ 3.Run Locally

# Start local function app
F5 in VS Code or run:
func start

## 🗃️ 4.Deploy to Azure

# In VS Code Command Palette
Azure Functions: Deploy to Function App


## 5.CleanUp Resources:

Delete resource group via Azure Portal to remove all linked resources.
