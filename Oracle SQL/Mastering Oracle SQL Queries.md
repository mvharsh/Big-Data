

# Creating table and insertion:

#### i) Creating Employee table with the following fields [eno,ename,edob,eage,egender,esal,eadd,dno] and insert fifteen records

      CREATE TABLE employee
      (
       eno INT,
       ename VARCHAR(30),
       edob DATE,
       eage INT,
       egender VARCHAR(6),
       esal DECIMAL(12,2),
       eadd VARCHAR(100),
       dno INT REFERENCES department(dno)
      );

      DESCRIBE employee

![image](https://github.com/mvharsh/Big-Data/assets/111365320/7daacfcb-be64-4cf8-a021-bb91b8225c04)

      INSERT ALL
      
      INTO employee(eno, ename, edob, eage, egender, esal, eadd, dno) VALUES (101, 'Harshini', '10/19/1980', 43, 'Female', '2500.00', 'Madurai', 1)
      INTO employee(eno, ename, edob, eage, egender, esal, eadd, dno) VALUES (102, 'Sweatha', '11/10/1977', 46, 'Female', '3000.00', 'Trichy', 1)
      INTO employee(eno, ename, edob, eage, egender, esal, eadd, dno) VALUES (103, 'Harish', '12/11/1975', 48, 'Male', '5500.50', 'Chennai', 1)
      INTO employee(eno, ename, edob, eage, egender, esal, eadd, dno) VALUES (104, 'Vivek', '02/09/1982', 41, 'Male', '4000.00', 'Coimbatore', 2)
      INTO employee(eno, ename, edob, eage, egender, esal, eadd, dno) VALUES (105, 'Ramya', '03/07/1981', 42, 'Female', '6500.00', 'Madurai', 2)
      INTO employee(eno, ename, edob, eage, egender, esal, eadd, dno) VALUES (106, 'Janani', '09/22/1980', 43, 'Female', '7000.50', 'Trichy', 2)
      INTO employee(eno, ename, edob, eage, egender, esal, eadd, dno) VALUES (107, 'Tinesh', '08/30/1983', 40, 'Male', '2500.00', 'Coimbatore', 2)
      INTO employee(eno, ename, edob, eage, egender, esal, eadd, dno) VALUES (108, 'Jessica', '04/23/1984', 39, 'Female', '8000.00', 'Madurai', 3)
      INTO employee(eno, ename, edob, eage, egender, esal, eadd, dno) VALUES (109, 'Sanjay', '07/15/1976', 47, 'Male', '3500.00', 'Trichy', 3)
      INTO employee(eno, ename, edob, eage, egender, esal, eadd, dno) VALUES (110, 'Sofen', '10/20/1977', 46, 'Male', '4000.50', 'Coimbatore', 4)
      INTO employee(eno, ename, edob, eage, egender, esal, eadd, dno) VALUES (111, 'Vinodh', '06/16/1975', 48, 'Male', '4500.00', 'Madurai', 4)
      INTO employee(eno, ename, edob, eage, egender, esal, eadd, dno) VALUES (112, 'Naveen', '10/04/1983', 40, 'Male', '2000.00', 'Trichy', 5)
      INTO employee(eno, ename, edob, eage, egender, esal, eadd, dno) VALUES (113, 'Anu', '05/13/1981', 42, 'Female', '3500.50', 'Chennai', 5)
      INTO employee(eno, ename, edob, eage, egender, esal, eadd, dno) VALUES (114, 'Rekha', '10/18/2006', 17, 'Female', '3000.00', 'Coimbatore', 5)
      INTO employee(eno, ename, edob, eage, egender, esal, eadd, dno) VALUES (115, 'Jaya', '04/25/1977', 46, 'Female', '5000.00', 'Trichy', 5)
      
      SELECT * FROM DUAL

#### ii) Creating Department table with the following fields [dno,dname,dhead,dlocation] and insert any five records

      CREATE TABLE department
      (
       dno INT PRIMARY KEY NOT NULL,
       dname VARCHAR(30),
       dhead VARCHAR(30),
       dlocation VARCHAR(60)
      );
      
      DESCRIBE department
      
![image](https://github.com/mvharsh/Big-Data/assets/111365320/48d3deba-17ec-40a6-8772-04029581b8c7)

      INSERT ALL
      
      INTO department(dno, dname, dhead, dlocation) VALUES (1, 'Finance', 'Dinesh', 'Madurai')
      INTO department(dno, dname, dhead, dlocation) VALUES (2, 'Healthcare', 'Prakash', 'Madurai')
      INTO department(dno, dname, dhead, dlocation) VALUES (3, 'Cybersecurity', 'Kumar', 'Coimbatore')
      INTO department(dno, dname, dhead, dlocation) VALUES (4, 'Data Science', 'Ramesh', 'Madurai')
      INTO department(dno, dname, dhead, dlocation) VALUES (5, 'Sales', 'Suresh', 'Coimbatore')
      
      SELECT * FROM DUAL

# Selecting records:

 
#### 1) Display all the employee details.
	  SELECT * FROM employee

![image](https://github.com/mvharsh/Big-Data/assets/111365320/6d3bb830-755d-4f6b-8fa3-d003275f72e6)
 

 #### 2) Display all department information.
	  SELECT * FROM department

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/0af0afa7-9004-45c3-b5d0-8d969a71f03e)


 #### 3) Display eno,ename and esal details from employee table.
	  SELECT eno, ename, esal FROM employee

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/c08d9465-9820-45fc-8627-79854ae957bc)


  #### 4) Display the all female employee name list.
	  SELECT ename FROM employee WHERE egender='Female'

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/47a2348f-d12d-46b3-a773-10a299c5b412)


  #### 5) Display the all employee details whose eno less than 105.
	  SELECT * FROM employee WHERE eno < 105

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/1b5f39e3-937a-4d00-9f5f-6c71f95d1cb8)


  #### 6) Display the all male employee names whose age greater than 45.
	  SELECT ename FROM employee WHERE egender='Male' AND eage>45

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/a148bcf5-10c2-42b1-8d7a-66400cc16c46)


 ####  7) List out the name of the employee who is belongs to the department no 3.
	  SELECT ename FROM employee WHERE dno=3
 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/73cd7ae4-ce7f-4a4d-92bb-1f1830c2d7ba)


  #### 8) List out all the department number uniquely from the employee table. 
	  SELECT DISTINCT dno FROM employee
