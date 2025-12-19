# ScienceQtech Employee Performance Mapping

## Overview

**ScienceQtech Employee Performance Mapping** is a SQL-centric project that structures and analyzes employee data to support the HR department in annual performance appraisals. The focus is on transforming raw datasets into a relational database, extracting insights via SQL queries, and generating performance metrics to aid strategic HR decision-making. 

---

## Table of Contents

- [Objectives](#objectives)
- [Dataset](#dataset)
- [Tools & Technologies](#tools-technologies)
- [Methodology](#methodology)
- [Key Findings](#key-findings)
- [Repository Structure](#repository-structure)


---

## Objectives

The primary goals of this project are:

- Structure and normalize employee data within a MySQL database.
- Create an Entity-Relationship (ER) diagram to clarify table relationships.
- Write SQL queries to retrieve and analyze employee performance data.
- Calculate performance-based bonuses using ratings and salaries.
- Validate job profiles relative to experience levels.
- Generate actionable insights for HR performance mapping and appraisal processes. 

---

## Dataset

This project uses the following CSV datasets:

### `emp_record_table.csv`

Contains core employee information:

| Column       | Description                     |
|--------------|---------------------------------|
| EMP_ID       | Employee ID                    |
| FIRST_NAME   | First Name                    |
| LAST_NAME    | Last Name                     |
| GENDER       | Gender                         |
| ROLE         | Job Role                      |
| DEPT         | Department                    |
| EXP          | Years of Experience          |
| COUNTRY      | Country of Residence         |
| CONTINENT    | Continent of Residence       |
| SALARY       | Salary                        |
| EMP_RATING   | Performance Rating           |
| MANAGER_ID   | Manager’s Employee ID        |
| PROJ_ID      | Project ID Assigned          |

### `proj_table.csv`

Details of projects:

| Column        | Description                  |
|---------------|------------------------------|
| PROJECT_ID   | Project ID                 |
| PROJ_NAME    | Project Name              |
| DOMAIN       | Project Domain             |
| START_DATE   | Project Start Date         |
| CLOSURE_DATE | Project End Date           |
| DEV_QTR      | Development Quarter       |
| STATUS       | Current Status            |

### `data_science_team.csv`

Contains subset details of employees in the Data Science team:

| Column     | Description              |
|------------|--------------------------|
| EMP_ID     | Employee ID             |
| FIRST_NAME | First Name             |
| LAST_NAME  | Last Name              |
| GENDER     | Gender                 |
| ROLE       | Job Role              |
| DEPT       | Department            |
| EXP        | Experience (Years)   |
| COUNTRY    | Country              |
| CONTINENT  | Continent            | 

---

## Tools & Technologies

This project leverages the following:

- **MySQL Workbench 8.0** – Database design, ER diagram creation, and query execution.
- **SQL** – Data manipulation and analysis through structured queries.

---

## Methodology

### Database Setup

- Created a database named `employee`.
- Imported CSV datasets into relational tables.
- Defined table relationships and primary/foreign keys to ensure referential integrity. 

### Analysis & Querying

- Executed SQL queries to extract detailed employee metrics.
- Grouped employees by performance ratings, roles, and departments.
- Calculated max/min salaries and performance-based bonuses.
- Mapped job profiles according to predefined experience tiers using SQL functions and stored procedures. 

### Optimization

- Created views, stored procedures, and functions for reusable logic.
- Implemented indexing to optimize query performance.

---

## Key Findings

- **Top Performers Identified:** Employees with the highest performance ratings were flagged for recognition.
- **Bonus Calculations:** Quantified bonus allocations using salary and performance ratings.
- **Role Validation:** Validated that job roles align with experience and organizational standards.
- **HR Insights:** Prepared insights to assist HR in appraisal, promotion, and compensation decisions.

---


### Clone the Repository

```bash
git clone https://github.com/yourusername/ScienceQtech-Employee-Performance-Mapping.git
```
## Set Up MySQL Database

### 1. Install and Launch MySQL Workbench

- Download and install **MySQL Workbench 8.0** if not already installed.
- Open MySQL Workbench and connect to your MySQL server instance.

### 2. Create the Database

In the MySQL query editor, create a new database for this project:

```sql
CREATE DATABASE employee;
USE employee;
```
### 3. Import CSV Files into MySQL

Use the **Table Data Import Wizard** in MySQL Workbench to load each CSV dataset into its respective table:

1. In the **Schemas** panel, right-click the `employee` database and select **Table Data Import Wizard**. 
2. Browse and select each CSV file (`emp_record_table.csv`, `proj_table.csv`, and `data_science_team.csv`) one by one. 
3. Follow the wizard steps to map CSV fields to table columns and configure appropriate data types.
4. Click **Finish** to complete the import. 

**Tip:** Ensure the first row of each CSV contains header column names that match your intended table schema. 

---

### 4. Define Table Relationships

Once the tables are imported:

- Establish primary keys such as `EMP_ID` and `PROJECT_ID` for each table.  
- Add foreign key relationships (for example, link `emp_record_table.PROJ_ID` to `proj_table.PROJECT_ID`) to enforce referential integrity.

---

## Execute Analysis Queries

Use the MySQL editor to run SQL queries that:

- Fetch employee performance data using `JOIN` operations across tables.  
- Aggregate performance by roles, departments, and projects.  
- Compute statistics such as highest salaries and top performers.  
- Create views or stored procedures for reusable logic.

Example SQL snippet:

```sql
SELECT e.EMP_ID,
       CONCAT(e.FIRST_NAME, ' ', e.LAST_NAME) AS Employee,
       e.ROLE,
       e.DEPT,
       e.SALARY,
       e.EMP_RATING
FROM emp_record_table e
JOIN proj_table p ON e.PROJ_ID = p.PROJECT_ID;
```

## Bonus Calculation Logic

To determine performance-based bonuses:

1. Define rating thresholds and corresponding bonus percentages.
2. Use SQL formulas or stored procedures to calculate bonus values based on salary and performance rating.

Example:

```sql
UPDATE emp_record_table
SET BONUS = CASE
               WHEN EMP_RATING = 'A' THEN SALARY * 0.10
               WHEN EMP_RATING = 'B' THEN SALARY * 0.07
               WHEN EMP_RATING = 'C' THEN SALARY * 0.05
               ELSE 0
            END;
```
This ensures employees are rewarded proportionally to their performance and base compensation.

### Optimize and Extend

- To enhance database performance and usability:

- Create indexes on frequently queried fields such as ROLE and DEPT.

- Define views for aggregated insights (e.g., top performers).

- Use stored procedures/functions to encapsulate complex logic and improve reusability. 


### Insights & Reporting

- With the data loaded and queries defined, generate reports such as:

- Top-performing employees by rating and department.

- Department salary distributions.

- Project involvement summaries across performance tiers.

## These insights assist HR in appraisal decisions, compensation planning, and organizational alignment.


