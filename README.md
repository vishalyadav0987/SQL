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





