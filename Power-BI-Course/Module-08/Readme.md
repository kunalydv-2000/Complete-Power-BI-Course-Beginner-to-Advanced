# Module 8: Building Visualizations in Power BI

## 📖 Overview

In the previous module, you learned the theory behind data visualization and dashboard design. In this module, you will apply those principles by creating visualizations in Power BI.

You will learn how to build, format, customize, and interact with Power BI visuals to transform raw data into meaningful insights.

This module focuses on the most commonly used visuals in real-world business reporting and dashboard development.

---

# 🎯 Learning Objectives

After completing this module, you will be able to:

- Create visualizations in Power BI
- Understand the Visualizations Pane
- Build charts and graphs
- Create KPI indicators
- Use tables and matrices
- Apply formatting and customization
- Configure tooltips and labels
- Create interactive reports
- Use slicers and filters effectively

---

# 📚 Table of Contents

1. Introduction to Visualizations
2. Visualizations Pane
3. Building Your First Visual
4. Bar Charts
5. Column Charts
6. Line Charts
7. Area Charts
8. Pie Charts
9. Donut Charts
10. Tables
11. Matrix Visuals
12. Card Visuals
13. KPI Visuals
14. Map Visuals
15. Slicers
16. Filters
17. Tooltips
18. Conditional Formatting
19. Formatting Visuals
20. Report Interactivity
21. Best Practices
22. Key Terminologies
23. Practice Exercises
24. Mini Project
25. Module Summary

---

# 1️⃣ Introduction to Visualizations

## What is a Visualization?

A visualization is a graphical representation of data that helps users:

- Analyze trends
- Compare values
- Identify patterns
- Make decisions

---

## Why Visualizations Matter

Instead of reading thousands of rows:

| Month | Sales |
|---------|---------|
| Jan | ₹100,000 |
| Feb | ₹120,000 |
| Mar | ₹150,000 |

A chart immediately communicates the trend.

---

# 2️⃣ Visualizations Pane

The Visualizations Pane is the primary workspace for creating charts.

---

## Main Sections

### Visual Gallery

Contains available visuals.

Examples:

- Bar Chart
- Line Chart
- Pie Chart
- Table
- Matrix

---

### Build Visual

Assign fields to visual components.

---

### Format Visual

Customize appearance.

---

### Analytics

Add:

- Trend Lines
- Forecasting
- Reference Lines

---

# 3️⃣ Building Your First Visual

## Steps

### Step 1

Load data into Power BI.

---

### Step 2

Select a visual.

Example:

```text
Clustered Column Chart
```

---

### Step 3

Drag fields.

Example:

```text
Category → Axis
Sales → Values
```

---

### Step 4

Power BI generates the chart automatically.

---

# 4️⃣ Bar Charts

## Purpose

Compare categories horizontally.

---

## Example

Sales by Product.

| Product | Sales |
|----------|--------|
| Laptop | ₹50,000 |
| Mobile | ₹35,000 |

---

## Types

### Clustered Bar Chart

Categories displayed side by side.

---

### Stacked Bar Chart

Displays contribution to total.

---

### 100% Stacked Bar Chart

Displays percentage contribution.

---

## Best Use Cases

- Product Comparison
- Regional Comparison
- Ranking Analysis

---

# 5️⃣ Column Charts

## Purpose

Compare categories vertically.

---

## Types

### Clustered Column Chart

Most common.

---

### Stacked Column Chart

Shows category contribution.

---

### 100% Stacked Column Chart

Shows proportional contribution.

---

## Best Use Cases

- Monthly Sales
- Quarterly Revenue
- Category Comparison

---

# 6️⃣ Line Charts

## Purpose

Show trends over time.

---

## Example

Monthly Revenue Trend.

---

## Components

### X-Axis

Time Dimension.

Example:

```text
Month
```

---

### Y-Axis

Measure.

Example:

```text
Revenue
```

---

## Best Use Cases

- Growth Analysis
- Trend Analysis
- Forecasting

---

# 7️⃣ Area Charts

## Purpose

Highlight trends and magnitude.

---

## Example

Monthly Sales Volume.

---

## Advantages

Shows:

- Trend
- Contribution
- Volume

---

## Best Use Cases

- Revenue Growth
- Website Traffic
- Customer Growth

---

# 8️⃣ Pie Charts

## Purpose

Show part-to-whole relationships.

---

## Example

Market Share.

| Brand | Share |
|----------|--------|
| A | 40% |
| B | 30% |
| C | 30% |

---

## Limitations

Avoid using:

- Too many categories
- Small differences

---

## Recommended

Maximum:

```text
5–6 categories
```

---

# 9️⃣ Donut Charts

## Purpose

Alternative to Pie Charts.

---

## Advantages

Can display:

- Total Value
- KPI

in center.

---

## Example

Revenue Distribution by Category.

---

# 🔟 Tables

## Purpose

Display detailed information.

---

## Example

| Customer | Revenue |
|------------|---------|
| Rahul | ₹15,000 |
| Priya | ₹12,000 |

---

## Features

- Sorting
- Filtering
- Drill-through

---

## Best Use Cases

- Transaction Details
- Detailed Reports

---

# 1️⃣1️⃣ Matrix Visuals

## Purpose

Cross-tab analysis.

Similar to Excel Pivot Tables.

---

## Example

| Region | Jan | Feb |
|----------|------|------|
| North | 100 | 120 |
| South | 150 | 180 |

---

## Advantages

Supports:

- Row Hierarchies
- Column Hierarchies
- Drill Down

---

# 1️⃣2️⃣ Card Visuals

