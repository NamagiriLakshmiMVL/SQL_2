
DB design for Zden guvi class has been designed in below sheet for refernce https://docs.google.com/spreadsheets/d/1YcuvEMSHERcPNr2vwtu-33fxdgT31Phc2bxWfdWL9LA/edit#gid=0

SCREENSHOT:
https://user-images.githubusercontent.com/26063120/163723022-3c6c6cba-807e-4d26-9791-8b2b8d37b2f6.png




Queries for above Table creation

STUDENT TABLE

1.Creating Student Table 
CREATE TABLE STUDENT (
    Student_ID int PRIMARY KEY,
    Name varchar(20),
    Batch_ID int,
    Fees_paid varchar(3),
    Task_ID int,
    Mentor_id int,
    Experience int,
    Joined_on varchar(20),
    Placement_eligible varchar(3),
    FOREIGN KEY (Batch_ID) REFERENCES Batch(Batch_ID)
    FOREIGN KEY (TASK_ID) REFERENCES TASK(TASK_ID)
    FOREIGN KEY (MENTOR_ID) REFERENCES MENTOR(MENTOR_ID)
);
2.INSERTING VALUES TO STUDENT TABLE
INSERT INTO STUDENT VALUES( 1,"sid01",1,"yes",1,2,0,"AUG 2023","yes");
INSERT INTO STUDENT VALUES( 2,"sid02",4,"no",3,2,0,"JAN 2024","no");
INSERT INTO STUDENT VALUES( 3,"sid03",3,"no",4,3,1,"SEP 2023","no");
INSERT INTO STUDENT VALUES( 4,"sid04",1,"yes",2,1,2,"JUNE 2023","no");
INSERT INTO STUDENT VALUES( 5,"sid05",2,"no",2,1,0,"OCT 2023","no");
3.RETRIEVING ALL FIELDS WITH DATA
SELECT * from STUDENT







BATCH TABLE

1.Creating Batch Table
CREATE TABLE BATCH (
    Batch_ID int PRIMARY KEY,
    Name varchar(20),
    Start_date varchar(10),
    Mentor_id int,
    Topics_covered varchar(20),
    language varchar(10),
  FOREIGN KEY (Mentor_ID) REFERENCES Mentor(Mentor_ID)
);
2.INSERTING VALUES INTO BATCH
INSERT INTO BATCH VALUES( 1,"B01WD","AUG 2023",3,"Node","yes");
INSERT INTO BATCH VALUES( 2,"B02WE","JAN 2024",1,"Mongo","no");
INSERT INTO BATCH VALUES( 3,"B03WD","SEP 2023",2,"React","no");
INSERT INTO BATCH VALUES( 4,"B04WE","JUNE 2023",3,"Advanced JS","no");


TASK TABLE

1.Creating TASK Table
CREATE TABLE TASK (
    Task_ID int PRIMARY KEY,
    Name varchar(20),
    Difficuly_level varchar(10),
    Person_ID int,
    Topic varchar(20),
    Success_rate int  ,
  FOREIGN KEY (Person_ID) REFERENCES TASK_CREATION(Person_ID)
);
2.INSERTING VALUES INTO TASK
INSERT INTO TASK VALUES( 1,"q1","hard",1,"js",67);
INSERT INTO TASK VALUES( 2,"q2","medium",2,"React",75);
INSERT INTO TASK VALUES( 3,"q3","easy",3,"Node",97);
INSERT INTO TASK VALUES( 4,"q4","medium",4,"React",83);
INSERT INTO TASK VALUES( 4,"q5","easy",1,"SQL",99);


MENTOR TABLE

1.Creating MENTOR Table
CREATE TABLE MENTOR (
    MENTOR_ID int PRIMARY KEY,
    Name varchar(20),
    Company varchar(2),
    Gender varchar(6),
    Experience int,
    Schedule varchar(20),
    Timings int,
);
2.INSERTING VALUES INTO MENTOR
INSERT INTO MENTOR VALUES( 1,"AAA","C1","Male",3,"Weekday","10-11");
INSERT INTO MENTOR VALUES( 2,"BBB","C2","Female",6,"Weekend","3-4");
INSERT INTO MENTOR VALUES( 3,"CCC","C3","Male",1,"Weekend","4-7");
INSERT INTO MENTOR VALUES( 4,"DDD","C4","Female",5,"Weekday","5-6");
INSERT INTO MENTOR VALUES( 4,"EEE","C5","Female",1,"Weekend","1-2");


TASK_CREATION TABLE

1.Creating TASK_CREATION Table
CREATE TABLE TASK_CREATION (
    PERSON_ID int PRIMARY KEY,
    Name varchar(20),
    Role varchar(2),
);
2.INSERTING VALUES INTO MENTOR
INSERT INTO MENTOR VALUES( 1,"PERSON-A","Co-Ordinator");
INSERT INTO MENTOR VALUES( 2,"PERSON-Z","Mentor");
INSERT INTO MENTOR VALUES( 3,"PERSON-B","Manager");
INSERT INTO MENTOR VALUES( 4,"PERSON-G","Interviewer");


