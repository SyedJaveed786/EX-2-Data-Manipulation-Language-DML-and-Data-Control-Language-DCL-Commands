# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
## Date:
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
```
update manager set salary=salary+(salary*0.10);
```
### OUTPUT:
![image](https://github.com/Aishwarya-sankar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121418444/fa2f6831-6cc7-4cdd-9980-414a35ad84d7)


### Q2) Delete the records from manager table where the salary less than 2750.


### QUERY:
```
delete from manager where salary<2750;
```

### OUTPUT:
![image](https://github.com/Aishwarya-sankar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121418444/3f38209d-fcab-4b61-a945-5c7634c0fc51)

### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)


### QUERY:
select ename as "Name",salary*12 as "Annual salary" from manager;

### OUTPUT:
![image](https://github.com/Aishwarya-sankar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121418444/39f1b7a0-3658-4469-a14e-e2243cb4e9ae)

### Q4)	List the names of Clerks from emp table.


### QUERY:
```
select ename from manager where designation='clerk';
```

### OUTPUT:
![image](https://github.com/Aishwarya-sankar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121418444/79cd7d39-9eac-4181-bb93-5d131fe83f96)


### Q5)	List the names of employee who are not Managers.


### QUERY:
```
select ename from manager where designation <> 'manager';
```

### OUTPUT:
![image](https://github.com/Aishwarya-sankar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121418444/d25606c3-81c6-4da3-b57d-b8d30245aaba)


### Q6)	List the names of employees not eligible for commission.


### QUERY:
```
select ename from manager where commission=0;
```
### OUTPUT:

![image](https://github.com/Aishwarya-sankar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121418444/0ccff547-98fc-4093-8a12-acae07d2b3e3)

### Q7)	List employees whose name either start or end with ‘s’.


### QUERY:
```
select ename from manager where ename like '%s' or ename like 's%';
```
### OUTPUT:
![image](https://github.com/Aishwarya-sankar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121418444/ab95a533-d384-4131-b5b4-1bec64ffe2e3)


### Q8) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.


### QUERY:
```
select ename,designation as "job",deptno,hiredate from manager order by hiredate asc;
```
### OUTPUT:
![image](https://github.com/Aishwarya-sankar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121418444/fe4706d0-e67b-45cc-9d8b-da1b8e5d7833)


### Q9) List the Details of Employees who have joined before 30 Sept 81.


### QUERY:
```
select * from manager where hiredate<to_date('1981-09-30','YYYY-MM-DD');
```
### OUTPUT:
![image](https://github.com/Aishwarya-sankar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121418444/e4583c5e-f5d1-4d98-9228-e93893b5498f)


### Q10)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.


### QUERY:
```
select ename,deptno,salary from manager order by deptno asc,salary desc;
```
### OUTPUT:

![image](https://github.com/Aishwarya-sankar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121418444/df211380-52ad-4687-b6bf-bd7531fdcf97)

### Q11) List the names of employees not belonging to dept no 30,40 & 10


### QUERY:
```
select ename from manager where deptno not in (30,40,10);
```
### OUTPUT:
![image](https://github.com/Aishwarya-sankar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121418444/65f92000-fd55-4270-bc58-2afd8cb05f2a)

### Q12) Find number of rows in the table EMP

### QUERY:
```
select count(*) from manager;
```
### OUTPUT:
![image](https://github.com/Aishwarya-sankar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121418444/1bbb5dd7-ca91-4889-a028-fca6c8818c26)


### Q13) Find maximum, minimum and average salary in EMP table.

### QUERY:
### MAXIMUM:
```
select max(salary) from manager;
```
### OUTPUT:
![image](https://github.com/Aishwarya-sankar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121418444/60915d73-72b6-4d32-9092-8d2219f698c0)

### MINIMUM:
```
select min(salary) from manager;
```
### OUTPUT:
![image](https://github.com/Aishwarya-sankar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121418444/019a6523-f835-418f-a3d1-2f574adb84a7)
### AVERAGE:
```
select avg(salary) from manager;
```
### OUTPUT:
![image](https://github.com/Aishwarya-sankar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121418444/ff89e0b5-81c2-41c8-94ea-1562382cdef2)
### Q14)List the jobs and number of employees in each job.The result should be in the descending order of the number of employees.
### QUERY:
```
SELECT designation AS job, COUNT(*) AS num_employees FROM manager GROUP BY designation ORDER BY num_employees DESC;

```


### OUTPUT:
![image](https://github.com/Aishwarya-sankar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121418444/e11d9e40-534f-4960-accb-40becd1c38e0)
### RESULT:
Hence successfully created a manager database and execute DML queries using SQL.
