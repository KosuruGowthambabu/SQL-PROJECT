📌 Project Title

Coaching Center Database Management System (MySQL)

A complete relational database project designed to manage students, courses, instructors, batches, enrollments, and payments for a coaching center using MySQL.

📝 Description

This project demonstrates a real-world database system for a coaching institute.
It includes schema design, sample data, and advanced SQL features such as joins, subqueries, window functions, views, stored procedures, triggers, transactions, and indexing.

🎯 Objectives

Design a normalized relational database

Maintain data integrity using constraints

Perform complex queries for reporting

Implement automation using triggers and procedures

Improve performance using indexing

🛠️ Technologies Used

Database: MySQL

Language: SQL

Tools: MySQL Workbench / MySQL CLI

Version Control: Git & GitHub

🗂️ Database Structure
Tables Included

Students

Courses

Instructors

Batches

Enrollments

Payments

Each table is connected using primary keys and foreign keys to ensure relational integrity.

🧱 Schema Details
👨‍🎓 Students

Stores student registration details.

StudentID (PK)

FullName

Email (Unique)

Phone

RegistrationDate

📘 Courses

Stores course information.

CourseID (PK)

CourseName

DurationWeeks

Fees

👩‍🏫 Instructors

Stores instructor details.

InstructorID (PK)

Name

Expertise

Phone

🧑‍🏫 Batches

Manages course batches.

BatchID (PK)

CourseID (FK)

InstructorID (FK)

StartDate

EndDate

TimeSlot

Capacity

📝 Enrollments

Tracks student enrollments.

EnrollmentID (PK)

StudentID (FK)

BatchID (FK)

EnrollmentDate

💳 Payments

Tracks payment transactions.

PaymentID (PK)

EnrollmentID (FK)

AmountPaid

PaymentDate

PaymentStatus

🧪 Sample Data

The database includes sample data:

20 Students

5 Courses

10 Instructors

10 Batches

20 Enrollments

20 Payments

This enables realistic query execution and testing.

🔍 SQL Concepts Implemented
✔️ Basic Queries

SELECT, WHERE, ORDER BY, DISTINCT

🔗 Joins

INNER JOIN across multiple tables

📊 Aggregation & Grouping

COUNT, SUM, AVG

GROUP BY, HAVING

📅 Date Functions

YEAR(), MONTH(), DATEDIFF()

🧠 Subqueries

Nested and correlated subqueries

🪟 Window Functions

RANK()

DENSE_RANK()

ROW_NUMBER()

Running totals

🔀 CASE Statements

Payment classification

Course fee categories

Student registration grouping

👁️ Views

Reusable database views:

StudentBasicInfo

PremiumCourses

EnrollmentDetails

CourseEnrollmentCount

PendingPayments

⚙️ Stored Procedures

Implemented procedures:

Get student by ID

List courses above fee threshold

Add instructor

Student count by year

Update payment status

🔔 Triggers

Automated actions:

Default payment status handling

Student insert logging

Batch capacity reduction

Payment logging

🔁 Transactions

Ensures consistency using:

START TRANSACTION

COMMIT

ROLLBACK

Used for payment safety and enrollment handling.

⚡ Indexing

Indexes created for:

Student email

Course name

Payment status

Batch time slot

Improves query performance.
