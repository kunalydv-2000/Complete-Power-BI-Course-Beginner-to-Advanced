# Module 9: Introduction to DAX (Data Analysis Expressions)

## 📖 Overview

DAX (Data Analysis Expressions) is the formula language used in Power BI, Power Pivot, and SQL Server Analysis Services (SSAS) Tabular Models.

DAX allows you to create calculations, business metrics, KPIs, and advanced analytical logic that cannot be achieved through visualizations alone.

Understanding DAX is one of the most important skills for becoming a Power BI Developer, Data Analyst, or BI Analyst.

This module introduces DAX fundamentals, syntax, calculated columns, measures, row context, filter context, and essential business calculations.

---

# 🎯 Learning Objectives

After completing this module, you will be able to:

- Understand what DAX is
- Learn DAX syntax
- Create Calculated Columns
- Create Measures
- Understand Row Context
- Understand Filter Context
- Write basic DAX formulas
- Build business calculations
- Follow DAX best practices

---

# 📚 Table of Contents

1. What is DAX?
2. Why DAX is Important
3. DAX vs Excel Formulas
4. DAX Syntax
5. Data Types in DAX
6. Operators in DAX
7. Understanding Calculated Columns
8. Understanding Measures
9. Calculated Columns vs Measures
10. Row Context
11. Filter Context
12. Context Transition
13. Common DAX Functions
14. Business Calculations
15. DAX Best Practices
16. Common DAX Mistakes
17. Key Terminologies
18. Practice Exercises
19. Mini Project
20. Module Summary

---

# 1️⃣ What is DAX?

## Definition

DAX stands for:

```text
Data Analysis Expressions
```

It is a formula language used to:

- Perform calculations
- Create KPIs
- Build business metrics
- Analyze data dynamically

---

## Where DAX is Used

- Power BI
- Power Pivot
- SSAS Tabular

---

## Examples

Calculate Total Sales:

:contentReference[oaicite:0]{index=0}

In Power BI:

```DAX
Total Sales =
SUM(Sales[Revenue])
```

---

# 2️⃣ Why DAX is Important

Without DAX, Power BI would only display raw data.

DAX enables:

### Business Logic

Example:

```text
Profit = Revenue - Cost
```

---

### KPIs

Example:

```text
Profit Margin %
```

---

### Time Intelligence

Example:

```text
Year-to-Date Sales
```

---

### Dynamic Calculations

Results change automatically based on filters.

---

# 3️⃣ DAX vs Excel Formulas

Many DAX functions resemble Excel formulas.

---

## Similarities

Examples:

```text
SUM()
IF()
AVERAGE()
COUNT()
```

---

## Differences

| Excel | DAX |
|---------|---------|
| Works on Cells | Works on Tables |
| Static | Dynamic |
| Single Worksheet | Data Model |
| Limited Relationships | Relationship Aware |

---

## Example

Excel:

```excel
=A1+B1
```

DAX:

```DAX
Total Revenue =
SUM(Sales[Revenue])
```

---

# 4️⃣ DAX Syntax

Every DAX formula follows a structure.

---

## Measure Syntax

```DAX
Measure Name =
Function()
```

---

## Example

```DAX
Total Sales =
SUM(Sales[Revenue])
```

---

### Breakdown

```text
Total Sales
```

Measure Name

---

```text
SUM
```

Function

---

```text
Sales[Revenue]
```

Column Reference

---

# 5️⃣ Data Types in DAX

DAX supports several data types.

---

## Whole Number

```text
100
```

---

## Decimal Number

```text
100.50
```

---

## Currency

```text
₹5000
```

---

## Text

```text
Laptop
```

---

## Date

```text
01-Jan-2026
```

---

## Boolean

```text
TRUE
FALSE
```

---

# 6️⃣ Operators in DAX

---

## Arithmetic Operators

| Operator | Meaning |
|-----------|---------|
| + | Addition |
| - | Subtraction |
| * | Multiplication |
| / | Division |
| ^ | Power |

---

## Example

```DAX
Profit =
Sales[Revenue] - Sales[Cost]
```

---

## Comparison Operators

| Operator | Meaning |
|-----------|---------|
| = | Equal |
| <> | Not Equal |
| > | Greater Than |
| < | Less Than |
| >= | Greater Than Equal |
| <= | Less Than Equal |

---

## Logical Operators

| Operator | Meaning |
|-----------|---------|
| && | AND |
| \|\| | OR |

---

# 7️⃣ Understanding Calculated Columns

## What is a Calculated Column?

A Calculated Column creates a new column in a table.

The calculation is performed row by row.

---

## Example

Sales Table

| Revenue | Cost |
|----------|------|
| 1000 | 700 |

---

Create:

```DAX
Profit =
Sales[Revenue] - Sales[Cost]
```

---

Result

| Revenue | Cost | Profit |
|----------|------|---------|
| 1000 | 700 | 300 |

---

## Characteristics

### Stored in Model

Consumes memory.

---

### Calculated During Refresh

Not calculated dynamically.

---

# 8️⃣ Understanding Measures

## What is a Measure?

A Measure performs calculations dynamically based on report filters.

---

## Example

```DAX
Total Revenue =
SUM(Sales[Revenue])
```

---

## Characteristics

### Not Stored

Consumes less memory.

---

### Dynamic

Changes according to:

- Filters
- Slicers
- User selections

---

# 9️⃣ Calculated Columns vs Measures

| Feature | Calculated Column | Measure |
|----------|------------------|----------|
| Storage | Stored | Not Stored |
| Calculation Time | Refresh | Query Time |
| Memory Usage | Higher | Lower |
| Dynamic | No | Yes |
| Use in Axis | Yes | No |
| Use in Values | Yes | Yes |

