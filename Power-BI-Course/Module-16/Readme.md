# Module 16: Row-Level Security (RLS) & Data Security

## 📖 Overview

Data is one of an organization's most valuable assets. While dashboards provide insights, not every user should have access to all data.

A Sales Manager may need access to all regions, while a Sales Representative should only see data for their assigned region.

Power BI provides Row-Level Security (RLS) and other security features that enable organizations to control data visibility, enforce governance, and protect sensitive information.

This module covers Power BI security fundamentals, Static RLS, Dynamic RLS, security roles, USERPRINCIPALNAME(), Object-Level Security (OLS), and enterprise security best practices.

---

# 🎯 Learning Objectives

After completing this module, you will be able to:

- Understand Power BI security concepts
- Implement Row-Level Security (RLS)
- Create Static RLS roles
- Create Dynamic RLS solutions
- Use USERPRINCIPALNAME()
- Configure security roles
- Test security implementations
- Understand Object-Level Security (OLS)
- Apply enterprise security best practices

---

# 📚 Table of Contents

1. Introduction to Data Security
2. Why Security Matters
3. Security Layers in Power BI
4. What is Row-Level Security (RLS)?
5. Types of RLS
6. Static RLS
7. Dynamic RLS
8. USERPRINCIPALNAME()
9. Security Mapping Tables
10. Creating Security Roles
11. Testing RLS
12. Publishing RLS Models
13. Object-Level Security (OLS)
14. Workspace Security
15. Data Governance
16. Enterprise Security Best Practices
17. Common Security Mistakes
18. Key Terminologies
19. Practice Exercises
20. Mini Project
21. Module Summary

---

# 1️⃣ Introduction to Data Security

## What is Data Security?

Data Security refers to protecting data from unauthorized access, misuse, or exposure.

---

## Security Objectives

### Confidentiality

Only authorized users can access data.

---

### Integrity

Data remains accurate and unchanged.

---

### Availability

Authorized users can access data when needed.

---

## CIA Triad

```text
Confidentiality
      +
Integrity
      +
Availability
```

---

# 2️⃣ Why Security Matters

Organizations often store:

- Financial Data
- Employee Data
- Customer Data
- Sales Data
- Strategic Information

---

## Example

A sales employee should not view:

- Executive salary information
- Other departments' confidential data
- Restricted financial reports

---

## Consequences of Poor Security

- Data Leaks
- Compliance Violations
- Financial Losses
- Reputational Damage

---

# 3️⃣ Security Layers in Power BI

Power BI security exists at multiple levels.

---

## Layer 1

Workspace Access

Controls who can access content.

---

## Layer 2

App Permissions

Controls who can consume reports.

---

## Layer 3

Row-Level Security

Controls which rows users can see.

---

## Layer 4

Object-Level Security

Controls which tables or columns users can see.

---

## Layer 5

Data Source Security

Database-level protection.

---

# 4️⃣ What is Row-Level Security (RLS)?

## Definition

Row-Level Security (RLS) restricts data visibility at the row level.

---

## Example

Sales Table

| Region | Revenue |
|----------|---------|
| North | ₹100,000 |
| South | ₹150,000 |

---

### User A

Can see:

| Region | Revenue |
|----------|---------|
| North | ₹100,000 |

---

### User B

Can see:

| Region | Revenue |
|----------|---------|
| South | ₹150,000 |

---

## Same Report

Different users see different data.

---

# 5️⃣ Types of RLS

Power BI supports two primary approaches.

---

## Static RLS

Rules are manually defined.

---

## Dynamic RLS

Rules are determined automatically based on the logged-in user.

---

# 6️⃣ Static RLS

## What is Static RLS?

Static RLS uses fixed filters.

---

## Example

Role:

```text
North Region
```

---

### Filter

```DAX
Sales[Region] = "North"
```

---

## Result

Users assigned to this role see only North region data.

---

## Advantages

- Easy to implement
- Simple maintenance

---

## Disadvantages

- Difficult to scale
- Requires many roles

---

# 7️⃣ Dynamic RLS

## What is Dynamic RLS?

Dynamic RLS automatically determines what data users can access.

---

## Example

| Email | Region |
|---------|---------|
| north@company.com | North |
| south@company.com | South |

---

Users see data based on their email address.

---

## Benefits

### Scalable

Supports thousands of users.

---

### Easier Maintenance

Single security model.

---

### Enterprise Standard

Most organizations use Dynamic RLS.

---

# 8️⃣ USERPRINCIPALNAME()

## What is USERPRINCIPALNAME()?

Returns the email address of the currently logged-in user.

---

## Example

```DAX
USERPRINCIPALNAME()
```

---

## Possible Result

```text
john@company.com
```

---

## Why Important?

Foundation of Dynamic RLS.

---

# 9️⃣ Security Mapping Tables

Dynamic RLS usually requires a mapping table.

---

## Example

### Security Table

| Email | Region |
|---------|---------|
| john@company.com | North |
| sara@company.com | South |

---

## Relationship

```text
Security Table
       ↓
Sales Table
```

---

## Dynamic Filter

```DAX
Security[Email] =
USERPRINCIPALNAME()
```

---

## Result

Users automatically see authorized data.

---

# 🔟 Creating Security Roles

