# MySQL-CheatSheet

## Table Of Contents
- [Display the name with different style](#Display-Name)

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
