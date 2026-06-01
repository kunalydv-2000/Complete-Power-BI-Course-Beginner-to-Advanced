# Module 15: Power BI Service & Cloud Reporting

## 📖 Overview

Creating reports in Power BI Desktop is only part of the Business Intelligence lifecycle. Organizations need a way to publish, share, secure, collaborate on, and refresh reports for business users.

This is where Power BI Service comes in.

Power BI Service is Microsoft's cloud-based Business Intelligence platform that enables report publishing, dashboard creation, collaboration, scheduled refreshes, governance, and enterprise-scale analytics.

This module covers the complete Power BI cloud ecosystem, including Workspaces, Dashboards, Apps, Data Refresh, Sharing, Security, and Deployment Pipelines.

---

# 🎯 Learning Objectives

After completing this module, you will be able to:

- Understand Power BI Service architecture
- Publish reports to the cloud
- Create and manage workspaces
- Build dashboards in Power BI Service
- Configure scheduled refreshes
- Share reports securely
- Understand Power BI Apps
- Manage permissions and access
- Understand deployment pipelines
- Learn Power BI governance concepts

---

# 📚 Table of Contents

1. Introduction to Power BI Service
2. Power BI Architecture
3. Power BI Desktop vs Service
4. Power BI Workspaces
5. Workspace Roles
6. Publishing Reports
7. Datasets & Semantic Models
8. Dashboards in Power BI Service
9. Tiles & Dashboard Design
10. Power BI Apps
11. Data Refresh
12. Gateways
13. Sharing Reports
14. Permissions & Security
15. Row-Level Security (Overview)
16. Collaboration Features
17. Deployment Pipelines
18. Governance & Administration
19. Licensing Overview
20. Best Practices
21. Common Mistakes
22. Key Terminologies
23. Practice Exercises
24. Mini Project
25. Module Summary

---

# 1️⃣ Introduction to Power BI Service

## What is Power BI Service?

Power BI Service is the cloud-based platform used to:

- Publish reports
- Share dashboards
- Collaborate with teams
- Schedule refreshes
- Manage security
- Distribute analytics

---

## Access Method

Power BI Service is accessed through a web browser.

---

## Primary Purpose

Transform personal reports into enterprise reporting solutions.

---

# 2️⃣ Power BI Architecture

## High-Level Architecture

```text
Data Sources
      ↓
Power BI Desktop
      ↓
Power BI Service
      ↓
Users
```

---

## Data Flow

```text
Source Data
      ↓
Transform Data
      ↓
Build Reports
      ↓
Publish
      ↓
Share
```

---

## Components

### Power BI Desktop

Development environment.

---

### Power BI Service

Cloud platform.

---

### Power BI Mobile

Report consumption.

---

### Gateway

On-premise connectivity.

---

# 3️⃣ Power BI Desktop vs Service

| Feature | Desktop | Service |
|----------|----------|----------|
| Build Reports | Yes | Limited |
| Data Modeling | Yes | No |
| DAX Development | Yes | No |
| Publish Reports | Yes | No |
| Share Reports | No | Yes |
| Schedule Refresh | No | Yes |
| Collaboration | No | Yes |
| Dashboard Creation | Limited | Yes |

---

## Simple Rule

Desktop = Development

Service = Distribution

---

# 4️⃣ Power BI Workspaces

## What is a Workspace?

A Workspace is a collaborative environment where reports, dashboards, datasets, and apps are stored.

---

## Purpose

Workspaces help teams:

- Collaborate
- Organize content
- Manage permissions

---

## Example

Sales Team Workspace

Contains:

- Sales Reports
- Sales Dashboards
- Sales Datasets

---

# 5️⃣ Workspace Roles

Power BI provides multiple workspace roles.

---

## Admin

Full control.

Can:

- Add users
- Remove users
- Manage permissions

---

## Member

Can edit content.

---

## Contributor

Can publish and update content.

---

## Viewer

Can only view content.

---

## Role Hierarchy

```text
Admin
 ↓
Member
 ↓
Contributor
 ↓
Viewer
```

---

# 6️⃣ Publishing Reports

## What is Publishing?

