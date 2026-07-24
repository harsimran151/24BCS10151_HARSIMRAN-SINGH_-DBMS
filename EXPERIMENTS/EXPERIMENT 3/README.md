# Experiment 3: SQL Aggregate Functions, CASE, HAVING, DISTINCT, and Subqueries

## Objective
To understand and implement SQL aggregate functions and clauses including `COUNT()`, `CASE`, `HAVING`, `AVG()`, `DISTINCT`, `COUNT(DISTINCT)`, and subqueries using `NOT IN`.

---

## Programs

### 3.1 Count Using CASE

**Aim:** Count the number of students in each department who scored more than 80 marks.

```sql
SELECT Department,
COUNT(CASE WHEN Marks > 80 THEN 1 ELSE NULL END) AS Dept_HighScore_Count
FROM STUDENT
GROUP BY Department;
```

---

### 3.2 HAVING Clause and Aggregate Functions

#### (a) Display cities having at least one employee with a salary greater than or equal to 90000.

```sql
SELECT emp_city
FROM EMPLOYEES
GROUP BY emp_city
HAVING SUM(CASE WHEN EMP_SALARY >= 90000 THEN 1 ELSE 0 END) > 0;
```

#### (b) Find the average employee salary of each city.

```sql
SELECT emp_city,
AVG(EMP_SALARY)::NUMERIC(20,2) AS CNT
FROM EMPLOYEES
GROUP BY emp_city;
```

#### (c) Display all distinct employee cities.

```sql
SELECT DISTINCT EMP_CITY
FROM EMPLOYEES;
```

#### (d) Count the number of distinct employee cities.

```sql
SELECT COUNT(DISTINCT EMP_CITY) AS CNT
FROM EMPLOYEES;
```

---

### 3.3 Customers Who Never Ordered

**Aim:** Display the names of customers who have never placed an order.

```sql
SELECT name AS Customers
FROM Customers
WHERE id NOT IN (
    SELECT customerId
    FROM Orders
);
```

---

## Learning Outcomes

- Learned to perform conditional counting using the `CASE` statement.
- Understood the use of the `HAVING` clause for filtering grouped data.
- Calculated average values using the `AVG()` aggregate function.
- Retrieved unique records using the `DISTINCT` keyword.
- Counted unique values using `COUNT(DISTINCT ...)`.
- Implemented subqueries with `NOT IN` to solve real-world database problems.

---

## Conclusion

This experiment helped in understanding SQL aggregate functions, conditional expressions, grouping, filtering grouped records, retrieving distinct values, and writing subqueries. These concepts are essential for analyzing and querying relational databases efficiently.
