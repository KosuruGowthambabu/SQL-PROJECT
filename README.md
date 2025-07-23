-- creating database ----->
CREATE DATABASE COACHINGCENTER;
USE COACHINGCENTER;

-- Creating tables ----->

-- Students table ---->

CREATE TABLE Students (
    StudentID INT AUTO_INCREMENT PRIMARY KEY,
    FullName VARCHAR(100),
    Email VARCHAR(100) UNIQUE,
    Phone VARCHAR(15),
    RegistrationDate DATETIME DEFAULT CURRENT_TIMESTAMP()
);

-- Courses Table --->


CREATE TABLE Courses (
    CourseID INT AUTO_INCREMENT PRIMARY KEY,
    CourseName VARCHAR(100),
    DurationWeeks INT,
    Fees DECIMAL(10,2)
);


-- Instructors Table -->


CREATE TABLE Instructors (
    InstructorID INT AUTO_INCREMENT PRIMARY KEY,
    Name VARCHAR(100),
    Expertise VARCHAR(100),
    Phone VARCHAR(15)
);


-- Batches Table --->

CREATE TABLE Batches (
    BatchID INT AUTO_INCREMENT PRIMARY KEY,
    CourseID INT,
    InstructorID INT,
    StartDate DATE,
    EndDate DATE,
    TimeSlot VARCHAR(50),
    FOREIGN KEY (CourseID) REFERENCES Courses(CourseID),
    FOREIGN KEY (InstructorID) REFERENCES Instructors(InstructorID)
);


-- Enrollments Table ---->

CREATE TABLE Enrollments (
    EnrollmentID INT AUTO_INCREMENT PRIMARY KEY,
    StudentID INT,
    BatchID INT,
    EnrollmentDate DATETIME DEFAULT CURRENT_TIMESTAMP(),
    FOREIGN KEY (StudentID) REFERENCES Students(StudentID),
    FOREIGN KEY (BatchID) REFERENCES Batches(BatchID)
);


-- Payments Table ---->


CREATE TABLE Payments (
    PaymentID INT AUTO_INCREMENT PRIMARY KEY,
    EnrollmentID INT,
    AmountPaid DECIMAL(10,2),
    PaymentDate DATETIME DEFAULT CURRENT_TIMESTAMP(),
    PaymentStatus ENUM('Pending', 'Completed') DEFAULT 'Pending',
    FOREIGN KEY (EnrollmentID) REFERENCES Enrollments(EnrollmentID)
);

-- Inserting Students Details --->


INSERT INTO Students (FullName, Email, Phone, RegistrationDate) VALUES ('Kosuru Saiteja', 
'sai123@gmail.com', '1234567890', '2023-08-22 22:24:45');
INSERT INTO Students (FullName, Email, Phone, RegistrationDate) VALUES ('Ravula Ajay',
'rajay@gmail.com', '2345678901', '2023-05-10 10:50:22');
INSERT INTO Students (FullName, Email, Phone, RegistrationDate) VALUES ('Sivudu Dinesh',
 'dinesh@gmail.com', '3456789012', '2024-11-12 23:44:11');
INSERT INTO Students (FullName, Email, Phone, RegistrationDate) VALUES ('Dasari Chakri',
 'dasari@gmail.com', '4567890123', '2022-07-12 16:05:05');
INSERT INTO Students (FullName, Email, Phone, RegistrationDate) VALUES ('perimidi Surya',
'perimidi@gmail.com', '5678901234', '2023-05-31 14:10:08');
INSERT INTO Students (FullName, Email, Phone, RegistrationDate) VALUES ('keerthipathi Prabhas',
'prabhas@gmail.com', '6612234978', '2024-01-02 09:50:53');
INSERT INTO Students (FullName, Email, Phone, RegistrationDate) VALUES ('CH Priyanka',
'priya@gmail.com', '7890123456', '2022-10-08 03:14:09');
INSERT INTO Students (FullName, Email, Phone, RegistrationDate) VALUES ('Katta Akashitha',
 'kata@gmail.com', '8901234567', '2022-06-25 13:44:27');
