# EXPERIMENT 4 - JOIN Operations

## Objective
To understand and implement different types of SQL JOIN operations by solving practical database queries involving multiple related tables. This experiment focuses on retrieving, combining, and analyzing data using various JOIN techniques.

---

## Learning Outcomes

After completing these experiments, I was able to:

- Understand the concept of relational databases.
- Perform INNER JOIN to retrieve matching records.
- Use LEFT JOIN to include unmatched records from the left table.
- Implement FULL OUTER JOIN to retrieve all records from both tables.
- Apply SELF JOIN to compare rows within the same table.
- Use CROSS JOIN to generate Cartesian products.
- Retrieve meaningful information by combining multiple related tables.
- Write optimized SQL queries using aliases and JOIN conditions.

---

# Experiments

## Experiment 4.1: INNER JOIN & LEFT JOIN Practice

### Objective
- Retrieve customers who have placed orders.
- Display all customers along with their orders.
- Find products that have been ordered.

### JOINs Used
- INNER JOIN
- LEFT JOIN

### Tables Used
- Customers
- Orders
- Products

---

## Experiment 4.2: Student and Course JOIN

### Objective
- Join Student and Course tables.
- Compare INNER JOIN and LEFT JOIN results.

### JOINs Used
- INNER JOIN
- LEFT JOIN

### Tables Used
- Student
- Course

---

## Experiment 4.3: Practical JOIN Problems

### Objective
- Display customer details for each order.
- Retrieve products with their categories.
- Display category names along with product details.

### JOINs Used
- INNER JOIN
- LEFT JOIN

### Tables Used
- Customers
- Orders
- Products
- Categories

---

## Experiment 4.4: FULL OUTER JOIN

### Objective
Retrieve all records from both Student and Course tables, including matching and non-matching records.

### JOIN Used
- FULL OUTER JOIN

### Tables Used
- Student
- Course

---

## Experiment 4.5: SELF JOIN & CROSS JOIN

### Objective

- Display employees along with their managers using SELF JOIN.
- Generate every possible combination of customers and products using CROSS JOIN.

### JOINs Used
- SELF JOIN
- CROSS JOIN

### Tables Used
- Employees
- Customers
- Products

---

## Experiment 4.6: SELF JOIN Practice

### Objective

- Find students belonging to the same department.
- Identify students having the same favourite course.

### JOIN Used
- SELF JOIN

### Tables Used
- Student

---

# SQL JOIN Summary

| JOIN Type | Purpose |
|-----------|---------|
| INNER JOIN | Returns only matching rows from both tables. |
| LEFT JOIN | Returns all rows from the left table and matching rows from the right table. |
| RIGHT JOIN | Returns all rows from the right table and matching rows from the left table. |
| FULL OUTER JOIN | Returns all rows from both tables with NULLs where no match exists. |
| CROSS JOIN | Produces every possible combination of rows from two tables. |
| SELF JOIN | Joins a table with itself to compare rows or represent hierarchical relationships. |

---

# Concepts Practiced

- Table Aliases
- Primary & Foreign Keys
- Join Conditions
- Data Retrieval from Multiple Tables
- Hierarchical Data Queries
- Cartesian Product
- Employee-Manager Relationships
- Self Comparison of Records

---

# Conclusion

Successfully implemented and practiced various SQL JOIN operations including INNER JOIN, LEFT JOIN, FULL OUTER JOIN, CROSS JOIN, and SELF JOIN. These experiments strengthened the understanding of relational database concepts, table relationships, and efficient data retrieval techniques using SQL.
