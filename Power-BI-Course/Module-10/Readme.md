# Module 10: Essential DAX Functions

## 📖 Overview

In the previous module, you learned the fundamentals of DAX, including measures, calculated columns, row context, and filter context.

This module focuses on the most important DAX functions used in real-world Power BI development. These functions form the foundation of business calculations, KPI creation, data transformation, and analytical reporting.

Mastering these functions is essential before moving to advanced DAX concepts such as CALCULATE(), FILTER(), Time Intelligence, and Iterator Functions.

---

# 🎯 Learning Objectives

After completing this module, you will be able to:

- Understand DAX function categories
- Use mathematical functions
- Use statistical functions
- Apply logical functions
- Work with text functions
- Use date and time functions
- Apply aggregation functions
- Build business metrics using DAX
- Follow DAX best practices

---

# 📚 Table of Contents

1. Introduction to DAX Functions
2. Function Categories
3. Mathematical Functions
4. Statistical Functions
5. Aggregation Functions
6. Logical Functions
7. Text Functions
8. Date & Time Functions
9. Information Functions
10. Business Calculation Examples
11. Function Nesting
12. Best Practices
13. Common Mistakes
14. Key Terminologies
15. Practice Exercises
16. Mini Project
17. Module Summary

---

# 1️⃣ Introduction to DAX Functions

## What is a DAX Function?

A DAX function is a predefined formula that performs a specific calculation.

---

## Syntax

```DAX
FunctionName(argument1, argument2)
```

---

## Example

```DAX
Total Revenue =
SUM(Sales[Revenue])
```

---

### Components

```text
SUM
```

Function Name

```text
Sales[Revenue]
```

Argument

---

# 2️⃣ Function Categories

DAX functions are grouped into categories.

---

## Major Categories

### Mathematical Functions

Perform arithmetic operations.

---

### Statistical Functions

Perform statistical analysis.

---

### Aggregation Functions

Summarize data.

---

### Logical Functions

Apply conditions.

---

### Text Functions

Manipulate text values.

---

### Date & Time Functions

Work with dates.

---

### Information Functions

Provide metadata about data.

---

# 3️⃣ Mathematical Functions

Used for arithmetic calculations.

---

## ABS()

Returns absolute value.

### Example

```DAX
ABS(-500)
```

Result:

```text
500
```

---

## POWER()

Raises a number to a power.

### Example

```DAX
POWER(5,2)
```

Result:

```text
25
```

---

## SQRT()

Returns square root.

### Example

```DAX
SQRT(81)
```

Result:

```text
9
```

---

## MOD()

Returns remainder.

### Example

```DAX
MOD(10,3)
```

Result:

```text
1
```

---

## ROUND()

Rounds a number.

### Example

```DAX
ROUND(25.678,2)
```

Result:

```text
25.68
```

---

# 4️⃣ Statistical Functions

Used for statistical analysis.

---

## AVERAGE()

Returns average value.

### Example

```DAX
Average Revenue =
AVERAGE(Sales[Revenue])
```

---

## MEDIAN()

Returns middle value.

### Example

```DAX
Median Revenue =
MEDIAN(Sales[Revenue])
```

---

## MIN()

Returns smallest value.

### Example

```DAX
Minimum Revenue =
MIN(Sales[Revenue])
```

---

## MAX()

Returns largest value.

### Example

```DAX
Maximum Revenue =
MAX(Sales[Revenue])
```

---

## STDEV.P()

Population standard deviation.

### Example

```DAX
STDEV.P(Sales[Revenue])
```

---

# 5️⃣ Aggregation Functions

Aggregation functions summarize data.

---

## SUM()

Adds values.

### Example

```DAX
Total Revenue =
SUM(Sales[Revenue])
```

---

## COUNT()

Counts non-blank values.

### Example

```DAX
Order Count =
COUNT(Sales[OrderID])
```

---

## COUNTA()

