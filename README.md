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