![image](https://github.com/mvharsh/Big-Data/assets/111365320/b04062d4-e63b-4943-8513-3408fcc15530)

 
  #### 9) List out the department number and their head in-charges.
	  SELECT dno, dhead FROM deparment

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/6386bbec-2f49-4d08-96d7-5a2d8f53d941)


  #### 10) Display the total number of employees working in the company.
	  SELECT COUNT(eno) AS total FROM employee
 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/069ec8fe-f305-4795-a686-3a29e3feb6b2)


  #### 11) Display the total number of employees working in the department no 2.
	  SELECT COUNT(eno) AS total FROM employee WHERE dno=2
 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/0d947cb0-430c-47ec-92b7-bdb43125dce7)


  #### 12) Display the names of the employee who is working in department number 3 with the age is greater than 40.
	  SELECT ename FROM employee WHERE dno=3 AND eage>40
![image](https://github.com/mvharsh/Big-Data/assets/111365320/469e203e-5105-41ca-bc13-90281d74a11f)

  #### 13) Display the names of the employee who’s getting salary between 2000 and 5000.
	  SELECT ename FROM employee WHERE esal BETWEEN 2000 AND 5000

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/a6dd4da9-dbbf-4d6f-b214-db67b6d9110f)

  #### 14)Display the names of the employee whose is not belongs to either department number 1 or 2.
	  SELECT ename FROM employee WHERE dno<>1 AND dno<>2
 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/d257c6f2-df7f-4c8d-9995-7fddc8fc51dd)


 #### 15) Who is getting maximum salary in the company.
	  SELECT ename FROM employee WHERE esal = (SELECT MAX(esal) FROM employee)
 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/e850582e-bd3d-422f-b09e-982940cc1c7a)


  #### 16) Who is getting minimum salary in the company.
	  SELECT ename FROM employee WHERE esal = (SELECT MIN(esal) FROM employee)
 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/6e607444-d862-4953-bf26-f4af10138031)

 #### 17) Who is getting maximum salary in the department number
	  SELECT e1.ename, e1.esal, e1.dno FROM employee e1 WHERE e1.esal= ( SELECT MAX(e2.esal) FROM employee e2 WHERE e2.dno = e1.dno)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/4dbae045-d59a-4c85-9861-9868874afaa9)

 #### 18) What is the average salary the company given to the employee.
      	SELECT AVG(esal) AS average FROM employee 
