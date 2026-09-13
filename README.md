# Exercise-3-SQL-CASE-Statements
--Create database / catalog
Create catalog if not exists istore;

-- Create schema 
Create schema if not exists istore.online;

-- Create table
Create table if not exists istore.online.products (
    PRODUCT_ID INT,
    PRODUCT_NAME STRING,
    PRICE DECIMAL);

--Insert information into the table
INSERT INTO istore.online.products VALUES
(1, 'Laptop', 1200.00),
(2, 'Phone', 800.00),
(3, 'Keyboard', 45.00),
(4, 'Monitor', 300.00),
(5, 'Mouse', 25.00);

--Display information
SELECT *
FROM istore.online.products;

-- Q1: Classify each product by price into the three tiers below.
--'Expensive' if price > 1000
--'Mid-range' if price between 100 and 1000
--'Budget' if price < 100
SELECT PRODUCT_NAME,
PRICE,
CASE
WHEN PRICE > 1000 THEN 'Expensive'
WHEN PRICE BETWEEN 100 AND 1000 THEN 'Mid-range'
WHEN PRICE < 100 THEN 'Budget'
END AS PRICE_CATEGORY
FROM istore.online.products;
 
 --Create database/ catalog
 Create catalog if not exists brightlearn;

 --Create schema 
 Create schema if not exists brightlearn.branch;

 --Create a table
 Create table if not exists brightlearn.branch.orders (
    ORDER_ID INT,
    CUSTOMER_NAME STRING,
    AMOUNT DECIMAL(10,2));

-- Insert information into the table
INSERT INTO brightlearn.branch.orders VALUES
(1, 'Alice', 150.00),
(2, 'Bob', 560.00),
(3, 'Charlie', 999.99),
(4, 'Diana', 45.50),
(5, 'Ethan', 1200.00);

--Display information
SELECT *
FROM brightlearn.branch.orders;

--Q02 Label each order by its value.
--'High Value' for orders ≥ 1000
--'Medium Value' for 500–999.99
--'Low Value' for orders < 500
SELECT CUSTOMER_NAME,
AMOUNT,
CASE
WHEN AMOUNT >= 1000 THEN 'High Value'
WHEN AMOUNT BETWEEN 500 AND 999.99 THEN 'Medium Value'
WHEN AMOUNT < 500 THEN 'Low Value'
END AS ORDER_VALUE_CATEGORY
FROM brightlearn.branch.orders; 

--Create database/ catalog
Create catalog if not exists brightlearn;

--Create a schema
Create schema if not exists brightlearn.harmony;

--Create table
Create table if not exists brightlearn.harmony.employees (
    EMPLOYEE_ID INT,
    EMPLOYEE_NAME STRING,
    DEPARTMENT STRING,
    SALARY INT);

--Insert information into the table
INSERT INTO brightlearn.harmony.employees VALUES
(1, 'John', 'IT', 85000),
(2, 'Sara', 'HR', 60000),
(3, 'Mark', 'IT', 75000),
(4, 'Lucy', 'Finance', 95000),
(5, 'Tom', 'HR', 55000);

--Display information
SELECT *
FROM brightlearn.harmony.employees;

--Q03 Categorize each employee's position level using both department and
salary.
If in 'IT' and salary > 80000 → 'Senior IT'
If in 'HR' and salary > 55000 → 'Experienced HR'
Otherwise → 'Staff
SELECT EMPLOYEE_NAME,
DEPARTMENT,
SALARY,
CASE
WHEN DEPARTMENT = 'IT' AND SALARY > 80000 THEN 'Senior IT'
WHEN DEPARTMENT = 'HR' AND SALARY > 55000 THEN 'Experienced HR'
ELSE 'Staff'
END AS POSITION_LEVEL
FROM brightlearn.harmony.employees;

--Create database / catalog
Create catalog if not exists brightlearn;

--Create schema
Create schema if not exists brightlearn.data;

--Create table
Create table if not exists brightlearn.data.students (
    STUDENT_ID INT,
    STUDENT_NAME STRING,
    SCORE INT);
    
