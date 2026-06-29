# Business Scenario

The Hospital Management System is designed to manage patient records, doctor information, and appointment scheduling efficiently in a hospital environment. It helps administrators track patient visits, monitor doctor performance, analyze appointment revenue, and improve operational decision-making through organized data management and reporting.

 Business Problem
Hospitals face challenges in efficiently managing and analyzing large amounts of data related to patients, doctors, and appointments. Manual record-keeping makes it difficult to track patient visits, monitor doctor performance, and analyze financial revenue accurately.
There is also a need to generate advanced reports that support decision-making, such as identifying high-value patients, evaluating doctor productivity, and understanding appointment trends over time.
Without a structured database system, the hospital may experience:
•	Data duplication and inconsistency 
•	Difficulty in tracking appointments 
•	Limited visibility into financial performance 
•	Inefficient reporting and decision-making processes 
Therefore, a relational database system is required to organize hospital data and enable advanced SQL analysis using CTEs and Window Functions for better operational and financial insights
 Database Schema
The hospital management system consists of three related relational tables designed to store and manage hospital operations efficiently.
________________________________________
🔹 1. Patients Table
Stores information about patients visiting the hospital.
Attributes:
•	patient_id (Primary Key): Unique identifier for each patient 
•	patient_name: Name of the patient 
•	gender: Gender of the patient 
•	age: Age of the patient 
________________________________________
🔹 2. Doctors Table
Stores information about doctors working in the hospital.
Attributes:
•	doctor_id (Primary Key): Unique identifier for each doctor 
•	doctor_name: Name of the doctor 
•	specialization: Medical field of the doctor 
________________________________________
🔹 3. Appointments Table
Stores appointment records between patients and doctors.
Attributes:

# ER Diagram – Hospital Management System

```text
PATIENTS
---------
patient_id (PK)
patient_name
gender
age

    1
    |
    | has
    |
    M

APPOINTMENTS
--------------
appointment_id (PK)
patient_id (FK)
doctor_id (FK)
appointment_date
fee

    M
    |
    | assigned to
    |
    1

DOCTORS
--------
doctor_id (PK)
doctor_name
specialization
```

### Relationship Summary

* One Patient can have many Appointments (1:M)
* One Doctor can have many Appointments (1:M)
* Each Appointment is linked to one Patient and one Doctor

  **Three Levels of Analysis**

**Descriptive Analysis** focuses on understanding **what happened**. It summarizes historical data using tables, reports, averages, percentages, and trends to provide a clear overview of the current situation.

**Diagnostic Analysis** focuses on understanding **why it happened**. It examines patterns, relationships, and underlying factors within the data to identify the causes of specific outcomes or performance results.

**Prescriptive Analysis** focuses on determining **what should be done**. Based on the findings from descriptive and diagnostic analysis, it provides recommendations, strategies, and actionable solutions to improve future performance and support better decision-making.

Business Value:
	The Simple CTE is used to temporarily filter high-value appointment records (fee > 100).
This helps hospital management quickly identify profitable appointments without modifying the original dataset.
It improves readability and simplifies query structure, making it easier to analyze important financial transactions.
	Multiple CTEs allow step-by-step analytical processing.
First, the system calculates the average appointment fee per patient, and then filters high-value patients.
This helps management identify patients who generate consistently high revenue, which can support decision-making in resource allocation and VIP service planning.
	The Recursive CTE is used to generate sequential data programmatically.
In a real hospital scenario, it can be applied to:


