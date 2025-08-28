# SQL

## How we connect with mysql server.
### Step 1
```bash
mysql.server start
```
- **Note:** For connect and start the mysql server.

---

### Step 2
```bash
mycli -u root -p mysql
```
- **Note:** These is for autocompletion of queries.

---

### Step 3
```bash
\q
```
- **Note:** Exit from mysql Cell.

---


### Step 4
```bash
mysql.server stop 
```
- **Note:** For stopping server jo ki bg me ru ho rha hai.

---

## command

### 1. Database Creation:
```bash
CREATE DATABASE <database_name>;
```
- **✅ Output in cell:** 
```
Query OK, 1 row affected
```
---

### 2. Using the Database:
```bash
USE <database_name>;
```
- **✅ Output in cell:** 
```
You are now connected to database "newDB" as user "root"
```
---

### 3. Creating a Table (Main):
```bash
CREATE TABLE <table_name> (id BIGINT PRIMARY KEY, name varchar(50), grades char(20), city varchar(30) );
```
- **✅ Output in cell:** 
```
Query OK, 0 rows affected
```
---


### 4. Viewing the Table and Accessing All Records (Main):
```bash
SELECT * FROM <table_name>;
```
- **✅ Output in cell:** 
```
+----+------+--------+------+
| id | name | grades | city |
+----+------+--------+------+
+----+------+--------+------+
```
---


### 4. Inserting Data into the Table (Main):
```bash
INSERT INTO <table_name> (id, name, grades, city) 
VALUES 
    (value1_id, 'value1_name', 'value1_grade', 'value1_city'),
    (value2_id, 'value2_name', 'value2_grade', 'value2_city'),
    (value3_id, 'value3_name', 'value3_grade', 'value3_city'),
    ...;
```
- **✅ Output in cell:** 
```
Query OK, 10 rows affected
```
- **✅ After - Output in cell:** 
```bash
SELECT * FROM <table_name>;
```
```
+----+---------------+--------+---------------+
| id | name          | grades | city          |
+----+---------------+--------+---------------+
| 1  | Alice Johnson | A      | New York      |
| 2  | Bob Smith     | B      | Los Angeles   |
| 3  | Charlie Brown | A      | Chicago       |
| 4  | Diana Prince  | C      | Houston       |
| 5  | Ethan Hunt    | B      | Miami         |
| 6  | Fiona Davis   | A      | Boston        |
| 7  | George Miller | C      | San Francisco |
| 8  | Hannah Lee    | B      | Seattle       |
| 9  | Ian Clark     | A      | Denver        |
| 10 | Julia Adams   | B      | Dallas        |
+----+---------------+--------+---------------+
```
---




### 5. Update Values in Table (Main):
```bash
UPDATE <table_name> SET name='XYZ' , grades='O' WHERE id=1;
```
- **✅ Output in cell:** 
```
Query OK, 1 row affected
```
- **✅ After - Output in cell:** 
```bash
SELECT * FROM <table_name>;
```
```
+----+---------------+--------+---------------+
| id | name          | grades | city          |
+----+---------------+--------+---------------+
| 1  | XYZ (changes) | O      | New York      |
| 2  | Bob Smith     | B      | Los Angeles   |
| 3  | Charlie Brown | A      | Chicago       |
| 4  | Diana Prince  | C      | Houston       |
| 5  | Ethan Hunt    | B      | Miami         |
| 6  | Fiona Davis   | A      | Boston        |
| 7  | George Miller | C      | San Francisco |
| 8  | Hannah Lee    | B      | Seattle       |
| 9  | Ian Clark     | A      | Denver        |
| 10 | Julia Adams   | B      | Dallas        |
+----+---------------+--------+---------------+
```
---





