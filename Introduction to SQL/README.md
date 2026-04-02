# Structured Query Language (SQL)
Structured Query Language (SQL) is the standard language used to interact with relational databases.

- It allows users to store, retrieve, update and manage data efficiently through simple commands.
- It is known for its user-friendly syntax and powerful capabilities, SQL is widely used across industries.
<img width="800" height="400" alt="image" src="https://github.com/user-attachments/assets/4fda665f-477d-442b-bde9-8f728af33309" />

## SQL Working
We interact with databases using SQL queries. DBMS tools like MySQL and SQL Server have their own SQL engine and an interface where users can write and execute SQL queries.
<img width="800" height="400" alt="image" src="https://github.com/user-attachments/assets/9f70a83c-1f8a-46ca-b01c-d15c358710b8" />

Below are the detailed steps involved in the SQL query execution.
- Input: The user sends a SQL query (like SELECT or INSERT).
- Parsing: The system checks if the query is written correctly.
- Optimization: It chooses the fastest way to run the query.
- Execution: The database runs the query.
- Output: The result or confirmation is sent back to the user.

## Components of a SQL System
Here are some key components of SQL system:

- Database: A structured collection of data stored in tables with rows and columns.
- Tables: Store data and apply rules to keep it accurate and consistent.
- Indexes: Help the database find data faster without scanning the whole table.
- Views: Virtual tables created from SELECT queries for easy access to data.
- Stored Procedures: Pre-saved SQL code that runs tasks and improves performance and security.
- Transactions: Group of SQL actions that either all succeed or all fail to keep data safe.
- Security & Permissions: Control who can view, change, or manage database data.
- Joins: Combine data from different tables based on relationships.

## Rules for Writing SQL Queries
There are certain rules for SQL which would ensure consistency and functionality across databases. By following these rules, queries will be well formed and well executed in any database.

- **Semicolon (;)**: Ends an SQL statement.
- **Case-Insensitive**: SQL keywords like SELECT and INSERT are not case-sensitive.
- **Whitespace**: Spaces and new lines are allowed for better readability.
- **Reserved Words**: Do not use SQL keywords as names, or write them in quotes/backticks.

**Comments:**
- Single-line: -- comment
- Multi-line: /* comment */

**Data Constraints**: Use NOT NULL, UNIQUE, PRIMARY KEY, etc., to ensure data accuracy.

**String Values**: Enclose strings in single quotes ('text').

**Naming Rules:**

We Start with a letter
We can only use Max 30 characters
We only use letters, numbers and underscores (_)
