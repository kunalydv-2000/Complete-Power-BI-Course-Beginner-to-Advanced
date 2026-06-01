# Module 20: Power BI Dataflows & Reusable Data Preparation

## 📖 Overview

In many organizations, multiple reports use the same data transformation logic. If each report performs its own data cleaning and transformation, it creates duplication, inconsistency, and maintenance challenges.

Power BI Dataflows solve this problem by centralizing data preparation in the Power BI Service.

Dataflows enable organizations to create reusable ETL (Extract, Transform, Load) processes, standardize business logic, improve data quality, and reduce development effort across multiple reports and datasets.

This module covers Dataflows, Power Query Online, Linked Tables, Computed Tables, Dataflow Governance, Performance Optimization, and Enterprise Data Preparation strategies.

---

# 🎯 Learning Objectives

After completing this module, you will be able to:

- Understand Power BI Dataflows
- Understand Dataflow architecture
- Create and manage Dataflows
- Use Power Query Online
- Build reusable ETL processes
- Create Linked Tables
- Create Computed Tables
- Improve data consistency
- Apply Dataflow governance
- Design enterprise data preparation solutions

---

# 📚 Table of Contents

1. Introduction to Dataflows
2. Why Dataflows Matter
3. Traditional ETL vs Dataflows
4. Dataflow Architecture
5. Power Query Online
6. Creating a Dataflow
7. Dataflow Storage
8. Entities in Dataflows
9. Linked Tables
10. Computed Tables
11. Reusable ETL Design
12. Dataflow Refresh
13. Incremental Refresh in Dataflows
14. Dataflow Governance
15. Dataflow Performance Optimization
16. Enterprise Data Architecture
17. Best Practices
18. Common Mistakes
19. Key Terminologies
20. Practice Exercises
21. Mini Project
22. Module Summary

---

# 1️⃣ Introduction to Dataflows

## What is a Dataflow?

A Dataflow is a cloud-based data preparation and transformation layer in Power BI Service.

---

## Purpose

Create reusable data transformation processes.

---

## Dataflow Workflow

```text
Data Sources
      ↓
Dataflow
      ↓
Semantic Model
      ↓
Report
```

---

## Benefits

- Centralized ETL
- Reusable Transformations
- Consistent Business Logic

---

# 2️⃣ Why Dataflows Matter

Without Dataflows:

```text
Report A
   ↓
Own ETL

Report B
   ↓
Own ETL

Report C
   ↓
Own ETL
```

---

## Problems

### Duplicate Logic

---

### Increased Maintenance

---

### Inconsistent Calculations

---

### Slower Development

---

## With Dataflows

```text
Dataflow
      ↓
Shared Clean Data
      ↓
Multiple Reports
```

---

# 3️⃣ Traditional ETL vs Dataflows

## Traditional ETL

Data preparation occurs inside each report.

---

## Dataflow Approach

Data preparation occurs once.

---

## Comparison

| Feature | Traditional ETL | Dataflow |
|----------|----------------|----------|
| Reusability | Low | High |
| Maintenance | Difficult | Easier |
| Consistency | Lower | Higher |
| Scalability | Limited | Better |
| Governance | Difficult | Easier |

---

# 4️⃣ Dataflow Architecture

## High-Level Architecture

```text
Data Source
      ↓
Power Query Online
      ↓
Dataflow
      ↓
Storage
      ↓
Semantic Model
      ↓
Report
```

---

## Components

### Source Systems

SQL Server

Excel

CSV

APIs

ERP Systems

---

### Transformation Layer

Power Query Online

---

### Storage Layer

Dataflow Storage

---

### Consumption Layer

Datasets and Reports

---

# 5️⃣ Power Query Online

## What is Power Query Online?

Cloud-based version of Power Query.

---

## Similarities to Desktop

Supports:

- M Language
- Transformations
- Data Cleaning
- Data Shaping

---

## Advantages

### Browser-Based

No Desktop required.

---

### Centralized

Shared transformations.

---

### Reusable

Used across reports.

---

# 6️⃣ Creating a Dataflow

## Steps

### Step 1

Open Workspace.

---

### Step 2

Select:

```text
New
 ↓
Dataflow
```

---

### Step 3

Choose Data Source.

---

### Step 4

Apply Transformations.

---

### Step 5

Save Dataflow.

---

### Step 6

Configure Refresh.

---

# 7️⃣ Dataflow Storage

## Where is Data Stored?

Dataflows store processed data in the Power BI cloud environment.

---

## Benefits

### Centralized Storage

---

### Reusability

---

### Improved Governance

---

## Architecture

```text
Raw Data
      ↓
Transformation
      ↓
Cloud Storage
      ↓
Reports
```

---

# 8️⃣ Entities in Dataflows

## What is an Entity?

An Entity is similar to a table.

---

## Example

### Customer Entity

| CustomerID | CustomerName |
|------------|--------------|

---

### Product Entity

| ProductID | ProductName |
|-----------|--------------|

---

## Purpose

Store transformed data.

---

# 9️⃣ Linked Tables

## What are Linked Tables?

Linked Tables reference entities from another Dataflow.

---

## Example

```text
Master Dataflow
      ↓
Customer Entity
      ↓
Linked Dataflow
```

---

## Benefits

### Avoid Duplication

---

### Centralized Maintenance

---

### Better Governance

---

# 🔟 Computed Tables

## What are Computed Tables?

Tables created from existing Dataflow entities.