![image](https://github.com/mvharsh/Big-Data/assets/111365320/eb6058dc-670c-4e56-baf5-511d8283892e)

  #### 19) List out the employee names whose name is starts with the character “s”
	    SELECT ename FROM employee WHERE ename LIKE 'S%'
![image](https://github.com/mvharsh/Big-Data/assets/111365320/8fa3a7b7-9db6-450e-9ecf-09611b370902)

 #### 20) List out the employee names whose name is ends with the character “n”.
	    SELECT ename FROM employee WHERE ename LIKE '%n'

![image](https://github.com/mvharsh/Big-Data/assets/111365320/30cc1a68-af2f-4f35-9789-fbd7b9c51b48)

  #### 21) Display the employee details who is living either in Madurai or Trichy.
	    SELECT * FROM employee WHERE eadd='Madurai' OR add='Trichy'

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/dbe32f01-5dd0-486d-b9fc-ae8bbacf96b1)

# Modify the records (Update and Delete Queries):

#### 1) Change the salary as Rs 10000 for any one of the employee.
	
	UPDATE employee
	SET esal = 10000 
	WHERE eno = 104;

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/20a457e1-cf66-44a9-bde4-644638c66237)


 ####  2) Increase the salary Rs 2000 for all female employees.
	
	UPDATE employee
	SET esal = esal + 2000 
	WHERE egender = 'Female';

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/69fd7ca1-9998-4402-9ea4-74297118717f)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/f0a1c8e1-5fbf-49b8-8eae-fb073e1a30d8)

 ####  3) Fix the salary Rs 6000 for all employees with the age less than 30.
	
	UPDATE employee
	SET esal = 6000 
	WHERE eage < 30;

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/ca6484c2-855d-4497-8184-81f378ced029)


 ####  4) Increase the salary Rs 1000 for all male employees working in the Department no 2.

	UPDATE employee
	SET esal = esal + 1000 
	WHERE egender = 'Male' AND dno = 2;

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/0bad93bf-c1a5-47f1-b876-0fa71041eb58)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/0cd1385b-d6da-48f4-9cdd-5b1f4652788c)

 ####  5) Fix the maximum salary for the employee with the age greater than 45.

	UPDATE employee
	SET esal = (SELECT MAX(esal) FROM employee) 
	WHERE eage > 45;

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/5ac98be8-6c71-4ffd-98f8-7078406591d3)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/ae5c8307-5df6-432f-8729-b70165256eb3)

 ####  6) Change the name of the employee as “johnson” whose eid is 103.
	UPDATE employee
	SET ename = 'Johnson' 
	WHERE eno = 103;

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/c346de52-17c8-47d6-9fb7-c9236fe3c8f0)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/4324db6a-e8f0-4bfb-8d50-f1dcecc71b69)

 ####  7) Fix the average salary for all employees who is belongs to madurai or Trichy
	UPDATE employee
	SET esal = (SELECT ROUND(AVG(esal), 2) FROM employee) 
	WHERE eadd='Madurai' OR eadd='Trichy';

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/9a46076e-c8d2-4366-b18a-855e272cfca9)
 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/909312e5-9aaf-48e2-8ddb-6e32ff72ee79)

  #### 8) Increase the salary Rs 2000 for the employee those who were born before 21st APR 1985.

	UPDATE employee
	SET esal = esal + 2000 
	WHERE edob < '04/21/1985';

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/ef72ea04-23dc-4e33-9fc8-2de830096890)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/43b6b9fc-1330-40b4-b979-aec9209d10ad)

  #### 9) Change the head of the department name as “J. Rajkumar” for the Department no 104.

	UPDATE department
	SET dhead = 'J. Rajkumar' 
	WHERE eno = 104;	

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/749e9f00-6dad-4764-8e57-0c1c5acb41b5)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/bb5947d2-fdd5-47e4-b525-1e6139ba3305)

 #### 10) Give the 20% increment of the salary for the employee who are not belongs to the department no 2,3,4.

	UPDATE employee
	SET esal = esal + esal*0.2 
	WHERE dno NOT IN (2,3,4);

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/e61326a5-e7b2-497f-aacb-da9314a26663)
 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/03810265-d6d2-4ce1-94fa-f5148b551eaa)

 ####  11) Delete the all employee details who get salary less than 5000.

    UPDATE employee SET esal = 3000 WHERE eno=103	
    DELETE FROM employee WHERE esal < 5000

![image](https://github.com/mvharsh/Big-Data/assets/111365320/d1be49c3-b455-4fe3-9159-7a5def1b3f21)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/1aa62da7-cd54-4d04-8044-7b69a29367c1)

  #### 12) Delete the details of employee who belongs to Chennai.

	DELETE FROM employee WHERE eadd = 'Chennai'

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/46d0f8ab-c921-4199-917b-21e6d99a5afb)
 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/28329a45-ba1b-4ffb-8140-85b177d06ff8)

  #### 13) Delete the employee details whose name start with the character “s”.

	DELETE FROM employee WHERE ename LIKE 'S%'
 
![image](https://github.com/mvharsh/Big-Data/assets/111365320/6bd0f543-eda3-4f6e-9bf6-66705dc29c06)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/61940516-4c7b-4a7f-88fa-82d4aad159bc)

  #### 14) Delete the all female employee whose age reach greater than 45.

	DELETE FROM employee WHERE egender='Female' AND eage>45

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/323c98a2-d023-46bb-bd23-740d51bb2e2c)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/e2a8739a-d7ee-4b31-982c-d3605669a8ff)

  #### 15) Delete the employee records whose age between 2nd Dec 2005 and 3rd Feb 2007.

	DELETE FROM employee WHERE edob BETWEEN '12/02/2005' AND '02/03/2007'

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/14cac1ed-0ea5-4d3e-aecd-c06918d994e9)
 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/bfe2a830-b5d7-4c97-ad1b-7f8312f74095)

# Modifying Tables (Alter, Truncate, Rename, Copy and Drop table):


 #### 1) Add a new column ‘edes’ in employee table. 

	ALTER TABLE employee
	ADD edes VARCHAR(100);

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/4de15b30-f499-458b-a564-402af66eca51)


 #### 2) Add a multiple columns email and econtact in employee table

  	ALTER TABLE employee
    ADD (email VARCHAR(100),
    econtact VARCHAR(15));

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/0cb7cf7c-ff61-4a18-bd28-17986e03ec64)


 #### 3) Modify the size of the column eadd in employee tables.

	ALTER TABLE employee
	MODIFY eadd VARCHAR(150); 

