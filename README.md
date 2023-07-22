# SQL-Zen-Database-creation
For creating a database  - create database zen_class 

<h3>Queries for Zen-Database creation:-</h3>

For creating a database  - create database zen_class
For using Database       - use zen_class

I have Created tables which are required as follow


CREATE TABLE Students (
    student_id INT PRIMARY KEY AUTO_INCREMENT,
    first_name VARCHAR(50) NOT NULL,
    last_name VARCHAR(50) NOT NULL,
    email VARCHAR(100) NOT NULL,
    phone_number VARCHAR(20),
    date_of_birth DATE,
    address VARCHAR(200)
);

CREATE TABLE Instructors (
    instructor_id INT PRIMARY KEY AUTO_INCREMENT,
    first_name VARCHAR(50) NOT NULL,
    last_name VARCHAR(50) NOT NULL,
    email VARCHAR(100) NOT NULL,
    phone_number VARCHAR(20)
);

CREATE TABLE Courses (
    course_id INT PRIMARY KEY AUTO_INCREMENT,
    course_name VARCHAR(100) NOT NULL,
    description VARCHAR(500),
    start_date DATE,
    end_date DATE,
    instructor_id INT,
    FOREIGN KEY (instructor_id) REFERENCES Instructors(instructor_id)
);

CREATE TABLE Enrollments (
    enrollment_id INT PRIMARY KEY AUTO_INCREMENT,
    student_id INT,
    course_id INT,
    enrollment_date DATE,
    FOREIGN KEY (student_id) REFERENCES Students(student_id),
    FOREIGN KEY (course_id) REFERENCES Courses(course_id)
);


And for example some data are inserted:

INSERT INTO Students (first_name, last_name, email, phone_number, date_of_birth, address)
VALUES ('VarunKumar', 'V', 'varunvenkat2020@gmail.com', '8870187077', '1998-08-06', 'Vellore');

INSERT INTO Instructors (first_name, last_name, email, phone_number)
VALUES ('Vishnu', 'Vardhan', 'vishnuvardhan@gmail.com', '9996664441');

INSERT INTO Courses (course_name, description, start_date, end_date, instructor_id)
VALUES ('Introduction to Full-Stack', 'Learn the basics of JavaScript programming', '2023-05-01', '2023-08-30', 1);

INSERT INTO Enrollments (student_id, course_id, enrollment_date)
VALUES (1, 1, '2023-05-01');


We can run the respective Query as per our requirement. 