### 6. Delete Values in Table (Main):
```bash
DELETE FROM <table_name> WHERE <condition_(id=1)>;
```
- **✅ Output in cell:** 
```
You're about to run a destructive command.
Do you want to proceed? (y/n): Y
Your call!
Query OK, 1 row affected
```
- **✅ After - Output in cell:** 
```bash
SELECT * FROM <table_name>;
```
```
+----+---------------+--------+---------------+
| id | name          | grades | city          |
+----+---------------+--------+---------------+
| 1  | XYZ           | O      | New York      |
| 2  | Bob Smith     | B      | Los Angeles   |
| 3  | Charlie Brown | A      | Chicago       |
| 4  | Diana Prince  | C      | Houston       |
| 5  | Ethan Hunt    | B      | Miami         |
| 7  | George Miller | C      | San Francisco |
| 8  | Hannah Lee    | B      | Seattle       |
| 9  | Ian Clark     | A      | Denver        |
| 10 | Julia Adams   | B      | Dallas        |
+----+---------------+--------+---------------+
```
---


### 6. ALTER Table (Main):
- **These command is used for add, delete and modify columns in an existing table.**
- **1. ALTER TABLE - Add column syntax**
```bash
ALTER TABLE <table_name> ADD COLUMN <column_name_with_type_like_int>;
```
- **✅ Output in cell:** 
```
You're about to run a destructive command.
Do you want to proceed? (y/n): Y
Your call!
Query OK, 1 row affected
```
- **✅ After ALTER - Output in cell:** 
```bash
SELECT * FROM <table_name>;
```
```
+----+---------------+--------+---------------+------------+
| id | name          | grades | city          | nativeLang |
+----+---------------+--------+---------------+------------+
| 1  | XYZ           | O      | New York      | <null>     |
| 2  | Bob Smith     | B      | Los Angeles   | <null>     |
| 3  | Charlie Brown | A      | Chicago       | <null>     |
| 4  | Diana Prince  | C      | Houston       | <null>     |
| 5  | Ethan Hunt    | B      | Miami         | <null>     |
| 7  | George Miller | C      | San Francisco | <null>     |
| 8  | Hannah Lee    | B      | Seattle       | <null>     |
| 9  | Ian Clark     | A      | Denver        | <null>     |
| 10 | Julia Adams   | B      | Dallas        | <null>     |
+----+---------------+--------+---------------+------------+
```
---

- **2. ALTER TABLE - Drop column syntax**
```bash
ALTER TABLE <table_name> DROP COLUMN <column_name>;
```
- **✅ Output in cell:** 
```
You're about to run a destructive command.
Do you want to proceed? (y/n): Y
Your call!
Query OK, 1 row affected
```
- **✅ After DROP - Output in cell:** 
```bash
SELECT * FROM <table_name>;
```
```
+----+---------------+--------+------------+
| id | name          | grades | nativeLang |
+----+---------------+--------+------------+
| 1  | XYZ           | O      | <null>     |
| 2  | Bob Smith     | B      | <null>     |
| 3  | Charlie Brown | A      | <null>     |
| 4  | Diana Prince  | C      | <null>     |
| 5  | Ethan Hunt    | B      | <null>     |
| 7  | George Miller | C      | <null>     |
| 8  | Hannah Lee    | B      | <null>     |
| 9  | Ian Clark     | A      | <null>     |
| 10 | Julia Adams   | B      | <null>     |
+----+---------------+--------+------------+
```
---

- **3. ALTER TABLE - Modify/Alter column syntax**
```bash
ALTER TABLE <table_name> MODIFY <column_name_with_type_like_int>;
ALTER TABLE students MODIFY grades VARCHAR(20);
```
- **✅ Output in cell:** 
```
You're about to run a destructive command.
Do you want to proceed? (y/n): Y
Your call!
Query OK, 1 row affected
```

---









### 7. TRUNCATE Table (Main): 
- **The TRUNCATE command in SQL is a Data Definition Language (DDL) statement used to remove all rows from a table instantly, while keeping the table structure, columns, and schema intact.**
```bash
TRUNCATE TABLE <table_name>;
```
- **✅ Output in cell:** 
```
You're about to run a destructive command.
Do you want to proceed? (y/n): y
Your call!
Query OK, 0 rows affected
```
- **✅ After - Output in cell:** 
```bash
SELECT * FROM <table_name>;
```
```
+----+-------+------+-------+------+
| id | color | name | model | type |
+----+-------+------+-------+------+
+----+-------+------+-------+------+
```
---






