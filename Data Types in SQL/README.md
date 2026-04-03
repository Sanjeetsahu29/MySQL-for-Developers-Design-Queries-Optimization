# SQL Data Types
In SQL, each column must be assigned a data type that defines the kind of data it can store, such as integers, dates, text, or binary values. Choosing the correct data type is crucial for data integrity, query performance and efficient indexing.
<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/6d43b1da-ca97-4e15-9dd8-87faf679bef4" />

## 1. Numeric Data Types
Numeric data types are fundamental to database design and are used to store numbers, whether they are integers, decimals or floating-point numbers. These data types allow for mathematical operations like addition, subtraction, multiplication and division, which makes them essential for managing financial, scientific and analytical data.

### Exact Numeric Datatype
Exact numeric types are used when precise numeric values are needed, such as for financial data, quantities, and counts. Some common exact numeric types include:
| Data Type | Description                                      | Range |
|-----------|--------------------------------------------------|-------|
| BIGINT    | Large integer numbers                            | -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807 |
| INT       | Standard integer values                          | -2,147,483,648 to 2,147,483,647 |
| SMALLINT  | Small integers                                   | -32,768 to 32,767 |
| TINYINT   | Very small integers                              | 0 to 255 |
| DECIMAL   | Exact fixed-point numbers (e.g., financial data) | -10^38 + 1 to 10^38 - 1 |
| NUMERIC   | Similar to DECIMAL, used for precision data      | -10^38 + 1 to 10^38 - 1 |

**Example**
```json
CREATE TABLE Product_Sales (
    ProductID INT PRIMARY KEY,
    Quantity SMALLINT,
    UnitPrice DECIMAL(10,2),
    TotalAmount DECIMAL(10,2)
);
```

### Approximate Numeric Datatype
These types are used to store approximate values, such as scientific measurements or large ranges of data that don't need exact precision.
| Data Type | Description                                   | Range |
|-----------|-----------------------------------------------|-------|
| FLOAT     | Approximate numeric values                    | -1.79E+308 to 1.79E+308 |
| REAL      | Similar to FLOAT, but with less precision     | -3.40E+38 to 3.40E+38 |

**Example**
```json
CREATE TABLE Measurements (
    SensorID INT,
    Temperature FLOAT,
    Humidity REAL
);
```
## 2. Character and String Data Types
Character data types are used to store text or character-based data. The choice between fixed-length and variable-length data types depends on the nature of your data.
| Data Type     | Description |
|---------------|-------------|
| CHAR          | Fixed-length non-Unicode characters. Maximum length: 8000 characters. |
| VARCHAR       | Variable-length non-Unicode characters. Maximum length: 8000 characters. |
| VARCHAR(MAX)  | Variable-length non-Unicode data. Maximum length: 2^31 - 1 characters (SQL Server 2005+). |
| TEXT          | Variable-length non-Unicode data. Maximum length: 2,147,483,647 characters. |

**Example**
```json
CREATE TABLE Employee_Info (
    EmpID INT PRIMARY KEY,
    FirstName VARCHAR(50),
    LastName CHAR(30),
    Bio TEXT
);
```

### Unicode Character String Data Types
Unicode data types are used to store characters from any language, supporting a wider variety of characters. These are given in below table.
| Data Type      | Description |
|----------------|-------------|
| NCHAR          | Fixed-length Unicode characters. Maximum length: 4000 characters. |
| NVARCHAR       | Variable-length Unicode characters. Maximum length: 4000 characters. |
| NVARCHAR(MAX)  | Variable-length Unicode data. Maximum length: 2^31 - 1 characters (SQL Server 2005+). |

**Example**:
```json
CREATE TABLE International_Users (
    UserID INT PRIMARY KEY,
    FullName NVARCHAR(100),
    Country NCHAR(50)
);
```
## 3. Date and Time Data Type
SQL provides several data types for storing date and time information. They are essential for managing timestamps, events and time-based queries. These are given in the below table.
| Data Type | Description                                              | Storage Size |
|-----------|----------------------------------------------------------|--------------|
| DATE      | Stores date values (year, month, day)                    | 3 Bytes      |
| TIME      | Stores time values (hour, minute, second)                | 3 Bytes      |
| DATETIME  | Stores both date and time (year, month, day, hour, minute, second) | 8 Bytes      |

**Example:**
```json
CREATE TABLE Orders (
    OrderID INT PRIMARY KEY,
    OrderDate DATE,
    OrderTime TIME,
    ShippedAt DATETIME
);
```

## 4. Binary Data Types in SQL
Binary data types are used to store binary data such as images, videos or other file types. These include

| Data Type  | Description                         | Max Length            |
|------------|-------------------------------------|------------------------|
| BINARY     | Fixed-length binary data            | 8000 bytes             |
| VARBINARY  | Variable-length binary data         | 8000 bytes             |
| IMAGE      | Stores binary data (e.g., images)   | 2,147,483,647 bytes    |

**Example:**
```json
CREATE TABLE Product_Images (
    ImageID INT PRIMARY KEY,
    ImageName VARCHAR(100),
    ImageData VARBINARY(MAX)
);
```
## 5. Boolean Data Type in SQL
he BOOLEAN data types are used to store logical values, typically TRUE or FALSE. It is commonly used for flag fields or binary conditions.In SQLite, there is no separate BOOLEAN or BIT data type. Instead, boolean values are stored using INTEGER, where:

- 1 represents TRUE
- 0 represents FALSE

**Example:**
```json
CREATE TABLE User_Status (
    UserID INT PRIMARY KEY,
    IsActive INTEGER,
    IsVerified INTEGER
);
```

## 6. Special Data Types
SQL also supports some specialized data types for advanced use cases:

- XML Data Type: Used to store XML data and manipulate XML structures in the database
  **Example:**
  ```json
    CREATE TABLE XML_Records (
        RecordID INT PRIMARY KEY,
        ConfigData XML
    );
    ```
- Spatial Data Type (Geometry): stores planar spatial data, such as points, lines, and polygons, in a database table.
  
  **Example:**
  ```json
  CREATE TABLE Locations (
    LocationID INT PRIMARY KEY,
    Area GEOMETRY
    );
    ```
