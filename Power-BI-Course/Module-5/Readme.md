# Module 5: Data Modeling Fundamentals

## 📖 Overview

Data modeling is one of the most important concepts in Power BI. A well-designed data model improves report performance, simplifies DAX calculations, and ensures accurate business insights.

Many Power BI beginners focus heavily on visualizations and DAX but overlook data modeling. In reality, most performance and reporting issues originate from poor data models.

This module covers relationships, cardinality, filter propagation, keys, and best practices for designing scalable Power BI models.

---

# 🎯 Learning Objectives

After completing this module, you will be able to:

- Understand Data Modeling concepts
- Understand the role of tables in Power BI
- Create relationships between tables
- Understand Primary Keys and Foreign Keys
- Understand Cardinality
- Understand Cross Filter Direction
- Manage Relationships
- Design efficient Power BI data models
- Troubleshoot relationship issues

---

# 📚 Table of Contents

1. Introduction to Data Modeling
2. Why Data Modeling is Important
3. Tables in Power BI
4. Understanding Relationships
5. Primary Keys
6. Foreign Keys
7. Relationship Types
8. Cardinality
9. Cross Filter Direction
10. Active vs Inactive Relationships
11. Creating Relationships
12. Managing Relationships
13. Relationship Troubleshooting
14. Data Modeling Best Practices
15. Common Modeling Mistakes
16. Key Terminologies
17. Practice Exercises
18. Mini Project
19. Module Summary

---

# 1️⃣ Introduction to Data Modeling

## What is Data Modeling?

Data Modeling is the process of organizing data and defining relationships between tables.

It determines how data is connected and how Power BI retrieves information when building reports.

---

## Simple Example

Imagine a company has two tables:

### Customers Table

| CustomerID | CustomerName |
|------------|-------------|
| 101 | Rahul |
| 102 | Priya |

---

### Orders Table

| OrderID | CustomerID | Sales |
|----------|------------|---------|
| 1 | 101 | 5000 |
| 2 | 102 | 3000 |

---

Power BI uses CustomerID to connect both tables.

This connection is called a relationship.

---

# 2️⃣ Why Data Modeling is Important

A proper model provides:

### Faster Performance

Efficient relationships reduce query execution time.

---

### Accurate Results

Ensures calculations return correct values.

---

### Easier Reporting

Users can build reports more easily.

---

### Better Scalability

Handles large datasets efficiently.

---

## Without Proper Modeling

Problems include:

- Duplicate results
- Incorrect totals
- Slow reports
- Complex DAX formulas

---

# 3️⃣ Tables in Power BI

Power BI models consist of tables.

---

## Types of Tables

### Fact Tables

Contain measurable business data.

Examples:

- Sales
- Orders
- Transactions
- Revenue

---

### Dimension Tables

Contain descriptive information.

Examples:

- Customer
- Product
- Employee
- Region
- Date

---

## Example

### Sales Fact Table

| OrderID | ProductID | CustomerID | Sales |
|----------|------------|------------|---------|
| 1 | P101 | C101 | 5000 |

---

### Product Dimension

| ProductID | ProductName |
|------------|-------------|
| P101 | Laptop |

---

# 4️⃣ Understanding Relationships

Relationships connect tables.

They allow Power BI to combine information from multiple tables.

---

## Example

### Customers

| CustomerID | Name |
|------------|------|
| 101 | Rahul |

---

### Orders

| OrderID | CustomerID |
|----------|------------|
| 1 | 101 |

---

Relationship:

```text
Customers[CustomerID]
         ↓
Orders[CustomerID]
```

---

# 5️⃣ Primary Keys

## Definition

A Primary Key uniquely identifies each row in a table.

---

## Characteristics

- Unique
- No duplicates
- No null values

---

## Example

### Customers Table

| CustomerID | Name |
|------------|------|
| 101 | Rahul |
| 102 | Priya |

CustomerID is the Primary Key.

---

## Invalid Example

| CustomerID |
|------------|
| 101 |
| 101 |

Duplicates make it invalid.

---

# 6️⃣ Foreign Keys

## Definition

A Foreign Key is a column that references a Primary Key from another table.

---

## Example

### Customers Table

| CustomerID |
|------------|
| 101 |

---

### Orders Table

| OrderID | CustomerID |
|----------|------------|
| 1 | 101 |

CustomerID in Orders is a Foreign Key.

---

## Purpose

Foreign Keys create relationships between tables.

---

# 7️⃣ Relationship Types

Power BI supports several relationship types.

---

## One-to-One (1:1)

One record matches one record.

### Example

| EmployeeID |
|------------|
| 1 |

↔

| EmployeeID |
|------------|
| 1 |

---

## One-to-Many (1:*)

Most common relationship.

### Example

One customer can place many orders.

```text
Customer
   ↓
Orders
```

---

### Customers

| CustomerID |
|------------|
| 101 |

---

### Orders

| OrderID | CustomerID |
|----------|------------|
| 1 | 101 |
| 2 | 101 |

---

## Many-to-One (*:1)

Reverse view of One-to-Many.

---

## Many-to-Many (*:*)

Both tables contain duplicates.

### Example

Students and Courses

A student can enroll in many courses.

A course can have many students.

---

# 8️⃣ Cardinality

## What is Cardinality?

Cardinality defines how tables relate to one another.

---

## Types

### One-to-One

```text
1 : 1
```

---

### One-to-Many

```text
1 : *
```

---

### Many-to-One

```text
* : 1
```

---

### Many-to-Many

```text
* : *
```

---

