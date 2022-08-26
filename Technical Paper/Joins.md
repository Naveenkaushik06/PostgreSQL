# Joins
The PostgreSQL Joins clause is used to combine records from two or more tables in a database. A JOIN is a means for combining fields from two tables by using values common to each.

Join Types in PostgreSQL are:

1. **Inner Join** : Returns records that have matching values in both tables

2. **Left Join** : Returns all records from the left table, and the matched records from the right table

3. **Right Join** : Returns all records from the right table, and the matched records from the left table

4. **Full Join** :  Returns all records when there is a match in either left or right table

Some special PostgreSQL joins are below:
* Natural Join
* Cross Join
* Self Join
## INNER JOIN
The INNER JOIN keyword selects records that have matching values in both tables.
### INNER JOIN Syntax
```sql
SELECT column_name(s)
FROM table1
INNER JOIN table2
ON table1.column_name = table2.column_name;
```
## LEFT JOIN
The LEFT JOIN keyword returns all records from the left table (table1), and the matching records from the right table (table2). The result is 0 records from the right side, if there is no match.
### LEFT JOIN Syntax
```sql
SELECT column_name(s)
FROM table1
LEFT JOIN table2
ON table1.column_name = table2.column_name;
```
## RIGHT JOIN
The RIGHT JOIN keyword returns all records from the right table (table2), and the matching records from the left table (table1). The result is 0 records from the left side, if there is no match.
### RIGHT JOIN Syntax
```sql
SELECT column_name(s)
FROM table1
RIGHT JOIN table2
ON table1.column_name = table2.column_name;
```
## OUTER JOIN
The FULL OUTER JOIN keyword returns all records when there is a match in left (table1) or right (table2) table records.
### FULL OUTER JOIN Syntax
```sql
SELECT column_name(s)
FROM table1
FULL OUTER JOIN table2
ON table1.column_name = table2.column_name
WHERE condition;
```
