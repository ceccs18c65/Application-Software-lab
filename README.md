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
