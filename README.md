
📊 ScienceQtech Employee Performance Mapping
🧠 Project Overview
This project focuses on analyzing employee data for ScienceQtech, a dynamic startup specializing in data science domains such as fraud detection, market basket analysis, self-driving cars, supply chain optimization, early lung cancer detection, customer sentiment analysis, and drug discovery.

As part of the annual appraisal cycle, the HR department requires detailed reports on employee details, performance metrics, and project involvements. The objective is to extract specific data based on varying requirements to facilitate informed decision-making for performance mapping.

🎯 Objectives
Structure and format the data within a MySQL database.

Generate an ER diagram for clear visualization of relationships.

Execute SQL queries to retrieve and analyze key employee data.

Calculate bonuses based on performance ratings and salaries.

Ensure job profiles align with organizational standards.

Provide insights to assist the HR department in finalizing employee performance mapping.

🗂️ Dataset Description
The project utilizes three primary datasets:

emp_record_table.csv: Contains comprehensive employee information, including:

EMP_ID: Employee ID

FIRST_NAME: First name

LAST_NAME: Last name

GENDER: Gender

ROLE: Job role

DEPT: Department

EXP: Years of experience

COUNTRY: Country of residence

CONTINENT: Continent of residence

SALARY: Salary

EMP_RATING: Performance rating

MANAGER_ID: Manager's employee ID

PROJ_ID: Project ID assigned

proj_table.csv: Details about projects, including:

PROJECT_ID: Project ID

PROJ_Name: Project name

DOMAIN: Project domain

START_DATE: Project start date

CLOSURE_DATE: Project end date

DEV_QTR: Development quarter

STATUS: Current status

data_science_team.csv: Information about employees in the Data Science team, including:

EMP_ID: Employee ID

FIRST_NAME: First name

LAST_NAME: Last name

GENDER: Gender

ROLE: Job role

DEPT: Department

EXP: Years of experience

COUNTRY: Country of residence

CONTINENT: Continent of residence

🛠️ Tools & Technologies
MySQL Workbench 8.0: For database design and management.

SQL: For querying and data manipulation.
GitHub

🔍 Methodology
Database Setup:

Created a database named employee.

Imported the provided CSV files into corresponding tables.

Established relationships between tables to maintain data integrity.

Data Analysis:

Executed SQL queries to fetch employee details, categorize performance ratings, and identify top performers.

Calculated maximum salaries across roles and designed bonus structures based on performance ratings.

Ensured job profiles aligned with organizational standards by mapping roles based on experience levels.

Advanced SQL Implementations:

Utilized stored procedures, functions, views, and indexing to optimize data retrieval and analysis.

📈 Key Findings
Identified top-performing employees based on performance ratings.

Calculated bonuses to determine additional expenses.

Ensured all job roles met the organization's profile standards.

Provided insights to assist the HR department in finalizing employee performance mapping.
