# Module 6: Star Schema & Snowflake Schema

## 📖 Overview

A well-designed data model is the backbone of every successful Power BI solution. While relationships connect tables, dimensional modeling determines how those tables should be organized for maximum performance, scalability, and ease of analysis.

In this module, you will learn the two most common data warehouse modeling techniques:

- Star Schema
- Snowflake Schema

You will also learn Fact Tables, Dimension Tables, Surrogate Keys, Conformed Dimensions, and industry best practices used in enterprise Business Intelligence solutions.

---

# 🎯 Learning Objectives

After completing this module, you will be able to:

- Understand Dimensional Modeling
- Design Star Schema models
- Design Snowflake Schema models
- Differentiate Fact and Dimension Tables
- Understand Surrogate Keys
- Understand Conformed Dimensions
- Build enterprise-grade Power BI models
- Improve report performance through proper modeling

---

# 📚 Table of Contents

1. Introduction to Dimensional Modeling
2. Why Schema Design Matters
3. Fact Tables
4. Dimension Tables
5. Measures vs Dimensions
6. Star Schema
7. Components of Star Schema
8. Benefits of Star Schema
9. Snowflake Schema
10. Components of Snowflake Schema
11. Benefits & Drawbacks of Snowflake Schema
12. Star Schema vs Snowflake Schema
13. Surrogate Keys
14. Natural Keys
15. Conformed Dimensions
16. Slowly Changing Dimensions (SCD)
17. Date Dimension
18. Best Practices
19. Common Modeling Mistakes
20. Key Terminologies
21. Practice Exercises
22. Mini Project
23. Module Summary

---

# 1️⃣ Introduction to Dimensional Modeling

## What is Dimensional Modeling?

Dimensional Modeling is a data modeling technique used in Business Intelligence and Data Warehousing.

Its goal is to organize data for:

- Faster querying
- Easier reporting
- Better performance
- Simpler analysis

---

## Traditional Database Design

Transactional databases are designed for:

- Insert Operations
- Update Operations
- Delete Operations

Examples:

- Banking Systems
- ERP Systems
- CRM Systems

---

## Analytical Database Design

Analytical systems are designed for:

- Reporting
- Dashboards
- Business Analysis

Power BI works best with analytical models.

---

# 2️⃣ Why Schema Design Matters

Poor schema design causes:

- Slow reports
- Complex DAX
- Incorrect aggregations
- Difficult maintenance

---

## Good Schema Design Provides

### Better Performance

Queries execute faster.

---

### Simpler Relationships

Fewer joins required.

---

### Easier Analysis

Users understand the model quickly.

---

### Better Scalability

Supports growing datasets.

---

# 3️⃣ Fact Tables

## What is a Fact Table?

A Fact Table stores measurable business events.

Facts are typically numeric values used for analysis.

---

## Characteristics

- Contains measurements
- Usually very large
- Connected to multiple dimensions
- Located at the center of the model

---

## Example

### FactSales

| OrderID | ProductID | CustomerID | DateID | SalesAmount |
|----------|-----------|------------|--------|-------------|
| 1 | P101 | C101 | D001 | 5000 |

---

## Common Fact Table Metrics

- Revenue
- Profit
- Quantity Sold
- Cost
- Discount
- Transactions

---

# 4️⃣ Dimension Tables

## What is a Dimension Table?

Dimension Tables contain descriptive attributes about business entities.

---

## Characteristics

- Descriptive information
- Smaller than fact tables
- Used for filtering and grouping

---

## Example

### DimProduct

| ProductID | ProductName | Category |
|------------|-------------|-----------|
| P101 | Laptop | Electronics |

---

## Common Dimension Tables

### Customer Dimension

Contains:

- Customer Name
- Gender
- Age
- City

---

### Product Dimension

Contains:

- Product Name
- Brand
- Category

---

### Date Dimension

Contains:

- Year
- Quarter
- Month
- Week

---

# 5️⃣ Measures vs Dimensions

Understanding the difference is critical.

---

## Measures

Numeric values that can be aggregated.

Examples:

```text
Revenue
Profit
Sales
Quantity
```

---

## Dimensions