INSERT INTO Students (FullName, Email, Phone, RegistrationDate) VALUES ('N Kavya',
'kavya@gmail.com', '9012345678', '2023-01-12 02:51:25');
INSERT INTO Students (FullName, Email, Phone, RegistrationDate) VALUES ('K Hema',
'hema@gmail.com', '1237890456', '2020-06-12 11:10:44');
INSERT INTO Students (FullName, Email, Phone, RegistrationDate) VALUES ('SK Jasmine',
 'jasmine@gmail.com', '2347890156', '2024-11-15 07:27:31');
INSERT INTO Students (FullName, Email, Phone, RegistrationDate) VALUES ('K Dharani', 
'dharani@gmail.com', '5671238903', '2023-04-02 10:05:53');
INSERT INTO Students (FullName, Email, Phone, RegistrationDate) VALUES ('K Himaja', 
'himaja@gmail.com', '1999800170', '2020-07-02 23:04:31');
INSERT INTO Students (FullName, Email, Phone, RegistrationDate) VALUES ('M Guna', 
'guna@gmail.com', '2521066709', '2020-08-22 03:18:18');
INSERT INTO Students (FullName, Email, Phone, RegistrationDate) VALUES ('CH Divya',
 'divya@gmail.com', '2858645010', '2020-07-14 23:04:40');
INSERT INTO Students (FullName, Email, Phone, RegistrationDate) VALUES ('E sathvika',
'sathvika@gmail.com', '3656612801', '2022-10-03 00:33:33');
INSERT INTO Students (FullName, Email, Phone, RegistrationDate) VALUES ('M Meghana',
'meghana@gmail.com', '5444849006', '2020-09-05 01:46:19');
INSERT INTO Students (FullName, Email, Phone, RegistrationDate) VALUES ('D  Chandu',
'chandu@gmail.com', '4262271212', '2024-06-02 19:36:19');
INSERT INTO Students (FullName, Email, Phone, RegistrationDate) VALUES ('Sivudu Vishnu',
'sivudu@gmail.com', '9099228534', '2022-05-05 07:57:28');
INSERT INTO Students (FullName, Email, Phone, RegistrationDate) VALUES ('Nasina Chandra', 
'nasina@gmail.com', '001-780-034-323', '2023-01-27 22:04:11');


-- Inserting Course Details ---->


INSERT INTO Courses (CourseName, DurationWeeks, Fees) 
VALUES ('Data Science', 10,49999);
INSERT INTO Courses (CourseName, DurationWeeks, Fees) 
VALUES ('Web Development', 6,16999);
INSERT INTO Courses (CourseName, DurationWeeks, Fees) 
VALUES ('Cyber Security', 8,20000);
INSERT INTO Courses (CourseName, DurationWeeks, Fees) 
VALUES ('AI & ML', 10, 50000);
INSERT INTO Courses (CourseName, DurationWeeks, Fees) 
VALUES ('Cloud Computing', 8,20000);



-- Inserting  Instructors Details --->

INSERT INTO Instructors (Name, Expertise, Phone) 
VALUES ('Henry ', 'Web Development', '4623161297');
INSERT INTO Instructors (Name, Expertise, Phone) 
VALUES ('Williams', 'Cyber Security', '7945894068');
INSERT INTO Instructors (Name, Expertise, Phone)
VALUES ('Samantha ', 'Data Science', '2802351398');
INSERT INTO Instructors (Name, Expertise, Phone)
VALUES ('Michael ', 'Cyber Security', '9533655495');
INSERT INTO Instructors (Name, Expertise, Phone) 
VALUES ('Smith', 'AI & ML','7082000116');
INSERT INTO Instructors (Name, Expertise, Phone) 
VALUES ('Maxwell', 'Cloud Computing','8320309543');
INSERT INTO Instructors (Name, Expertise, Phone) 
VALUES ('Rashid', 'Web Development', '7311311260');
INSERT INTO Instructors (Name, Expertise, Phone) 
VALUES ('Vinay', 'AI & ML','8348037911');
INSERT INTO Instructors (Name, Expertise, Phone) 
VALUES ('Srinu', 'Data Science','8348037911');
INSERT INTO Instructors (Name, Expertise, Phone) 
VALUES ('Raju', 'Cloud Computing','8348037911');


