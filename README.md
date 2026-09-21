# SQL Mastery: From Queries to Database Design

A practical SQL and database development guide covering fundamental queries, advanced SQL techniques, performance optimization, and database modeling through an e-commerce database.

## Overview

This project demonstrates how SQL can be used to retrieve, analyze, optimize, and structure relational data.

The examples are built around three core entities:

* **Customers** — customer information and locations
* **Products** — product names and prices
* **Sales** — customer transactions and sales amounts 

The material progresses from straightforward SQL queries to more advanced database concepts such as CTEs, window functions, stored procedures, indexing, normalization, star schemas, and denormalization.

---

## Contents

### 1. Core SQL

The first section introduces essential SQL operations, including:

* Filtering records with `WHERE`
* Joining related tables
* Aggregating data with `SUM()`
* Grouping results with `GROUP BY`
* Sorting with `ORDER BY`
* Removing duplicates with `DISTINCT`
* Limiting query results with `LIMIT`

Examples include finding customers in Nairobi, displaying customers and their products, calculating total customer spending, and finding the highest-spending customers.  

---

### 2. Advanced SQL

The advanced section explores techniques for more complex data analysis:

* **Common Table Expressions (CTEs)**
* **Window functions**
* **Ranking**
* **Views**
* **Stored procedures**
* **Recursive CTEs**

For example, customer totals are calculated with a CTE and compared against the average customer sales value. 

Product performance is also ranked using the `RANK()` window function. 

---

### 3. Query Optimization

This section focuses on improving database performance.

Topics include:

* Creating indexes
* Selecting only required columns
* Avoiding unnecessary `SELECT *`
* Using `EXPLAIN` to inspect query execution

For example, an index can be created on `total_sales` to improve filtering:

```sql
CREATE INDEX idx_sales_total
ON sales(total_sales);
```

The guide also demonstrates using `EXPLAIN` to evaluate queries filtering customers by location.  

---

### 4. Database Design

The final section moves beyond querying into database architecture.

It covers:

* **Third Normal Form (3NF)**
* Primary keys
* Foreign keys
* Fact tables
* Dimension tables
* Star schema design
* Denormalization

The normalized design separates customer, product, and sales information into related tables. 

The star-schema section introduces:

```text
                 dim_customer
                      │
                      │
dim_location ─── fact_sales ─── dim_product
```

This structure is designed for analytical workloads and supports fast aggregations. 

---

## Database Structure

The main relational model consists of:

```text
customer_info
├── customer_id
├── full_name
└── location

products
├── product_id
├── product_name
└── price

sales
├── sales_id
├── customer_id
├── product_id
└── total_sales
```

The sales table connects customers and products through foreign keys in the redesigned schema. 

---

## Technologies & Concepts

| Area               | Technologies / Concepts |
| ------------------ | ----------------------- |
| Querying           | SQL                     |
| Filtering          | `WHERE`                 |
| Relationships      | `JOIN`                  |
| Aggregation        | `SUM()`, `AVG()`        |
| Grouping           | `GROUP BY`              |
| Sorting            | `ORDER BY`              |
| Advanced SQL       | CTEs                    |
| Analytics          | Window Functions        |
| Reusability        | Views                   |
| Automation         | Stored Procedures       |
| Recursion          | Recursive CTEs          |
| Performance        | Indexes, `EXPLAIN`      |
| Data Modeling      | 3NF                     |
| Analytics Modeling | Star Schema             |
| Reporting          | Denormalization         |

---

## Suggested Project Structure

```text
sql-database-project/
│
├── README.md
│
├── schema/
│   └── schema.sql
│
├── data/
│   └── data.sql
│
├── queries/
│   ├── basic.sql
│   ├── advanced.sql
│   ├── optimization.sql
│   └── database_design.sql
│
└── results/
    └── query-results.md
```

---

## What This Project Demonstrates

By working through this project, the following SQL and database development areas are demonstrated:

* Writing relational database queries
* Retrieving data from multiple tables
* Performing sales analysis
* Creating reusable SQL structures
* Ranking and comparing records
* Building cumulative calculations
* Improving query performance
* Designing normalized relational databases
* Building analytical star schemas
* Understanding reporting-oriented denormalization

---

## Database Compatibility

The material contains SQL syntax from different database environments. In particular, the stored procedure section explicitly specifies **MySQL**. 

Some table definitions use `SERIAL`, so SQL syntax may need to be adjusted depending on the database system being used.

---

## Key Takeaway

This project provides a progression from **writing SQL queries** to **designing and optimizing databases**:

```text
Basic Queries
     ↓
Joins & Aggregations
     ↓
Advanced SQL
     ↓
Query Optimization
     ↓
Database Normalization
     ↓
Star Schema
     ↓
Reporting & Denormalization
```

It can therefore serve as a practical reference for SQL querying, data analysis, performance tuning and relational database design.