Descriptive fields used to categorize measures.

Examples:

```text
Product
Region
Customer
Date
```

---

## Example

| Product | Revenue |
|----------|----------|
| Laptop | 5000 |

Product = Dimension

Revenue = Measure

---

# 6️⃣ Star Schema

## What is a Star Schema?

A Star Schema is a dimensional model where a central fact table connects directly to multiple dimension tables.

---

## Structure

```text
            DimCustomer
                  |
                  |
DimProduct --- FactSales --- DimDate
                  |
                  |
             DimRegion
```

---

## Characteristics

- Fact table in center
- Dimensions around fact table
- Simple relationships
- Most recommended design

---

# 7️⃣ Components of Star Schema

---

## Fact Table

Stores business transactions.

Example:

### FactSales

| ProductID | CustomerID | Sales |
|------------|------------|--------|
| P101 | C101 | 5000 |

---

## Dimension Tables

### DimCustomer

| CustomerID | Name |
|------------|------|
| C101 | Rahul |

---

### DimProduct

| ProductID | ProductName |
|------------|-------------|
| P101 | Laptop |

---

### DimDate

| DateID | Month |
|---------|--------|
| D001 | January |

---

# 8️⃣ Benefits of Star Schema

### Better Performance

Requires fewer joins.

---

### Easier Maintenance

Simple structure.

---

### Better DAX Performance

Optimized filter propagation.

---

### Easier Reporting

Business users understand the model.

---

## Why Power BI Prefers Star Schema

Power BI's VertiPaq Engine performs best with star schemas.

---

# 9️⃣ Snowflake Schema

## What is a Snowflake Schema?

A Snowflake Schema is an extension of Star Schema where dimension tables are normalized into additional tables.

---

## Structure

```text
                 DimCategory
                       |
                       |
DimProduct ---- FactSales ---- DimDate
       |
       |
DimBrand
```

---

## Characteristics

- Normalized dimensions
- More relationships
- Reduced data redundancy

---

# 🔟 Components of Snowflake Schema

---

## Fact Table

Same as Star Schema.

---

## Dimension Tables

Split into smaller related tables.

---

### Example

#### Product Table

| ProductID | BrandID | CategoryID |
|------------|---------|-----------|
| P101 | B1 | C1 |

---

#### Brand Table

| BrandID | BrandName |
|---------|------------|
| B1 | Dell |

---

#### Category Table

| CategoryID | Category |
|------------|-----------|
| C1 | Electronics |

---

# 1️⃣1️⃣ Benefits & Drawbacks of Snowflake Schema

## Benefits

### Reduced Redundancy

Data stored once.

---

### Better Data Integrity

Consistent information.

---

### Smaller Dimension Tables

Less duplication.

---

## Drawbacks

### More Complex

Harder to understand.

---

### More Relationships

Additional joins required.

---

### Slower Queries

Compared to Star Schema.

---

# 1️⃣2️⃣ Star Schema vs Snowflake Schema

| Feature | Star Schema | Snowflake Schema |
|----------|------------|------------------|
| Structure | Denormalized | Normalized |
| Complexity | Simple | Complex |
| Performance | Faster | Slower |
| Relationships | Fewer | More |
| Maintenance | Easier | Harder |
| Power BI Recommendation | Preferred | Less Preferred |

---

# 1️⃣3️⃣ Surrogate Keys

## What is a Surrogate Key?

A system-generated unique identifier.

---

## Example

| CustomerKey | CustomerID |
|-------------|------------|
| 1 | C101 |
| 2 | C102 |

---

## Benefits

- Stable identifiers
- Improved performance
- Simplified relationships

---

# 1️⃣4️⃣ Natural Keys

## What is a Natural Key?

A key that already exists in business data.

---

## Example

| CustomerID |
|------------|
| C101 |

CustomerID is a natural key.

---

## Problems

Business identifiers may change over time.

---

# 1️⃣5️⃣ Conformed Dimensions

## What is a Conformed Dimension?

A dimension shared across multiple fact tables.

---

## Example

### Date Dimension

Used by:

- Sales Fact
- Inventory Fact
- Finance Fact

---