-- Inserting Batches Details ---->


INSERT INTO Batches (CourseID, InstructorID, StartDate, EndDate, TimeSlot) 
VALUES (1,1,'2024-10-05', '2024-12-21', 'Afternoon');
INSERT INTO Batches (CourseID, InstructorID, StartDate, EndDate, TimeSlot) 
VALUES (2,2, '2025-03-31', '2025-06-02', 'Evening');
INSERT INTO Batches (CourseID, InstructorID, StartDate, EndDate, TimeSlot) 
VALUES (3,3, '2025-04-17', '2025-07-03', 'Morning');
INSERT INTO Batches (CourseID, InstructorID, StartDate, EndDate, TimeSlot) 
VALUES (4,4, '2025-02-15', '2025-04-12', 'Evening');
INSERT INTO Batches (CourseID, InstructorID, StartDate, EndDate, TimeSlot) 
VALUES (5,5, '2024-12-13', '2025-02-21', 'Evening');
INSERT INTO Batches (CourseID, InstructorID, StartDate, EndDate, TimeSlot) 
VALUES (5,6, '2024-12-31', '2025-03-04', 'Afternoon');
INSERT INTO Batches (CourseID, InstructorID, StartDate, EndDate, TimeSlot) 
VALUES (1,7, '2024-08-26', '2024-10-21', 'Afternoon');
INSERT INTO Batches (CourseID, InstructorID, StartDate, EndDate, TimeSlot) 
VALUES (3,8, '2025-05-26', '2025-08-18', 'Evening');
INSERT INTO Batches (CourseID, InstructorID, StartDate, EndDate, TimeSlot) 
VALUES (2,9, '2025-02-13', '2025-04-24', 'Evening');
INSERT INTO Batches (CourseID, InstructorID, StartDate, EndDate, TimeSlot) 
VALUES (4,10, '2024-10-19', '2024-12-14', 'Morning');


-- Inserting Enrollments Details ----->

INSERT INTO Enrollments (StudentID, BatchID, EnrollmentDate) VALUES (1, 10, '2025-03-21 09:15:44');
INSERT INTO Enrollments (StudentID, BatchID, EnrollmentDate) VALUES (2, 9, '2025-02-09 21:33:26');
INSERT INTO Enrollments (StudentID, BatchID, EnrollmentDate) VALUES (3, 8, '2025-04-20 01:51:12');
INSERT INTO Enrollments (StudentID, BatchID, EnrollmentDate) VALUES (4, 7, '2025-02-08 23:44:16');
INSERT INTO Enrollments (StudentID, BatchID, EnrollmentDate) VALUES (5, 6, '2025-04-15 08:02:49');
INSERT INTO Enrollments (StudentID, BatchID, EnrollmentDate) VALUES (6, 5, '2025-07-13 21:02:30');
INSERT INTO Enrollments (StudentID, BatchID, EnrollmentDate) VALUES (7, 4, '2025-05-01 16:45:45');
INSERT INTO Enrollments (StudentID, BatchID, EnrollmentDate) VALUES (8, 3, '2025-06-20 16:28:04');
INSERT INTO Enrollments (StudentID, BatchID, EnrollmentDate) VALUES (9, 2, '2025-05-13 03:40:48');
INSERT INTO Enrollments (StudentID, BatchID, EnrollmentDate) VALUES (10, 1, '2025-03-02 01:39:05');
INSERT INTO Enrollments (StudentID, BatchID, EnrollmentDate) VALUES (11, 1, '2025-03-22 07:03:15');
INSERT INTO Enrollments (StudentID, BatchID, EnrollmentDate) VALUES (12, 2, '2025-04-20 02:57:15');
INSERT INTO Enrollments (StudentID, BatchID, EnrollmentDate) VALUES (13, 3, '2025-04-09 12:51:41');
INSERT INTO Enrollments (StudentID, BatchID, EnrollmentDate) VALUES (14, 4, '2025-06-27 16:18:42');
INSERT INTO Enrollments (StudentID, BatchID, EnrollmentDate) VALUES (15, 5, '2025-06-05 15:52:26');
INSERT INTO Enrollments (StudentID, BatchID, EnrollmentDate) VALUES (16, 6, '2025-05-26 15:27:46');
INSERT INTO Enrollments (StudentID, BatchID, EnrollmentDate) VALUES (17, 7, '2025-06-06 18:47:18');
INSERT INTO Enrollments (StudentID, BatchID, EnrollmentDate) VALUES (18, 8, '2025-02-12 13:11:33');
INSERT INTO Enrollments (StudentID, BatchID, EnrollmentDate) VALUES (19, 9, '2025-05-09 21:14:06');
INSERT INTO Enrollments (StudentID, BatchID, EnrollmentDate) VALUES (20, 10, '2025-02-08 03:12:47');


