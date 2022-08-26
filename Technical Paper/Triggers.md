# Triggers
A “trigger” is defined as any event that sets a course of action in a motion.

In PostgreSQL, if you want to take action on specific database events, such as INSERT, UPDATE, DELETE, or TRUNCATE, then trigger functionality can be useful as it will invoke the required function on defined events.

## Types of Triggers
1. Row Level Trigger: If the trigger is marked FOR EACH ROW then the trigger function will be called for each row that is getting modified by the event.

For example: If we UPDATE 100 rows in the table, the UPDATE trigger function will be called 100 times, once for each updated row.

2. Statement Level Trigger: The FOR EACH STATEMENT option will call the trigger function only once for each statement, regardless of the number of the rows getting modified.
# Creating a Trigger
## 1. INSERT event Trigger
The INSERT event trigger gets called when a new record is added to a table using the INSERT statement.
```sql
CREATE TRIGGER trigger_name
    AFTER INSERT
    ON table_name FOR EACH ROW
        trigger_body
Code language: SQL (Structured Query Language) (sql)
```
## 2. UPDATE event Trigger
The UPDATE event trigger gets called at the time of UPDATE statement execution.

Example -
```sql
CREATE TRIGGER verify_user_for_update

 BEFORE UPDATE

 ON "Employee"

 FOR EACH ROW

EXECUTE PROCEDURE employee_verify_user_priv();
```
## 3. DELETE event Trigger
This the DELETE event trigger, which can be added on transactions that DELETE the records.

Example -
```sql
CREATE TRIGGER employee_delete_trigger

  AFTER DELETE

  ON "Employee"

  FOR EACH ROW

 EXECUTE PROCEDURE aft_delete();
```

## Dropping a Trigger
DROP TRIGGER is used to remove a trigger. The syntax is very simple.
```sql
drop trigger employee_insert_trigger on "Employee" ;
```
## Uses Of Triggers
1. Auditing: You can use triggers to track the table transactions by logging the event details.

2. Forcing Check Constraint: You can create a trigger by which you can check the constraints before applying the transaction to the table.

3. Automatic Population: By using triggers you can also auto populate tables fields by new transactions records manipulation.

## Important Points To Remember
1.    To create a trigger on a table, the user must have the TRIGGER privilege on the table and EXECUTE privilege on the trigger function.

2.    You can check system catalogue “pg_trigger” for the existing trigger information in the database.

3.    If you create multiple triggers on the same object for the same event, those triggers will be fired in alphabetical order by name.