## Benefits

Provides consistency across reports.

---

# 1️⃣6️⃣ Slowly Changing Dimensions (SCD)

## What is SCD?

Dimension attributes change over time.

---

## Example

Customer moves:

```text
Delhi → Mumbai
```

---

### SCD Type 1

Overwrite old value.

---

### SCD Type 2

Keep historical records.

---

### SCD Type 3

Store limited history.

---

# 1️⃣7️⃣ Date Dimension

A Date Table is one of the most important dimensions.

---

## Example

| Date | Year | Quarter | Month |
|--------|------|----------|--------|
| 01-Jan-2026 | 2026 | Q1 | January |

---

## Why Important?

Required for:

- Time Intelligence
- YTD Analysis
- MTD Analysis
- YoY Comparison

---

## Typical Columns

- Date
- Day
- Week
- Month
- Quarter
- Year
- Fiscal Year

---

# 1️⃣8️⃣ Best Practices

### Use Star Schema

Preferred for Power BI.

---

### Keep Dimensions Descriptive

Store attributes in dimensions.

---

### Keep Facts Numeric

Store measurements in facts.

---

### Create Date Dimension

For all reporting models.

---

### Avoid Many-to-Many Relationships

Whenever possible.

---

### Use Meaningful Naming

Examples:

```text
FactSales
DimCustomer
DimProduct
DimDate
```

---

# 1️⃣9️⃣ Common Modeling Mistakes

### Using One Massive Table

Creates poor performance.

---

### Ignoring Date Dimension

Limits Time Intelligence.

---

### Excessive Snowflaking

Adds complexity.

---

### Duplicate Dimensions

Creates inconsistency.

---

### Incorrect Relationships

Causes reporting errors.

---

# 📌 Key Terminologies

| Term | Definition |
|--------|------------|
| Fact Table | Stores measurable data |
| Dimension Table | Stores descriptive attributes |
| Star Schema | Central fact with surrounding dimensions |
| Snowflake Schema | Normalized dimensions |
| Surrogate Key | System-generated identifier |
| Natural Key | Business-generated identifier |
| Conformed Dimension | Shared dimension across facts |
| SCD | Slowly Changing Dimension |
| Denormalization | Combining tables |
| Normalization | Splitting tables |

---

# 📝 Practice Exercises

## Exercise 1

Identify Fact and Dimension tables from a retail dataset.

---

## Exercise 2

Design a Star Schema for:

- Customers
- Products
- Sales
- Dates

---

## Exercise 3

Convert a Star Schema into a Snowflake Schema.

---

## Exercise 4

Create a Date Dimension table.

---

## Exercise 5

Compare Star and Snowflake Schema advantages.

---

# 🎯 Mini Project

## Retail Data Warehouse Model

### Tables

#### FactSales

| SaleID | CustomerID | ProductID | DateID | Revenue |
|---------|------------|-----------|--------|---------|

---

#### DimCustomer

| CustomerID | CustomerName |
|------------|-------------|

---

#### DimProduct

| ProductID | ProductName |
|------------|-------------|

---

#### DimDate

| DateID | Month | Year |
|---------|--------|------|

---

### Tasks

1. Build Star Schema
2. Create Relationships
3. Verify Cardinality
4. Create Sales Report
5. Analyze Performance

---

# 📚 Module Summary

In this module, you learned:

✅ Dimensional Modeling

✅ Fact Tables

✅ Dimension Tables

✅ Measures vs Dimensions

✅ Star Schema

✅ Snowflake Schema

✅ Surrogate Keys

✅ Natural Keys

✅ Conformed Dimensions

✅ Slowly Changing Dimensions

✅ Date Dimensions

✅ Enterprise Modeling Best Practices

A properly designed Star Schema is one of the most important factors in creating fast, scalable, and maintainable Power BI solutions.

---

## ⏭️ Next Module

**Module 7: Data Visualization Fundamentals**

Topics Covered:

- Principles of Data Visualization
- Data Storytelling
- Choosing the Right Chart
- Visual Perception
- Dashboard Design Fundamentals
- Color Theory
- User Experience (UX) in Reporting
- Visualization Best Practices