# Module 11: Time Intelligence in DAX

## 📖 Overview

Time Intelligence is one of the most powerful capabilities in Power BI. Businesses rarely analyze data in isolation—they compare performance across months, quarters, years, and fiscal periods.

Time Intelligence functions allow analysts to answer questions such as:

- How much revenue have we generated this year?
- How does this month's performance compare to last month?
- What is the year-over-year growth rate?
- What were sales during the same period last year?

This module covers Date Tables, Calendar Tables, Time Intelligence concepts, and essential DAX functions used in real-world business reporting.

---

# 🎯 Learning Objectives

After completing this module, you will be able to:

- Understand Time Intelligence concepts
- Create and configure Date Tables
- Build Calendar Tables
- Use Time Intelligence functions
- Calculate YTD, MTD, and QTD metrics
- Compare performance across periods
- Perform Year-over-Year analysis
- Create Running Totals
- Build business KPIs based on time

---

# 📚 Table of Contents

1. Introduction to Time Intelligence
2. Why Time Intelligence Matters
3. Understanding Date Tables
4. Creating a Calendar Table
5. Marking a Date Table
6. Time Intelligence Requirements
7. TOTALYTD()
8. TOTALMTD()
9. TOTALQTD()
10. DATESYTD()
11. SAMEPERIODLASTYEAR()
12. DATEADD()
13. PARALLELPERIOD()
14. PREVIOUSMONTH()
15. PREVIOUSYEAR()
16. Running Totals
17. Year-over-Year Analysis
18. Month-over-Month Analysis
19. Business KPI Examples
20. Best Practices
21. Common Mistakes
22. Key Terminologies
23. Practice Exercises
24. Mini Project
25. Module Summary

---

# 1️⃣ Introduction to Time Intelligence

## What is Time Intelligence?

Time Intelligence refers to calculations that compare data across time periods.

Examples:

- Daily Sales
- Monthly Revenue
- Quarterly Profit
- Yearly Growth

---

## Common Business Questions

```text
What are current year sales?
```

```text
How much did revenue grow compared to last year?
```

```text
What is the monthly sales trend?
```

---

# 2️⃣ Why Time Intelligence Matters

Businesses make decisions based on trends over time.

---

## Examples

### Finance

Compare revenue across years.

---

### Sales

Track monthly performance.

---

### HR

Analyze employee turnover trends.

---

### Marketing

Measure campaign effectiveness over time.

---

# 3️⃣ Understanding Date Tables

## What is a Date Table?

A Date Table is a dedicated table containing one row for every date.

---

## Example

| Date | Year | Quarter | Month |
|--------|------|----------|--------|
| 01-Jan-2026 | 2026 | Q1 | January |
| 02-Jan-2026 | 2026 | Q1 | January |

---

## Why Important?

Time Intelligence functions require a proper Date Table.

Without it:

- Many functions won't work correctly.
- Performance may suffer.
- Analysis becomes inconsistent.

---

# 4️⃣ Creating a Calendar Table

## Method 1: CALENDAR()

Creates a continuous date range.

```DAX
Date Table =
CALENDAR(
    DATE(2020,1,1),
    DATE(2030,12,31)
)
```

---

## Method 2: CALENDARAUTO()

Automatically detects date ranges.

```DAX
Date Table =
CALENDARAUTO()
```

---

## Recommended

Use CALENDAR() for better control.

---

# 5️⃣ Marking a Date Table

After creating a Date Table:

### Step 1

Select Date Table

---

### Step 2

Go to:

```text
Table Tools
```

---

### Step 3

Choose:

```text
Mark as Date Table
```

---

### Step 4

Select Date Column

---

## Why Required?

Allows Power BI to recognize the table for Time Intelligence functions.

---

# 6️⃣ Time Intelligence Requirements

Before using Time Intelligence:

### Requirement 1

Continuous Date Table

---

### Requirement 2

Unique Dates

No duplicates allowed.

---

### Requirement 3

No Missing Dates

Every day must exist.

---

### Requirement 4

Marked as Date Table

---

### Requirement 5

Relationship with Fact Table

Example:

```text
Date Table[Date]
        ↓
Sales[Order Date]
```

---

# 7️⃣ TOTALYTD()

## Purpose

Calculates Year-to-Date values.

---

## Concept

YTD accumulates values from the beginning of the year to the current date.

---

### Visualization

```text
January
     ↓
February
     ↓
March
     ↓
Current Month
```

---

## Syntax

```DAX
TOTALYTD(
    Expression,
    Dates
)
```

