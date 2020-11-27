# Application-Software-Lab1

 #Lab1

#a
CREATE TABLE student (
	sno INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(50) NOT NULL,
    marks INT NOT NULL,
    dept VARCHAR(20) NOT NULL
);

#b
ALTER TABLE student ADD COLUMN age INT NOT NULL;

#c
ALTER TABLE student MODIFY COLUMN dept VARCHAR(10); 

#d
ALTER TABLE student DROP COLUMN marks;

#e
RENAME TABLE student TO students;

#f
TRUNCATE TABLE students;

#g
DROP TABLE students;


# Application-Software-Development-Lab2

ASP LAB 2
create table Employee (code char(4),name char(10),designation char(30), dob date, salary numeric) ;

Insert into Employee (code, name, designation, dob, salary) values("e1", "chikku", "manager", " 1997-01-05", 3500) ;

Insert into Employee (code, name, designation, dob, salary) values("e2", "abin", "manager", " 1997-04-08", 3000) ;

Select * from Employee;

Update Employee set salary="4000" Where code="e1";

Select * from Employee;

Delete from Employee;

Select * from Employee;

#code	name	designation	dob	salary
#e1	chikku	manager	1997-01-05	3500
#e2	abin	manager	1997-04-08	3000

#code	name	designation	dob	salary
#e1	chikku	manager	1997-01-05	4000
#e2	abin	manager	1997-04-08	3000

# Application-Software-Development-Lab3

#1
create table employe(emp_id varchar(4),Name varchar(10),Age int(2),primary key(emp_id));
insert into employe values("E1","Binu",22); 
insert into employe values("E2","Rijo",24);
insert into employe values("E3","Shijin",23);  
insert into employe values("E4","Sachin",25);

#2
create table employee_details(sno int(3),emp_id varchar(4),Department varchar(10),primary key(sno),
foreign key(emp_id) references employee(emp_id));
insert into employee_detail values(1,"E2","Finance");
insert into employee_detail values(2,"E2","Sales");
insert into employee_detail values(3,"E1","HR");
insert into employee_detail values(4,"E3","Marketing");
insert into employee_detail values(5,"E4","Purchasing");
 insert into employee_detail values(6,"E1","Production");
 insert into employee_detail values(7,"E3","Designing");
 select * from employee_detail;

 #3
 select * from employe where emp_id in (select emp_id from employee_detail);

# Aplication-Software-Development-Lab4

#1
use emdb;
create table department(Code varchar(10),Title varchar(10),Dept_name varchar(10),Dept_id varchar(5),
Salary int(6),primary key(Code),unique(Dept_name),check(Salary>2000));
insert into department values("D1","ABC","Designing","D1234",15000);
insert into department values("D2","DEF","Marketing","M5678",25000);
insert into department values("D3","GHI","Finance","F9101",10000);
insert into department values("D4","JKL","HR","H1213",20000);
select * from department;

#2
create table instructor(Name varchar(20) not null,Code varchar(10),ID int(5) default 00023);
insert into instructor values("Shijin","D1",00012);
insert into instructor values("Binu","D2",00043);
insert into instructor values("Elvin","D3",00056);
insert into instructor values("Amith","D4",00098);
select * from instructor;
