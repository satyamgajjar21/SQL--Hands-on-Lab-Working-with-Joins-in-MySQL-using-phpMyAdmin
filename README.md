# Hands-on Lab: Working with Joins in MySQL using phpMyAdmin

This lab covers SQL JOIN operations to combine data from multiple tables in a MySQL database using the phpMyAdmin interface.

---

## Table of Contents

- [Overview](#overview)  
- [Objectives](#objectives)  
- [Software and Database](#software-and-database)  
- [Setup Instructions](#setup-instructions)  
- [Types of Joins](#types-of-joins)  
- [Example Queries](#example-queries)  
- [Practice Problems](#practice-problems)  
- [Conclusion](#conclusion)  
- [Authors](#authors)

---

## Overview

A **SQL JOIN** clause combines rows from two or more tables based on a related column. This lab explains how to use various JOIN types to retrieve combined data efficiently.

---

## Objectives

By the end of this lab, you will be able to:

- Write SQL queries using **INNER JOIN**  
- Write SQL queries using **OUTER JOINs** (LEFT, RIGHT, FULL OUTER)  

---

## Software and Database

- **Software:** MySQL with phpMyAdmin interface  
- **Database:** Sample HR database with tables:  
  - `EMPLOYEES`  
  - `JOB_HISTORY`  
  - `JOBS`  
  - `DEPARTMENTS`  
  - `LOCATIONS`  

---

## Setup Instructions

1. Open the phpMyAdmin interface in the Skills Network Cloud IDE.  
2. Create a blank database named `HR`.  
3. Execute the `Script_Create_Tables.sql` script to create required tables.  
4. Import CSV files into corresponding tables:  
   - `Departments.csv`  
   - `Jobs.csv`  
   - `JobsHistory.csv`  
   - `Locations.csv`  
   - `Employees.csv`  

---

## Types of Joins

- **INNER JOIN:** Returns rows with matching values in both tables.  
- **LEFT JOIN:** Returns all rows from the left table and matching rows from the right table.  
- **RIGHT JOIN:** Returns all rows from the right table and matching rows from the left table.  
- **FULL OUTER JOIN:** Returns all rows when there is a match in either table. (Implemented in MySQL as a UNION of LEFT and RIGHT JOINs.)

---

## Example Queries

1. **Retrieve names and job start dates for employees in department 5:**

```sql
SELECT E.F_NAME, E.L_NAME, JH.START_DATE
FROM EMPLOYEES AS E
INNER JOIN JOB_HISTORY AS JH
ON E.EMP_ID = JH.EMPL_ID
WHERE E.DEP_ID = '5';