---

## Example

```DAX
YTD Sales =
TOTALYTD(
    [Total Revenue],
    'Date Table'[Date]
)
```

---

## Use Cases

- Revenue Tracking
- Profit Analysis
- Budget Monitoring

---

# 8️⃣ TOTALMTD()

## Purpose

Calculates Month-to-Date values.

---

## Example

```DAX
MTD Sales =
TOTALMTD(
    [Total Revenue],
    'Date Table'[Date]
)
```

---

## Business Use

Track current month's progress.

---

# 9️⃣ TOTALQTD()

## Purpose

Calculates Quarter-to-Date values.

---

## Example

```DAX
QTD Sales =
TOTALQTD(
    [Total Revenue],
    'Date Table'[Date]
)
```

---

## Business Use

Quarterly performance tracking.

---

# 🔟 DATESYTD()

## Purpose

Returns all dates from the start of the year to the current date.

---

## Example

```DAX
YTD Revenue =
CALCULATE(
    [Total Revenue],
    DATESYTD('Date Table'[Date])
)
```

---

## Difference from TOTALYTD()

DATESYTD() returns dates.

TOTALYTD() returns calculated values.

---

# 1️⃣1️⃣ SAMEPERIODLASTYEAR()

## Purpose

Returns the same period from the previous year.

---

## Example

Current Period:

```text
March 2026
```

Returns:

```text
March 2025
```

---

## Syntax

```DAX
SAMEPERIODLASTYEAR(
    'Date Table'[Date]
)
```

---

## Example

```DAX
Sales LY =
CALCULATE(
    [Total Revenue],
    SAMEPERIODLASTYEAR(
        'Date Table'[Date]
    )
)
```

---

## Use Cases

- YoY Growth
- Historical Comparison

---

# 1️⃣2️⃣ DATEADD()

## Purpose

Shifts dates by a specified interval.

---

## Syntax

```DAX
DATEADD(
    Dates,
    Number,
    Interval
)
```

---

## Example

Previous Month Sales

```DAX
Previous Month Sales =
CALCULATE(
    [Total Revenue],
    DATEADD(
        'Date Table'[Date],
        -1,
        MONTH
    )
)
```

---

## Intervals

- DAY
- MONTH
- QUARTER
- YEAR

---

# 1️⃣3️⃣ PARALLELPERIOD()

## Purpose

Returns a parallel period relative to current selection.

---

## Example

```DAX
Previous Year Sales =
CALCULATE(
    [Total Revenue],
    PARALLELPERIOD(
        'Date Table'[Date],
        -1,
        YEAR
    )
)
```

---

## Difference from DATEADD()

PARALLELPERIOD works at period level.

DATEADD works at date level.

---

# 1️⃣4️⃣ PREVIOUSMONTH()

## Purpose

Returns dates from previous month.

---

## Example

```DAX
Previous Month Revenue =
CALCULATE(
    [Total Revenue],
    PREVIOUSMONTH(
        'Date Table'[Date]
    )
)
```

---

# 1️⃣5️⃣ PREVIOUSYEAR()

## Purpose

Returns dates from previous year.

---

## Example

```DAX
Previous Year Revenue =
CALCULATE(
    [Total Revenue],
    PREVIOUSYEAR(
        'Date Table'[Date]
    )
)
```

---

# 1️⃣6️⃣ Running Totals

## What is a Running Total?

A cumulative total over time.

---

## Example

| Month | Sales | Running Total |
|---------|---------|---------------|
| Jan | 100 | 100 |
| Feb | 200 | 300 |
| Mar | 300 | 600 |

---

## Formula

```DAX
Running Total =
CALCULATE(
    [Total Revenue],
    FILTER(
        ALL('Date Table'),
        'Date Table'[Date]
        <= MAX('Date Table'[Date])
    )
)
```

---

# 1️⃣7️⃣ Year-over-Year Analysis

## Purpose

Compare current year with previous year.

---

## Previous Year Sales

```DAX
Sales LY =
CALCULATE(
    [Total Revenue],
    SAMEPERIODLASTYEAR(
        'Date Table'[Date]
    )
)
```

---

## YoY Growth

```DAX
YoY Growth % =
DIVIDE(
    [Total Revenue] - [Sales LY],
    [Sales LY]
)
```

---

## Formula Concept

:contentReference[oaicite:0]{index=0}

---

# 1️⃣8️⃣ Month-over-Month Analysis

## Purpose

Compare current month with previous month.

---