Publishing uploads a Power BI report from Desktop to Power BI Service.

---

## Steps

### Step 1

Open Power BI Desktop.

---

### Step 2

Save Report.

---

### Step 3

Select:

```text
Home → Publish
```

---

### Step 4

Choose Workspace.

---

### Step 5

Upload Report.

---

## Result

Report becomes available in Power BI Service.

---

# 7️⃣ Datasets & Semantic Models

## What is a Dataset?

A Dataset contains:

- Imported Data
- Relationships
- Measures
- Calculations

---

## Modern Terminology

Microsoft increasingly refers to datasets as:

```text
Semantic Models
```

---

## Why Important?

Reports connect to semantic models.

---

## Architecture

```text
Semantic Model
       ↓
Multiple Reports
```

---

## Benefits

Single source of truth.

---

# 8️⃣ Dashboards in Power BI Service

## What is a Dashboard?

A dashboard is a collection of visual tiles from one or more reports.

---

## Characteristics

- Single Page
- Interactive
- High-Level Overview

---

## Example

Executive Dashboard

Contains:

- Revenue KPI
- Profit KPI
- Sales Trend
- Top Products

---

# 9️⃣ Tiles & Dashboard Design

## What is a Tile?

A tile is an individual visual pinned to a dashboard.

---

## Examples

- KPI Card
- Line Chart
- Map
- Table

---

## Pinning a Visual

```text
Report
   ↓
Pin Visual
   ↓
Dashboard
```

---

## Benefits

Allows consolidation of insights from multiple reports.

---

# 🔟 Power BI Apps

## What is a Power BI App?

An App is a packaged collection of:

- Reports
- Dashboards
- Semantic Models

Distributed to users.

---

## Benefits

### Centralized Distribution

One location for content.

---

### Controlled Access

Users consume without editing.

---

### Professional Deployment

Enterprise-friendly.

---

# 1️⃣1️⃣ Data Refresh

## Why Refresh?

Source data changes continuously.

Reports must remain current.

---

## Types of Refresh

### Manual Refresh

User initiates refresh.

---

### Scheduled Refresh

Automatic updates.

Examples:

```text
Daily
Hourly
Weekly
```

---

### Incremental Refresh

Refreshes only changed data.

---

## Benefits

- Faster updates
- Better performance

---

# 1️⃣2️⃣ Gateways

## What is a Gateway?

A gateway securely connects on-premise systems to Power BI Service.

---

## Why Needed?

Power BI Service cannot directly access internal databases.

---

## Types

### Personal Gateway

Single-user use.

---

### Standard Gateway

Enterprise use.

Multiple users supported.

---

## Architecture

```text
SQL Server
      ↓
Gateway
      ↓
Power BI Service
```

---

# 1️⃣3️⃣ Sharing Reports

## Sharing Options

### Direct Sharing

Share report with users.

---

### Workspace Access

Users access workspace content.

---

### App Distribution

Publish apps to groups.

---

### Embedded Analytics

Integrate reports into applications.

---

# 1️⃣4️⃣ Permissions & Security

## Why Security Matters

Business reports often contain sensitive information.

---

## Permission Types

### View

Read-only access.

---

### Build

Create reports using datasets.

---

### Edit

Modify content.

---

### Reshare

Allow sharing with others.

---

## Principle

Least Privilege Access

Grant only necessary permissions.

---

# 1️⃣5️⃣ Row-Level Security (Overview)

## What is RLS?

Row-Level Security restricts data visibility based on users.

---

## Example

### Manager

Sees all regions.

---

### Salesperson

Sees only assigned region.

---

## Benefits

Protects sensitive data.

---

## Detailed Implementation

Covered in Module 16.

---

# 1️⃣6️⃣ Collaboration Features

Power BI Service supports collaboration.

---

## Comments

Users discuss report insights.

---

## Subscriptions

Receive reports via email.

---

## Alerts

Notifications when KPIs exceed thresholds.

---

## Teams Integration

Integrates with Microsoft Teams.

---

# 1️⃣7️⃣ Deployment Pipelines

## What is a Deployment Pipeline?

A deployment pipeline manages report promotion across environments.

---

## Stages

