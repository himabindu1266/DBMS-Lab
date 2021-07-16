DBMS LAB EXP: 9 STORED PROCEDURES:

SQL QUERY:
CREATE TABLE Employee(eid INT, ename VARCHAR(20), salary INT);
INSERT INTO Employee VALUES(1, 'suguna', 50000);
INSERT INTO Employee VALUES(2, 'balaji', 60000);
INSERT INTO Employee VALUES(3, 'achuth', 70000);
INSERT INTO Employee VALUES(4, 'Anju', 80000);
INSERT INTO Employee VALUES(5, 'seetharam', 90000);
INSERT INTO Employee VALUES(6, 'anusha', 50000);
INSERT INTO Employee VALUES(7, 'ammar', 90000);
INSERT INTO Employee VALUES(8, 'sitha', 40000);
SELECT * FROM Employee;

delimiter //
CREATE PROCEDURE myproc()
BEGIN
Select * from Employee where ename like 's%';
END;
CALL myproc();//



delimiter //
CREATE PROCEDURE myinputproc(IN salarytocompare REAL)
BEGIN
Select * from Employee where salary < salarytocompare;
END;
CALL myinputproc(80000);//

delimiter //
CREATE PROCEDURE myoutproc(OUT countofemp int)
BEGIN
Select count(*) INTO countofemp from Employee where salary<20000;
END;
Call myoutproc(@a);//  
Select @a;//

