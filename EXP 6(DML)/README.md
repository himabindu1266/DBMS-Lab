EXPERIMENT 6

Practicing DML Commands:
SELECT - retrieve data from the  database
INSERT - insert data into a table
UPDATE - updates existing data within a table
DELETE - deletes all records from a table, the space for the records remain

Query:
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

DELETE FROM Ticket T  WHERE Sources = 'Kadapa';
SELECT * FROM Ticket;

UPDATE Ticket SET Destination  ='Amaravathi' WHERE P_id = '456';
SELECT * FROM Ticket;