## Step 1

Open Power BI Desktop.

---

## Step 2

Navigate to:

```text
Modeling
   ↓
Manage Roles
```

---

## Step 3

Create Role.

Example:

```text
North Region
```

---

## Step 4

Define Filter.

```DAX
Sales[Region] = "North"
```

---

## Step 5

Save Role.

---

# 1️⃣1️⃣ Testing RLS

## Why Test?

Verify users only see authorized data.

---

## Steps

```text
Modeling
   ↓
View As
```

---

## Example

Test:

```text
North Region
```

---

Power BI simulates the selected role.

---

## Best Practice

Test every role before deployment.

---

# 1️⃣2️⃣ Publishing RLS Models

After publishing:

---

## Step 1

Open Power BI Service.

---

## Step 2

Navigate to:

```text
Semantic Model
```

---

## Step 3

Select:

```text
Security
```

---

## Step 4

Assign users to roles.

---

## Example

```text
North Region
```

↓

```text
john@company.com
```

---

## Result

Role becomes active.

---

# 1️⃣3️⃣ Object-Level Security (OLS)

## What is OLS?

Object-Level Security restricts access to:

- Tables
- Columns

---

## Difference

### RLS

Controls rows.

---

### OLS

Controls objects.

---

## Example

Finance Team:

Can view:

```text
Salary
```

---

Sales Team:

Cannot view:

```text
Salary
```

---

## Use Cases

### HR Systems

### Payroll Reports

### Financial Data

---

# 1️⃣4️⃣ Workspace Security

Workspace permissions control content access.

---

## Roles

### Admin

Full control.

---

### Member

Can edit content.

---

### Contributor

Can publish content.

---

### Viewer

Read-only access.

---

## Important

Workspace permissions do not replace RLS.

---

# 1️⃣5️⃣ Data Governance

## What is Governance?

Governance ensures secure and controlled data usage.

---

## Goals

### Consistency

Single source of truth.

---

### Security

Protect sensitive information.

---

### Compliance

Meet regulations.

---

### Accountability

Track usage and access.

---

# 1️⃣6️⃣ Enterprise Security Best Practices

### Use Dynamic RLS

Preferred for scalability.

---

### Implement Least Privilege

Grant only required access.

---

### Test Security Thoroughly

Before deployment.

---

### Document Security Roles

Maintain role definitions.

---

### Monitor Access

Audit user activity.

---

### Use Security Groups

Manage users through groups.

---

### Protect Sensitive Columns

Use OLS where needed.

---

# 1️⃣7️⃣ Common Security Mistakes

### No RLS Implementation

Exposes all data.

---

### Excessive Permissions

Violates least privilege principle.

---

### Hardcoded Security Logic

Difficult to maintain.

---

### Not Testing Roles

May expose unauthorized data.

---

### Ignoring Governance

Creates compliance risks.

---

# 📌 Key Terminologies

| Term | Definition |
|--------|------------|
| RLS | Row-Level Security |
| OLS | Object-Level Security |
| Static RLS | Fixed security filters |
| Dynamic RLS | User-based security |
| USERPRINCIPALNAME() | Returns current user email |
| Security Role | Collection of security rules |
| Security Table | Maps users to permissions |
| Governance | Controlled data management |
| Least Privilege | Minimum required access |
| Compliance | Regulatory adherence |

---

# 📝 Practice Exercises

## Exercise 1

Create a Static RLS role:

```DAX
Sales[Region] = "North"
```

---

## Exercise 2

Test RLS using:

```text
View As
```

---

## Exercise 3

Create a Security Mapping Table.

---

## Exercise 4

Implement Dynamic RLS using:

```DAX
USERPRINCIPALNAME()
```

---

## Exercise 5

Compare:

- RLS
- OLS

---

# 🎯 Mini Project

## Secure Sales Analytics Dashboard

### Dataset

Sales Data

| Region | Revenue |
|----------|---------|

---

### Security Table

| Email | Region |
|---------|---------|

---

### Requirements

#### Dynamic RLS

Users see only assigned region.

---

#### Roles

- Sales Manager
- Sales Representative

---

#### Testing

Verify multiple users.

---

### Deliverables

1. Security Mapping Table
2. Dynamic RLS Configuration
3. Role Documentation
4. Security Testing Results

---

# 📚 Module Summary

In this module, you learned:

✅ Data Security Fundamentals

✅ Power BI Security Layers

✅ Row-Level Security (RLS)

✅ Static RLS

✅ Dynamic RLS

✅ USERPRINCIPALNAME()

✅ Security Mapping Tables

✅ Role Management

✅ Testing Security

✅ Object-Level Security (OLS)

✅ Workspace Security

✅ Data Governance

✅ Enterprise Security Best Practices

Security is a critical component of enterprise Power BI solutions. Proper implementation of RLS and governance ensures users access only the data they are authorized to see while maintaining compliance and protecting sensitive business information.

---

## ⏭️ Next Module

**Module 17: Power BI Performance Optimization**

Topics Covered:

- Performance Fundamentals
- Performance Analyzer
- Query Optimization
- DAX Optimization
- Data Model Optimization
- Storage Optimization
- Star Schema Performance
- Incremental Refresh
- Aggregations
- Enterprise Performance Best Practices