--Insert information into the table
INSERT INTO brightlearn.data.students VALUES
(1, 'Anna', 92),
(2, 'Ben', 76),
(3, 'Cara', 59),
(4, 'David', 83),
(5, 'Ella', 68);

--Display information
SELECT *
FROM brightlearn.data.students;

--Q4.Assign each student a letter grade based on their score.
≥ 90 → 'A'
80–89 → 'B'
70–79 → 'C'
60–69 → 'D'
< 60 → 'F'
SELECT STUDENT_NAME,
SCORE,
CASE
WHEN SCORE >= 90 THEN 'A'
WHEN SCORE BETWEEN 80 AND 89 THEN 'B'
WHEN SCORE BETWEEN 70 AND 79 THEN 'C'
WHEN SCORE BETWEEN 60 AND 69 THEN 'D'
ELSE 'F'
END AS GRADE
FROM brightlearn.data.students;

--Create a database / catalog
Create catalog if not exists istore;

--Create schema
Create schema if not exists istore.online;

--Create table
Create table if not exists istore.online.deliveries (
    PRODUCT_ID INT,
    DELIVERY_TIME_MINUTES INT);

--Insert information into the table
INSERT INTO istore.online.deliveries VALUES
(1, 45),
(2, 80),
(3, 30),
(4, 65),
(5, 100);

--Display information
SELECT *
FROM istore.online.deliveries;


--Q5.Label delivery performance based on the time taken.
≤ 30 mins → 'Fast'
31–60 mins → 'On Time'
> 60 mins → 'Late'
SELECT PRODUCT_ID,
DELIVERY_TIME_MINUTES,
CASE
WHEN DELIVERY_TIME_MINUTES <= 30 THEN 'Fast'
WHEN DELIVERY_TIME_MINUTES BETWEEN 31 AND 60 THEN 'On Time'
WHEN DELIVERY_TIME_MINUTES > 60 THEN 'Late'
END AS PERFORMANCE
FROM istore.online.deliveries;


--Create database / catalog
Create catalog if not exists brightlearn;

--Create schema
Create schema if not exists brightlearn.quiries;

--Create table
Create table if not exists brightlearn.data.tickets (
    TICKET_ID INT,
    ISSUE_TYPE STRING,
    PRIORITY INT);

--Insert information into the table
INSERT INTO brightlearn.data.tickets VALUES
(1, 'Login issue', 1),
(2, 'Server down', 3),
(3, 'Slow system', 2),
(4, 'Email error', 2),
(5, 'Password reset', 1);

--Display information
SELECT *
FROM brightlearn.data.tickets;

--Q6. Convert the numeric priority into a readable label.
3 → 'High'
2 → 'Medium'
1 → 'Low'
SELECT ISSUE_TYPE,
PRIORITY,
CASE
WHEN PRIORITY = 3 THEN 'High'
WHEN PRIORITY = 2 THEN 'Medium'
WHEN PRIORITY = 1 THEN 'Low'


--Q6.Assign a priority level to each ticket based on its priority value.
1 → 'High'
2 → 'Medium'
3 → 'Low'
4 → 'Very Low'
SELECT
ISSUE_TYPE,
PRIORITY,
CASE
WHEN PRIORITY = 1 THEN 'High'
WHEN PRIORITY = 2 THEN 'Medium'
WHEN PRIORITY = 3 THEN 'Low'
WHEN PRIORITY = 4 THEN 'Very Low'
END AS PRIORITY_LABEL
FROM brightlearn.data.tickets;

Create catalog if not exists brightlearn;

Create schema if not exists brightlearn.engineering;

Create table if not exists brightlearn.engineering.attendance (
STUDENT_ID INT, 
DAYS_PRESENT INT,
TOTAL_DAYS INT);

INSERT INTO brightlearn.engineering.attendance VALUES
(1, 45, 50),
(2, 30, 50),
(3, 48, 50),
(4, 25, 50),
(5, 50, 50);

SELECT *
FROM brightlearn.engineering.attendance;

