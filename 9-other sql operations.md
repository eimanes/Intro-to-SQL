# CHAPTER 9: OTHER SQL OPERATIONS

## `UNION` / `UNION ALL`
- glue data on multiple tables together vertically
- `UNION` - return **unique rows (distinct)** on the combined table
- `UNION ALL` - return **all the row data regardless of duplications**
- example:

![image](https://user-images.githubusercontent.com/80232250/170179901-dbf5ec50-b626-4fce-bddb-997058e1b662.png)
> `UNION` removing duplicates data set
```
SELECT year
FROM movies
UNION
SELECT year
FROM tv_shows
```
![image](https://user-images.githubusercontent.com/80232250/170179958-706e976a-b749-4f78-8d2b-2b07e1cf65cb.png)
> `UNION ALL` not removing duplicates data set
```
SELECT year
FROM movies
UNION ALL
SELECT year
FROM tv_shows
```
![image](https://user-images.githubusercontent.com/80232250/170179983-06d415cf-abf8-4feb-925b-d20760305416.png)

-------------------------------------

## `CREATE TABLE`
- to create a table
- [table name] , [column name], [data type]
- note: it is only to create an **empty table**
```
CREATE TABLE table_name (
  column_name_1 data_type,
  column_name_2 data_type,
  ...
)
```
- example:
![image](https://user-images.githubusercontent.com/80232250/170183117-b8bd0a81-9477-4a91-add8-b5378700af30.png)

## `ALTER TABLE`
- to make changes on table

common syntax example:
```
ALTER TABLE table_name
ADD column_name datatype
```
```
ALTER TABLE table_name
DROP COLUMN column_name 
```
```
ALTER TABLE table_name
RENAME COLUMN column_name TO new_name
```
```
ALTER TABLE table_name
RENAME TO new_table_name
```

## `DROP TABLE`
- delete table
- [table name]
> as you will delete the whole table alongside with the data in it
```
DROP TABLE table_name
```
-----
## `INSERT INTO`
- insert records into table
- [table name], [column name], [data values]
```
INSERT INTO table_name
(column_name_1, column_name_2)
VALUES
(data_value_1, data_value_2)
```
![image](https://user-images.githubusercontent.com/80232250/170184652-d4eb87c6-6d89-4724-9cc4-7e3149a90603.png)

## `UPDATE`
- update records
- [data values], [condition]
```
UPDATE table_name
SET column1 = value1, column2 = value2 ...
where condition
```
example:
```
UPDATE movies
SET name = Star Wars, year = 1978
where id = 1
```
![image](https://user-images.githubusercontent.com/80232250/170185072-fc60afba-ee1f-4b42-923d-b7ad4667add1.png)

## `DELETE FROM`
- delete the row of table
- [table name], [condition]
```
DELETE FROM table_name WHERE condition
```
example:
```
DELETE FROM movies where id=1
```