---

## Example

```text
Sales Entity
      ↓
Aggregation
      ↓
Monthly Sales Table
```

---

## Benefits

### Reusable Business Logic

---

### Faster Development

---

### Improved Performance

---

# 1️⃣1️⃣ Reusable ETL Design

## Goal

Transform data once and reuse everywhere.

---

## Example

Instead of:

```text
Sales Report
  ↓
Clean Customer Names

Finance Report
  ↓
Clean Customer Names

HR Report
  ↓
Clean Customer Names
```

---

Use:

```text
Dataflow
      ↓
Clean Customer Names
      ↓
All Reports
```

---

## Benefits

### Consistency

### Reduced Maintenance

### Faster Development

---

# 1️⃣2️⃣ Dataflow Refresh

## Purpose

Keep data current.

---

## Refresh Types

### Manual Refresh

---

### Scheduled Refresh

---

### On-Demand Refresh

---

## Workflow

```text
Source Data
      ↓
Refresh
      ↓
Updated Dataflow
      ↓
Updated Reports
```

---

# 1️⃣3️⃣ Incremental Refresh in Dataflows

## What is Incremental Refresh?

Refresh only changed data.

---

## Example

Historical Data

```text
2021
2022
2023
2024
```

---

Refresh only:

```text
2024
```

---

## Benefits

### Faster Refreshes

---

### Lower Resource Usage

---

### Better Scalability

---

# 1️⃣4️⃣ Dataflow Governance

## Why Governance Matters

Dataflows often become enterprise assets.

---

## Governance Areas

### Ownership

Assign responsible teams.

---

### Documentation

Describe transformations.

---

### Security

Control access.

---

### Monitoring

Track usage.

---

## Goal

Create trusted data assets.

---

# 1️⃣5️⃣ Dataflow Performance Optimization

## Best Practices

### Remove Unnecessary Columns

---

### Filter Early

Reduce data volume.

---

### Use Incremental Refresh

---

### Avoid Redundant Transformations

---

### Optimize Source Queries

---

## Benefits

### Faster Refresh

### Better Scalability

### Reduced Costs

---

# 1️⃣6️⃣ Enterprise Data Architecture

## Recommended Architecture

```text
Source Systems
      ↓
Dataflows
      ↓
Semantic Models
      ↓
Reports
      ↓
Dashboards
```

---

## Benefits

### Standardization

---

### Reusability

---

### Scalability

---

### Governance

---

# 1️⃣7️⃣ Best Practices

### Create Shared Dataflows

---

### Use Consistent Naming

---

### Document Transformations

---

### Establish Ownership

---

### Monitor Refreshes

---

### Reuse Existing Dataflows

---

### Apply Governance Policies

---

# 1️⃣8️⃣ Common Mistakes

### Duplicate Dataflows

---

### Poor Documentation

---

### No Ownership

---

### Excessive Transformations

---

### Ignoring Refresh Failures

---

### Rebuilding Existing Logic

---

# 📌 Key Terminologies

| Term | Definition |
|--------|------------|
| Dataflow | Reusable cloud-based ETL process |
| ETL | Extract, Transform, Load |
| Entity | Table within a Dataflow |
| Linked Table | Reference to another Dataflow entity |
| Computed Table | Derived Dataflow table |
| Power Query Online | Cloud-based transformation engine |
| Refresh | Updating Dataflow data |
| Incremental Refresh | Refreshing only changed data |
| Governance | Managing Dataflow usage |
| Reusable ETL | Shared transformation process |

---

# 📝 Practice Exercises

## Exercise 1

Create a Dataflow using a CSV source.

---

## Exercise 2

Create Customer and Product entities.

---

## Exercise 3

Configure scheduled refresh.

---

## Exercise 4

Design a reusable ETL architecture.

---

## Exercise 5

Compare:

- Dataflows
- Power Query in Desktop

---

# 🎯 Mini Project

## Enterprise Sales Dataflow

### Scenario

Multiple departments use sales data.

---

### Requirements

#### Data Sources

- Sales Data
- Customer Data
- Product Data

---

#### Transformations

- Clean Customer Names
- Standardize Product Categories
- Remove Duplicates

---

#### Dataflow

Create reusable entities.

---

#### Governance

Define:

- Ownership
- Documentation
- Refresh Schedule

---

### Deliverables

1. Dataflow Design
2. Entity Structure
3. Refresh Strategy
4. Governance Plan

---

# 📚 Module Summary

In this module, you learned:

✅ Dataflows

✅ Dataflow Architecture

✅ Power Query Online

✅ Dataflow Storage

✅ Entities

✅ Linked Tables

✅ Computed Tables

✅ Reusable ETL

✅ Dataflow Refresh

✅ Incremental Refresh

✅ Dataflow Governance

✅ Performance Optimization

✅ Enterprise Data Architecture

Dataflows provide a scalable, reusable, and governed approach to data preparation. They are a key component of enterprise Power BI architectures and help organizations create a single source of trusted, reusable data.

---

## ⏭️ Next Module

**Module 21: Power BI Data Modeling Masterclass**

Topics Covered:

- Advanced Data Modeling
- Fact & Dimension Design
- Surrogate Keys
- Degenerate Dimensions
- Slowly Changing Dimensions (SCD)
- Bridge Tables
- Many-to-Many Modeling
- Role-Playing Dimensions
- Composite Models
- Enterprise Data Warehouse Design