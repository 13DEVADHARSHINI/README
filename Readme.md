

         COLUMN FAMILY DATABASE

       (CASSENDRA DATABASE)

To create a Cassandra database for a college management system, we would first need to identify the different entities that we need to store data for, and then create tables accordingly using Cassendra query language.


 First we create a KEYSPACE.and then use the database.the database is college_managenent_system
        
         CREATE KEYSPACE college_management_system WITH replication = {'class': 'SimpleStrategy', 'replication_factor': '3'};

The tables are:
              students
              courses
              enrollements
              grades

The student table include
           student_id (UUID PRIMARY KEY)
           first_name                          
           last_name 
           email 
           phone 
           address 
           date_of_birth 

The courses table include
          course_id (UUID PRIMARY KEY)
          course_name 
          department
          instructor
          start_date
          end_date


The enrollements table include
         student_id (UUID)
         course_id (UUID)
         enroll_date 


The grades table include
        student_id (UUID)
        course_id (UUID)
        grade 

Syntax for creating a table
           

        CREATE TABLE <table_name> (
       <column_name> <data_type>,
       <column_name> <data_type>,
       PRIMARYKEY(<partition_key_column_name>,     <clustering_column_name>)
);

        CREATE TABLE
             
          CREATE TABLE students (
         student_id UUID,
         first_name text,
         last_name text,
         email text,
         phone_number text,
         address text,
         PRIMARY KEY ((student_id))
);




     CREATE TABLE courses (
    course_id UUID PRIMARY KEY,
    course_name TEXT,
    department TEXT,
    instructor TEXT,
    start_date DATE,
    end_date DATE
);

CREATE TABLE enrollments (
    student_id UUID,
    course_id UUID,
    enroll_date DATE,
    PRIMARY KEY (student_id, course_id)
);

CREATE TABLE grades (
    student_id UUID,
    course_id UUID,
    grade INT,
    PRIMARY KEY (student_id, course_id)
);


To adding values to the attribute are performed below.

INSERT INTO TABLE

students
             
        college_management_system> INSERT INTO students (student_id, first_name, last_name, email, phone, address, date_of_birth) VALUES ('IT1', 'deva', 'T', 'tdeva@example.com', '9994986798', '123 Main St', '2003-08-13');

college_management_system> INSERT INTO students (student_id, first_name, last_name, email, phone, address, date_of_birth) VALUES ('IT2', 'jan', 'M', 'jan@example.com', '8790986798', '13 second St', '2003-02-27');

college_management_system> INSERT INTO students (student_id, first_name, last_name, email, phone, address, date_of_birth) VALUES ('IT3', 'dhivya', 'R', 'dhivya@example.com', '80436798', '123 first St', '2003-08-17');

college_management_system> INSERT INTO students (student_id, first_name, last_name, email, phone, address, date_of_birth) VALUES ('IT4', 'madu', 'S', 'madu@example.com', '4567891298', '123 Main St', '2003-08-23');




courses

college_management_system> INSERT INTO courses (course_id, course_name, department, instructor, start_date, end_date) VALUES ('C11', 'JAVA', 'IT', 'Ram', '2023-09-01', '2023-12-15');

college_management_system> INSERT INTO courses (course_id, course_name, department, instructor, start_date, end_date) VALUES ('C12', 'C++', 'CSE', 'Raji', '2023-09-21', '2023-12-6');

college_management_system> INSERT INTO courses (course_id, course_name, department, instructor, start_date, end_date) VALUES ('C13 ', 'PYTHON', 'IT', 'dhivya', '2023-09-11', '2023-12-11');

college_management_system> INSERT INTO courses (course_id, course_name, department, instructor, start_date, end_date) VALUES ('C14 ', 'HTML', 'CSE', 'madu', '2023-09-21', '2023-12-8');



enrollements
     
    college_management_system> INSERT INTO enrollments (student_id, course_id, enroll_date) VALUES ('E1', 'C14', '2023-09-01');


                                                                       ^
college_management_system> INSERT INTO enrollments (student_id, course_id, enroll_date) VALUES ('E2', 'C12', '2023-09-13');

college_management_system> INSERT INTO enrollments (student_id, course_id, enroll_date) VALUES ('E3', 'C13', '2023-09-11');

college_management_system> INSERT INTO enrollments (student_id, course_id, enroll_date) VALUES ('E4', 'C11', '2023-09-21');

    
grades
   
      college_management_system> INSERT INTO grades (student_id, course_id, grade) VALUES ('IT1â€™, 'C14' , 85);

college_management_system> INSERT INTO grades (student_id, course_id, grade) VALUES ('IT2 ', 'C13', 95);

college_management_system> INSERT INTO grades (student_id, course_id, grade) VALUES ('IT3 ', 'C12', 98);

college_management_system> INSERT INTO grades (student_id, course_id, grade) VALUES ('IT4 ', 'C11' , 89);


DELETE VALUES IN TABLE

      college_management_system> DELETE            FROM students WHERE student_id = 'IT4 ';

college_management_system> DELETE FROM courses WHERE course_id = 'C12';

        


       UPDATE TABLE

         college_management_system> UPDATE students SET first_name = 'kani', last_name = 'S' WHERE student_id ='IT2' ;



                                                           
college_management_system> UPDATE courses SET instructor = 'Johh' WHERE course_id = 'C14' ;

college_management_system> UPDATE grades SET grade = 100 WHERE student_id = 'IT3' AND course_id = 'C12';


SEARCH TABLE


      college_management_system> SELECT * FROM students;



CONCLUSION
     
      This readme file explain about how to create tables using cassendra query language and perform opreations like insert,delete,update and search.