-- Inserting Payment Details ----->

INSERT INTO Payments (EnrollmentID, AmountPaid, PaymentDate, PaymentStatus) 
VALUES (1,15891.67, '2025-02-27 08:57:00', 'Pending');
INSERT INTO Payments (EnrollmentID, AmountPaid, PaymentDate, PaymentStatus) 
VALUES (2,16999, '2025-01-09 08:08:37', 'Completed');
INSERT INTO Payments (EnrollmentID, AmountPaid, PaymentDate, PaymentStatus) 
VALUES (3,18957.29, '2025-04-18 14:00:22', 'Pending');
INSERT INTO Payments (EnrollmentID, AmountPaid, PaymentDate, PaymentStatus) 
VALUES (4,49999, '2025-05-29 20:27:47', 'Completed');
INSERT INTO Payments (EnrollmentID, AmountPaid, PaymentDate, PaymentStatus) 
VALUES (5,20000, '2025-01-22 06:56:18', 'Completed');
INSERT INTO Payments (EnrollmentID, AmountPaid, PaymentDate, PaymentStatus) 
VALUES (6,20000, '2025-06-13 18:31:28', 'Completed');
INSERT INTO Payments (EnrollmentID, AmountPaid, PaymentDate, PaymentStatus)
VALUES (7,12940.64, '2025-01-13 01:15:18', 'Pending');
INSERT INTO Payments (EnrollmentID, AmountPaid, PaymentDate, PaymentStatus) 
VALUES (8,7935.04, '2025-03-03 02:33:14', 'Pending');
INSERT INTO Payments (EnrollmentID, AmountPaid, PaymentDate, PaymentStatus) 
VALUES (9,13300.46, '2025-06-29 00:15:52', 'Pending');
INSERT INTO Payments (EnrollmentID, AmountPaid, PaymentDate, PaymentStatus) 
VALUES (10,49999, '2025-06-15 14:33:04', 'Completed');
INSERT INTO Payments (EnrollmentID, AmountPaid, PaymentDate, PaymentStatus) 
VALUES (11,18564.39, '2025-03-09 14:37:23', 'Pending');
INSERT INTO Payments (EnrollmentID, AmountPaid, PaymentDate, PaymentStatus) 
VALUES (12,16999, '2025-01-11 18:55:43', 'Completed');
INSERT INTO Payments (EnrollmentID, AmountPaid, PaymentDate, PaymentStatus) 
VALUES (13,19444.08, '2025-07-07 03:48:43', 'Pending');
INSERT INTO Payments (EnrollmentID, AmountPaid, PaymentDate, PaymentStatus) 
VALUES (14,11292.58, '2025-05-03 22:02:15', 'Pending');
INSERT INTO Payments (EnrollmentID, AmountPaid, PaymentDate, PaymentStatus) 
VALUES (15,8563.03, '2025-04-07 08:33:30', 'Pending');
INSERT INTO Payments (EnrollmentID, AmountPaid, PaymentDate, PaymentStatus) 
VALUES (16,20000, '2025-05-03 17:10:15', 'Completed');
INSERT INTO Payments (EnrollmentID, AmountPaid, PaymentDate, PaymentStatus) 
VALUES (17,13051.84, '2025-03-12 05:12:26', 'Pending');
INSERT INTO Payments (EnrollmentID, AmountPaid, PaymentDate, PaymentStatus)  
VALUES (18,20000, '2025-07-15 05:30:43', 'Completed');
INSERT INTO Payments (EnrollmentID, AmountPaid, PaymentDate, PaymentStatus) 
VALUES (19,16999, '2025-02-07 01:52:14', 'Completed');
INSERT INTO Payments (EnrollmentID, AmountPaid, PaymentDate, PaymentStatus) 
VALUES (20,50000, '2025-03-23 10:23:19', 'Completed');

