# Indexes
## The CREATE INDEX Command
The basic syntax of CREATE INDEX is as follows −
```
CREATE INDEX index_name ON table_name;
```
## Index Types
PostgreSQL provides several index types: B-tree, Hash, GiST, SP-GiST and GIN. Each Index type uses a different algorithm that is best suited to different types of queries. By default, the CREATE INDEX command creates B-tree indexes, which fit the most common situations.
## Single-Column Indexes
A single-column index is one that is created based on only one table column. The basic syntax is as follows −
```
CREATE INDEX index_name
ON table_name (column_name);
```
## Multicolumn Indexes
A multicolumn index is defined on more than one column of a table. The basic syntax is as follows −
```
CREATE INDEX index_name
ON table_name (column1_name, column2_name);
```
## Unique Indexes
Unique indexes are used not only for performance, but also for data integrity. A unique index does not allow any duplicate values to be inserted into the table. The basic syntax is as follows −
```
CREATE UNIQUE INDEX index_name
on table_name (column_name);
```
## Partial Indexes
A partial index is an index built over a subset of a table; the subset is defined by a conditional expression (called the predicate of the partial index). The index contains entries only for those table rows that satisfy the predicate. The basic syntax is as follows −
```
CREATE INDEX index_name
on table_name (conditional_expression);
```
## Implicit Indexes
Implicit indexes are indexes that are automatically created by the database server when an object is created. Indexes are automatically created for primary key constraints and unique constraints.

## The DROP INDEX Command
An index can be dropped using PostgreSQL DROP command. Care should be taken when dropping an index because performance may be slowed or improved.

The basic syntax is as follows −
```
DROP INDEX index_name;
```
You can use following statement to delete previously created index −
```
# DROP INDEX salary_index;
```
## When Should Indexes be Avoided?
Although indexes are intended to enhance a database's performance, there are times when they should be avoided. The following guidelines indicate when the use of an index should be reconsidered −

* Indexes should not be used on small tables.

* Tables that have frequent, large batch update or insert operations.

* Indexes should not be used on columns that contain a high number of NULL values.

* Columns that are frequently manipulated should not be indexed.

## B-tree indexes
B-tree is the default index in Postgres and is best used for specific value searches, scanning ranges, data sorting or pattern matching. If we don’t specify any particular index type in the CREATE INDEX command, Postgres creates a B-tree index which follows the Lehman & Yao Algorithm and B+-Trees.

At a high-level, the B-tree has Root, Intermediate and Leaf node.

* The Root node and intermediate node contain keys and points to the lower level nodes.

* The Leaf node contains keys as well as data points to the heap.

## Hash index
Hash indexes are best suited to work with equality operators. The equality operator looks for the exact match of data. Starting from Postgres 9.x version, the hash indexes are WAL-logged and crash-safe.

In the following CREATE INDEX statement, we create a hash index on the “City” column ( Using HASH(“City”).
```
CREATE INDEX IX_Addresses_city on addresses using HASH("city");
```

## GiST indexes
The Generalized Search Tree (GiST) is balanced, and it implements indexing schemes for new data types in a familiar balanced tree structure. It can index complex data such as geometric data and network address data. It can also implement different strategies such as B-tree or R-tree as well.

## SP-GiST indexes
The SP-GiST index refers to a space partitioned GiST index. It is useful for indexing non-balanced data structures using the partitioned search tree.

It is best suited for overlapping geometries and heterogeneous distributions. It can implement various trees such as quad-trees, k-d trees, and radix trees.

## GIN indexes
The Generalized Inverted Index (GIN) is beneficial for indexing columns that have composite types. It is best suited for data types such as JSONB, Array, Range types and full-text search.

Suppose you have a directory database where users can search the database using partial matches. For example, if a user puts a search string “raj,” it should return all rows for names such as Rajendra, Raju and Hansraj. In this instance, we can implement the GIN index for executing performance-optimized queries.

## BRIN index
The BRIN index is also known as Block Range Index. It stores the summary of blocks (minimum value, maximum value and page number). Once a BRIN index is implemented, it uses the BRIN values for validating each page. In case the page is not modified, its BRIN value remains the same. Now, once we specify a query to retrieve the result, it uses the minimum and maximum value range to check whether the page satisfied the result set. It is useful for extensive data such as timestamps and temperature sensor data. It also uses less storage compared to a B-tree index.


## List indexes in Postgres
Suppose you require a list of indexes for all objects in a specific schema or a particular table. For this purpose, we can use the pg_indexes view. It returns the index definition as well the index. In the below query, it returns index information for all tables in the public schema.
```
SELECT
tablename as "TableName",
indexname as "Index Name",
indexdef as "Index script"
FROM
pg_indexes
WHERE
schemaname = 'public'
ORDER BY
tablename,
indexname;
```
## Important guidelines for Postgres indexes
* The default Postgres index is a B-tree index.

* You should always properly analyze your workload using query execution plans to determine the suitable Postgres index type.

* Always create indexes on the most executed and costly queries. Avoid creating an index to satisfy a specific query.

* As per best practice, always define a primary or unique key in a Postgres table. It automatically creates the B-tree index.

* Avoid creating multiple indexes on a single column. It is better to look at which index is appropriate for your workload and drop the unnecessary indexes.

* There is no specific limit on the number of indexes in the table; however, try to create the minimum indexes satisfying your workload.
