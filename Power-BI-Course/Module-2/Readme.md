# Module 2: Data Analytics Fundamentals

## 📖 Overview

Before building dashboards and reports in Power BI, it is essential to understand the fundamentals of data analytics. This module introduces the core concepts of data, analytics, databases, data warehouses, and analytical thinking.

Data analytics is the foundation of Business Intelligence because reports and dashboards are only as valuable as the insights they provide.

---

# 🎯 Learning Objectives

After completing this module, you will be able to:

- Understand the fundamentals of Data Analytics
- Differentiate between data and information
- Understand different types of analytics
- Learn common data types
- Understand structured and unstructured data
- Understand databases and data warehouses
- Learn the analytics lifecycle
- Understand the role of data analysts in organizations

---

# 📚 Table of Contents

1. What is Data Analytics?
2. Why Data Analytics Matters
3. Data vs Information vs Insight
4. Types of Analytics
5. Data Types
6. Structured vs Unstructured Data
7. Databases
8. Data Warehouses
9. Data Lakes
10. Analytics Lifecycle
11. Data Analyst Roles & Responsibilities
12. Common Analytics Tools
13. Key Terminologies
14. Practice Exercises
15. Module Summary

---

# 1️⃣ What is Data Analytics?

## Definition

Data Analytics is the process of examining, cleaning, transforming, and interpreting data to discover meaningful patterns, trends, and insights that support decision-making.

---

## Simple Example

Imagine an online store has the following sales data:

| Month | Sales |
|---------|---------|
| January | ₹50,000 |
| February | ₹60,000 |
| March | ₹75,000 |

Raw numbers alone are data.

Analyzing these numbers to determine sales growth is analytics.

Concluding that sales are increasing because of a marketing campaign is an insight.

---

## Main Goal of Data Analytics

Transform:

```text
Data
 ↓
Information
 ↓
Insights
 ↓
Business Decisions
```

---

# 2️⃣ Why Data Analytics Matters

Organizations generate large amounts of data every day.

Examples:

- Customer transactions
- Website visits
- Employee records
- Inventory data
- Marketing campaign results

Without analytics:

- Data remains unused
- Decision-making becomes difficult

With analytics:

- Trends become visible
- Opportunities are identified
- Risks are reduced

---

## Benefits of Data Analytics

### Better Decision Making

Organizations make data-driven decisions instead of assumptions.

### Cost Reduction

Identifies inefficiencies and waste.

### Revenue Growth

Discovers profitable opportunities.

### Customer Understanding

Analyzes customer behavior and preferences.

### Competitive Advantage

Provides insights faster than competitors.

---

# 3️⃣ Data vs Information vs Insight

Understanding these concepts is critical.

---

## Data

Raw facts without context.

Example:

```text
100
150
200
```

These numbers alone have little meaning.

---

## Information

Data organized into a meaningful format.

Example:

```text
January Sales = 100
February Sales = 150
March Sales = 200
```

Now the data has context.

---

## Insight

An actionable conclusion derived from information.

Example:

```text
Sales increased by 100% in three months.
Marketing efforts may be contributing to growth.
```

---

# 4️⃣ Types of Analytics

There are four major types of analytics.

---

## 1. Descriptive Analytics

### Question Answered

```text
What happened?
```

### Example

Monthly Sales Report

| Month | Sales |
|---------|---------|
| January | ₹50,000 |
| February | ₹60,000 |

Descriptive analytics summarizes historical data.

---

## 2. Diagnostic Analytics

### Question Answered

```text
Why did it happen?
```

### Example

Sales increased because:

- Marketing campaign succeeded
- Website traffic increased

Diagnostic analytics identifies causes.

---

## 3. Predictive Analytics

### Question Answered

```text
What is likely to happen?
```

### Example

Forecast next month's sales using historical trends.

Predictive analytics uses statistical models and machine learning.

---

## 4. Prescriptive Analytics

### Question Answered

```text
What should we do?
```

### Example

Recommend increasing advertising budget.

Prescriptive analytics suggests actions.

---

## Analytics Maturity Model

```text
Descriptive
     ↓
Diagnostic
     ↓
Predictive
     ↓
Prescriptive
```

---

# 5️⃣ Data Types

Understanding data types is important for reporting and analysis.

---

## Numeric Data

Contains numbers.

Examples:

```text
100
5000
25.75
```

Used for calculations.

---

## Text Data

Contains characters and words.

Examples:

```text
Delhi
Laptop
Customer Name
```

---

## Date & Time Data

Examples:

```text
01-Jan-2026
12:30 PM
```

Used for trend analysis.

---

## Boolean Data

Contains only:

```text
TRUE
FALSE
```

Examples:

- Is Active?
- Is Paid?

---

## Currency Data

Examples:

```text
₹1000
$500
€300
```

Used in financial reporting.

---

# 6️⃣ Structured vs Unstructured Data

---

## Structured Data

Organized into rows and columns.

Example:

| Customer ID | Name |
|------------|--------|
| 101 | Rahul |
| 102 | Priya |

Sources:

- SQL Databases
- Excel
- CSV Files

---

## Unstructured Data

Does not follow a predefined format.

Examples:

