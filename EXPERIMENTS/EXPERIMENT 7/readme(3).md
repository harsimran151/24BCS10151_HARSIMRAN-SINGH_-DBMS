# Experiment 7: Cursor and Exception Handling in PL/SQL

## Objective

To understand and implement explicit cursors, variable declarations, conditional statements, exception handling, and database updates using Oracle PL/SQL.

---

## Programs

### 7.1 Update Employee Salaries Using a Cursor

**Aim:** Create an employee table, use an explicit cursor to retrieve employee IDs and salaries, increase each employee's salary by 10%, and handle the case where an employee has a zero salary.

#### Table Creation

```sql
CREATE TABLE EMPLOYEE (
    EMP_ID NUMBER PRIMARY KEY,
    SALARY NUMBER
);
```

#### Insert Sample Data

```sql
INSERT INTO EMPLOYEE VALUES (1, 50000);
INSERT INTO EMPLOYEE VALUES (2, 60000);
INSERT INTO EMPLOYEE VALUES (3, 0);
INSERT INTO EMPLOYEE VALUES (4, 70000);
```

#### PL/SQL Program

```sql
DECLARE
    CURSOR emp_cursor IS
        SELECT EMP_ID, SALARY FROM EMPLOYEE;

    V_EMP_ID Employee.EMP_ID%TYPE;
    V_SALARY Employee.SALARY%TYPE;
    SALARY_ZERO EXCEPTION;

BEGIN
    OPEN emp_cursor;

    FETCH emp_cursor INTO V_EMP_ID, V_SALARY;

    WHILE emp_cursor%FOUND
    LOOP
        IF V_SALARY = 0 THEN
            RAISE SALARY_ZERO;
        END IF;

        UPDATE EMPLOYEE
        SET SALARY = V_SALARY * 1.10
        WHERE EMP_ID = V_EMP_ID;

        FETCH emp_cursor INTO V_EMP_ID, V_SALARY;
    END LOOP;

    CLOSE emp_cursor;

EXCEPTION
    WHEN SALARY_ZERO THEN
        DBMS_OUTPUT.PUT_LINE('Salary is zero. Increment not possible.');
END;
```

The program declares an explicit cursor named `emp_cursor` to retrieve `EMP_ID` and `SALARY` from the `EMPLOYEE` table. The cursor is opened and records are fetched one by one. For each employee, the salary is increased by 10% using an `UPDATE` statement. If the salary is `0`, the user-defined `SALARY_ZERO` exception is raised.

**Output:**

```text
Salary is zero. Increment not possible.

PL/SQL procedure successfully completed.
```

The sample data contains an employee with a salary of `0`, so the `SALARY_ZERO` exception is raised and the corresponding message is displayed. The code and sample data are based on the uploaded experiment file. fileciteturn0file0L6-L8

---

## Key Concepts Used

- **Explicit Cursor:** `emp_cursor` is used to retrieve employee records one at a time.
- **%TYPE:** `V_EMP_ID` and `V_SALARY` inherit their data types from the corresponding table columns.
- **FETCH:** Retrieves the current row from the cursor into PL/SQL variables.
- **%FOUND:** Checks whether the most recent `FETCH` successfully returned a row.
- **IF Statement:** Checks whether the employee's salary is zero.
- **User-Defined Exception:** `SALARY_ZERO` is declared and raised when the salary is zero.
- **UPDATE Statement:** Increases the employee salary by 10%.
- **DBMS_OUTPUT.PUT_LINE:** Displays the exception message.

The explicit cursor, `%TYPE` variables, salary check, update operation, and exception handling are shown in the uploaded code. fileciteturn0file0L11-L16 fileciteturn0file0L24-L34 fileciteturn0file0L39-L41

---

## Learning Outcomes

- Understood the concept of explicit cursors in PL/SQL.
- Learned how to declare and use cursor variables.
- Learned to retrieve records using `FETCH`.
- Understood the use of `%FOUND` with cursors.
- Learned how to use `%TYPE` for variable declarations.
- Implemented conditional logic using `IF`.
- Learned to create and raise a user-defined exception.
- Used `UPDATE` statements inside a PL/SQL block.
- Used `DBMS_OUTPUT.PUT_LINE` to display messages during execution.

---

## Conclusion

This experiment provided practical knowledge of explicit cursors and exception handling in Oracle PL/SQL. The program retrieves employee records using a cursor, increases salaries by 10%, and handles the special case of a zero salary using a user-defined exception. These concepts are useful for processing database records sequentially and handling exceptional situations in procedural database programming.