## Why Cardinality Matters

It affects:

- Data Accuracy
- Filter Propagation
- Query Performance

---

# 9️⃣ Cross Filter Direction

## What is Cross Filtering?

Determines how filters move between tables.

---

## Single Direction

```text
Dimension
    ↓
Fact
```

Most recommended.

---

### Example

Product filters Sales.

Sales does not filter Product.

---

## Both Direction

```text
Dimension ↔ Fact
```

Filters move in both directions.

---

## Advantages

Useful for advanced scenarios.

---

## Disadvantages

May:

- Reduce performance
- Create ambiguity
- Produce unexpected results

---

## Best Practice

Use Single Direction whenever possible.

---

# 🔟 Active vs Inactive Relationships

Power BI allows multiple relationships between tables.

However, only one relationship can be active at a time.

---

## Active Relationship

Represented by:

```text
Solid Line
```

Used automatically.

---

## Inactive Relationship

Represented by:

```text
Dashed Line
```

Requires DAX functions like:

```DAX
USERELATIONSHIP()
```

---

## Example

Orders Table:

- Order Date
- Delivery Date

Date Table can only have one active relationship.

---

# 1️⃣1️⃣ Creating Relationships

## Automatic Detection

Power BI attempts to detect relationships automatically.

---

## Manual Creation

### Method 1

Drag column to matching column.

---

### Method 2

```text
Model View
      ↓
Manage Relationships
      ↓
New
```

---

## Required Information

- Table
- Column
- Cardinality
- Filter Direction

---

# 1️⃣2️⃣ Managing Relationships

## Manage Relationships Window

Allows:

- Edit Relationships
- Delete Relationships
- Create Relationships
- Activate Relationships

---

## Relationship Settings

### Cardinality

Choose relationship type.

### Filter Direction

Single or Both.

### Active Status

Enable or disable relationship.

---

# 1️⃣3️⃣ Relationship Troubleshooting

## Problem 1

Missing Relationship

### Symptoms

Blank visuals.

### Solution

Create relationship.

---

## Problem 2

Duplicate Keys

### Symptoms

Relationship creation fails.

### Solution

Remove duplicates.

---

## Problem 3

Incorrect Data Types

### Symptoms

Relationship unavailable.

### Solution

Ensure matching data types.

---

## Problem 4

Ambiguous Paths

### Symptoms

Incorrect filtering.

### Solution

Simplify model.

---

# 1️⃣4️⃣ Data Modeling Best Practices

## Use Star Schema

Preferred structure.

---

## Avoid Many-to-Many

Use only when necessary.

---

## Use Meaningful Names

Examples:

```text
FactSales
DimCustomer
DimProduct
```

---

## Remove Unused Columns

Improves performance.

---

## Create Date Table

Required for Time Intelligence.

---

## Use Single Direction Filtering

Unless a specific need exists.

---

# 1️⃣5️⃣ Common Modeling Mistakes

### Loading Everything

Imports unnecessary data.

---

### Using Flat Files Only

Creates inefficient models.

---

### Ignoring Relationships

Causes reporting errors.

---

### Excessive Bi-Directional Filtering

Reduces performance.

---

### Poor Naming Conventions

Makes maintenance difficult.

---

# 📌 Key Terminologies

| Term | Definition |
|--------|------------|
| Data Model | Collection of connected tables |
| Relationship | Connection between tables |
| Primary Key | Unique identifier |
| Foreign Key | References another table |
| Cardinality | Relationship structure |
| Fact Table | Contains measurable data |
| Dimension Table | Contains descriptive data |
| Filter Propagation | Movement of filters |
| Active Relationship | Default relationship |
| Inactive Relationship | Secondary relationship |

---

# 📝 Practice Exercises

## Exercise 1

Create two tables:

- Customers
- Orders

Build a relationship using CustomerID.

---

## Exercise 2

Identify Primary Keys and Foreign Keys.

---

## Exercise 3

Create:

- One-to-One Relationship
- One-to-Many Relationship

---

## Exercise 4

Experiment with:

- Single Filter Direction
- Both Filter Direction

Observe results.

---

## Exercise 5

Create a model using:

- Product Table
- Sales Table
- Customer Table

---

# 🎯 Mini Project

## Retail Sales Data Model

### Tables

#### Customers

| CustomerID | CustomerName |
|------------|-------------|

#### Products

| ProductID | ProductName |
|------------|-------------|

#### Sales

| SaleID | CustomerID | ProductID | Sales |
|---------|------------|-----------|--------|

---

### Tasks

1. Import all tables
2. Create relationships
3. Identify Primary Keys
4. Identify Foreign Keys
5. Verify filter behavior
6. Create basic report

---

# 📚 Module Summary

In this module, you learned:

✅ Data Modeling Fundamentals

✅ Fact Tables & Dimension Tables

✅ Relationships

✅ Primary Keys

✅ Foreign Keys

✅ Relationship Types

✅ Cardinality

✅ Cross Filter Direction

✅ Active & Inactive Relationships

✅ Relationship Management

✅ Data Modeling Best Practices

A strong data model is the foundation of every successful Power BI solution. Before creating advanced visualizations and DAX measures, always ensure your model is designed correctly.

---

## ⏭️ Next Module

**Module 6: Star Schema & Snowflake Schema**

Topics Covered:

- Dimensional Modeling
- Star Schema Design
- Snowflake Schema Design
- Fact & Dimension Tables
- Surrogate Keys
- Conformed Dimensions
- Performance Optimization
- Real-World Data Warehouse Models