### 8. DROP Table (Main):
- **This command permanently removes a table and all of its data from the database.**
```bash
DROP TABLE <table_name>;
```
- **✅ Output in cell:** 
```
You're about to run a destructive command.
Do you want to proceed? (y/n): y
Your call!
Query OK, 0 rows affected
```
- **✅ After - Output in cell:** 
```bash
SELECT * FROM <table_name>;
```
```
(1146, "Table 'newdb.cars' doesn't exist")
```
---




### 9. SELECT statement (Main):
- **1. The SELECT statement is used to select data from the table.**
```bash
SELECT <col_names,col2_name,...> FROM <table_name>;
SELECT grades,name FROM students;
```
- **✅ Output in cell:** 
```
+--------+---------------+
| grades | name          |
+--------+---------------+
| O      | XYZ           |
| B      | Bob Smith     |
| A      | Charlie Brown |
| C      | Diana Prince  |
| B      | Ethan Hunt    |
| C      | George Miller |
| B      | Hannah Lee    |
| A      | Ian Clark     |
| B      | Julia Adams   |
+--------+---------------+
```


- **2. The SELECT statement is used to retrieve all the fields (columns) and their data (rows) from a table. In other words, it allows you to access and fetch data stored in the table.**
```bash
SELECT * FROM <table_name>;
```
- **✅ Output in cell:** 
```
+----+---------------+--------+------------+
| id | name          | grades | nativeLang |
+----+---------------+--------+------------+
| 1  | XYZ           | O      | <null>     |
| 2  | Bob Smith     | B      | <null>     |
| 3  | Charlie Brown | A      | <null>     |
| 4  | Diana Prince  | C      | <null>     |
| 5  | Ethan Hunt    | B      | <null>     |
| 7  | George Miller | C      | <null>     |
| 8  | Hannah Lee    | B      | <null>     |
| 9  | Ian Clark     | A      | <null>     |
| 10 | Julia Adams   | B      | <null>     |
+----+---------------+--------+------------+

```



- **3. To SELECT distinct/unique fields available in the table.**
```bash
SELECT DISTINCT <col_names,col2_name,...> FROM <table_name>;
```
- **✅ Output in cell:** 
```
+--------+
| grades |
+--------+
| O      |
| B      |
| A      |
| C      |
+--------+

```

---



### 10. WHERE Clause (Main):
- **The WHERE Clause is used to filter records. It is used to extract only those records that fulfill a specified conditions.**
```bash
SELECT * FROM table_name WHERE condtion;
```
- **✅ Output in cell:** 
```
+----+---------------+--------+------------+
| id | name          | grades | nativeLang |
+----+---------------+--------+------------+
| 3  | Charlie Brown | A      | <null>     |
| 9  | Ian Clark     | A      | <null>     |
+----+---------------+--------+------------+
```
```bash
SELECT <col_names,col2_name,...> FROM table_name WHERE condtion;
```
- **✅ Output in cell:** 
```
+----+---------------+
| id | name          |
+----+---------------+
| 3  | Charlie Brown |
| 9  | Ian Clark     |
+----+---------------+
```


---

### 10.A Operator in SQL
- **The SQL reserved words and characters are called operators, which are used with a WHERE cluase in a SQL query.**
#### Most used Operater:
- **Arithmetic operators:** +, -, *, /, % ``numerical value``
- **Comparison operators:** =, !=, >, <, >=, <= ``Compare two different tables data``
- **Logical operators:** ALL, IN, BETWEEN, LIKE, AND, OR, NOT, ANY ``Perform Boolen values``
- **Bitwise operators:** AND(&) , OR(|) ``perform the bit operations``

