##Create datase 
~~~ 
CREATE DATABASE IF NOT EXISTS RUNOOB DEFAULT CHARSET utf8 COLLATE utf8_general_ci;
~~~


##Drop database;
~~~
Drop database [database name]
~~~

OR

~~~
mysqladmin -u root -p drop [database name]

~~~

##check the length of property
~~~
select LENGTH(fieldname) from tablename
~~~

##create table
```CREATE TABLE table_name (column_name column_type);```
Example:
~~~
CREATE TABLE IF NOT EXISTS `runoob_tbl`(
   `runoob_id` INT UNSIGNED AUTO_INCREMENT,
   `runoob_title` VARCHAR(100) NOT NULL,
   `runoob_author` VARCHAR(40) NOT NULL,
   `submission_date` DATE,
   PRIMARY KEY ( `runoob_id` )
)ENGINE=InnoDB DEFAULT CHARSET=utf8;
~~~


##drop table
```DROP TABLE table_name```

different from 

~~~
delete from tablename where conditions;
truncate table tablename;
~~~

#insert data
~~~
INSERT INTO table_name ( field1, field2,...fieldN )
                       VALUES
                       ( value1, value2,...valueN );
~~~

#query

~~~
SELECT column_name,column_name
FROM table_name
[WHERE Clause]
[LIMIT N][ OFFSET M]
~~~

##update
~~~
UPDATE table_name SET field1=new-value1, field2=new-value2
[WHERE Clause]

UPDATE runoob_tbl SET runoob_title = REPLACE(runoob_title, 'C++', 'Python') where 
runoob_id = 3;
~~~

'%a'     //ends with a
'a%'     //starts with a
'%a%'    //includes a
'_a_'    //a in the middle with a length of 3
'_a'     //ends with a in with a length of 2
'a_'     //starts with a with a lenght of 2

#Union

~~~
SELECT expression1, expression2, ... expression_n
FROM tables
[WHERE conditions]
UNION [ALL | DISTINCT]
SELECT expression1, expression2, ... expression_n
FROM tables
[WHERE conditions];
~~~
##order
~~~
SELECT field1, field2,...fieldN table_name1, table_name2...
ORDER BY field1, [field2...] [ASC [DESC]]
~~~

#group
~~~
SELECT name ,sum(*)  FROM employee_tb1 WHERE id<>1 GROUP BY name  HAVING sum(*)>5 ORDER BY sum(*) DESC;
~~~

#dump
~~~
mysqldump -u root -p RUNOOB runoob_tbl > dump.txt
~~~
##dump to a remote mysql server
~~~
mysqldump -u root -p database_name \
       | mysql -h other-host.com database_name
~~~

##dump form a remote server
~~~
mysqldump -h other-host.com -P port -u root -p database_name > dump.txt
password ****
~~~
##import sql
mysql -uroot -p123456 < runoob.sql
or 
Source path:/file.sql