![image](https://github.com/mvharsh/Big-Data/assets/111365320/4ad1de43-3175-42f3-9edd-940044ed6cd2)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/ae0da799-3220-4ff6-8427-c5c0fc95459e)

 #### 4) Modify the data type for the column esal as float format (precision- 5, Scale – 2) 

	UPDATE employee SET esal = NULL;

  ALTER TABLE employee
	MODIFY esal DECIMAL(5,2); 

![image](https://github.com/mvharsh/Big-Data/assets/111365320/d6a20617-a418-4445-afb9-0fe5666588d9)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/f2a28c9a-5343-47f1-9879-5e17ffa7e0e1)

 #### 5) Rename the employee table 

	ALTER TABLE employee
	RENAME TO emp;
 
![image](https://github.com/mvharsh/Big-Data/assets/111365320/cbb1e24b-9e40-454e-b01f-6328579f907d)
![image](https://github.com/mvharsh/Big-Data/assets/111365320/97ffebf2-c4b9-421f-914e-8b4c629871c4)

 #### 6) Rename an existing column egender as esex in employee table

	ALTER TABLE emp
	RENAME COLUMN egender TO esex;

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/f7bcff05-ac00-4cd6-abef-eefa3f873b89)
 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/1185d595-edee-4883-8f9c-7f77a0908542)

 #### 7) Remove all the records from the employee table 

	CREATE TABLE employee AS SELECT * FROM emp;

	TRUNCATE TABLE emp;

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/e563dbc2-dd6e-42b2-ba55-08629fa434e6)

 #### 8) Recover the deleted records of employee table 

	SELECT * FROM employee;

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/4421fef1-1c60-4f93-996d-dd56cec66b8b)

 #### 9) Create the customer table and then drop it.

	CREATE TABLE customer (
    	  cust_id INT PRIMARY KEY,
    	  cust_name VARCHAR(50),
	  cust_amt DECIMAL(5,2),
	  cust_add VARCHAR(50)
	);

	DESCRIBE customer 

![image](https://github.com/mvharsh/Big-Data/assets/111365320/cbd47ce4-8093-4a71-ba47-0e6d9470f7ee)
 
	DROP TABLE customer;

![image](https://github.com/mvharsh/Big-Data/assets/111365320/8439bb15-bedc-48b6-b2e3-9be1c30aa97f)

 #### 10) Add default value for the field ‘email’ in employee table

  	ALTER TABLE employee
    ADD email_default VARCHAR(100) DEFAULT 'default@email.com';
 
![image](https://github.com/mvharsh/Big-Data/assets/111365320/2a2a1398-194a-4025-a847-7d242ab6314b)

    ALTER TABLE employee DROP COLUMN email;

    ALTER TABLE employee
    RENAME COLUMN email_default TO email;

![image](https://github.com/mvharsh/Big-Data/assets/111365320/9a20df15-e67b-44e4-8766-fe629c3d7079)


 #### 11) Set the Not Null for the field ‘ename’ in employee table

  	ALTER TABLE employee
    ADD new_ename VARCHAR(50);

![image](https://github.com/mvharsh/Big-Data/assets/111365320/c08bab3c-86f4-4fbd-b860-b3099405e8ed)

    UPDATE employee SET new_ename = ename;

![image](https://github.com/mvharsh/Big-Data/assets/111365320/acb63ea4-7fb7-4e0f-aa44-94e67f0bf7ec)

    ALTER TABLE employee 
    DROP COLUMN ename;
    
    ALTER TABLE employee
    RENAME COLUMN new_ename TO ename;

![image](https://github.com/mvharsh/Big-Data/assets/111365320/f6e0f6c9-99f1-4411-87e2-8d4239cbadac)

 #### 12) Drop the column email from employee table

  	ALTER TABLE employee	
  	DROP COLUMN email 

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/b5a541da-1d8f-441c-b04d-7acb322dc0d6)
 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/f4394009-5e6b-46bc-8f62-fba484648bd8)

 #### 13) Enable and Disable the primary key constraint

	ALTER TABLE employee
	ADD CONSTRAINT pk_eno PRIMARY KEY (eno);

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/9d618efb-148a-4c14-bbe8-4efe40b82827)

	ALTER TABLE employee
	DROP PRIMARY KEY;

 ![image](https://github.com/mvharsh/Big-Data/assets/111365320/45080cff-2f12-4bf7-b477-627bf71db050)