Counts non-empty values.

### Example

```DAX
Customer Count =
COUNTA(Customers[CustomerName])
```

---

## DISTINCTCOUNT()

Counts unique values.

### Example

```DAX
Unique Customers =
DISTINCTCOUNT(Sales[CustomerID])
```

---

## COUNTROWS()

Counts rows in a table.

### Example

```DAX
Total Rows =
COUNTROWS(Sales)
```

---

# 6️⃣ Logical Functions

Logical functions evaluate conditions.

---

## IF()

Returns one value if condition is TRUE and another if FALSE.

### Syntax

```DAX
IF(condition,value_if_true,value_if_false)
```

---

### Example

```DAX
Sales Status =
IF(
    Sales[Revenue] > 1000,
    "High",
    "Low"
)
```

---

## SWITCH()

Alternative to multiple IF statements.

### Example

```DAX
Rating =
SWITCH(
    TRUE(),
    Sales[Revenue] >= 5000,"Excellent",
    Sales[Revenue] >= 3000,"Good",
    "Average"
)
```

---

## AND()

Checks multiple conditions.

### Example

```DAX
AND(
    Sales[Revenue]>1000,
    Sales[Profit]>200
)
```

---

## OR()

Returns TRUE if any condition is TRUE.

### Example

```DAX
OR(
    Sales[Revenue]>1000,
    Sales[Profit]>200
)
```

---

## NOT()

Reverses logical value.

### Example

```DAX
NOT(TRUE())
```

Result:

```text
FALSE
```

---

# 7️⃣ Text Functions

Used for string manipulation.

---

## LEFT()

Extracts characters from left.

### Example

```DAX
LEFT("PowerBI",5)
```

Result:

```text
Power
```

---

## RIGHT()

Extracts characters from right.

### Example

```DAX
RIGHT("PowerBI",2)
```

Result:

```text
BI
```

---

## MID()

Extracts characters from middle.

### Example

```DAX
MID("PowerBI",3,4)
```

Result:

```text
werB
```

---

## LEN()

Returns text length.

### Example

```DAX
LEN("Power BI")
```

Result:

```text
8
```

---

## UPPER()

Converts to uppercase.

### Example

```DAX
UPPER("power bi")
```

Result:

```text
POWER BI
```

---

## LOWER()

Converts to lowercase.

### Example

```DAX
LOWER("POWER BI")
```

Result:

```text
power bi
```

---

## TRIM()

Removes extra spaces.

### Example

```DAX
TRIM("  Rahul  ")
```

Result:

```text
Rahul
```

---

# 8️⃣ Date & Time Functions

Critical for business reporting.

---

## TODAY()

Returns current date.

### Example

```DAX
TODAY()
```

---

## NOW()

Returns current date and time.

### Example

```DAX
NOW()
```

---

## YEAR()

Returns year.

### Example

```DAX
YEAR(Sales[OrderDate])
```

---

## MONTH()

Returns month number.

### Example

```DAX
MONTH(Sales[OrderDate])
```

---

## DAY()

Returns day number.

### Example

```DAX
DAY(Sales[OrderDate])
```

---

## WEEKDAY()

Returns weekday number.

### Example

```DAX
WEEKDAY(Sales[OrderDate])
```

---

## DATEDIFF()

Returns difference between dates.

### Example

```DAX
DATEDIFF(
    Orders[OrderDate],
    Orders[ShipDate],
    DAY
)
```

---

# 9️⃣ Information Functions

Provide metadata about values.

---

## ISBLANK()

Checks if value is blank.

### Example

```DAX
ISBLANK(Sales[Revenue])
```

---

## ISNUMBER()

Checks if value is numeric.

### Example

```DAX
ISNUMBER(Sales[Revenue])
```

---

## ISTEXT()

Checks if value is text.

### Example

```DAX
ISTEXT(Customers[CustomerName])
```

---

