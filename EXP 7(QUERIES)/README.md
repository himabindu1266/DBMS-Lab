EXPERIMENT 7

In this week you are going to practice queries (along with sub queries) using ANY, ALL, IN, Exists, NOT EXISTS, UNION, INTERSECT, Constraints etc.

1.	Display unique PNR_no of all passengers.
2.	Display all the names of male passengers.
3.	Display the ticket numbers and names of all the passengers.
4.	Find the ticket numbers of the passengers whose name start with ‘r’ and ends with ‘h’.
5.	Find the names of passengers whose age is between 30 and 45.
6.	Display all the passengers names beginning with ‘A’
7.	Display the sorted list of passengers names

QUERY:
CREATE SCHEMA 19WH1A1266;
USE 19WH1A1266;
CREATE TABLE Bus(bus_no VARCHAR(20),Sources VARCHAR(20),Destination VARCHAR(20));
INSERT INTO Bus VALUES('TS123','Hyderabad','Chennai');
INSERT INTO Bus VALUES('TS124','kadapa',   'mydukuru');
INSERT INTO Bus VALUES('TS125','kurnool',  'Chennai');
INSERT INTO Bus VALUES('TS126','Hyderabad','banglore');
SELECT * FROM Bus;

DELETE FROM Bus b WHERE b.Sources ='Hyderabad';
SELECT * FROM Bus;

UPDATE Bus SET Destination ='Tirupati' WHERE bus_no = 'TS123';
SELECT * FROM Bus;
               
CREATE TABLE Passengers(P_name VARCHAR(20),P_id INT,Gender VARCHAR(20),Age INT,P_destination VARCHAR(20));
INSERT INTO Passengers VALUES('Seetha',123,'Female',25,'Bharagiri');
INSERT INTO Passengers VALUES('Ramayaih',741,'male',45,'Banglore');
INSERT INTO Passengers VALUES('Navya',456,'Female',20,'kadapa');
INSERT INTO Passengers VALUES('Ravi',852,'male',32,'chennai');
SELECT * FROM Passengers;

DELETE FROM Passengers P  WHERE P_name = 'Navya';
SELECT * FROM Passengers;

UPDATE Passengers SET P_name ='Ramesh' WHERE P_id = '852';
SELECT * FROM Passengers;



CREATE TABLE Ticket(T_id int, Sources VARCHAR(20),  Destination VARCHAR(20),P_id int);
INSERT INTO Ticket VALUES(1,'Hyderabad','banglore',123);
INSERT INTO Ticket VALUES(2,'Kadapa','chennai',741);
INSERT INTO Ticket VALUES(3,'Kurnool','chennai',456);
INSERT INTO Ticket VALUES(4,'Hyderabad','Bharagiri',852);

SELECT DISTINCT P.P_id FROM Passengers P ;

SELECT P.P_name FROM Passengers P WHERE P.Gender = 'male';

SELECT T.T_id,P.P_name FROM Ticket T,Passengers P WHERE P.P_id = T.P_id;

SELECT T.T_id FROM Ticket T ,Passengers P WHERE P.P_name LIKE 'R%h' AND P.P_id = T.T_id ;

 SELECT P.P_name FROM Passengers P WHERE  P.Age >= 30 AND  P.Age <= 45;
 
 SELECT P.P_name FROM Passengers P WHERE P.P_name LIKE 'A%';
 
 SELECT P.P_name FROM Passengers P ORDER BY P_name ASC;

