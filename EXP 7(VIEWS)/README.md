                                                                 VIEWS

1.	Create View PassengerView As Select * from Passenger; 
2.	Select Passengerno,name from Passenger where Destinationid in(10,30); 
3.	Create View Reservation_vw As Select reservation_id from reservation; 
4.	Insert into Reservation_vw values(1126,’Brijesh’,20);
5.	Update Reservation_vw set busid=30 where busroute=”Hyderabad”;
6.	Delete from Reservation_vw where busid=30;


QUERY:
CREATE TABLE Bus(bus_no int ,Sources VARCHAR(20),Destination VARCHAR(20));
INSERT INTO Bus VALUES('31','Hyderabad','Chennai');
INSERT INTO Bus VALUES('24','kadapa',   'Hyderabad');
INSERT INTO Bus VALUES('125','kurnool',  'Chennai');
INSERT INTO Bus VALUES('126','Hyderabad','banglore');
SELECT * FROM Bus;
ALTER TABLE Bus ADD (Color VARCHAR(20));
UPDATE Bus SET Destination ='Tirupati' WHERE bus_no = '123';
SELECT * FROM Bus;

CREATE TABLE Passengers(P_name VARCHAR(20),P_id INT,Gender VARCHAR(20),Age INT,P_destination VARCHAR(20),P_destinationid INT);
INSERT INTO Passengers VALUES('Seetha',123,'Female',25,'Bharagiri',30);
INSERT INTO Passengers VALUES('Ramayaih',741,'male',45,'Banglore',10);
INSERT INTO Passengers VALUES('Navya',456,'Female',20,'kadapa',44);
INSERT INTO Passengers VALUES('Ravi',852,'male',32,'chennai',11);
SELECT * FROM Passengers;
DELETE FROM Passengers P  WHERE P_name = 'Navya';
SELECT * FROM Passengers;
UPDATE Passengers SET P_name ='Ramesh' WHERE P_id = '852';
SELECT * FROM Passengers;

CREATE TABLE Ticket(T_id int,T_name VARCHAR(20), Sources VARCHAR(20),  Destination VARCHAR(20),P_id int,bus_no int);
INSERT INTO Ticket VALUES(1,'Seetha','Hyderabad','chennai',123,30);
INSERT INTO Ticket VALUES(2,'Ramayaih','Kadapa','mydukuru',741,24);
INSERT INTO Ticket VALUES(3,'Navya','Kurnool','chennai',456,125);
INSERT INTO Ticket VALUES(4,'Ravi','Hyderabad','banglore',852,126);
DELETE FROM Ticket T  WHERE Sources = 'Kadapa';
SELECT * FROM Ticket;
UPDATE Ticket SET Destination  ='Amaravathi' WHERE P_id = '456';
SELECT * FROM Ticket;

CREATE TABLE Cancellation(C_id INT, T_id INT,P_id INT, seat_no VARCHAR(20), contact BIGINT, C_name VARCHAR(20));
INSERT INTO Cancellation VALUES(01, 1,123, "L67", 958607849, "Seetha");
INSERT INTO Cancellation VALUES(02,2, 741, "L42", 567485960, "Ramayaih");
INSERT INTO Cancellation VALUES(03, 4,852, "L52", 475638596, "Ravi");
SELECT * FROM Cancellation;


Create View PassView As Select * from Passengers;
Select P_id,P_name from PassView where P_destinationid in(10,30); 
Create View TicView As Select T_id from Ticket;
select * from TicView;
Create View CanView As Select * from Cancellation;
SELECT * FROM CanView;
CREATE View BusView AS Select * From Bus;
Update BusView set bus_no=30 where Destination = 'Hyderabad';
select * From BusView;
CREATE View TicketView As SELECT * FROM Ticket;
Delete from TicketView where bus_no = 30; 
SELECT * From TicketView;