```bash
UPDATE students SET nativeLang='English' WHERE grades='C' || grades='O';
```
- **✅ Output in cell:** 
```
+----+---------------+--------+------------+
| id | name          | grades | nativeLang |
+----+---------------+--------+------------+
| 1  | XYZ           | O      | English    |
| 2  | Bob Smith     | B      | Hindi      |
| 3  | Charlie Brown | A      | Hindi      |
| 4  | Diana Prince  | C      | English    |
| 5  | Ethan Hunt    | B      | Hindi      |
| 7  | George Miller | C      | English    |
| 8  | Hannah Lee    | B      | Hindi      |
| 9  | Ian Clark     | A      | Hindi      |
| 10 | Julia Adams   | B      | Hindi      |
+----+---------------+--------+------------+
```
---

```bash
SELECT name FROM students WHERE id>4 && nativeLang='Hindi';
```
- **✅ Output in cell:** 
```
+-------------+
| name        |
+-------------+
| Ethan Hunt  |
| Hannah Lee  |
| Ian Clark   |
| Julia Adams |
+-------------+
```
---

```bash
SELECT * FROM students WHERE id>4 && nativeLang='Hindi';
```
- **✅ Output in cell:** 
```
+----+-------------+--------+------------+
| id | name        | grades | nativeLang |
+----+-------------+--------+------------+
| 5  | Ethan Hunt  | B      | Hindi      |
| 8  | Hannah Lee  | B      | Hindi      |
| 9  | Ian Clark   | A      | Hindi      |
| 10 | Julia Adams | B      | Hindi      |
+----+-------------+--------+------------+
```

---

### 10.B LIMIT Clause
- **The LIMIT clause is used to set an upper limit on the number of tuples return by SQL.**
```bash
SELECT <col_names,col2_name,...,*> FROM <table_name> LIMIT <NUMBER>;
```
- **✅ Output in cell:** 
```
LIMIT 5
+----+---------------+--------+------------+
| id | name          | grades | nativeLang |
+----+---------------+--------+------------+
| 2  | Bob Smith     | B      | Hindi      |
| 3  | Charlie Brown | A      | Hindi      |
| 4  | Diana Prince  | C      | English    |
| 5  | Ethan Hunt    | B      | Hindi      |
| 7  | George Miller | C      | English    |
+----+---------------+--------+------------+
```

---

### 10.C ORDER BY Clause
- **The ORDER BY is used to sort the result-set in ascending (ASC) or descending order (DESC).**
```bash
SELECT <col_names,col2_name,...,*> FROM <table_name> ORDER BY <single_col_name> ASC/DESC;
```
- **✅ Output in cell:** 
```
DESC
+----+---------------+--------+------------+
| id | name          | grades | nativeLang |
+----+---------------+--------+------------+
| 1  | XYZ           | O      | English    |
| 10 | Julia Adams   | B      | Hindi      |
| 9  | Ian Clark     | A      | Hindi      |
| 8  | Hannah Lee    | B      | Hindi      |
| 7  | George Miller | C      | English    |
| 5  | Ethan Hunt    | B      | Hindi      |
| 4  | Diana Prince  | C      | English    |
| 3  | Charlie Brown | A      | Hindi      |
| 2  | Bob Smith     | B      | Hindi      |
+----+---------------+--------+------------+

ASC
+----+---------------+--------+------------+
| id | name          | grades | nativeLang |
+----+---------------+--------+------------+
| 2  | Bob Smith     | B      | Hindi      |
| 3  | Charlie Brown | A      | Hindi      |
| 4  | Diana Prince  | C      | English    |
| 5  | Ethan Hunt    | B      | Hindi      |
| 7  | George Miller | C      | English    |
| 8  | Hannah Lee    | B      | Hindi      |
| 9  | Ian Clark     | A      | Hindi      |
| 10 | Julia Adams   | B      | Hindi      |
| 1  | XYZ           | O      | English    |
+----+---------------+--------+------------+

```

---