-- Select Query ----->
-- 1. Get all students----->
SELECT * FROM Students;

SELECT * FROM Courses;

SELECT * FROM Instructors;

SELECT * FROM Batches;

SELECT * FROM Enrollments;

SELECT * FROM Payments;

-- 2. Get only student names and emails--->
SELECT FullName, Email FROM Students;

-- 3. Get unique course durations--->
SELECT DISTINCT DurationWeeks FROM Courses;

-- 4. Get all courses with fees above 20,000----->
SELECT * FROM Courses WHERE Fees > 20000;

-- 5. Sort instructors by name--->
SELECT * FROM Instructors ORDER BY Name;

-- where Clause --->

-- 1. Students who registered in 2023--->
SELECT * FROM Students WHERE YEAR(RegistrationDate) = 2023;

-- 2. Courses with duration >= 8 weeks--->
SELECT * FROM Courses WHERE DurationWeeks >= 8;

-- 3. Payments with status "Pending"----->
SELECT * FROM Payments WHERE PaymentStatus = 'Pending';

-- 4. Instructors with "AI & ML" expertise----->
SELECT * FROM Instructors WHERE Expertise = 'AI & ML';

-- 5. Batches with time slot 'Evening'------>
SELECT * FROM Batches WHERE TimeSlot = 'Evening';


-- Joins --->

-- 1. Student names with enrolled course names------>
SELECT s.FullName, c.CourseName
FROM Students s
JOIN Enrollments e ON s.StudentID = e.StudentID
JOIN Batches b ON e.BatchID = b.BatchID
JOIN Courses c ON b.CourseID = c.CourseID;

-- 2. Payment status with student names---->
SELECT s.FullName, p.AmountPaid, p.PaymentStatus
FROM Students s
JOIN Enrollments e ON s.StudentID = e.StudentID
JOIN Payments p ON e.EnrollmentID = p.EnrollmentID;

-- 3. Instructors with their course names------>
SELECT i.Name, c.CourseName
FROM Instructors i
JOIN Batches b ON i.InstructorID = b.InstructorID
JOIN Courses c ON b.CourseID = c.CourseID;

-- 4. Enrollments with course, instructor, student------>
SELECT s.FullName, c.CourseName, i.Name AS Instructor
FROM Enrollments e
JOIN Students s ON s.StudentID = e.StudentID
JOIN Batches b ON b.BatchID = e.BatchID
JOIN Courses c ON c.CourseID = b.CourseID
JOIN Instructors i ON i.InstructorID = b.InstructorID;

-- 5. Students with payment details------->
SELECT s.FullName, p.AmountPaid, p.PaymentDate
FROM Students s
JOIN Enrollments e ON s.StudentID = e.StudentID
JOIN Payments p ON e.EnrollmentID = p.EnrollmentID;


-- Group By + Aggergated Functions ---->

-- 1. Count students per year---->
SELECT YEAR(RegistrationDate) AS Year, COUNT(*) AS Total
FROM Students GROUP BY YEAR(RegistrationDate);

