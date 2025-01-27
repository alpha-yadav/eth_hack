# 5. Data Manipulation

Data manipulation is the process of altering, transforming, or reorganizing data to make it more useful and insightful. This involves a range of techniques and operations, depending on the type of data and the desired outcome.  Here's a breakdown of key aspects:

**Key Techniques and Operations:**

* **Filtering:** Selecting specific rows or columns based on certain criteria.  For example, selecting only customers from a specific region or transactions above a certain value.

* **Sorting:** Arranging data in a specific order based on one or more columns. This could be ascending (A-Z, smallest to largest) or descending (Z-A, largest to smallest).

* **Aggregation:** Summarizing data using functions like `SUM`, `AVERAGE`, `COUNT`, `MIN`, `MAX`, etc.  This allows for the calculation of totals, averages, and other statistical measures.

* **Joining/Merging:** Combining data from multiple tables or datasets based on common fields.  Common types include inner joins (only matching rows), outer joins (all rows from at least one table), and left/right joins.

* **Transformation:** Changing the format or values of data. This could involve:
    * **Renaming columns:** Changing column names for clarity.
    * **Data type conversion:** Converting data from one type to another (e.g., string to number).
    * **Creating new columns:** Calculating new values based on existing columns (e.g., adding a column for total price by multiplying quantity and unit price).
    * **Handling missing values:** Imputing missing data or removing rows/columns with missing values.
    * **Data cleaning:** Correcting inconsistencies, errors, and outliers in the data.
    * **Data standardization/normalization:** Transforming data to a common scale or format.

* **Reshaping:** Changing the structure of the data. This could include:
    * **Pivoting:** Restructuring data from a long format to a wide format (or vice versa).
    * **Melting/Unpivoting:** Converting wide data to long format, useful for analyzing data with many columns representing different variables.

**Tools and Technologies:**

Data manipulation is performed using various tools and technologies, including:

* **Spreadsheets (Excel, Google Sheets):** Suitable for smaller datasets and simpler manipulations.
* **Programming Languages (Python, R):** Powerful for complex data manipulation tasks, using libraries like Pandas (Python) and dplyr (R).
* **Database Management Systems (SQL, NoSQL):** Used for managing and manipulating large datasets stored in databases.
* **Data manipulation tools (Tableau, Power BI):** Offer visual interfaces for data cleaning, transformation, and exploration.


**Example (Python with Pandas):**

Let's say we have a Pandas DataFrame called `df` with information about sales:

```python
import pandas as pd

data = {'Region': ['North', 'South', 'North', 'East'],
        'Sales': [100, 150, 200, 80],
        'Profit': [20, 30, 40, 16]}
df = pd.DataFrame(data)

# Filtering: Selecting sales from the North region
north_sales = df[df['Region'] == 'North']

# Aggregation: Calculating total sales
total_sales = df['Sales'].sum()

# Creating a new column: Calculating profit margin
df['Profit Margin'] = (df['Profit'] / df['Sales']) * 100

print(north_sales)
print(total_sales)
print(df)
```

This example demonstrates basic filtering, aggregation, and creating a new column using Pandas.  More complex manipulations can be achieved with more advanced Pandas functions and other libraries.  The choice of tools and techniques depends on the specific data manipulation task and the scale of the data.

# 1. Intro to SQL

SQL (Structured Query Language) is the standard language for managing and manipulating databases.  There's no single "Intro to SQL in SQL," as SQL itself is the language used to interact with databases, not a language that *contains* introductions.  However, we can use SQL to demonstrate introductory concepts.

Let's assume we have a simple database table called `Customers` with the following columns:

* `CustomerID` (INT, primary key)
* `FirstName` (VARCHAR)
* `LastName` (VARCHAR)
* `City` (VARCHAR)
* `Country` (VARCHAR)


Here's how we'd demonstrate some basic SQL commands:

**1. Creating a Table:**

```sql
CREATE TABLE Customers (
    CustomerID INT PRIMARY KEY,
    FirstName VARCHAR(255),
    LastName VARCHAR(255),
    City VARCHAR(255),
    Country VARCHAR(255)
);
```

This creates a table named `Customers` with the specified columns and data types.  `PRIMARY KEY` indicates that `CustomerID` uniquely identifies each row.

**2. Inserting Data:**

```sql
INSERT INTO Customers (CustomerID, FirstName, LastName, City, Country) VALUES
(1, 'John', 'Doe', 'New York', 'USA'),
(2, 'Jane', 'Smith', 'London', 'UK'),
(3, 'David', 'Lee', 'Paris', 'France');
```

This adds three new rows to the `Customers` table.

**3. Selecting Data (Retrieving Information):**

```sql
SELECT * FROM Customers;
```

