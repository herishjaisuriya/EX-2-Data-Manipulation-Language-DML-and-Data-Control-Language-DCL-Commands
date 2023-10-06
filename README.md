# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
## AIM:
To create a manager database and execute DML queries using SQL.


## DML(Data Manipulation Language)
<div align="justify">
The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.
</div>

## List of DML commands: 
<div align="justify">
INSERT: It is used to insert data into a table.<br>
UPDATE: It is used to update existing data within a table.<br>
DELETE: It is used to delete records from a database table.<br>
</div>

## Create the table as given below:
```sql
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
## insert the following values into the table
```sql
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:
```sql
UPDATE manager SET salary=salary+(salary*0.10);
```
### OUTPUT:
![image](https://github.com/DHARINIPV/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119400845/db68c2de-d965-4641-92ab-4edf1a80db8c)
![image](https://github.com/DHARINIPV/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119400845/8dbf518f-36ce-4899-8a2b-3a096c94904a)

### Q2) Delete the records from manager table where the salary less than 2750.

### QUERY:
```sql
DELETE FROM manager WHERE salary < 2750;
```
### OUTPUT:
![image](https://github.com/DHARINIPV/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119400845/4dc63e90-8f96-46f6-9448-695db88bb463)

### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)

### QUERY:
```sql
SELECT ename AS "Name", salary*12 AS "Annual Salary" from manager;
```
### OUTPUT:
![image](https://github.com/DHARINIPV/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119400845/2a6707e8-dfa7-46db-98fe-bfc4bc9095f6)

### Q5)	List the names of Clerks from emp table.

### QUERY:
```sql
SELECT ename FROM manager WHERE designation = 'clerk';
```
### OUTPUT:
![image](https://github.com/DHARINIPV/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119400845/6c5adb35-93ec-4c3c-a04b-22d8945f8ad2)

### Q6)	List the names of employee who are not Managers.

### QUERY:
```sql
SELECT ename FROM manager WHERE designation <> 'manager';
```
### OUTPUT:
![image](https://github.com/DHARINIPV/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119400845/210c9b8c-5323-48d6-820e-47231a1df4c7)

### Q7)	List the names of employees not eligible for commission.

### QUERY:
```sql
SELECT ename FROM manager WHERE commission = 0;
```
### OUTPUT:
![image](https://github.com/DHARINIPV/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119400845/98751030-7a39-47a4-a5ab-3d52ed5360b7)

### Q8)	List employees whose name either start or end with ‘s’.

### QUERY:
```sql
SELECT ename FROM manager WHERE ename LIKE '%S' OR ename LIKE 'S%';
```
### OUTPUT:
![image](https://github.com/DHARINIPV/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119400845/0c5e6df9-54f0-4587-a977-56f8b175783c)

### Q9) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.

### QUERY:
```sql
SELECT ename,designation AS "JOB",deptno,Hiredate FROM manager ORDER BY Hiredate ASC;
```
### OUTPUT:
![image](https://github.com/DHARINIPV/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119400845/ea3d522e-46d6-465b-ab62-0f68581451c9)

### Q10) List the Details of Employees who have joined before 30 Sept 81.

### QUERY:
```sql
SELECT * FROM manager WHERE Hiredate < '30-SEP-81';
```
### OUTPUT:
![image](https://github.com/DHARINIPV/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119400845/97a7d7ab-ce71-4db5-ad96-91a364133dd5)

### Q11)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.

### QUERY:
```sql
SELECT ename,deptno,salary FROM manager ORDER BY deptno ASC,salary DESC;
```
### OUTPUT:
![image](https://github.com/DHARINIPV/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119400845/f5483361-963d-40b4-8617-83ac1fe96c24)

### Q12) List the names of employees not belonging to dept no 30,40 & 10

### QUERY:
```sql
SELECT ename FROM manager WHERE deptno NOT IN (30,40,10);
```
### OUTPUT:
![image](https://github.com/DHARINIPV/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119400845/34413227-f8d0-471c-830c-b9b7d1e1a1a0)

### Q13) Find number of rows in the table EMP

### QUERY:
```sql
SELECT COUNT(*) AS "No_of_rows" FROM manager;
```
### OUTPUT:
![image](https://github.com/DHARINIPV/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119400845/03e7a3b2-ee53-4b23-8ea9-da41efc4f584)

### Q14) Find maximum, minimum and average salary in EMP table.

### QUERY:
```sql
SELECT MAX(salary),MIN(salary),AVG(salary) FROM manager;
```
### OUTPUT:
![image](https://github.com/DHARINIPV/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119400845/83b8d529-fecb-45a9-8b8e-9e5ae12dd909)

### Q15) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
```sql
SELECT designation AS "JOB",COUNT(*) AS "NO_OF_EMPLOYEES" FROM manager GROUP BY designation ORDER BY NO_OF_EMPLOYEES DESC;
```
### OUTPUT:
![image](https://github.com/DHARINIPV/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119400845/39fc0115-26ff-4ca4-9ac6-be8b72e5cfa1)

### RESULT:
To create a manager database and execute DML queries using SQL is executed successfully.
