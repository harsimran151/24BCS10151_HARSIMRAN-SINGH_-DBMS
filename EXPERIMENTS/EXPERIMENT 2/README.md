# Experiment 2: SQL Set Operators (UNION, INTERSECT & EXCEPT)

## Objective

- Understand the concept of SQL Set Operators.
- Learn how to combine the results of multiple `SELECT` statements.
- Differentiate between `UNION`, `UNION ALL`, `INTERSECT`, and `EXCEPT`.
- Perform row-wise operations on multiple tables using SQL set operators.

---

## Software Requirements
- CodeChef SQL 

---

## Theory

SQL **Set Operators** are used to combine the results of two or more `SELECT` queries. Unlike **JOIN**, which combines tables column-wise, set operators combine them **row-wise**.

### 1. UNION
- Combines the result of two or more queries.
- Removes duplicate rows.
- Both queries must have:
  - Same number of columns
  - Compatible data types
  - Same column order

**Syntax**

```sql
SELECT column_name
FROM table1

UNION

SELECT column_name
FROM table2;
```

---

### 2. UNION ALL
- Combines all rows from both queries.
- Keeps duplicate rows.
- Faster than `UNION` because duplicate elimination is not performed.

**Syntax**

```sql
SELECT column_name
FROM table1

UNION ALL

SELECT column_name
FROM table2;
```

---

### 3. INTERSECT
- Returns only the rows that are present in both result sets.

**Syntax**

```sql
SELECT column_name
FROM table1

INTERSECT

SELECT column_name
FROM table2;
```

---

### 4. EXCEPT
- Returns rows from the first query that are **not present** in the second query.

**Syntax**

```sql
SELECT column_name
FROM table1

EXCEPT

SELECT column_name
FROM table2;
```

---

## Experiments Performed

### Experiment 2.1 – UNION

**Aim**

Combine the records from the `Arts` and `Science` tables into a single result.

**SQL Query**

```sql
SELECT *
FROM Arts

UNION

SELECT *
FROM Science;
```

---

### Experiment 2.2 – UNION ALL

**Aim**

Display employee names from both full-time and part-time employee tables while preserving duplicate names.

**SQL Query**

```sql
SELECT emp_name
FROM Employee

UNION ALL

SELECT emp_name
FROM pt_employee;
```

---

### Experiment 2.3 – INTERSECT

**Aim**

Find the fruits that are available in both the `fruit` table and the `inventory` table.

**SQL Query**

```sql
SELECT f_name
FROM fruit

INTERSECT

SELECT inv_name
FROM inventory;
```

---

### Experiment 2.4 – EXCEPT

**Aim**

Find the fruits listed in the `fruit` table that are **not available** in the inventory.

**SQL Query**

```sql
SELECT f_name
FROM fruit

EXCEPT

SELECT inv_name
FROM inventory;
```

---

## Source Code

```sql
-- Experiment 2.1
SELECT * FROM Arts
UNION
SELECT * FROM Science;

-- Experiment 2.2
SELECT emp_name
FROM Employee
UNION ALL
SELECT emp_name
FROM pt_employee;

-- Experiment 2.3
SELECT f_name
FROM fruit
INTERSECT
SELECT inv_name
FROM inventory;

-- Experiment 2.4
SELECT f_name
FROM fruit
EXCEPT
SELECT inv_name
FROM inventory;
```

---

## Results

- Successfully combined records from two tables using **UNION**.
- Retrieved all records, including duplicates, using **UNION ALL**.
- Identified common records between two tables using **INTERSECT**.
- Retrieved records present only in the first table using **EXCEPT**.

---

## Applications

- Combining records from multiple departments or branches.
- Merging customer or employee lists.
- Finding common records across datasets.
- Identifying missing or unavailable records.
- Data comparison and validation.

---

## Advantages

- Simple and efficient way to combine query results.
- Reduces the need for complex joins in many scenarios.
- Useful for data comparison.
- Improves readability of SQL queries.

---

## Conclusion

This experiment demonstrated the use of SQL Set Operators—**UNION**, **UNION ALL**, **INTERSECT**, and **EXCEPT**. These operators allow multiple query results to be combined or compared efficiently. Understanding their behavior helps in performing data analysis, comparison, and retrieval tasks effectively in relational databases.

---