This retrieves all columns (`*`) from all rows in the `Customers` table.

```sql
SELECT FirstName, LastName FROM Customers;
```

This retrieves only the `FirstName` and `LastName` columns from all rows.

```sql
SELECT * FROM Customers WHERE Country = 'USA';
```

This retrieves all columns from rows where the `Country` is 'USA'.

**4. Updating Data:**

```sql
UPDATE Customers SET City = 'Los Angeles' WHERE CustomerID = 1;
```

This changes the `City` to 'Los Angeles' for the customer with `CustomerID` 1.

**5. Deleting Data:**

```sql
DELETE FROM Customers WHERE CustomerID = 3;
```

This deletes the row with `CustomerID` 3.


**Important Notes:**

* These commands are executed within a specific Database Management System (DBMS) like MySQL, PostgreSQL, SQL Server, Oracle, etc.  The exact syntax might have minor variations depending on the DBMS.
* Before running these commands, you'll need to connect to a database and create a database to store the `Customers` table.  The methods for doing this vary depending on your chosen DBMS.

This is a very basic introduction.  SQL has many more commands and features, including joins, subqueries, aggregate functions (SUM, AVG, COUNT, etc.), and more advanced data manipulation techniques.  To learn more, explore tutorials and documentation specific to your chosen DBMS.

## - Definition of SQL

There isn't a single, universally agreed-upon SQL statement to define SQL itself.  SQL is a *language*, not a single data object that can be described within SQL.  You'd need to use descriptive text within a SQL comment to explain what it is.  For example:

```sql
-- SQL (Structured Query Language) is a domain-specific language used for managing and manipulating databases.
-- It is used to interact with relational database management systems (RDBMS) such as MySQL, PostgreSQL, Oracle, and SQL Server.
--  Key functionalities include creating, reading, updating, and deleting data (CRUD operations),  as well as managing database schema and security.
```

This comment explains what SQL is, but it's not a definition *in* SQL in the sense of querying or retrieving information about SQL from a database.  SQL itself is the tool used to query databases; it can't be queried to describe itself using a formal "definition" query.

## - Purpose of SQL

The purpose of SQL (Structured Query Language) is to **manage and manipulate data stored in relational database management systems (RDBMS).**  This encompasses a wide range of tasks, including:

* **Creating databases and tables:** Defining the structure of the data, specifying data types for columns (e.g., integers, text, dates), and setting constraints (e.g., primary keys, foreign keys).

* **Inserting, updating, and deleting data:**  Adding new records, modifying existing records, and removing records from tables.

* **Querying data:** Retrieving specific data from tables based on specified criteria. This is arguably the most common use of SQL, allowing users to select, filter, sort, and join data from multiple tables to answer complex questions about the data.

* **Controlling access to data:** Defining user roles and permissions to ensure data security and integrity.  This involves granting or revoking access privileges to specific users or groups.

* **Managing transactions:** Ensuring data consistency and reliability by grouping multiple SQL operations into transactions that are either all committed or all rolled back in case of failure.

* **Managing database structure:** Modifying tables (adding, deleting, or altering columns), creating indexes for performance optimization, and other schema-related tasks.


In short, SQL provides a standardized way to interact with relational databases, making it essential for anyone working with structured data in applications, websites, and data analysis.

## - Relational DBs 

Relational databases (RDBs) are database management systems (DBMS) that store data in tables with rows and columns, organized according to the relational model.  SQL (Structured Query Language) is the standard language used to interact with RDBs.  Here's a breakdown of key concepts:

**I. Core Concepts of Relational Databases:**

* **Tables:**  Data is stored in tables, which are essentially two-dimensional arrays. Each table has a name and contains rows (records) and columns (attributes or fields).

* **Rows (Records):**  Each row represents a single instance or record of data.

* **Columns (Attributes/Fields):** Each column represents a specific piece of information about the entity represented by the rows.

* **Relationships:**  The relational aspect comes from the ability to link tables based on common columns (foreign keys). This allows for efficient data organization and querying across multiple tables.  Types of relationships include one-to-one, one-to-many, and many-to-many.

* **Primary Key:** A unique identifier for each row in a table.  No two rows can have the same primary key value.  It ensures data integrity.

* **Foreign Key:** A column in one table that references the primary key of another table. It establishes the relationship between tables.

* **Normalization:** The process of organizing data to reduce redundancy and improve data integrity.  This typically involves breaking down larger tables into smaller, more manageable tables and defining relationships between them.  Different normal forms (1NF, 2NF, 3NF, BCNF, etc.) exist to guide the normalization process.

* **Data Integrity:**  Ensuring the accuracy, consistency, and validity of data.  Constraints like primary keys, foreign keys, and data type restrictions help maintain data integrity.