-- 2. Count enrollments per course------>
SELECT c.CourseName, COUNT(*) AS TotalEnrollments
FROM Courses c
JOIN Batches b ON c.CourseID = b.CourseID
JOIN Enrollments e ON b.BatchID = e.BatchID
GROUP BY c.CourseName;

-- 3. Sum of payments per status----->
SELECT PaymentStatus, SUM(AmountPaid) AS Total
FROM Payments GROUP BY PaymentStatus;

-- 4. Average course fees------>
SELECT AVG(Fees) AS AvgFee FROM Courses;

-- 5. Number of batches per instructor------>
SELECT i.Name, COUNT(*) AS TotalBatches
FROM Instructors i
JOIN Batches b ON i.InstructorID = b.InstructorID
GROUP BY i.Name;


-- Date Functions --->

-- 1. Students who registered this year----->
SELECT * FROM Students WHERE YEAR(RegistrationDate) = YEAR(CURDATE());

-- 2. Payments made this month----->
SELECT * FROM Payments WHERE MONTH(PaymentDate) = MONTH(CURDATE());

-- 3. Difference in days between batch start and end------>
SELECT BatchID, DATEDIFF(EndDate, StartDate) AS Duration
FROM Batches;

-- 4. Extract month from payment date----->
SELECT PaymentID, MONTHNAME(PaymentDate) AS Month FROM Payments;

-- 5. Find batches starting in 2025------>
SELECT * FROM Batches WHERE YEAR(StartDate) = 2025;

-- Sub Queries ---->

-- 1. Students who paid more than average------->
SELECT s.FullName, p.AmountPaid
FROM Students s
JOIN Enrollments e ON s.StudentID = e.StudentID
JOIN Payments p ON p.EnrollmentID = e.EnrollmentID
WHERE p.AmountPaid > (SELECT AVG(AmountPaid) FROM Payments);

-- 2. Courses with max duration------->
SELECT * FROM Courses WHERE DurationWeeks = (
  SELECT MAX(DurationWeeks) FROM Courses
);

-- 3. Instructors teaching more than 1 batch------>
SELECT Name FROM Instructors WHERE InstructorID IN (
  SELECT InstructorID FROM Batches GROUP BY InstructorID HAVING COUNT(*) > 1
);

-- 4. Students with no enrollments------->
SELECT * FROM Students WHERE StudentID NOT IN (
  SELECT StudentID FROM Enrollments
);

-- 5. Batches with no enrollments-------->
SELECT * FROM Batches WHERE BatchID NOT IN (
  SELECT BatchID FROM Enrollments
);


-- Window Functions --->

-- 1. Rank students by payment amount------->
SELECT s.FullName, p.AmountPaid,
       RANK() OVER (ORDER BY p.AmountPaid DESC) AS PaymentRank
FROM Payments p
JOIN Enrollments e ON p.EnrollmentID = e.EnrollmentID
JOIN Students s ON s.StudentID = e.StudentID;

-- 2. Row number for each student------->
SELECT s.FullName, ROW_NUMBER() OVER (ORDER BY s.RegistrationDate) AS RowNum
FROM Students s;

-- 3. Running total of payments------->
SELECT p.PaymentID, p.AmountPaid,
       SUM(p.AmountPaid) OVER (ORDER BY p.PaymentDate) AS RunningTotal
FROM Payments p;

-- 4. Dense rank by payment amount------>
SELECT s.FullName, p.AmountPaid,
       DENSE_RANK() OVER (ORDER BY p.AmountPaid DESC) AS DenseRank
FROM Students s
JOIN Enrollments e ON s.StudentID = e.StudentID
JOIN Payments p ON p.EnrollmentID = e.EnrollmentID;

-- 5. Average payment per student over all their enrollments------>
SELECT s.FullName, AVG(p.AmountPaid) OVER (PARTITION BY s.StudentID) AS AvgPaid
FROM Students s
JOIN Enrollments e ON s.StudentID = e.StudentID
JOIN Payments p ON p.EnrollmentID = e.EnrollmentID;


-- Case statements --->

