# SQL-101
Introduction to Sql  

This repository aims to give a brief introduction to SQL commands with syntax and examples.  
An artworks database is used and the commands to create the same are available below. The database consists of two simple tables - paintings and artist. Paintings table consists of information pertaining to a particular painting like artist name, painting name, and year. Artist table provides details of the artist such as name and nationality.

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

-- create artist table
create table artist(name varchar(255), nationality varchar(255));
-- create painting table
create table painting(name varchar(255), artistName varchar(255), year YEAR);
```

### Alter table
- add column
```
-- syntax
ALTER TABLE table_name ADD Col_name datatype; 
-- add columns to artist table
alter table artist add yearOfBirth YEAR;
alter table artist add yearOfDeath YEAR;
```

-- add primary key
```
-- syntax 
alter table table_name add PRIMARY KEY(col_name);
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
 
 
 ### Update
 
 ### Delete
 
 ### Select
 - all columns
 - display only certain columns
 - where
 - order by
 - limit
 - distinct
 
 ### Set Operations
 
 ### Aggregate Operations
 
 ### Join Operations  
 
 ### View
 
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
 
 