* **Transactions:**  A sequence of database operations treated as a single unit of work.  They either all succeed or all fail, ensuring data consistency even in the event of errors.  Properties of ACID transactions (Atomicity, Consistency, Isolation, Durability) are crucial.


**II. SQL and its Use with Relational Databases:**

SQL is used to perform various operations on RDBs, including:

* **Data Definition Language (DDL):** Used to create, modify, and delete database objects like tables, views, and indexes.  Examples include `CREATE TABLE`, `ALTER TABLE`, `DROP TABLE`.

* **Data Manipulation Language (DML):** Used to insert, update, delete, and retrieve data from tables.  Examples include `SELECT`, `INSERT`, `UPDATE`, `DELETE`.

* **Data Control Language (DCL):** Used to manage access control and permissions.  Examples include `GRANT`, `REVOKE`.

* **Transaction Control Language (TCL):** Used to manage transactions.  Examples include `COMMIT`, `ROLLBACK`, `SAVEPOINT`.


**III. Example using SQL:**

Let's say we have two tables: `Customers` and `Orders`.

**Customers Table:**

| CustomerID (PK) | Name       | City      |
|-----------------|------------|-----------|
| 1               | John Doe   | New York  |
| 2               | Jane Smith | London    |
| 3               | David Lee  | Paris     |

**Orders Table:**

| OrderID (PK) | CustomerID (FK) | OrderDate  | Amount |
|-------------|-----------------|------------|--------|
| 101         | 1               | 2024-03-08 | 100    |
| 102         | 2               | 2024-03-15 | 200    |
| 103         | 1               | 2024-03-22 | 150    |

**SQL Queries:**

* **Retrieve all customers:** `SELECT * FROM Customers;`

* **Retrieve orders placed by John Doe:**  `SELECT * FROM Orders WHERE CustomerID = (SELECT CustomerID FROM Customers WHERE Name = 'John Doe');`  or using JOIN (more efficient): `SELECT o.* FROM Orders o JOIN Customers c ON o.CustomerID = c.CustomerID WHERE c.Name = 'John Doe';`

* **Insert a new customer:** `INSERT INTO Customers (Name, City) VALUES ('Alice Brown', 'Tokyo');`

* **Update a customer's city:** `UPDATE Customers SET City = 'Los Angeles' WHERE CustomerID = 1;`

* **Delete an order:** `DELETE FROM Orders WHERE OrderID = 101;`


This provides a basic overview of relational databases and SQL.  There are many more advanced concepts and features to explore, including views, stored procedures, triggers, indexes, and different database systems (like MySQL, PostgreSQL, Oracle, SQL Server).

## - DBMS

DBMS (Database Management System) in the context of SQL refers to the software system used to create, manage, and manipulate databases that use the SQL (Structured Query Language) standard.  SQL is the language used to *interact* with the DBMS.  The DBMS itself is the underlying engine that handles tasks like:

* **Data Storage and Retrieval:**  The DBMS stores data in an organized way and provides efficient methods for retrieving specific data based on user queries (written in SQL).

* **Data Definition:**  Using SQL's DDL (Data Definition Language) commands (like `CREATE TABLE`, `ALTER TABLE`, `DROP TABLE`), the DBMS allows users to define the structure of the database, including tables, columns, data types, and constraints.

* **Data Manipulation:** Using SQL's DML (Data Manipulation Language) commands (like `SELECT`, `INSERT`, `UPDATE`, `DELETE`), users can add, modify, retrieve, and delete data within the database.

* **Data Control:** The DBMS manages access to the data, ensuring data integrity and security through features like user authentication, authorization, and concurrency control (managing simultaneous access by multiple users).

* **Transaction Management:**  The DBMS ensures that database operations are atomic (all or nothing), consistent, isolated, and durable (ACID properties), maintaining data integrity even in case of failures.

* **Data Integrity:**  The DBMS enforces data constraints (e.g., primary keys, foreign keys, data type restrictions) defined using SQL to prevent invalid data from entering the database.

* **Backup and Recovery:**  The DBMS provides mechanisms to back up the database and recover it in case of failures or disasters.


**Examples of DBMS that use SQL:**

* **MySQL:** An open-source relational database management system.
* **PostgreSQL:** Another powerful open-source relational database management system known for its advanced features.
* **Oracle Database:** A commercial relational database management system known for its scalability and performance.
* **Microsoft SQL Server:** A commercial relational database management system tightly integrated with the Microsoft ecosystem.
* **SQLite:** A lightweight, embedded relational database management system often used in mobile applications and other embedded systems.


In short, SQL is the *language* you use, and the DBMS is the *system* that executes those commands and manages the database itself. They work together to provide a complete database solution.