```text
Development
      ↓
Test
      ↓
Production
```

---

## Benefits

### Quality Assurance

Test before release.

---

### Controlled Deployment

Reduces production risks.

---

### Enterprise Governance

Supports large teams.

---

# 1️⃣8️⃣ Governance & Administration

## Governance

Governance ensures Power BI usage follows organizational standards.

---

## Areas

### Security

Access control.

---

### Compliance

Regulatory requirements.

---

### Data Quality

Reliable reporting.

---

### Monitoring

Usage tracking.

---

## Administrative Responsibilities

- User Management
- Capacity Management
- Audit Logs
- Workspace Governance

---

# 1️⃣9️⃣ Licensing Overview

Power BI licensing affects sharing capabilities.

---

## Power BI Free

Individual use.

---

## Power BI Pro

Collaboration and sharing.

---

## Power BI Premium Per User (PPU)

Advanced enterprise features.

---

## Power BI Premium Capacity

Large-scale enterprise deployment.

---

## General Rule

Most organizations use:

```text
Pro
```

or

```text
Premium
```

---

# 2️⃣0️⃣ Best Practices

### Use Workspaces Properly

Separate teams and projects.

---

### Schedule Refresh Carefully

Avoid unnecessary refresh frequency.

---

### Use Apps for Distribution

Provides better governance.

---

### Implement Security Early

Protect sensitive data.

---

### Monitor Usage

Identify adoption trends.

---

# 2️⃣1️⃣ Common Mistakes

### Sharing Without Security Planning

Creates risks.

---

### Excessive Workspace Creation

Causes management issues.

---

### Ignoring Refresh Failures

Leads to stale reports.

---

### No Governance Strategy

Creates reporting chaos.

---

### Publishing Directly to Production

Increases risk.

---

# 📌 Key Terminologies

| Term | Definition |
|--------|------------|
| Power BI Service | Cloud-based BI platform |
| Workspace | Collaboration environment |
| Dashboard | Collection of visual tiles |
| Tile | Individual dashboard visual |
| Semantic Model | Dataset containing business logic |
| App | Packaged reporting solution |
| Gateway | Secure on-premise connector |
| Refresh | Updating data |
| Deployment Pipeline | Environment promotion process |
| RLS | Row-Level Security |

---

# 📝 Practice Exercises

## Exercise 1

Create a Workspace.

---

## Exercise 2

Publish a report from Power BI Desktop.

---

## Exercise 3

Create a Dashboard using pinned visuals.

---

## Exercise 4

Schedule a data refresh.

---

## Exercise 5

Research Power BI licensing options.

---

# 🎯 Mini Project

## Cloud Reporting Solution

### Objective

Publish and distribute a Sales Dashboard.

---

### Tasks

#### Workspace

Create:

```text
Sales Analytics Workspace
```

---

#### Publish

Upload report.

---

#### Dashboard

Pin:

- Revenue KPI
- Profit KPI
- Sales Trend

---

#### App

Create:

```text
Sales Analytics App
```

---

#### Security

Assign:

- Viewer
- Contributor

roles.

---

### Deliverables

1. Published Report
2. Dashboard
3. Workspace Setup
4. App Distribution Plan

---

# 📚 Module Summary

In this module, you learned:

✅ Power BI Service Architecture

✅ Workspaces

✅ Workspace Roles

✅ Publishing Reports

✅ Semantic Models

✅ Dashboards

✅ Tiles

✅ Power BI Apps

✅ Data Refresh

✅ Gateways

✅ Sharing & Collaboration

✅ Security & Permissions

✅ Deployment Pipelines

✅ Governance & Administration

Power BI Service transforms standalone reports into enterprise reporting solutions. Understanding the Service layer is essential for sharing insights, managing security, and supporting business users at scale.

---

## ⏭️ Next Module

**Module 16: Row-Level Security (RLS) & Data Security**

Topics Covered:

- Data Security Fundamentals
- Row-Level Security (RLS)
- Static RLS
- Dynamic RLS
- USERPRINCIPALNAME()
- Security Roles
- Testing Security
- Object-Level Security (OLS)
- Data Governance
- Enterprise Security Best Practices