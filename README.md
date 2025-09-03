# NullClass-Internship
TASK1 - Create an RDS MySQL Database and Connect from EC2 Launch an RDS MySQL instance inside your VPC. Modify the security group to allow connections from your EC2 instance. Connect to the database from your EC2 instance using MySQL CLI

🚀 Create an RDS MySQL Database and Connect from EC2

This guide explains how to launch an RDS MySQL instance inside a VPC, allow EC2 to connect, and use MySQL CLI to manage the database.

   Launch EC2 Instance

1. Go to AWS Console → EC2 → Launch Instance.
2. Choose Amazon Linux 2 or Ubuntu.
3. Select t2.micro (Free tier).
4. Ensure it is inside your VPC.
5. Modify Security Group for RDS
    Go to EC2 → Security Groups.
    Edit Inbound rules → Add MySQL/Aurora (3306).
    Source: IPV4 Anywhere or your IP for testing.
   

   Launch RDS MySQL Instance
1. Go to AWS Console → RDS → Create Database.
2. Select:
    Engine: MySQL
3. Template: Free tier (for this project)
4.Instance class: db.t3.micro
5.Storage: General Purpose (20GB)
6.Username/Password: Set your credentials for MYSQl server
7.Ensure it is inside your VPC same as that of EC2-instance.


   Install MySQL Client on EC2
For Ubuntu:
    1.sudo apt update
    2.sudo apt install mysql-client -y

    Connect EC2 to RDS
1.mysql -h <RDS-ENDPOINT> -u <USERNAME> -p
2.Enter the password → You’re connected to the MYSQL server


    MySQL CLI Commands
SHOW DATABASES;
CREATE DATABASE NullClass;
USE NullClass;

CREATE TABLE employees (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    department VARCHAR(100),
    salary INT
);

INSERT INTO employees (name, department, salary) 
VALUES ('Vidumukhi', 'DevOps', 80000);

SELECT * FROM employees;

CREATE TABLE Interns (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    department VARCHAR(100),
    stipend INT
);

INSERT INTO Interns (name, department, stipend) 
VALUES ('Shivani', 'Cloud_Intern', 8000);

SELECT * FROM Interns;

SHOW TABLES;

DESCRIBE employees;

DESCRIBE Interns;

EXIT;










