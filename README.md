# SQL-101
Introduction to Sql  

This repository aims to give a brief introduction to SQL commands with syntax and examples.  
An artworks database is used and the commands to create the same are available <a href="https://github.com/Renita1206/SQL-101/edit/main/README.md#insert">here</a>. The database consists of two simple tables - paintings and artist. Paintings table consists of information pertaining to a particular painting like artist name, painting name, and year. Artist table provides details of the artist such as name and nationality.

- view available databases 
```
show databases;
```
- create a database
```
create database db_name;
-- creating artworks database
create database artworks;
```
- use
```
use db_name
-- for this example
use artworks;
```
- delete or drop database
```
drop database db_name;
```

### Create tables
```
-- syntax
CREATE TABLE table_name( 
Col_name1 datatype(), 
Col_name2 datatype(),…
Col_namen datatype(), 
);
```
```
-- create artist table
create table artist(name varchar(255), nationality varchar(255));
-- create painting table
create table painting(name varchar(255), artistName varchar(255), year int);
```

### Alter table
- add column
```
-- syntax
ALTER TABLE table_name ADD Col_name datatype; 
```
```
-- add columns to artist table
alter table artist add yearOfBirth int;
alter table artist add yearOfDeath int;
```

-- add primary key
```
-- syntax 
alter table table_name add PRIMARY KEY(col_name);
```
```
-- add primary keys for artist and painting tables
 alter table artist add PRIMARY KEY(name);
 alter table painting add PRIMARY KEY(name);
 ```
 
 - Rename column
 ```
 -- syntax
ALTER TABLE table_name 
RENAME COLUMN (Old_fieldname TO New_fieldname);
 ```
 
 - Modify column
 ```
 -- syntax
 ALTER TABLE table_name MODIFY (fieldname datatype()); 
 ```
 
 - drop columns
 ```
 -- syntax
ALTER TABLE table_name DROP COLUMN 
column_name;
 ```
 
 ### Insert
 - syntax
 ```
 -- inserting one row
 insert into tableName values("value 1", "value 2",....);
 -- insert multiple rows
 insert into tableName values("value 1a", "value 1b",....), ("value 2a", "value 2b",....).....;
 
```

