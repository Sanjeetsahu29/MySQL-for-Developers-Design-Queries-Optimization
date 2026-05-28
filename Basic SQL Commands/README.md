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
