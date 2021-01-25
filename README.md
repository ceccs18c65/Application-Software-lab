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

# Application-Software-Development-Lab9

Assignment -9

ASD_Lab_Experiment

#1
create table employee(code char(4) primary key,name varchar(60),dob date,designation varchar(80),salary float);
insert into employee(code,name,dob,designation,salary)values('abc1','Shijin','1997-11-12','ceo',19000),
('abc2','Arun','1998-12-12','sales',20000),('abc3','Abin','2001-07-05','hr',45000);

#2
select code,name,designation from employee order by name desc;

#3
create table deposit(baccno bigint(20),branch_name varchar(20),amount float);
insert into deposit(baccno,branch_name,amount)values(12345,'Pathanamthitta',100000),
(67891,'Pathanamthitta',250000),(11121,'Pathanamthitta',223000);
insert into deposit values(12131,'Edayaranmula',180300);
insert into deposit values(14145,'Edayaranmula',500000);

#4
select branch_name,count(baccno),sum(amount)from deposit group by  branch_name;


# Application-Software-Development-Lab10
Assignment-10


CREATE TABLE CUR (
	name CHAR(10),
    dob DATE,
    salary INT(11)
);

DELIMITER //

CREATE PROCEDURE IMP()
BEGIN
	DECLARE done INT DEFAULT FALSE;
    DECLARE emp_name CHAR(10);
    DECLARE emp_dob DATE;
    DECLARE emp_salary INT(11);
    DECLARE emp_record CURSOR FOR SELECT name,dob,salary FROM employee;
    DECLARE CONTINUE HANDLER FOR NOT FOUND SET done = TRUE;
    OPEN emp_record;
    read_loop: LOOP
		FETCH emp_record INTO emp_name,emp_dob,emp_salary;
        IF done THEN
			LEAVE read_loop;
		END IF;
        INSERT INTO CUR VALUES(emp_name,emp_dob,emp_salary);
	END LOOP;
    CLOSE emp_record;
END;//
DELIMITER ;

CALL IMP();

SELECT * FROM CUR;


# Application-Software-Development-Lab11

Experiment-11


CREATE TABLE EMPLOYEE (
CODE VARCHAR(10),
NAME CHAR(20),
DOB DATE NOT NULL,
DESIGNATION CHAR(25),
SALARY INT
);
INSERT INTO EMPLOYEE VALUES ('E69','AMINA','1990-06-14','CLERK','40000');
INSERT INTO EMPLOYEE VALUES ('E37','RAHUL','1989-12-08','PROJECT DESGINER','60000');
INSERT INTO EMPLOYEE VALUES ('E93','MANEESHA','1992-02-18','SALES MANAGER','50000');
INSERT INTO EMPLOYEE VALUES ('E08','ADITYA','1992-04-22','CLERK','40000');
INSERT INTO EMPLOYEE VALUES ('E29','RADIKA','1984-09-26','ACCOUNTANT','48000');

DELIMITER $$
CREATE TRIGGER INSERT_PREVENT
BEFORE INSERT
ON EMPLOYEE FOR EACH ROW
BEGIN
IF (CURRENT_TIME() BETWEEN '17:00' AND '00:00' ) THEN
SIGNAL SQLSTATE '45000' SET MESSAGE_TEXT = 'NO CHANGES TO EMPLOYEE TABLE';
END IF;
END $$
DELIMITER ;

DELIMITER $$
CREATE TRIGGER UPDATE_PREVENT
BEFORE UPDATE
ON EMPLOYEE FOR EACH ROW
BEGIN
IF (CURRENT_TIME() BETWEEN '17:00' AND '00:00' ) THEN
SIGNAL SQLSTATE '45000' SET MESSAGE_TEXT = 'NO CHANGES TO EMPLOYEE TABLE';
END IF;
END $$
DELIMITER ;

DELIMITER $$
CREATE TRIGGER DELETE_PREVENT
BEFORE DELETE
ON EMPLOYEE FOR EACH ROW
BEGIN
IF (CURRENT_TIME() BETWEEN '17:00' AND '00:00' ) THEN
SIGNAL SQLSTATE '45000' SET MESSAGE_TEXT = 'NO CHANGES TO EMPLOYEE TABLE';
END IF;
END $$
DELIMITER ;

# Application-Software-Development-Lab12

Experiment-12


SELECT a.sid, a.sname, a.rating, a.age
FROM sailors AS a
INNER JOIN reserves AS c ON a.sid = c.sid AND c.bid =101;

SELECT b.bname
FROM reserves AS c
INNER JOIN sailors AS a ON a.sid = c.sid AND a.sname = 'Bob'
INNER JOIN boats AS b ON b.bid = c.bid;

SELECT a.sname
FROM sailors AS a
INNER JOIN reserves AS c ON a.sid = c.sid
INNER JOIN boats AS b ON b.bid = c.bid AND b.colour = 'red'
ORDER BY a.age;

SELECT DISTINCT a.sname
FROM sailors AS a
INNER JOIN reserves AS c ON a.sid IN (c.sid);

SELECT a.sid,a.sname
FROM reserves AS c
INNER JOIN reserves AS d ON c.sid <> d.sid AND c.day = d.day
INNER JOIN sailors AS a ON d.sid = a.sid;
