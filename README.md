#Task-2(Data Insertion and Handling Nulls)
# 📚 College Management System Database

This project demonstrates how to design and implement a relational database schema for a **College Management System** using SQL. It includes the Insertion, Updating and deleting of a data.

## 🔍 Project Overview

This database system is designed to manage:

- Insertion of a record
- Handling missing values using NULL or default
- Using DELETE and UPDATE with WHERE conditions

The goal is to build a **well-structured, normalized schema** using SQL with clearly defined **NOT NULL** values.

This project is part of my learning and internship submission, aimed at demonstrating my understanding of database design concepts.

## 🏗️ Database Schema

### 📌 Tables:

1. **Students**
2. **Courses**
3. **Enrollments** 


## 🧾 SQL Script

Creating the data
```
-- Create the database
CREATE DATABASE College;
USE College;

-- Create Students table
CREATE TABLE Students (
    StudentID INT PRIMARY KEY,
    Name VARCHAR(50) NOT NULL,
    Email VARCHAR(60) UNIQUE,
    DOB DATE
);

-- Create Courses table
CREATE TABLE Courses (
    CourseID INT PRIMARY KEY,
    CourseName VARCHAR(50) NOT NULL,
    Credits INT CHECK (Credits > 0)
);

-- Create Enrollments table
CREATE TABLE Enrollments (
    EnrollmentID INT PRIMARY KEY,
    StudentID INT,
    CourseID INT,
    EnrollmentDate DATE,
    FOREIGN KEY (StudentID) REFERENCES Students(StudentID),
    FOREIGN KEY (CourseID) REFERENCES Courses(CourseID)
);

```
Inserting the data

```
--Inserting the data in Student table

Insert into students (StudentID, Name, Email,DOB) 
values (1,'Prajjawal', 'kushwaha344@gmail.com','2002-07-20'),
(2,'khushi','khushi345@gmail.com','2000-08-23');

--Inserting the data in Courses table

Insert into Courses(CourseID,CourseName,Credits)
values(201,'Web Development',8),
(202,'SQL Developer',9);

--Inserting the data in Enrollment table

Insert into Enrollments(EnrollmentID,StudentID,CourseID,EnrollmentDate)
values(2001,1,202,'2025-06-23'),
(2002,2,201,'2025-06-12');

```

Updating the data

```
Update students set name ='Naved Mansoori' where StudentID = 2;
```

Deleting the data

```
Delete from Enrollments where EnrollmentID=2002;

```
