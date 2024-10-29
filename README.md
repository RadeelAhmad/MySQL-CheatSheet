# MySQL-CheatSheet

## Table Of Contents
- [Create Table in database](#Create-Table)
- [Insert value in table of database](#Insert-Value)
- [Display the name with different style](#Display-Name)
- [Use of concat](#Use-of-conact)

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