-- 1. Label payment status------>
SELECT AmountPaid,
  CASE
    WHEN PaymentStatus = 'Completed' THEN 'Paid'
    ELSE 'Unpaid'
  END AS StatusLabel
FROM Payments;

-- 2. Grade payment levels------->
SELECT FullName, AmountPaid,
  CASE 
    WHEN AmountPaid >= 40000 THEN 'High'
    WHEN AmountPaid >= 20000 THEN 'Medium'
    ELSE 'Low'
  END AS PaymentLevel
FROM Students s
JOIN Enrollments e ON s.StudentID = e.StudentID
JOIN Payments p ON p.EnrollmentID = e.EnrollmentID;

-- 3. Categorize students by registration year---->
SELECT FullName,
  CASE 
    WHEN YEAR(RegistrationDate) < 2021 THEN 'Old'
    WHEN YEAR(RegistrationDate) BETWEEN 2021 AND 2023 THEN 'Recent'
    ELSE 'New'
  END AS Category
FROM Students;

-- 4. Show course cost category------>
SELECT CourseName, Fees,
  CASE
    WHEN Fees >= 40000 THEN 'Premium'
    WHEN Fees >= 20000 THEN 'Standard'
    ELSE 'Budget'
  END AS FeeLevel
FROM Courses;

-- 5. Time slot description--------->
SELECT BatchID, TimeSlot,
  CASE TimeSlot
    WHEN 'Morning' THEN '☀️ Morning Batch'
    WHEN 'Afternoon' THEN '🌞 Afternoon Batch'
    WHEN 'Evening' THEN '🌙 Evening Batch'
    ELSE 'Unknown Slot'
  END AS SlotLabel
FROM Batches;

-- Views ---->


-- 1. View of basic student info-------->
CREATE VIEW StudentBasicInfo AS
SELECT FullName, Email, Phone FROM Students;

-- 2. View for high-fee courses------>
CREATE VIEW PremiumCourses AS
SELECT CourseName, Fees FROM Courses WHERE Fees > 25000;

-- 3. View for enrollments with course and student info------->
CREATE VIEW EnrollmentDetails AS
SELECT e.EnrollmentID, s.FullName, c.CourseName
FROM Enrollments e
JOIN Students s ON s.StudentID = e.StudentID
JOIN Batches b ON e.BatchID = b.BatchID
JOIN Courses c ON b.CourseID = c.CourseID;

-- 4. View to count enrollments per course------->
CREATE VIEW CourseEnrollmentCount AS
SELECT c.CourseName, COUNT(e.EnrollmentID) AS TotalEnrollments
FROM Courses c
JOIN Batches b ON b.CourseID = c.CourseID
JOIN Enrollments e ON e.BatchID = b.BatchID
GROUP BY c.CourseName;

-- 5. View for pending payments------->
CREATE VIEW PendingPayments AS
SELECT s.FullName, p.AmountPaid, p.PaymentStatus
FROM Students s
JOIN Enrollments e ON s.StudentID = e.StudentID
JOIN Payments p ON p.EnrollmentID = e.EnrollmentID
WHERE p.PaymentStatus = 'Pending';


-- Store Procedure --->

-- 1. Procedure to get student by ID-------->
DELIMITER //
CREATE PROCEDURE GetStudent(IN id INT)
BEGIN
  SELECT * FROM Students WHERE StudentID = id;
END;
//
DELIMITER ;

-- 2. Procedure to list all courses above a fee threshold------->
DELIMITER //
CREATE PROCEDURE CoursesAboveFee(IN fee DECIMAL(10,2))
BEGIN
  SELECT * FROM Courses WHERE Fees > fee;
END;
//
DELIMITER ;

-- 3. Procedure to add a new instructor------->
DELIMITER //
CREATE PROCEDURE AddInstructor(IN name VARCHAR(100), IN email VARCHAR(100), IN expertise VARCHAR(100))
BEGIN
  INSERT INTO Instructors (Name, Email, Expertise)
  VALUES (name, email, expertise);
END;
//
DELIMITER ;

