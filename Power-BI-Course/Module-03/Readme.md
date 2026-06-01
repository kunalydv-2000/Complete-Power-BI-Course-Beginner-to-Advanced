# Module 3: Data Sources & Data Connectivity in Power BI

## 📖 Overview

Data is the foundation of every Power BI report. Before creating visualizations, dashboards, or advanced analytics, you must understand where data comes from and how Power BI connects to different data sources.

This module focuses on data sources, connectivity methods, storage modes, and best practices for importing data into Power BI.

---

# 🎯 Learning Objectives

After completing this module, you will be able to:

- Understand different types of data sources
- Connect Power BI to various data sources
- Understand Import Mode, DirectQuery, and Live Connection
- Learn data refresh concepts
- Understand data gateways
- Connect Excel, CSV, SQL Server, Web APIs, and Cloud Sources
- Choose the appropriate connectivity mode for business requirements

---

# 📚 Table of Contents

1. Introduction to Data Sources
2. Types of Data Sources
3. Power BI Connectivity Architecture
4. Storage Modes in Power BI
5. Import Mode
6. DirectQuery Mode
7. Live Connection
8. Comparing Storage Modes
9. Connecting to Excel Files
10. Connecting to CSV Files
11. Connecting to SQL Server
12. Connecting to Web Data
13. Connecting to Cloud Data Sources
14. Data Refresh Concepts
15. Power BI Gateway
16. Best Practices
17. Key Terminologies
18. Practice Exercises
19. Mini Project
20. Module Summary

---

# 1️⃣ Introduction to Data Sources

## What is a Data Source?

A data source is any location where data is stored and can be accessed for analysis.

Examples:

- Excel Files
- CSV Files
- SQL Databases
- Cloud Applications
- APIs
- Websites

---

## Why Data Sources Matter

Power BI cannot create reports without data.

The quality, structure, and accessibility of your data source directly impact:

- Report Performance
- Data Accuracy
- Dashboard Reliability
- Business Decisions

---

# 2️⃣ Types of Data Sources

Power BI supports hundreds of data sources.

---

## File-Based Sources

Examples:

- Excel (.xlsx)
- CSV (.csv)
- Text Files (.txt)
- XML
- JSON
- PDF

---

## Database Sources

Examples:

- SQL Server
- MySQL
- PostgreSQL
- Oracle
- SQLite

---

## Cloud Sources

Examples:

- SharePoint
- OneDrive
- Azure SQL Database
- Google Analytics
- Salesforce

---

## Online Services

Examples:

- Dynamics 365
- Microsoft Fabric
- GitHub
- Adobe Analytics

---

## Web Sources

Examples:

- Public APIs
- Websites
- JSON Endpoints

---

# 3️⃣ Power BI Connectivity Architecture

Power BI follows a data flow process:

```text
Data Source
      ↓
Power BI Connector
      ↓
Power Query
      ↓
Data Model
      ↓
Visualizations
      ↓
Reports & Dashboards
```

---

## Explanation

### Data Source

Stores raw data.

### Connector

Allows Power BI to communicate with the source.

### Power Query

Performs transformations.

### Data Model

Organizes relationships.

### Visualization Layer

Displays information through charts and reports.

---

# 4️⃣ Storage Modes in Power BI

Power BI provides multiple methods to access data.

Three major storage modes:

1. Import Mode
2. DirectQuery Mode
3. Live Connection

Choosing the correct mode is critical for performance.

---

# 5️⃣ Import Mode

## What is Import Mode?

Power BI copies data from the source and stores it inside the Power BI dataset.

---

## How It Works

```text
Source Data
      ↓
Imported into Power BI
      ↓
Stored Locally
      ↓
Reports Query Local Data
```

---

## Advantages

### Fast Performance

Data is stored inside Power BI.

### Advanced Features

Supports:

- DAX
- Calculated Tables
- Calculated Columns

### Offline Reporting

Reports work even if the source becomes unavailable.

---

## Disadvantages

### Data Becomes Static

Requires refreshes to get new data.

### Dataset Size Limitations

Very large datasets may become difficult to manage.

---

## Best Use Cases

- Small to Medium Datasets
- Historical Reporting
- High Performance Dashboards

---

# 6️⃣ DirectQuery Mode

## What is DirectQuery?

Power BI does not store data locally.

Queries are sent directly to the source whenever users interact with reports.

---

## How It Works

```text
User Clicks Visual
       ↓
Power BI Sends Query
       ↓
Database Processes Query
       ↓
Results Returned
```

---

## Advantages

### Real-Time Data

Always retrieves current information.

### No Large Data Imports

Useful for massive databases.

---

## Disadvantages

### Slower Performance

Dependent on database speed.

### Limited Features

Some DAX features may not be available.

---

## Best Use Cases

- Real-Time Dashboards
- Large Enterprise Databases
- Frequently Changing Data

---

# 7️⃣ Live Connection

## What is Live Connection?

Power BI connects directly to an existing analytical model.

Examples:

- SQL Server Analysis Services (SSAS)
- Azure Analysis Services
- Semantic Models

---

## Characteristics

- No data import
- No local storage
- Centralized model management

---

## Advantages

### Single Source of Truth

All reports use the same model.

### Central Governance

Controlled by BI teams.

---

## Disadvantages

### Limited Modeling Flexibility

Users cannot modify the model significantly.

---

# 8️⃣ Comparing Storage Modes

| Feature | Import | DirectQuery | Live Connection |
|----------|---------|------------|----------------|
| Speed | Fast | Medium | Depends |
| Real-Time Data | No | Yes | Yes |
| Data Stored in Power BI | Yes | No | No |
| Supports Full DAX | Yes | Limited | Limited |
| Best for Small Data | Yes | No | No |
| Best for Large Data | No | Yes | Yes |