- inserting values into artist table
```
insert into artist values
("Vincent Van Gogh", "Netherlands", 1853, 1890),
("Leonardo Da Vinci", "Republic of Florence", 1452, 1519),
("Pablo Picasso", "Spain", 1881, 1973),
("Frida Kahlo", "Mexico", 1907, 1954),
("Oscar-Claude Monet", "France", 1840, 1926);
```
- inserting values into painting table
```
insert into painting values
("The Starry Night", "Vincent Van Gogh", 1889),
("The Potato Eaters", "Vincent Van Gogh", 1885),
("Wheatfield with Crows", "Vincent Van Gogh", 1890),
("Cafe Terrace at Night", "Vincent Van Gogh", 1888),
("The Old Guitarist", "Pablo Picasso", 1904),
("Le Reve", "Pablo Picasso", 1932),
("The Weeping Woman", "Pablo Picasso", 1937),
("Portrait of Dora Maar", "Pablo Picasso", 1937),
("The Two Fridas", "Frida Kahlo", 1939),
("The Broken Column", "Frida Kahlo", 1944),
("The Wounded Deer", "Frida Kahlo", 1946),
("Diego and I", "Frida Kahlo", 1949),
("Mona Lisa", "Leonardo Da Vinci", 1503),
("Salvator Mundi", "Leonardo Da Vinci", 1500),
("Vitruvian Man", "Leonardo Da Vinci", 1490),
("The Last Supper", "Leonardo Da Vinci", 1498),
("Poppies", "Claude Monet", 1873),
("The Beach at Trouville", "Claude Monet", 1870),
("The Magpie", "Claude Monet", 1869);
```

 ### Update
 ```
 -- syntax
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
 ```
 ```
 -- example
 -- create a new column age and set age in artist table
 alter table Artist add age int;
 update artist set age = yearOfDeath - yearOfBirth;
 ```
 ![image](https://user-images.githubusercontent.com/66276711/206161871-43d1ac41-2dcc-439b-8bc5-b145f7533dd9.png)
  
  
 ### Delete
 ```
 -- syntax
 delete from tableName where cond;
 ```
 ```
 -- delete paintings by Da Vinci
 delete from painting where artistName = "Leonardo Da Vinci";
 ```
   
     
     
 ### Select
 - all columns
 ```
 -- syntax
 select * from tableName;
 ```
 ```
 -- view all records in artist
 select * from artist;
 ```
 ![image](https://user-images.githubusercontent.com/66276711/206012528-c7e11e55-8b2d-4ae6-bd8d-d2e3b0620b63.png)

 ```
 -- view all records from paintings;
 select * from painting;
 ```
 ![image](https://user-images.githubusercontent.com/66276711/206012638-b42b039c-ac9f-4964-b503-2988bc1c378b.png)

 - display only certain columns
 ```
 -- syntax  
 select columnName from tableName;
 ```
 ```
 -- example  
 select name from artist;
 ```
 ![image](https://user-images.githubusercontent.com/66276711/206012962-27a0b501-b856-4e9d-9a5b-e21bd99bde06.png)

 - where - Used to display records meeting a certain condition or criteria
 ```
 -- syntax 
 select * from tablName where cond;
 ```
 ```
 -- example to display all paintings of Picasso
 select name, year from painting where artistName = "Pablo Picasso";
 ```
 ![image](https://user-images.githubusercontent.com/66276711/206013613-2ff5762f-53a7-4571-9cfb-811516db21ac.png)

 - order by
 ```
 -- syntax 
 select * from tablName order by property;
 ```
 ```
 -- example to display all paintings sorted by year
 select * from painting order by year;
 ```
 ![image](https://user-images.githubusercontent.com/66276711/206014319-c5968340-264b-4288-a97f-dfe90e7db046.png)

 - limit
```
 -- syntax 
 select * from tablName limit 5;
 ```
 ```
 -- example to display only 3 artists
 select * from artist limit 3;
 ```
 ![image](https://user-images.githubusercontent.com/66276711/206014389-346a2781-136c-4c22-ae35-179980ec837a.png)

 - distinct
 ```
 -- syntax 
 select distinct property from tablName;
 ```
 ```
 -- example to display distinct artists with paintings from painting table
 select distinct artistName from painting;
 ```
 ![image](https://user-images.githubusercontent.com/66276711/206014829-1208114e-68b5-49db-b154-bdb4b1bc7149.png)
 
 - IN
 ```
 --syntax
select * from tableName where property in (value1, value2..);
```
```
-- get paintings by Van Gogh or Picasso
select name, year from painting where artistName IN ("Vincent Van Gogh", "Pablo Picasso");
```
![image](https://user-images.githubusercontent.com/66276711/206160867-8abdda8a-1e9a-4e36-bb6f-80c40eec2c4e.png)


 - LIKE  
   Use  % to represent 1 or more characters. Example - "%School" will accept "ABC School", "PQRST School" etc.  
   Use _ to represent exactly 1 character. Example - "_at" will accept "cat", "bat" and "mat" but not "that", "flat" or "neat".
```
--syntax
select * from tableName where property in (value1, value2..);
```
```
-- get all paintings from 15th century
select name, artistName from painting where year like "14__";
 ```
![image](https://user-images.githubusercontent.com/66276711/206160967-4365bb99-c296-40de-89cc-d41eec273a14.png)


 ### Set Operations
 - Union
 ```
 -- syntax
 query 1 UNION query 2;
 ```
 ```
 -- example - Paintings by Picasso or Frida Kahlo
 select * from painting where artistName = "Pablo Picasso"
 UNION
  select * from painting where artistName = "Frida Kahlo";
 ```
 ![image](https://user-images.githubusercontent.com/66276711/206164782-a4ed6a7f-c2c0-4e51-a1f9-54d7eadaac50.png)
 
 - Intersect
 ```
 -- syntax
 query 1 INTERSECT query 2
 ```
 ```
 -- example - Paintings by Picasso and in the year 1937
 select * from painting where artistName = "Pablo Picasso"
INTERSECT
select * from painting where year = 1937;
 ```
 ![image](https://user-images.githubusercontent.com/66276711/206165118-8fd3d758-d66f-43e1-ae53-0f4782bda7db.png)

 - MINUS
 ```
 -- syntax
 query 1 MINUS query 2
 ```
 
 ### Aggregate Operations
 - count
  ```
 -- syntax
 SELECT COUNT(column_name)
FROM table_name
WHERE condition;
 ```
 ```
 -- example -  count no of paintings for each artist
 select artistName, count(name) from painting group by artistName;
 -- count number of paintings by Frida Kahlo
 select count(name) from painting where artistName = "Frida Kahlo";
 ```
 ![image](https://user-images.githubusercontent.com/66276711/206163944-739409e7-fc55-48a3-b3ef-ffa862bfbb98.png)


 - average
   ```
 -- syntax
 SELECT COUNT(column_name)
FROM table_name
WHERE condition;
 ```
 ```
 -- Find average age of artists
 select avg(age) from artist;
 ```
 ![image](https://user-images.githubusercontent.com/66276711/206164029-461dd616-99f0-4aa4-8f4b-67270f9ea67c.png)

 - sum
   ```
 -- syntax
 SELECT COUNT(column_name)
FROM table_name
WHERE condition;
 ```
 
 ### Join Operations
  ```
 -- syntax
 ```
 ```
 -- example
 ```
 
 ### View
 - syntax
 ```
 create view ViewName as
[select query];
 ```
 
- example
```
create view DaVinciPaintings as
 select name, year from painting where artistName="Leonardo Da Vinci";
```
![image](https://user-images.githubusercontent.com/66276711/206016099-182fbd80-29f1-4a4e-a0fd-adefcc3613b6.png)


 ### Some other commands
 - describe
 ```
 -- syntax
 describe tableName;
 -- example
 describe table artist;
 ```
 - drop table
 ```
 -- syntax
 drop tableName;
 -- example
 drop artist;
 ```
 
 - rename
 ```
 -- syntax
 RENAME table TableName to NewTableNamel
 -- example
 RENAME table artist to People;
 ```
 
 - truncate (used to delete all rows in a table)
 ```
 -- syntax
 TRUNCATE TABLE TableName;
 -- example
 TRUNCATE TABLE artist;
 ```  
   
     
More Examples for SQL can be viewed <a href="https://github.com/Renita1206/DBMS-CS301/tree/master/SQL%20Notes"> here </a>.