--Q7.Calculate attendance percentage and classify the result.
≥ 90% → 'Excellent'
75–89% → 'Good'
< 75% → 'Needs Improvement'
SELECT STUDENT_ID,
ROUND(DAYS_PRESENT/TOTAL_DAYS*100, 2) AS ATTENDANCE_PERCENTAGE,
CASE
WHEN ROUND(DAYS_PRESENT/TOTAL_DAYS*100, 2) >= 90 THEN 'Excellent'
WHEN ROUND(DAYS_PRESENT/TOTAL_DAYS*100, 2) BETWEEN 75 AND 89 THEN 'Good'
WHEN ROUND (DAYS_PRESENT/TOTAL_DAYS*100, 2) < 75 THEN 'Needs Improvement'
END AS ATTENDANCE_STATUS
FROM brightlearn.engineering.attendance;

--Create database/ catalog
Create catalog if not exists brightlearn;

--Create schema
Create schema if not exists brightlearn.books;

--Create table
Create table if not exists brightlearn.books.products_inventory (
    PRODUCT_ID INT,
    STOCK_QTY INT);

--Insert information into the table
INSERT INTO brightlearn.books.products_inventory VALUES
(1, 5),
(2, 0),
(3, 25),
(4, 10),
(5, 03);

--Display information
SELECT *
FROM brightlearn.books.products_inventory;

--Q8. Label the stock status of each product.
--0 → 'Out of Stock'
--1–5 → 'Low Stock'
--> 5 → 'In Stock'
SELECT PRODUCT_ID,
STOCK_QTY,
CASE
WHEN STOCK_QTY = 0 THEN 'Out of Stock'
WHEN STOCK_QTY BETWEEN 1 AND 5 THEN 'Low Stock'
WHEN STOCK_QTY > 5 THEN 'In Stock'
END AS STOCK_STATUS
FROM brightlearn.books.products_inventory;

--Create database /catalog
Create catalog if not exists brightlearn;

--Create a schema
Create schema if not exists brightlearn.developer;

--Create a table
Create table if not exists brightlearn.developer.classes (
CLASS_ID INT,
SUBJECT VARCHAR(100),
ENROLLED_STUDENTS INT);

--Insert information
INSERT INTO brightlearn.developer.classes VALUES
(1, 'Math', 30),
(2, 'English', 25),
(3, 'Science', 15),
(4, 'Art', 5),
(5, 'History', 20);

--Display information
SELECT *
FROM brightlearn.developer.classes;

--Q9.Label the class size based on enrolled students.
--≤ 10 → 'Small'
--11–25 → 'Medium'
--> 25 → 'Large'
SELECT SUBJECT,
ENROLLED_STUDENTS,
CASE
WHEN ENROLLED_STUDENTS <= 10 THEN 'Small'
WHEN ENROLLED_STUDENTS BETWEEN 11 AND 25 THEN 'Medium'
WHEN ENROLLED_STUDENTS > 25 THEN 'Large'
END AS CLASS_SIZE_CATEGORY
FROM brightlearn.developer.classes;

--Create database / catalog
Create catalog if not exists wits;

--Create schema
Create schema if not exists wits.finance;

--Create table
Create table if not exists wits.finance.payments (
payment_id INT,
amount DECIMAL(10,2),
payment_method STRING);

--Insert infomation
INSERT INTO wits.finance.payments VALUES
(1, 50.00, 'Card'),
(2, 200.00, 'Cash'),
(3, 150.00, 'Card'),
(4, 75.00, 'PayPal'),
(5, 300.00, 'Cash');

--Display information
SELECT *
FROM wits.finance.payments;

--Q10.Apply a discount flag based on the payment method and amount.
If payment_method = 'Cash' and amount ≥ 200 → 'Eligible for Discount'
Otherwise → 'Not Eligible
SELECT payment_id,
payment_method,
amount,
CASE
WHEN payment_method = 'Cash' AND amount >= 200 THEN 'Eligible for Discount'
ELSE 'Not Eligible'
END AS discount_eligibility
FROM wits.finance.payments;

