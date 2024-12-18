# MySQL-CheatSheet

## Table Of Contents
- [Create Table in database](#Create-Table)
- [Insert value in table of database](#Insert-Value)
- [Display the name with different style](#Display-Name)
- [Use of concat](#Conact)
- [Insert Value Condition](#Condition)
- [Use of alter](#Alter)
- [Use of Nested Query](#Nested-Query)
- 
## Create Table
Example:
```SQL
create table persons (
ID int not null,
LastName varchar(255) not null,
FirstName varchar(255),
Age int check (age>=18),
city varchar(255) default 'Islamabad'
);
```

## Insert Value
Example:

```SQL
insert into persons(ID, LastName, FirstName, Age,city)
value(221544,'Ahmad','Radeel',20,'khushab');
```

## Display Name

### Which actors have the first name ‘Scarlett’
```SQL
select * from actor where first_name = 'Scarlett';
```

### Which actors have the last name ‘Johansson’

```SQL
select * from actor where last_name = 'Johansson';
```

### Find all actors whose last name contain the letters GEN:

```SQL
select * from actor where last_name = '%GEN%';
```

### Retrieve names of movies starting with S.

```SQL
select title from film where title like 'S%';
```

### Select release year of movies starting with M?

```SQL
select release_year from film where title like 'M%';
```

### Retrieve data of all actors whose names are not ending on T.

```SQL
select * from actor where last_name not like '%T';
```

## Conact

### Create a new table called customer_names with first_name, last_name, and full_name columns, where full_name combines first and last names of all customers.
```SQL
create table customer_name as select
First_name , Last_name , concat(first_name,' ',last_name ) as full_name
from customer;

select * from customer_name
```

## condition

### In this user must enter age above and greater then 18  
```SQL
create table persons (
ID int not null,
LastName varchar(255) not null,
FirstName varchar(255),
Age int check (age>=18),
city varchar(255) default 'Islamabad'
);
```

## Alter

### change the Data type and condition
```SQL
alter table student modify age int check (age>=18 and age<=35) ;
alter table faculty modify fname VARCHAR(30);
alter table faculty modify deptid int not null;
alter table student add age int;
```

## Nested Query

### less, greater, equal and condition
```SQL
SELECT fName, lName, salary
FROM employee
WHERE salary > (SELECT AVG(salary)
FROM employee);
```

```SQL
SELECT fName, lName, salary
FROM employee
WHERE salary = (SELECT min(salary)
FROM employee);
```

```SQL
select fName, lName,salary
from employee where salary > (select salary
from employee
where fName like 'Ahmed')
```

### Find the names of all juniors (Level = JR) who are enrolled in a class taught by ‘Ivana Teach’.

```SQL
select s.sname from student s
where s.level = 'JR' and snum in (
select e.snum from
class c,
faculty f,
enrolled e
where e.cname = c.cname and
c.fid = f.fid and
f.fname = 'Ivana'
);
```

### 

```SQL

```

### 

```SQL

```

### 

```SQL

```

### 

```SQL

```
