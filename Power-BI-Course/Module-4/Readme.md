# Module 4: Power Query Editor & Data Transformation

## 📖 Overview

Data collected from various sources is rarely clean and ready for analysis. It often contains missing values, duplicates, inconsistent formats, incorrect data types, and other quality issues.

Power Query is Power BI's data preparation and transformation engine. It allows analysts to clean, transform, combine, and reshape data before loading it into the data model.

This module covers Power Query fundamentals, data transformation techniques, query management, and best practices for preparing high-quality datasets.

---

# 🎯 Learning Objectives

After completing this module, you will be able to:

- Understand Power Query Editor
- Navigate the Power Query interface
- Perform data cleaning operations
- Transform data efficiently
- Handle missing values and duplicates
- Merge and append queries
- Pivot and unpivot data
- Understand Query Folding
- Use Applied Steps effectively
- Prepare datasets for analysis

---

# 📚 Table of Contents

1. Introduction to Power Query
2. Why Data Transformation is Important
3. Power Query Architecture
4. Opening Power Query Editor
5. Power Query Interface
6. Data Types
7. Data Profiling Tools
8. Data Cleaning Techniques
9. Column Transformations
10. Row Transformations
11. Handling Missing Values
12. Handling Duplicates
13. Splitting & Merging Columns
14. Pivot & Unpivot Operations
15. Group By Operations
16. Merge Queries
17. Append Queries
18. Query Folding
19. Applied Steps
20. Best Practices
21. Key Terminologies
22. Practice Exercises
23. Mini Project
24. Module Summary

---

# 1️⃣ Introduction to Power Query

## What is Power Query?

Power Query is a data connection and transformation tool used to:

- Connect to data sources
- Clean data
- Transform data
- Combine datasets
- Prepare data for reporting

It acts as the ETL layer of Power BI.

---

## ETL Process

ETL stands for:

```text
Extract
   ↓
Transform
   ↓
Load
```

### Extract

Retrieve data from sources.

### Transform

Clean and modify data.

### Load

Load transformed data into Power BI.

---

# 2️⃣ Why Data Transformation is Important

Raw data often contains problems.

Examples:

| Problem | Example |
|----------|----------|
| Missing Values | Blank Sales Amount |
| Duplicates | Same Customer Appears Twice |
| Wrong Data Types | Date Stored as Text |
| Inconsistent Formatting | DELHI, Delhi, delhi |
| Extra Spaces | " Rahul " |

---

## Consequences of Poor Data Quality

- Incorrect Reports
- Wrong Business Decisions
- Inaccurate KPIs
- Poor Dashboard Performance

---

# 3️⃣ Power Query Architecture

```text
Data Source
      ↓
Power Query
      ↓
Transformations
      ↓
Data Model
      ↓
Reports
```

---

## Transformation Storage

Power Query does not immediately change source data.

Instead:

- Records transformation steps
- Replays them during refresh

This makes transformations repeatable.

---

# 4️⃣ Opening Power Query Editor

## Method 1

```text
Home → Transform Data
```

---

## Method 2

During data import:

```text
Get Data → Transform Data
```

---

# 5️⃣ Power Query Interface

The Power Query Editor contains several important areas.

---

## Ribbon

Contains commands for:

- Transformations
- Data Management
- Query Operations

---

## Queries Pane

Located on the left side.

Displays:

- Tables
- Queries
- Connections

---

## Data Preview Area

Displays current data.

---

## Applied Steps Pane

Displays transformation history.

Example:

```text
Source
Changed Type
Removed Columns
Filtered Rows
```

---

## Formula Bar

Shows transformation formulas.

---

# 6️⃣ Data Types

Power BI automatically detects data types.

---

## Common Data Types

| Data Type | Example |
|------------|-----------|
| Whole Number | 100 |
| Decimal Number | 15.75 |
| Currency | ₹1000 |
| Text | Delhi |
| Date | 01-Jan-2026 |
| Date/Time | 01-Jan-2026 10:30 AM |
| Boolean | TRUE/FALSE |

