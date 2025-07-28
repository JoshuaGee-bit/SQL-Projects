# AxiaStores SQL Database Project

## Project Overview
This project demonstrates a complete SQL based solution for an Electronic and Accessories retail business, **AxiaStores**. It involves designing and implementing a relational database with three core tables, Customer, Product, and Orders. While performing various analytical queries to extract insights.


## Table of Content



## Objectives
The primary goal of this project is to
- Create a sample relational database
- Creation of multiple tables within the database with appropriate data types and constraints:
- Insertion of sample records into all tables
- Query functions like:
    - Retriveal of customer details
    - Sorting alphabetically
    - The use of Join function for multiple tables
    - Use of aggregate functions like average and sum


## Tools and Methodologies
**Tool Used:** **SQL SERVER MANAGEMENT STUDIO 21** [Download Here](https://www.microsoft.com/en-us/sql-server/sql-server-downloads)


1. Open your SSMS.
2. Load and execute script like:
   - Create a new database called **AxiaStores**
   - Create **CustomerTB**, **ProductTB**, and **OrdersTB** tables using proper data types and data constraints
   - Populate **CustomerTB**, **ProductTB**, and **OrdersTB** tables with the necessary data
   - Anwser analytical questions and run queries, save and document results for reporting and insights
  
## Key Analytical Questions 
The queries in this project aim to answer the following key questions based on the AxiaStores dataset: 
1. Return the FirstName and Email of every customer who has ever purchased the product “Wireless Mouse”
2. List all customers’ full names in ascending alphabetical order (LastName, then FirstName)
3. Show every order together with the customer’s full name, the product name, quantity, unit price, total price (quantity × unit price), and order date
4. Show average sales per product category and sort in descending order
5. Which city generated the highest revenue for AxiaStores


 ## Samples of SQL Queries and Results.
 Here are examples of key queries used in the project and their results: 
 1. **CREATING DATABASE**
<pre> 
CREATE DATABASE [AxiaStores]; --SQL Server
</pre>

2. **CREATING CustomerTB**
<pre> 
CREATE TABLE CustomerTB 
(CustomerID INT PRIMARY KEY, 
FirstName VARCHAR (255), 
LastName VARCHAR (255), 
Email VARCHAR (255), 
Phone VARCHAR (50), 
City VARCHAR (100));
INSERT INTO CustomerTB (CustomerID, FirstName, LastName, Email, Phone, City) 
VALUES
(1, 'Musa', 'Ahmed', 'musa.ahmed@hotmail.com', '0803‑123‑0001', 'Lagos'),
('2', 'Ray', 'Samson', 'ray.samson@yahoo.com', '0803‑123‑0002', 'Ibadan'), 
('3', 'Chinedu', 'Okafor', 'chinedu.ok@yahoo.com', '0803‑123‑0003', 'Enugu'),
('4', 'Dare', 'Adewale', 'dare.ad@hotmail.com', '0803‑123‑0004', 'Abuja'), 
('5', 'Efe', 'Ojo', 'efe.oj@gmail.com', '0803‑123‑0005', 'Port Harcourt'), 
('6', 'Aisha', 'Bello', 'aisha.bello@hotmail.com', '0803‑123‑0006', 'Kano'),
('7', 'Tunde', 'Salami', 'tunde.salami@yahoo.com', '0803‑123‑0007', 'Ilorin'),
('8', 'Nneka', 'Umeh', 'nneka.umeh@gmail.com', '0803‑123‑0008', 'Owerri'), 
('9', 'Kelvin', 'Peters', 'kelvin.peters@hotmail.com', '0803‑123‑0009', 'Asaba'),
('10', 'Blessing', 'Mark', 'Blessing.mark@gmail.com', '0803‑123‑0010', 'Uyo');
</pre> 

![image alt](https://github.com/JoshuaGee-bit/SQL-Projects/blob/01405202269d7c5220bf59948c941d86b60643a5/CustomerTB.png)


## Answers to Analytical Questions and Results 
1. **Return the FirstName and Email of every customer who has ever purchased the product “Wireless Mouse”**
<pre> 
--Return the FirstName and Email of every customer who has ever purchased the product “Wireless Mouse” 
select c.firstname, c.email from customerTB c
join OrdersTB o on c.CustomerID = o.CustomerID 
join ProductTB p on o.ProductID = p.ProductID 
where p.ProductID=1 
</pre> 

![image alt](https://github.com/JoshuaGee-bit/SQL-Projects/blob/697671aa1bb335e9f63d46a98222a677cf4b4092/Return%20the%20FirstName%20and%20Email%20of%20every%20customer%20who%20has%20ever%20purchased%20the%20product%20Wireless%20Mouse.png)