-- 4. Procedure to count students per year--------->
DELIMITER //
CREATE PROCEDURE StudentCountByYear()
BEGIN
  SELECT YEAR(RegistrationDate) AS RegYear, COUNT(*) AS Total
  FROM Students
  GROUP BY RegYear;
END;
//
DELIMITER ;

-- 5. Procedure to update payment status-------->
DELIMITER //
CREATE PROCEDURE MarkPaymentCompleted(IN pid INT)
BEGIN
  UPDATE Payments SET PaymentStatus = 'Completed' WHERE PaymentID = pid;
END;
//
DELIMITER ;


-- Triggers --->


-- 1. Before insert trigger to set default payment status------->
CREATE TRIGGER before_payment_insert
BEFORE INSERT ON Payments
FOR EACH ROW
SET NEW.PaymentStatus = IFNULL(NEW.PaymentStatus, 'Pending');

-- 2. After insert trigger to log student insert------------>
CREATE TRIGGER after_student_insert
AFTER INSERT ON Students
FOR EACH ROW
INSERT INTO AuditLog(TableName, Action, ActionTime)
VALUES ('Students', 'INSERT', NOW());

-- 3. Before insert trigger to prevent overpayment--------->
 CREATE TRIGGER prevent_overpayment
 BEFORE INSERT ON Payments
FOR EACH ROW
BEGIN
IF NEW.AmountPaid > 50000 THEN
      SIGNAL SQLSTATE '45000' SET MESSAGE_TEXT = 'Payment exceeds limit!';
  END IF;
END;



-- 4. After insert trigger to reduce batch capacity----->
CREATE TRIGGER reduce_batch_capacity
AFTER INSERT ON Enrollments
FOR EACH ROW
UPDATE Batches SET Capacity = Capacity - 1 WHERE BatchID = NEW.BatchID;

-- 5. After payment insert log------->
CREATE TRIGGER log_payment
AFTER INSERT ON Payments
FOR EACH ROW
INSERT INTO PaymentLogs(PaymentID, Amount, CreatedAt)
VALUES (NEW.PaymentID, NEW.AmountPaid, NOW());

DROP TRIGGER IF EXISTS log_payment;


-- Transaction --->


-- 1. Insert payment with rollback support------>
START TRANSACTION;
INSERT INTO Payments (EnrollmentID, AmountPaid, PaymentStatus, PaymentDate)
VALUES (1, 20000, 'Pending', CURDATE());
ROLLBACK;

-- 2. Update student email and commit------->
START TRANSACTION;
UPDATE Students SET Email = 'updated@example.com' WHERE StudentID = 1;
COMMIT;

-- 3. Delete a batch and rollback----->
START TRANSACTION;
 DELETE FROM Batches WHERE BatchID = 3;
 ROLLBACK;
ALTER TABLE Batches ADD Capacity INT DEFAULT 30;

-- 4. Enroll a student and update capacity------>
START TRANSACTION;
INSERT INTO Enrollments (StudentID, BatchID) VALUES (2, 4);
UPDATE Batches SET Capacity = Capacity - 1 WHERE BatchID = 4;
COMMIT;

-- 5. Add new student and auto-enroll----->
START TRANSACTION;
INSERT INTO Students (FullName, Email, Phone, RegistrationDate)
 VALUES ('Ravi Kumar', 'ravi@example.com', '9998887776', CURDATE());
 INSERT INTO Enrollments (StudentID, BatchID)
 VALUES (LAST_INSERT_ID(), 2);
 COMMIT;


-- Indexing ---->


-- 1. Index on student email------>
CREATE INDEX idx_students_email ON Students(Email);

-- 2. Index on course name----->
CREATE INDEX idx_courses_name ON Courses(CourseName);

-- 3. Index on payment status------>
CREATE INDEX idx_payments_status ON Payments(PaymentStatus);

-- 4. Index on batch time slot------>
CREATE INDEX idx_batches_timeslot ON Batches(TimeSlot);

-- 5. Unique index on instructor email----->
CREATE UNIQUE INDEX idx_instructors_email ON Instructors(Name);