---

## Rule of Thumb

Prefer Measures whenever possible.

---

# 🔟 Row Context

## What is Row Context?

Row Context means DAX evaluates one row at a time.

---

## Example

```DAX
Profit =
Sales[Revenue] - Sales[Cost]
```

---

Power BI processes:

Row 1

```text
1000 - 700 = 300
```

---

Row 2

```text
1500 - 900 = 600
```

---

This is Row Context.

---

# 1️⃣1️⃣ Filter Context

## What is Filter Context?

Filter Context is created by:

- Visuals
- Slicers
- Filters
- Report Pages

---

## Example

A report shows:

```text
Total Revenue
```

---

User selects:

```text
Region = North
```

---

Measure automatically recalculates.

This behavior is called Filter Context.

---

# 1️⃣2️⃣ Context Transition

## Definition

Context Transition occurs when Row Context becomes Filter Context.

---

Most commonly triggered by:

```DAX
CALCULATE()
```

---

## Why Important?

Foundation of advanced DAX.

---

# 1️⃣3️⃣ Common DAX Functions

---

## SUM

Adds values.

```DAX
Total Sales =
SUM(Sales[Revenue])
```

---

## AVERAGE

Calculates average.

```DAX
Average Sales =
AVERAGE(Sales[Revenue])
```

---

## COUNT

Counts rows.

```DAX
Order Count =
COUNT(Sales[OrderID])
```

---

## DISTINCTCOUNT

Counts unique values.

```DAX
Customers =
DISTINCTCOUNT(Sales[CustomerID])
```

---

## MIN

Returns minimum value.

```DAX
Minimum Sales =
MIN(Sales[Revenue])
```

---

## MAX

Returns maximum value.

```DAX
Maximum Sales =
MAX(Sales[Revenue])
```

---

# 1️⃣4️⃣ Business Calculations

## Total Revenue

```DAX
Total Revenue =
SUM(Sales[Revenue])
```

---

## Total Cost

```DAX
Total Cost =
SUM(Sales[Cost])
```

---

## Total Profit

```DAX
Total Profit =
SUM(Sales[Revenue]) -
SUM(Sales[Cost])
```

---

## Profit Margin %

```DAX
Profit Margin % =
DIVIDE(
    [Total Profit],
    [Total Revenue]
)
```

---

## Average Order Value

```DAX
Average Order Value =
DIVIDE(
    [Total Revenue],
    [Order Count]
)
```

---

# 1️⃣5️⃣ DAX Best Practices

### Use Measures Instead of Columns

When possible.

---

### Use Meaningful Names

Example:

```text
Total Revenue
```

instead of:

```text
TR
```

---

### Use DIVIDE()

Instead of:

```DAX
Revenue / Cost
```

Use:

```DAX
DIVIDE(Revenue, Cost)
```

---

### Organize Measures

Create dedicated measure tables.

---

### Avoid Unnecessary Calculated Columns

They increase memory usage.

---

# 1️⃣6️⃣ Common DAX Mistakes

### Using Columns Instead of Measures

Leads to inefficient models.

---

### Ignoring Filter Context

Produces incorrect results.

---

### Hardcoding Values

Avoid:

```DAX
Revenue > 1000
```

when values may change.

---

### Poor Naming Conventions

Makes maintenance difficult.

---

### Not Using DIVIDE()

Can cause division errors.

---

# 📌 Key Terminologies

| Term | Definition |
|--------|------------|
| DAX | Data Analysis Expressions |
| Measure | Dynamic calculation |
| Calculated Column | Stored row-by-row calculation |
| Row Context | Current row being evaluated |
| Filter Context | Filters affecting calculations |
| Context Transition | Row Context becoming Filter Context |
| Function | Built-in DAX operation |
| Expression | Formula returning a value |
| KPI | Key Performance Indicator |
| Aggregation | Summarizing data |

---

# 📝 Practice Exercises

## Exercise 1

Create the following measures:

```DAX
Total Revenue
```

```DAX
Total Cost
```

```DAX
Total Profit
```

---

## Exercise 2

Create a Profit calculated column.

---

## Exercise 3

Calculate:

```DAX
Average Revenue
```

---

## Exercise 4

Create:

```DAX
Distinct Customer Count
```

---

## Exercise 5

Observe how measures change when slicers are applied.

---

# 🎯 Mini Project

## Sales KPI Dashboard

### Dataset

Sales Data containing:

- Revenue
- Cost
- CustomerID
- OrderID

---

### Tasks

Create:

### Measures

```DAX
Total Revenue
```

```DAX
Total Cost
```

```DAX
Total Profit
```

```DAX
Profit Margin %
```

```DAX
Customer Count
```

---

### Visuals

- KPI Cards
- Revenue Trend
- Profit Analysis

---

### Objective

Understand how DAX powers business reporting.

---

# 📚 Module Summary

In this module, you learned:

✅ What DAX Is

✅ DAX Syntax

✅ Data Types

✅ Operators

✅ Calculated Columns

✅ Measures

✅ Row Context

✅ Filter Context

✅ Context Transition

✅ Basic DAX Functions

✅ Business Calculations

✅ DAX Best Practices

DAX is the analytical engine of Power BI. Mastering DAX enables you to create sophisticated business metrics, KPIs, and advanced analytical solutions.

---

## ⏭️ Next Module

**Module 10: Essential DAX Functions**

Topics Covered:

- Mathematical Functions
- Statistical Functions
- Logical Functions
- Text Functions
- Date & Time Functions
- Information Functions
- Aggregation Functions
- Real-World Business Calculations
- DAX Function Best Practices