## Purpose

Display a single KPI.

---

## Example

```text
Total Revenue

₹5.2M
```

---

## Common KPIs

- Revenue
- Profit
- Customers
- Orders

---

## Best Practices

Use large readable fonts.

---

# 1️⃣3️⃣ KPI Visuals

## Purpose

Track performance against targets.

---

## Components

### Indicator

Current value.

---

### Target

Expected value.

---

### Trend

Historical performance.

---

## Example

```text
Revenue

Current: ₹5M
Target: ₹4.5M

↑ 11%
```

---

# 1️⃣4️⃣ Map Visuals

## Purpose

Visualize geographical data.

---

## Requirements

Location fields:

- Country
- State
- City
- Latitude
- Longitude

---

## Types

### Bubble Map

Displays values as bubbles.

---

### Filled Map

Colors regions.

---

## Example

Sales by State.

---

# 1️⃣5️⃣ Slicers

## What is a Slicer?

A visual filter allowing users to interact with reports.

---

## Example

Filter by:

- Year
- Region
- Product

---

## Types

### Dropdown

Compact format.

---

### List

Displays all values.

---

### Date Slicer

Filters time periods.

---

## Benefits

Improves user experience.

---

# 1️⃣6️⃣ Filters

Power BI supports multiple filter levels.

---

## Visual-Level Filters

Affect one visual.

---

## Page-Level Filters

Affect all visuals on a page.

---

## Report-Level Filters

Affect entire report.

---

## Drillthrough Filters

Navigate to detailed pages.

---

# 1️⃣7️⃣ Tooltips

## What are Tooltips?

Information displayed when hovering over visuals.

---

## Example

Hover over a sales bar:

```text
Sales: ₹50,000
Profit: ₹10,000
```

---

## Benefits

Provides additional details.

---

# 1️⃣8️⃣ Conditional Formatting

## Purpose

Highlight important values automatically.

---

## Example

### Profit

Positive:

```text
Green
```

Negative:

```text
Red
```

---

## Applications

- Tables
- Matrix
- KPIs

---

## Types

### Background Color

### Font Color

### Data Bars

### Icons

---

# 1️⃣9️⃣ Formatting Visuals

Formatting improves readability.

---

## Common Formatting Options

### Titles

Add meaningful titles.

Example:

```text
Monthly Revenue Trend
```

---

### Data Labels

Display values.

---

### Legends

Identify categories.

---

### Colors

Apply consistent themes.

---

### Borders

Use sparingly.

---

### Background

Maintain clean design.

---

# 2️⃣0️⃣ Report Interactivity

Interactive reports improve analysis.

---

## Cross Filtering

Selecting one visual filters others.

---

## Cross Highlighting

Highlights related data.

---

## Drill Down

Move from summary to detail.

Example:

```text
Year
 ↓
Quarter
 ↓
Month
```

---

## Drill Through

Navigate to detailed report pages.

---

# 2️⃣1️⃣ Visualization Best Practices

### Use Appropriate Charts

Choose based on business question.

---

### Avoid Visual Clutter

Limit unnecessary elements.

---

### Use Consistent Colors

Maintain uniformity.

---

### Prioritize KPIs

Place at top.

---

### Keep Layout Clean

Use white space effectively.

---

### Limit Pie Charts

Use only when necessary.

---

# 📌 Key Terminologies

| Term | Definition |
|--------|------------|
| Visual | Graphical representation of data |
| Axis | Horizontal or vertical chart dimension |
| Measure | Numeric value |
| Dimension | Category field |
| KPI | Key Performance Indicator |
| Slicer | Interactive filter |
| Tooltip | Hover information |
| Drill Down | Navigate to lower-level data |
| Cross Filter | Visual interaction |
| Conditional Formatting | Dynamic visual styling |

---

# 📝 Practice Exercises

## Exercise 1

Create:

- Bar Chart
- Column Chart
- Line Chart

Using sales data.

---

## Exercise 2

Create a Card Visual displaying:

```text
Total Revenue
```

---

## Exercise 3

Build a Matrix showing:

```text
Region × Month
```

---

## Exercise 4

Create a Date Slicer.

---

## Exercise 5

Apply Conditional Formatting to a Profit column.

---

# 🎯 Mini Project

## Sales Performance Dashboard

### Requirements

Create:

### KPI Section

- Total Revenue
- Total Profit
- Total Orders

---

### Trend Analysis

- Monthly Sales Trend

---

### Category Analysis

- Revenue by Product Category

---

### Geographic Analysis

- Sales by Region

---

### Filters

- Year
- Region
- Product

---

## Deliverables

1. Interactive Dashboard
2. Formatted Visuals
3. User-Friendly Layout
4. Meaningful Titles

---

# 📚 Module Summary

In this module, you learned:

✅ Visualizations Pane

✅ Bar Charts

✅ Column Charts

✅ Line Charts

✅ Area Charts

✅ Pie & Donut Charts

✅ Tables

✅ Matrix Visuals

✅ Card Visuals

✅ KPI Visuals

✅ Maps

✅ Slicers

✅ Filters

✅ Tooltips

✅ Conditional Formatting

✅ Report Interactivity

These visualization skills form the foundation of professional Power BI reporting. The next module introduces DAX, the calculation engine that powers advanced analytics and business metrics in Power BI.

---

## ⏭️ Next Module

**Module 9: Introduction to DAX (Data Analysis Expressions)**

Topics Covered:

- What is DAX?
- DAX Syntax
- Calculated Columns
- Measures
- Row Context
- Filter Context
- Basic DAX Functions
- Business Calculations
- Best Practices