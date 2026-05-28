## SQL CREATE TABLE 
The `CREATE TABLE` statement in SQL is used to define a new table in a database. It specifies the table structure including column names and their data types.
- It is used to create a new table in a database.
- It defines column names and their data types.
- It helps in organizing and storing data systematically

**Syntax**
```
CREATE TABLE table_name (
  Column1 datatype (size),
  column2 datatype (size),
  .
  .
  columnN datatype(size)
);
```
- **table_name**: The name you assign to the new table.
- **column1, column2, ...** : The names of the columns in the table.
- **datatype(size)**: Defines the data type and size of each column.

#### Example: Create a Customer Table
Let’s walk through a practical example where we create a Customer table that stores customer data. We will define various columns such as CustomerID, CustomerName, Country, Age and Phone with appropriate data types and constraints.

```
CREATE TABLE Customer(
    CustomerID INT PRIMARY KEY,
    FirstName VARCHAR(50),
    LastName VARCHAR(50),
    Country VARCHAR(50),
    Age INT CHECK (Age >= 0 AND Age <= 99),
    Phone int(10)
);
```
**Output**
<img width="926" height="79" alt="image" src="https://github.com/user-attachments/assets/8e0e0453-cdaa-45aa-8017-f2f2ede31b80" />

- CustomerID is an integer and serves as the PRIMARY KEY, ensuring each record is unique.
- FirstName, LastName and Country are VARCHAR fields to store variable-length text.
- Age has a CHECK constraint, ensuring it’s within the range of 0 to 99.
- Phone is an integer field, although in real scenarios, a VARCHAR would often be used for storing phone numbers to allow for leading zeros and formatting.

#### Inserting Data into the Table
After creating the table, you can use INSERT INTO command to add data into it. Here is how to add some sample records into the Customer table:
```
INSERT INTO Customer (CustomerID, FirstName, LastName, Country, Age, Phone)
VALUES 
  (1, 'Luca', 'Bianchi', 'Italy', 23, 'xxxxxxxxxx'),
  (2, 'Aiko', 'Tanaka', 'Japan', 21, 'xxxxxxxxxx'),
  (3, 'Carlos', 'Gomez', 'Spain', 24, 'xxxxxxxxxx'),
  (4, 'Sofia', 'Müller', 'Germany', 22, 'xxxxxxxxxx'),
  (5, 'Ethan', 'Johnson', 'USA', 25, 'xxxxxxxxxx');
```

**Output:**
<img width="823" height="183" alt="image" src="https://github.com/user-attachments/assets/a4232258-564a-4042-8182-d2e815e7f5f0" />

### Create Table from Existing Table
We can also create a new table based on the structure (and optionally the data) of an existing table. The CREATE TABLE AS SELECT command allows us to duplicate an entire table or select specific columns to form a new one. The following query creates a new table called SubTable that contains CustomerID and CustomerName from the existing Customer table.

**Syntax:**
```
CREATE TABLE new_table_name AS
SELECT column1, column2, ...
FROM existing_table_name
WHERE ...
```

In this example, we create a new table SubTable that contains just the CustomerID and CustomerName columns from the Customer table. This method is useful for creating backups or performing quick data migrations.
```
CREATE TABLE SubTable AS
SELECT CustomerID, CustomerName
FROM customer;
```
```Note: CREATE TABLE ... AS SELECT does NOT copy constraints, indexes or keys```

**Output**
<img width="815" height="222" alt="image" src="https://github.com/user-attachments/assets/09d89624-eb7c-49fe-a75b-98ffb44ac50c" />
```Note: We can use * instead of column name to copy whole table to another table.```

#### Tips for Using CREATE TABLE in SQL
To ensure the smooth creation and management of your tables, keep these points in mind:

1. The CREATE TABLE statement can also define constraints like NOT NULL, UNIQUE and DEFAULT.

2. If you attempt to create a table that already exists, SQL will throw an error. To avoid this, you can use the IF NOT EXISTS clause.
   ```
    CREATE TABLE IF NOT EXISTS Customer (...);
   ```
4. Always define appropriate data types for each column (e.g., VARCHAR(50) for names and INT for IDs) to optimize performance and storage.
5. After creating a table, use the following command to view the structure of your table:
   ```
   DESC table_name;
   ```
6. If you need to change the table’s structure after creation (e.g., renaming a column, adding a new column), use the ALTER TABLE statement.


----------------------------------------------------------------------------------------------
## SQL ALTER TABLE
The SQL ALTER TABLE statement is used to modify an existing table’s structure without deleting it. It helps update the design of a database as requirements change.
Can add, delete or modify columns in a table.
Can also rename a table or change data types and constraints.
Useful for adjusting database structure without losing data.

Example: First, we will create a demo SQL database and Employees table, on which we will use the ALTER TABLE command.
<img width="813" height="145" alt="image" src="https://github.com/user-attachments/assets/dda14f80-31be-49fb-b571-f8b8d9d86d5b" />

**Query:**
```
ALTER TABLE Employees RENAME TO Staff;
```
**Output**
<img width="812" height="148" alt="image" src="https://github.com/user-attachments/assets/451b7898-1a88-40b9-8b79-0aa579284126" />

#### SYNTAX 
```
  ALTER TABLE table_name [ADD | DROP | MODIFY] column_name datatype;
```
- **table_name**: name of the table you want to modify.
- **ADD**: used to add a new column.
- **DROP**: used to remove an existing column.
- **MODIFY**: used to change datatype or definition of an existing column.
