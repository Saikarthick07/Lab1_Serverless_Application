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

1. Create Azure Storage Account + Blob Container.
2. Add `AzureWebJobsStorage` to `local.settings.json`.
3. Add `blob` output binding.
4. Trigger via HTTP POST with `{ "name": "file.txt", "content": "..." }`.

---

## 🗃️ 2. SQL Database Function (HTTP → SQL Table)

### Steps

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
