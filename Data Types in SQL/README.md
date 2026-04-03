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
