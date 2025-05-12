# 🏫 School Attendance System

A Java-based desktop application to manage student attendance using **Java Swing** for GUI and **MySQL** as the backend database.

---

## 📌 Features

- 🔒 Admin, Faculty, and Student login roles
- ✅ Mark and view attendance
- 📊 Attendance percentage calculation
- 📁 CRUD operations on students and faculty
- 🖥️ Built with **IntelliJ IDEA** and **Java SDK 24**

---

## 🛠️ Technologies Used

| Component              | Technology           |
|------------------------|----------------------|
| GUI                    | Java Swing           |
| Backend Database       | MySQL                |
| Database Connectivity  | JDBC                 |
| IDE                    | IntelliJ IDEA        |
| Java Version           | Java SE 24           |

---

## 🗃️ Database Schema (MySQL)


```sql



create database school_attendance_system;


CREATE TABLE `attendance` (
  `attendance_id` int NOT NULL AUTO_INCREMENT,
  `class_name` varchar(50) NOT NULL,
  `roll_number` varchar(20) NOT NULL,
  `attendance_date` date NOT NULL,
  `status` enum('Present','Absent') NOT NULL,
  PRIMARY KEY (`attendance_id`),
  KEY `roll_number` (`roll_number`),
  CONSTRAINT `attendance_ibfk_1` FOREIGN KEY (`roll_number`) REFERENCES `students` (`roll_number`) ON DELETE CASCADE
) ;



--
-- Table structure for table `class_schedule`
--


CREATE TABLE `class_schedule` (
  `class_id` int NOT NULL AUTO_INCREMENT,
  `class_name` varchar(50) DEFAULT NULL,
  `subject` varchar(100) DEFAULT NULL,
  `schedule_time` varchar(50) DEFAULT NULL,
  PRIMARY KEY (`class_id`)
);
--
-- Table structure for table `students`
--




CREATE TABLE `students` (
  `student_id` int NOT NULL AUTO_INCREMENT,
  `name` varchar(100) NOT NULL,
  `roll_number` varchar(20) NOT NULL,
  `class_name` varchar(50) NOT NULL,
  PRIMARY KEY (`student_id`),
  UNIQUE KEY `roll_number` (`roll_number`)
);

-- Table structure for table `users`
--



CREATE TABLE `users` (
  `user_id` int NOT NULL AUTO_INCREMENT,
  `username` varchar(50) NOT NULL,
  `password` varchar(255) NOT NULL,
  `role` enum('Admin','Teacher','Student') NOT NULL,
  PRIMARY KEY (`user_id`),
  UNIQUE KEY `username` (`username`)
) ;




🚀 How to Run the Project
1. 📦 Download Project
Download ZIP from GitHub and extract it.

2. 🧩 Add MySQL JDBC Driver
Download from MySQL Connector/J

In IntelliJ:
File → Project Structure → Modules → Dependencies → + → JARs or directories

3. ⚙️ Setup Database
Import the SQL schema provided above in MySQL Workbench or phpMyAdmin.

4. ▶️ Run
Open Main.java and click Run.

👥 Group Members
Jawad Ali

Shoiab Ahmed

