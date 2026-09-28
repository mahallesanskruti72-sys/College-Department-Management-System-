# -- ==========================================
-- COLLEGE DEPARTMENT MANAGEMENT SYSTEM (SQL)
-- ==========================================

-- 1. USER LOGIN TABLE
CREATE TABLE users (
    user_id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50) NOT NULL UNIQUE,
    password VARCHAR(50) NOT NULL,
    role VARCHAR(20) DEFAULT 'Admin'
);

-- Login Credentials Insert karna
INSERT INTO users (username, password, role) 
VALUES 
('admin', 'admin123', 'Admin'),
('faculty', 'pass123', 'Staff');

-- 2. STUDENT/DEPARTMENT TABLE
CREATE TABLE students (
    student_id INT AUTO_INCREMENT PRIMARY KEY,
    full_name VARCHAR(100) NOT NULL,
    email VARCHAR(100) NOT NULL,
    phone VARCHAR(15) NOT NULL,
    gender VARCHAR(10) NOT NULL,
    department VARCHAR(50) NOT NULL,
    academic_year VARCHAR(20) NOT NULL
);

-- 3. ADD RECORDS (INSERT)
INSERT INTO students (full_name, email, phone, gender, department, academic_year) 
VALUES 
('Rahul Sharma', 'rahul@college.edu', '9876543210', 'Male', 'Computer Science', '3rd Year'),
('Priya Verma', 'priya@college.edu', '9123456789', 'Female', 'Information Tech', '2nd Year'),
('Amit Patel', 'amit@college.edu', '9988776655', 'Male', 'Electronics', '1st Year'),
('Neha Gupta', 'neha@college.edu', '9811223344', 'Female', 'Computer Science', '4th Year');

-- 4. LOGIN VALIDATION CHECK (SELECT with WHERE)
SELECT 'Login Successful!' AS Status, username, role 
FROM users 
WHERE username = 'admin' AND password = 'admin123';

-- 5. VIEW ALL RECORDS (SELECT)
SELECT * FROM students;

-- 6. SEARCH RECORDS BY DEPARTMENT (SEARCH)
SELECT * FROM students 
WHERE department = 'Computer Science';

-- 7. UPDATE RECORD (UPDATE)
UPDATE students 
SET academic_year = '4th Year', phone = '9998887770' 
WHERE student_id = 1;

-- 8. DELETE RECORD (DELETE)
DELETE FROM students 
WHERE student_id = 3;

-- 9. FINAL VIEW (To verify Update and Delete)
SELECT * FROM students;