## Previous Month Revenue

```DAX
Previous Month Revenue =
CALCULATE(
    [Total Revenue],
    DATEADD(
        'Date Table'[Date],
        -1,
        MONTH
    )
)
```

---

## MoM Growth %

```DAX
MoM Growth % =
DIVIDE(
    [Total Revenue] -
    [Previous Month Revenue],
    [Previous Month Revenue]
)
```

---

# 1️⃣9️⃣ Business KPI Examples

---

## YTD Revenue

```DAX
YTD Revenue =
TOTALYTD(
    [Total Revenue],
    'Date Table'[Date]
)
```

---

## YTD Profit

```DAX
YTD Profit =
TOTALYTD(
    [Total Profit],
    'Date Table'[Date]
)
```

---

## Sales Growth %

```DAX
Sales Growth % =
DIVIDE(
    [Total Revenue] -
    [Sales LY],
    [Sales LY]
)
```

---

## Running Revenue

```DAX
Running Revenue =
CALCULATE(
    [Total Revenue],
    FILTER(
        ALL('Date Table'),
        'Date Table'[Date]
        <= MAX('Date Table'[Date])
    )
)
```

---

# 2️⃣0️⃣ Best Practices

### Always Create a Date Table

Required for professional models.

---

### Mark Date Table

Enables Time Intelligence.

---

### Use Continuous Dates

Avoid gaps.

---

### Use Dedicated Date Dimensions

Avoid using transaction dates directly.

---

### Use Meaningful Measure Names

Example:

```text
YTD Revenue
```

instead of:

```text
YTD Rev
```

---

# 2️⃣1️⃣ Common Mistakes

### No Date Table

Most common issue.

---

### Duplicate Dates

Breaks calculations.

---

### Missing Relationships

Prevents proper filtering.

---

### Using Fact Table Dates Directly

Not recommended.

---

### Ignoring Fiscal Calendars

Can cause reporting inconsistencies.

---

# 📌 Key Terminologies

| Term | Definition |
|--------|------------|
| Date Table | Dedicated calendar table |
| Calendar Table | Continuous date dimension |
| YTD | Year-to-Date |
| MTD | Month-to-Date |
| QTD | Quarter-to-Date |
| Running Total | Cumulative total |
| YoY | Year-over-Year |
| MoM | Month-over-Month |
| Time Intelligence | Time-based calculations |
| Fiscal Calendar | Business-specific calendar |

---

# 📝 Practice Exercises

## Exercise 1

Create a Date Table using:

```DAX
CALENDAR()
```

---

## Exercise 2

Create:

```DAX
YTD Revenue
```

---

## Exercise 3

Create:

```DAX
Sales Last Year
```

using:

```DAX
SAMEPERIODLASTYEAR()
```

---

## Exercise 4

Calculate:

```DAX
YoY Growth %
```

---

## Exercise 5

Build a Running Total measure.

---

# 🎯 Mini Project

## Executive Sales Dashboard

### Create Measures

```DAX
Total Revenue
```

```DAX
YTD Revenue
```

```DAX
MTD Revenue
```

```DAX
QTD Revenue
```

```DAX
Sales LY
```

```DAX
YoY Growth %
```

```DAX
Running Revenue
```

---

### Visuals

- KPI Cards
- Monthly Revenue Trend
- YoY Comparison
- Running Total Chart

---

### Objective

Build a professional executive dashboard using Time Intelligence functions.

---

# 📚 Module Summary

In this module, you learned:

✅ Date Tables

✅ Calendar Tables

✅ Time Intelligence Requirements

✅ TOTALYTD()

✅ TOTALMTD()

✅ TOTALQTD()

✅ DATESYTD()

✅ SAMEPERIODLASTYEAR()

✅ DATEADD()

✅ PARALLELPERIOD()

✅ PREVIOUSMONTH()

✅ PREVIOUSYEAR()

✅ Running Totals

✅ YoY Analysis

✅ MoM Analysis

Time Intelligence is one of the most frequently used areas of DAX in business reporting. These concepts are essential for executive dashboards, financial reporting, sales analysis, and performance monitoring.

---

## ⏭️ Next Module

**Module 12: Advanced DAX & Context Manipulation**

Topics Covered:

- CALCULATE()
- FILTER()
- ALL()
- ALLEXCEPT()
- VALUES()
- SELECTEDVALUE()
- Iterator Functions (SUMX, AVERAGEX)
- Context Transition
- Virtual Tables
- Advanced Business Metrics
- Performance Optimization