---

## Why Data Types Matter

Incorrect data types may cause:

- Calculation Errors
- Incorrect Visuals
- Poor Performance

---

# 7️⃣ Data Profiling Tools

Power Query provides tools to evaluate data quality.

---

## Column Quality

Shows:

- Valid Values
- Errors
- Empty Values

---

## Column Distribution

Shows frequency of values.

---

## Column Profile

Displays:

- Minimum
- Maximum
- Distinct Count
- Data Distribution

---

## Enable Profiling

```text
View
 ↓
Column Quality
Column Distribution
Column Profile
```

---

# 8️⃣ Data Cleaning Techniques

Data cleaning improves dataset quality.

---

## Common Cleaning Tasks

- Remove Duplicates
- Replace Values
- Trim Spaces
- Change Data Types
- Remove Errors
- Handle Missing Values

---

# 9️⃣ Column Transformations

Columns can be modified in various ways.

---

## Rename Column

```text
Right Click → Rename
```

---

## Remove Column

```text
Home → Remove Columns
```

---

## Duplicate Column

Creates a copy of an existing column.

---

## Add Custom Column

Example:

```text
Profit = Revenue - Cost
```

---

## Format Text

Options:

- Uppercase
- Lowercase
- Capitalize Each Word

---

# 🔟 Row Transformations

Rows can also be manipulated.

---

## Filter Rows

Example:

Show only sales greater than ₹10,000.

---

## Sort Rows

Ascending or Descending.

---

## Keep Top Rows

Example:

```text
Top 10 Customers
```

---

## Remove Bottom Rows

Useful for eliminating totals.

---

# 1️⃣1️⃣ Handling Missing Values

Missing values are represented as:

```text
null
```

---

## Methods

### Remove Rows

Delete rows containing null values.

---

### Replace Values

Replace null with:

```text
0
Unknown
N/A
```

---

### Fill Down

Copies previous value downward.

Example:

| Before |
|----------|
| A |
| null |
| null |

↓

| After |
|----------|
| A |
| A |
| A |

---

# 1️⃣2️⃣ Handling Duplicates

Duplicates create inaccurate results.

---

## Example

| CustomerID |
|------------|
| 101 |
| 101 |
| 102 |

---

## Remove Duplicates

```text
Home → Remove Rows → Remove Duplicates
```

---

# 1️⃣3️⃣ Splitting & Merging Columns

---

## Split Column

Example:

```text
Rahul Sharma
```

Split by space:

| First Name | Last Name |
|------------|-----------|
| Rahul | Sharma |

---

## Merge Columns

Combine:

```text
First Name + Last Name
```

Result:

```text
Rahul Sharma
```

---

# 1️⃣4️⃣ Pivot & Unpivot Operations

---

## Pivot

Converts rows into columns.

### Before

| Month | Sales |
|---------|---------|
| Jan | 100 |
| Feb | 200 |

---

### After

| Jan | Feb |
|------|------|
| 100 | 200 |

---

## Unpivot

Converts columns into rows.

### Before

| Jan | Feb |
|------|------|
| 100 | 200 |

---

### After

| Month | Sales |
|---------|---------|
| Jan | 100 |
| Feb | 200 |

---

## Why Unpivot?

Many datasets require unpivoting before analysis.

---

# 1️⃣5️⃣ Group By Operations

Similar to SQL GROUP BY.

---

## Example

Sales Data

| Region | Sales |
|---------|---------|
| North | 100 |
| North | 200 |

---

## Group By Result

| Region | Total Sales |
|---------|------------|
| North | 300 |

---

## Aggregations

- Sum
- Average
- Count
- Min
- Max

---

# 1️⃣6️⃣ Merge Queries

Merge combines tables using a common field.

---

## Similar to SQL JOIN

Example:

### Customers Table

| CustomerID | Name |
|------------|------|
| 1 | Rahul |

---

### Orders Table

| CustomerID | Sales |
|------------|---------|
| 1 | 5000 |

---

### Result

| CustomerID | Name | Sales |
|------------|------|---------|
| 1 | Rahul | 5000 |

---

## Join Types

- Left Outer
- Right Outer
- Full Outer
- Inner Join
- Anti Join

---

# 1️⃣7️⃣ Append Queries

Append stacks tables vertically.

---

### Table A

| Product |
|----------|
| Laptop |

---

### Table B

| Product |
|----------|
| Mobile |

---

### Result

| Product |
|----------|
| Laptop |
| Mobile |

---

## Use Cases

- Monthly Sales Files
- Multiple Branch Data
- Historical Records

---

# 1️⃣8️⃣ Query Folding

## What is Query Folding?

Power Query pushes transformations back to the source database.

---

### Without Query Folding

```text
Database
   ↓
Entire Dataset Downloaded
   ↓
Transformations Applied
```

---

### With Query Folding

```text
Database
   ↓
Transformation Executed in Database
   ↓
Only Required Data Returned
```

---

## Benefits

- Faster Refresh
- Reduced Memory Usage
- Better Performance

---

# 1️⃣9️⃣ Applied Steps

Every transformation becomes a step.

Example:

```text
Source
Changed Type
Filtered Rows
Removed Columns
Added Custom Column
```

---

## Advantages

- Easy to Modify
- Easy to Audit
- Reusable

---

# 2️⃣0️⃣ Best Practices

### Remove Unnecessary Columns

Reduces model size.

---

### Set Correct Data Types

Improves performance.

---

### Use Query Folding

Whenever possible.

---

### Clean Data Before Modeling

Avoid fixing issues later.

---

### Use Meaningful Column Names

Improves readability.

---

### Avoid Loading Unused Tables

Reduces memory consumption.

---

# 📌 Key Terminologies

| Term | Definition |
|--------|------------|
| Power Query | Data transformation engine |
| ETL | Extract, Transform, Load |
| Query | Connection to a data source |
| Transformation | Data modification step |
| Pivot | Rows to columns |
| Unpivot | Columns to rows |
| Merge | Combine tables horizontally |
| Append | Combine tables vertically |
| Query Folding | Processing at source system |
| Null | Missing value |

---

# 📝 Practice Exercises

## Exercise 1

Import an Excel dataset.

Perform:

- Rename Columns
- Remove Columns
- Change Data Types

---

## Exercise 2

Identify and remove duplicate records.

---

## Exercise 3

Replace null values.

---

## Exercise 4

Split a Full Name column into:

- First Name
- Last Name

---

## Exercise 5

Merge two datasets using CustomerID.

---

# 🎯 Mini Project

## Customer Sales Data Cleaning

### Dataset Contains

- Missing Values
- Duplicate Records
- Incorrect Data Types
- Extra Spaces

### Tasks

1. Clean Dataset
2. Remove Duplicates
3. Handle Missing Values
4. Merge Customer Table with Sales Table
5. Create Clean Final Dataset

---

# 📚 Module Summary

In this module, you learned:

✅ Power Query Fundamentals

✅ ETL Process

✅ Power Query Interface

✅ Data Profiling

✅ Data Cleaning Techniques

✅ Column & Row Transformations

✅ Handling Missing Values

✅ Removing Duplicates

✅ Pivot & Unpivot

✅ Merge Queries

✅ Append Queries

✅ Query Folding

✅ Applied Steps

These skills form the foundation of professional data preparation and are essential before building data models and relationships.

---

## ⏭️ Next Module

**Module 5: Data Modeling Fundamentals**

Topics Covered:

- Data Modeling
- Relationships
- Cardinality
- Cross Filter Direction
- Primary Keys
- Foreign Keys
- Relationship Best Practices
- Model Optimization