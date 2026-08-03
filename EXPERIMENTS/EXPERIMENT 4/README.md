SQL Intermediate - JOIN Operations

Objective

To understand and implement different SQL JOIN operations through practical experiments.

Experiment 1: INNER JOIN & LEFT JOIN Practice

Screenshot



Solution

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

Experiment 2: Student & Course JOIN

Screenshot



Solution

SELECT *
FROM student s
INNER JOIN course c
ON s.Course_id = c.Course_id;

SELECT *
FROM student s
LEFT JOIN course c
ON s.Course_id = c.Course_id;

Experiment 3: JOIN Practice-2

Screenshot



Solution

SELECT c.customer_name, o.order_id, c.customer_id,
       o.product_name, o.order_date, o.quantity
FROM orders o
INNER JOIN customers c
ON o.customer_id = c.customer_id;

SELECT p.product_name, c.category_name
FROM products p
LEFT JOIN categories c
ON p.category_id = c.category_id;

SELECT c.category_name, p.product_name, p.price
FROM products p
LEFT JOIN categories c
ON c.category_id = p.category_id;

Experiment 4: FULL OUTER JOIN

Screenshot



Solution

SELECT *
FROM student AS s1
FULL OUTER JOIN course AS c1
ON s1.Course_id = c1.Course_id;

Experiment 5: SELF JOIN & CROSS JOIN

Screenshot



Solution

SELECT e1.employee_name AS Employee,
       e2.employee_name AS Manager
FROM employees e1
LEFT JOIN employees e2
ON e1.manager_id = e2.employee_id;

SELECT customer_name, product_name
FROM customers c
CROSS JOIN products p;

Experiment 6: SELF JOIN Practice

Screenshot



Solution

SELECT s1.St_id,
       s1.St_Name,
       s1.Department,
       s2.St_id,
       s2.St_Name,
       s2.Department
FROM student s1
INNER JOIN student s2
ON s1.Department = s2.Department
AND s1.St_id != s2.St_id;

SELECT s1.St_id,
       s1.St_Name,
       s1.Course_id
FROM student s1
INNER JOIN student s2
ON s1.Course_id = s2.Course_id
AND s1.St_id != s2.St_id
ORDER BY s1.Course_id;

SQL JOIN Summary

JOIN Type

Description

INNER JOIN

Matching records only

LEFT JOIN

All left records + matching right

RIGHT JOIN

All right records + matching left

FULL OUTER JOIN

All records from both tables

CROSS JOIN

Cartesian product

SELF JOIN

Join a table with itself

Conclusion

These experiments demonstrate the practical use of SQL JOIN operations for combining and analyzing relational data.
