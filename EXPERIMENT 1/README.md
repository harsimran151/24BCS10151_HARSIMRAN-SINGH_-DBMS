# Experiment 1: Populate Data in Advanced SQL

## 📌 Objective

Implement **DDL, DML, and DCL queries with Integrity Constraints** by populating multiple relational database tables and retrieving records using SQL queries.

---

## 📖 Problem Statement

This task focuses on inserting data into an existing Hospital Management System database and retrieving records from the tables.

The following operations are performed:

- Insert records into the **Doctors** table.
- Insert records into the **Patients** table.
- Insert records into the **Appointments** table.
- Insert records into the **Treatments** table.
- Insert records into the **MedicalRecords** table.
- Insert records into the **Billing** table.
- Retrieve the first record from:
  - Doctors
  - Patients
  - Appointments

---

## 🗂 Database Tables Used

1. Doctors
2. Patients
3. Appointments
4. Treatments
5. MedicalRecords
6. Billing

These tables are connected through **Primary Keys** and **Foreign Keys** to maintain relational integrity.

---

## 🛠 SQL Concepts Used

### DML (Data Manipulation Language)

- `INSERT INTO`
- `SELECT`

### Integrity Constraints

- Primary Key
- Foreign Key
- Referential Integrity

---

## 💻 SQL Solution

### Insert Data into Doctors Table

```sql
INSERT INTO Doctors (DoctorID, Name, Specialization, ContactNumber, Email) VALUES
(1, 'Dr. John Smith', 'Cardiology', '1234567890', 'john.smith@hospital.com'),
(2, 'Dr. Lisa Brown', 'Neurology', '0987654321', 'lisa.brown@hospital.com');
```

### Insert Data into Patients Table

```sql
INSERT INTO Patients (PatientID, Name, DOB, Gender, ContactNumber, Address) VALUES
(1, 'Alice Johnson', '1990-05-21', 'Female', '1112223333', '123 Main St'),
(2, 'Bob Martin', '1985-08-14', 'Male', '4445556666', '456 Elm St');
```

### Insert Data into Appointments Table

```sql
INSERT INTO Appointments (AppointmentID, PatientID, DoctorID, AppointmentDate, Status) VALUES
(1, 1, 1, '2025-02-15', 'Scheduled'),
(2, 2, 2, '2025-02-16', 'Completed');
```

### Insert Data into Treatments Table

```sql
INSERT INTO Treatments (TreatmentID, PatientID, DoctorID, Diagnosis, TreatmentDescription, TreatmentDate) VALUES
(1, 1, 1, 'Hypertension', 'Prescribed medication', '2025-02-15'),
(2, 2, 2, 'Migraine', 'MRI Scan and medications', '2025-02-16');
```

### Insert Data into MedicalRecords Table

```sql
INSERT INTO MedicalRecords (RecordID, PatientID, TreatmentID, Notes) VALUES
(1, 1, 1, 'Patient responding well to treatment'),
(2, 2, 2, 'Further evaluation required');
```

### Insert Data into Billing Table

```sql
INSERT INTO Billing (BillID, PatientID, TreatmentID, Amount, BillDate, Status) VALUES
(1, 1, 1, 200.00, '2025-02-15', 'Paid'),
(2, 2, 2, 500.00, '2025-02-16', 'Unpaid');
```

---

## 🔍 Retrieve the First Records

### Doctors

```sql
SELECT * FROM Doctors
WHERE DoctorID = 1;
```

### Patients

```sql
SELECT * FROM Patients
WHERE PatientID = 1;
```

### Appointments

```sql
SELECT * FROM Appointments
WHERE AppointmentID = 1;
```

---

## 📊 Expected Output

The queries return:

- The first doctor record.
- The first patient record.
- The first appointment record.

This verifies that the data has been inserted successfully into the database.

---

## 📚 Learning Outcomes

After completing this task, you will be able to:

- Populate relational database tables using `INSERT INTO`.
- Maintain relationships using Primary Keys and Foreign Keys.
- Work with multiple related tables.
- Retrieve records using `SELECT` statements.
- Understand how integrity constraints ensure data consistency.
- Practice real-world Hospital Management System database operations.

---

## ✅ Conclusion

This task demonstrates how to populate multiple related tables in a relational database while preserving data integrity through key constraints. It also reinforces the use of SQL DML commands for inserting and retrieving records, which are essential skills for database management and application development.
