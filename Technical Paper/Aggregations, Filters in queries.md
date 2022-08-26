# Aggregations, Filters in queries
An aggregate function in SQL returns one value after calculating multiple values of a column. We often use aggregate functions with the GROUP BY and HAVING clauses of the SELECT statement.

Various types of SQL aggregate functions are:

* Count()
* Sum()
* Avg()
* Min()
* Max()

## COUNT() Function
The COUNT() function returns the number of rows in a database table.

Syntax:
```sql
COUNT(*)

or

COUNT( [ALL|DISTINCT] expression )
```

## SUM() Function
The SUM() function returns the total sum of a numeric column.

Syntax:
```sql
SUM()

or

SUM( [ALL|DISTINCT] expression )
```
## AVG() Function
The AVG() function calculates the average of a set of values.

Syntax:
```sql
AVG()

or

AVG( [ALL|DISTINCT] expression )
```
## MIN() Function
The MIN() aggregate function returns the lowest value (minimum) in a set of non-NULL values.

Syntax:
```sql
MIN()

or

MIN( [ALL|DISTINCT] expression )
```
## MAX() Function
The MAX() aggregate function returns the highest value (maximum) in a set of non-NULL values.

Syntax:
```sql
AVG()

or

AVG( [ALL|DISTINCT] expression )
```
##  Filter
Queries retrieve rows and columns from tables. After you run a query, you can further limit the number of items shown in the datasheet by applying filters. Filters are a good choice when you want to temporarily limit the query results without going into Design View to edit your query.

For SQL database and internal data types, the filter is an SQL WHERE clause that provides a set of comparisons that must be true in order for a data item to be returned. These comparisons are typically between field names and their corresponding values.

### Syntax
For SQL database data types, the syntax of the SQL filter is specified by the underlying data source. The SQL filter is the contents of an SQL WHERE clause specified in the format provided by the underlying database. When the data items are retrieved from the data source, this filter is passed directly to the underlying database for processing.

For internal data types, the SQL filter is processed internally by the policy engine. For internal data types, the syntax is as follows:
```sql
Field
				Operator
				Value [AND | OR | NOT (Field
				Operator
				Value) ...]
```
where Field is the name of a data type field, Operator is a comparative operator, and Value is the field value.
