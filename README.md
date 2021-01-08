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

# Application-Software-Development-Lab5

Assignment -5

a)
create table class(id varchar(3),name char(10));

b)
insert into class values("a0","Amal"),("a1","Binu");

c)
select * from class;

d)
set autocommit=0;
start transaction;
insert into class values("a2","vivek");
select * from class;
savepoint class1;
insert into class values("a3","Arun");
select * from class;
savepoint class2;
rollback to class1;
select * from class;
commit;


# Application-Software-Development-Lab6

Assignment -6
ASD_Lab_Experiment

#a
create table store(order_no int(5),code varchar(10),item varchar(20),quantity int(2),price int(5),discound int(2),MRP int(5),primary key(order_no));

#b
insert into store values(10001,'A10001','onion',2,180,30,150);
insert into store values(10002,'A20001','tyre',1,559,25,720);
insert into store values(10003,'A30001','birlas',2,432,50,832);
insert into store values(10004,'A40001','juvain',4,1300,60,1500);

#c
select * from store;

#d
create view itm_qnty as select item,quantity from store;

#e
select * from itm_qty;

#f
drop view itm_qnty;


# Application-Software-Development- Lab7


Assignment -7

ASD_Lab_Experiment

#a
create table store(order_no int(5),code varchar(10),item varchar(20),quantity int(2),price int(5),discound int(2),mrp int(5),primary key(order_no));

#b
insert into store values(10001,"a0001","aazz",2,649,30,879);
insert into store values(10002,"a0002","bbzz",1,559,25,720);
insert into store values(10003,"a0003","cczz",2,432,50,832);
insert into store values(10004,"a0004","cczz",3,800,30,1255);

#c
select * from store;

#d
select mod(price,9) from store;

#e
select price,power(price,2) from store;

#f
select round(quantity div 7) from store;


# Application-Software-Development-Lab8

Assignment -8
ASD_Lab_Experiment

#1
create table employe(code char(6) primary key,name varchar(10),dob date,designation varchar(20),salary float);
#2
insert into employe(code,name,dob,designation,salary) values('abc1','Shijin','1997-11-12','Clerk',25000)
,('abc2','Binu','1997-05-05','AC mechanic',35000),('abc3','Alan','1999-11-02','Clerk',20000),
('abc4','Rijo','2000-01-12','Marketing Executive',30000);
#3
select sum(salary) from employe where designation='Clerk';
#4
select max(salary) from employe;
#5
select avg(salary) from employe;
#6
select min(salary) from employe;
#7
select count(*) from employe;