# 🔟 Business Calculation Examples

---

## Total Revenue

```DAX
Total Revenue =
SUM(Sales[Revenue])
```

---

## Average Revenue

```DAX
Average Revenue =
AVERAGE(Sales[Revenue])
```

---

## Total Profit

```DAX
Total Profit =
SUM(Sales[Revenue])
-
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

## Customer Count

```DAX
Customer Count =
DISTINCTCOUNT(Sales[CustomerID])
```

---

# 1️⃣1️⃣ Function Nesting

Functions can be combined.

---

## Example

```DAX
Profit Status =
IF(
    [Profit Margin %] > 0.20,
    "Good",
    "Needs Improvement"
)
```

---

## Nested Example

```DAX
Category =
IF(
    Sales[Revenue] > 5000,
    UPPER("Premium"),
    LOWER("standard")
)
```

---

# 1️⃣2️⃣ DAX Best Practices

### Use DIVIDE()

Instead of:

```DAX
Revenue / Cost
```

Use:

```DAX
DIVIDE(Revenue,Cost)
```

---

### Use Measures Whenever Possible

Reduces memory usage.

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

### Keep Formulas Simple

Avoid unnecessary complexity.

---

# 1️⃣3️⃣ Common Mistakes

### Ignoring Blank Values

Can cause incorrect calculations.

---

### Using Calculated Columns Unnecessarily

Increases model size.

---

### Hardcoding Values

Avoid fixed numbers whenever possible.

---

### Poor Naming Conventions

Makes maintenance difficult.

---

# 📌 Key Terminologies

| Term | Definition |
|--------|------------|
| Function | Predefined calculation |
| Argument | Input supplied to a function |
| Aggregation | Summarizing data |
| Logical Function | Evaluates conditions |
| Text Function | Manipulates text |
| Statistical Function | Performs statistical calculations |
| Date Function | Works with dates |
| Nested Function | Function inside another function |
| Measure | Dynamic calculation |
| Expression | Formula returning a value |

---

# 📝 Practice Exercises

## Exercise 1

Create measures:

```DAX
Total Revenue
```

```DAX
Average Revenue
```

```DAX
Customer Count
```

---

## Exercise 2

Create a calculated column:

```DAX
Revenue Category
```

Using IF().

---

## Exercise 3

Extract first 3 characters from Product Name.

---

## Exercise 4

Calculate order processing days using:

```DAX
DATEDIFF()
```

---

## Exercise 5

Create a Profit Status measure using:

```DAX
IF()
```

---

# 🎯 Mini Project

## Sales KPI Dashboard

### Measures Required

```DAX
Total Revenue
```

```DAX
Average Revenue
```

```DAX
Customer Count
```

```DAX
Total Profit
```

```DAX
Profit Margin %
```

---

### Additional Tasks

Create:

- Revenue Category Column
- Profit Status Indicator
- Revenue KPI Card
- Profit KPI Card

---

### Objective

Apply the most commonly used DAX functions in a real business reporting scenario.

---

# 📚 Module Summary

In this module, you learned:

✅ Mathematical Functions

✅ Statistical Functions

✅ Aggregation Functions

✅ Logical Functions

✅ Text Functions

✅ Date & Time Functions

✅ Information Functions

✅ Function Nesting

✅ Business Calculations

✅ DAX Best Practices

These functions form the core toolkit of every Power BI developer and analyst. Mastering them prepares you for advanced DAX concepts, including Time Intelligence and Context Manipulation.

---

## ⏭️ Next Module

**Module 11: Time Intelligence in DAX**

Topics Covered:

- Date Tables
- Calendar Tables
- Time Intelligence Concepts
- TOTALYTD()
- TOTALMTD()
- TOTALQTD()
- SAMEPERIODLASTYEAR()
- DATEADD()
- PARALLELPERIOD()
- Year-over-Year Analysis
- Running Totals
- Business Time-Based KPIs