- Images
- Videos
- Audio Files
- Social Media Posts
- Emails

---

## Semi-Structured Data

Partially organized.

Examples:

- JSON
- XML

---

## Comparison

| Structured | Unstructured |
|------------|------------|
| Organized | Not Organized |
| Easy to Analyze | More Complex |
| SQL Databases | Images, Videos |
| Excel Files | Social Media Content |

---

# 7️⃣ Databases

## What is a Database?

A database is an organized collection of data stored electronically.

---

## Example

Customer Database

| CustomerID | Name | City |
|------------|------|------|
| 1 | Rahul | Delhi |
| 2 | Priya | Mumbai |

---

## Popular Databases

- SQL Server
- MySQL
- PostgreSQL
- Oracle
- SQLite

---

## Advantages

- Fast retrieval
- Data security
- Data consistency
- Multi-user access

---

# 8️⃣ Data Warehouses

## What is a Data Warehouse?

A Data Warehouse is a centralized repository that stores data from multiple sources for reporting and analysis.

---

## Purpose

Operational databases are optimized for transactions.

Data warehouses are optimized for analytics.

---

## Characteristics

### Subject-Oriented

Organized around business subjects.

Example:

- Sales
- Finance
- HR

---

### Integrated

Combines multiple data sources.

---

### Historical

Stores long-term data.

---

### Non-Volatile

Data remains stable after loading.

---

# 9️⃣ Data Lakes

## What is a Data Lake?

A Data Lake stores large amounts of raw data in its original format.

---

## Data Warehouse vs Data Lake

| Data Warehouse | Data Lake |
|---------------|------------|
| Processed Data | Raw Data |
| Structured | Structured & Unstructured |
| Reporting | Advanced Analytics |
| Faster Queries | Flexible Storage |

---

# 🔟 Analytics Lifecycle

Data analytics follows a structured process.

---

## Step 1: Business Understanding

Identify business objectives.

Example:

```text
Why are sales decreasing?
```

---

## Step 2: Data Collection

Gather data from:

- Databases
- APIs
- Excel Files
- Applications

---

## Step 3: Data Cleaning

Remove:

- Missing Values
- Duplicates
- Errors

---

## Step 4: Data Analysis

Identify:

- Trends
- Patterns
- Relationships

---

## Step 5: Visualization

Create:

- Reports
- Dashboards
- Charts

---

## Step 6: Decision Making

Use insights to take action.

---

# 1️⃣1️⃣ Data Analyst Roles & Responsibilities

A Data Analyst typically performs:

### Data Collection

Gathering data from various sources.

---

### Data Cleaning

Preparing data for analysis.

---

### Data Analysis

Finding trends and insights.

---

### Data Visualization

Creating dashboards and reports.

---

### Business Communication

Presenting findings to stakeholders.

---

# 1️⃣2️⃣ Common Analytics Tools

## Spreadsheet Tools

- Microsoft Excel
- Google Sheets

---

## Database Tools

- SQL Server
- MySQL
- PostgreSQL

---

## Visualization Tools

- Power BI
- Tableau
- Looker Studio

---

## Programming Languages

- Python
- R

---

## Cloud Platforms

- Microsoft Azure
- AWS
- Google Cloud Platform

---

# 📌 Key Terminologies

| Term | Definition |
|--------|------------|
| Data | Raw facts |
| Information | Organized data |
| Insight | Actionable understanding |
| Analytics | Process of extracting insights |
| Database | Organized data storage |
| Data Warehouse | Analytics-focused repository |
| Data Lake | Raw data storage |
| KPI | Key Performance Indicator |
| Dashboard | Visual summary of metrics |
| Visualization | Graphical representation of data |

---

# 📝 Practice Exercises

## Exercise 1

Identify examples of:

- Structured Data
- Unstructured Data
- Semi-Structured Data

---

## Exercise 2

Choose a company and list:

- Data Sources
- Possible KPIs
- Business Decisions

---

## Exercise 3

Explain the difference between:

- Database
- Data Warehouse
- Data Lake

---

## Exercise 4

Research the four types of analytics and provide one real-world example of each.

---

## Exercise 5

Create a diagram showing the Analytics Lifecycle.

---

# 🎯 Mini Project

## Retail Sales Analysis Planning

Imagine you are working for a retail company.

### Task

Identify:

- Business Problem
- Data Sources
- KPIs
- Expected Insights

### Deliverable

Prepare a one-page analytics plan.

---

# 📚 Module Summary

In this module, you learned:

✅ Fundamentals of Data Analytics

✅ Data vs Information vs Insight

✅ Four Types of Analytics

✅ Data Types

✅ Structured, Unstructured & Semi-Structured Data

✅ Databases

✅ Data Warehouses

✅ Data Lakes

✅ Analytics Lifecycle

✅ Data Analyst Responsibilities

These concepts form the analytical foundation required before working with data sources, transformations, and modeling in Power BI.

---

## ⏭️ Next Module

**Module 3: Data Sources & Data Connectivity in Power BI**

Topics Covered:

- Understanding Data Sources
- Import Mode
- DirectQuery
- Live Connection
- Connecting Excel, CSV, SQL Server & Web Data
- Data Refresh Concepts