---

# 9️⃣ Connecting to Excel Files

## Why Excel?

Excel is one of the most common business data sources.

---

## Steps

### Step 1

```text
Home → Get Data
```

---

### Step 2

Select:

```text
Excel Workbook
```

---

### Step 3

Choose File

---

### Step 4

Navigator Window Appears

Select:

- Worksheets
- Tables

---

### Step 5

Choose:

```text
Load
```

or

```text
Transform Data
```

---

## Best Practice

Convert Excel ranges into Tables before importing.

---

# 🔟 Connecting to CSV Files

## What is CSV?

CSV = Comma Separated Values

Example:

```csv
CustomerID,CustomerName,Sales
101,Rahul,1000
102,Priya,1500
```

---

## Steps

```text
Home → Get Data → Text/CSV
```

---

### Preview Data

Verify:

- Column Names
- Data Types
- Delimiters

---

### Load Data

```text
Load
```

or

```text
Transform Data
```

---

# 1️⃣1️⃣ Connecting to SQL Server

## Why SQL Server?

Most enterprise systems store data inside SQL databases.

---

## Connection Steps

### Step 1

```text
Home → Get Data → SQL Server
```

---

### Step 2

Provide:

```text
Server Name
Database Name
```

---

### Step 3

Choose Connection Mode

- Import
- DirectQuery

---

### Step 4

Authenticate

Methods:

- Windows Authentication
- Database Authentication
- Microsoft Account

---

### Step 5

Load Tables

---

## Example

Sales Table:

| OrderID | Product | Revenue |
|---------|----------|---------|
| 1 | Laptop | 50000 |

---

# 1️⃣2️⃣ Connecting to Web Data

## What is Web Data?

Data available through websites or APIs.

---

## Types

### HTML Tables

Example:

Tables displayed on websites.

---

### JSON APIs

Example:

```json
{
  "city":"Delhi",
  "temperature":42
}
```

---

## Steps

```text
Home → Get Data → Web
```

Enter URL

Load or Transform Data.

---

# 1️⃣3️⃣ Connecting to Cloud Data Sources

Popular Cloud Sources:

- SharePoint
- OneDrive
- Azure SQL Database
- Azure Blob Storage
- Microsoft Fabric

---

## Benefits

### Automatic Updates

Data synchronization becomes easier.

### Collaboration

Multiple users access the same data.

### Scalability

Supports large datasets.

---

# 1️⃣4️⃣ Data Refresh Concepts

## Why Refresh Data?

Source systems continuously change.

Reports must reflect current information.

---

## Manual Refresh

```text
Home → Refresh
```

---

## Scheduled Refresh

Configured in Power BI Service.

Examples:

- Daily
- Hourly
- Weekly

---

## Incremental Refresh

Only refreshes new or changed data.

Benefits:

- Faster refreshes
- Improved performance

---

# 1️⃣5️⃣ Power BI Gateway

## What is Gateway?

A gateway securely connects on-premise data sources to Power BI Service.

---

## Why Needed?

Power BI Service cannot directly access internal company databases.

Gateway acts as a bridge.

---

## Types

### Personal Gateway

Single-user scenario.

---

### Standard Gateway

Enterprise environment.

Multiple users supported.

---

# 1️⃣6️⃣ Best Practices

## Choose Correct Storage Mode

Small Data → Import

Large Data → DirectQuery

Enterprise Model → Live Connection

---

## Validate Data Types

Always verify:

- Numbers
- Dates
- Currency Fields

---

## Use Power Query

Clean data before loading.

---

## Remove Unnecessary Columns

Improves performance.

---

## Use Incremental Refresh

For large datasets.

---

# 📌 Key Terminologies

| Term | Definition |
|--------|------------|
| Data Source | Location where data is stored |
| Connector | Tool used to connect to data |
| Dataset | Collection of imported data |
| Import Mode | Data stored inside Power BI |
| DirectQuery | Queries sent directly to source |
| Live Connection | Connection to external model |
| Refresh | Updating dataset with latest data |
| Gateway | Secure bridge to on-premise data |
| API | Application Programming Interface |
| Cloud Source | Data stored in cloud platforms |

---

# 📝 Practice Exercises

## Exercise 1

List five data sources commonly used in businesses.

---

## Exercise 2

Compare:

- Import Mode
- DirectQuery
- Live Connection

---

## Exercise 3

Connect an Excel file to Power BI.

---

## Exercise 4

Connect a CSV file and verify data types.

---

## Exercise 5

Research Power BI Gateway and explain its purpose.

---

# 🎯 Mini Project

## Multi-Source Data Import

### Objective

Import data from multiple sources.

### Tasks

Import:

- Excel File
- CSV File

Verify:

- Column Names
- Data Types
- Data Quality

Create:

- One Table Visual
- One Bar Chart

---

# 📚 Module Summary

In this module, you learned:

✅ Types of Data Sources

✅ Power BI Connectivity Architecture

✅ Import Mode

✅ DirectQuery Mode

✅ Live Connection

✅ Connecting Excel Files

✅ Connecting CSV Files

✅ Connecting SQL Server

✅ Connecting Web Data

✅ Cloud Data Sources

✅ Data Refresh Concepts

✅ Power BI Gateway

These concepts form the foundation for data preparation, which will be covered in the next module using Power Query.

---

## ⏭️ Next Module

**Module 4: Power Query Editor & Data Transformation**

Topics Covered:

- Introduction to Power Query
- Data Cleaning
- Data Transformation
- Query Folding
- Data Profiling
- Merge Queries
- Append Queries
- Pivot & Unpivot Operations
- Best Practices for Data Preparation