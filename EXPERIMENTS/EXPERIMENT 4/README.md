# Experiment 4: SQL JOIN Operations

## Objective

To understand and implement different SQL JOIN operations including INNER JOIN, LEFT JOIN, FULL OUTER JOIN, CROSS JOIN, and SELF JOIN for retrieving and combining data from multiple related tables.

---

## Programs

### 4.1 INNER JOIN and LEFT JOIN Practice

**Aim:** Retrieve customer and product information using INNER JOIN and LEFT JOIN.

```sql
-- Customers and Orders
SELECT c.customer_name, o.order_date
FROM customers c
INNER JOIN orders o
ON c.customer_id = o.customer_id;

-- All Customers and Their Orders
SELECT c.customer_name, o.product_name
FROM customers c
LEFT JOIN orders o
ON c.customer_id = o.customer_id;

-- Products and Their Orders
SELECT p.product_name, o.order_date
FROM products p
INNER JOIN orders o
ON p.product_name = o.product_name;
```

**Output**

> *(Insert Screenshot: 4.1.png)*

---

### 4.2 INNER JOIN and LEFT JOIN using Student and Course Tables

**Aim:** Join Student and Course tables using INNER JOIN and LEFT JOIN.

```sql
SELECT *
FROM student s
INNER JOIN course c
ON s.Course_id = c.Course_id;

SELECT *
FROM student s
LEFT JOIN course c
ON s.Course_id = c.Course_id;
```

**Output**

> *(Insert Screenshot: 4.2.png)*

---

### 4.3 JOIN Practice

#### (a) Customer Details with Orders

**Aim:** Display all orders along with the respective customer details.

```sql
SELECT c.customer_name,
       o.order_id,
       c.customer_id,
       o.product_name,
       o.order_date,
       o.quantity
FROM orders o
INNER JOIN customers c
ON o.customer_id = c.customer_id;
```

#### (b) Products and Categories

**Aim:** Display all product names with their category names.

```sql
SELECT p.product_name,
       c.category_name
FROM products p
LEFT JOIN categories c
ON p.category_id = c.category_id;
```

#### (c) Categories with Product Details

**Aim:** Display category names along with product names and prices.

```sql
SELECT c.category_name,
       p.product_name,
       p.price
FROM products p
LEFT JOIN categories c
ON c.category_id = p.category_id;
```

**Output**

> *(Insert Screenshot: 4.3.png)*

---

### 4.4 FULL OUTER JOIN

**Aim:** Retrieve all records from Student and Course tables using FULL OUTER JOIN.

```sql
SELECT *
FROM student s1
FULL OUTER JOIN course c1
ON s1.Course_id = c1.Course_id;
```

**Output**

> *(Insert Screenshot: 4.4.png)*

---

### 4.5 SELF JOIN and CROSS JOIN

#### (a) Employee and Manager

**Aim:** Display employee names along with their managers.

```sql
SELECT e1.employee_name AS Employee,
       e2.employee_name AS Manager
FROM employees e1
LEFT JOIN employees e2
ON e1.manager_id = e2.employee_id;
```

#### (b) CROSS JOIN

**Aim:** Display every possible combination of customers and products.

```sql
SELECT customer_name,
       product_name
FROM customers c
CROSS JOIN products p;
```

**Output**

> *(Insert Screenshot: 4.5.png)*

---

### 4.6 SELF JOIN Practice

#### (a) Students in the Same Department

**Aim:** Display pairs of students belonging to the same department.

```sql
SELECT s1.St_id,
       s1.St_Name,
       s1.Department,
       s2.St_id,
       s2.St_Name,
       s2.Department
FROM student s1
INNER JOIN student s2
ON s1.Department = s2.Department
AND s1.St_id <> s2.St_id;
```

#### (b) Students Having the Same Favourite Course

**Aim:** Display students having the same favourite course.

```sql
SELECT s1.St_id,
       s1.St_Name,
       s1.Course_id
FROM student s1
INNER JOIN student s2
ON s1.Course_id = s2.Course_id
AND s1.St_id <> s2.St_id
ORDER BY s1.Course_id;
```

**Output**

> *(Insert Screenshot: 4.6.png)*

---

## Learning Outcomes

- Understood the concept of SQL JOIN operations.
- Learned to retrieve matching records using **INNER JOIN**.
- Used **LEFT JOIN** to include unmatched records from the left table.
- Implemented **FULL OUTER JOIN** to retrieve all records from both tables.
- Learned **SELF JOIN** for comparing records within the same table.
- Generated Cartesian products using **CROSS JOIN**.
- Used table aliases for writing readable SQL queries.
- Retrieved related information from multiple relational tables.
- Strengthened understanding of primary key and foreign key relationships.

---

## Conclusion

This experiment provided practical knowledge of SQL JOIN operations and their applications in relational databases. Different JOIN techniques such as INNER JOIN, LEFT JOIN, FULL OUTER JOIN, CROSS JOIN, and SELF JOIN were implemented to retrieve meaningful information from related tables. These concepts are fundamental for efficient database querying and are widely used in real-world database management systems.
