# Transactions
A transaction is the propagation of one or more changes to the database. For example, if you are creating a record, updating a record, or deleting a record from the table, then you are performing transaction on the table. It is important to control transactions to ensure data integrity and to handle database errors.

## Properties of Transactions
Transactions have the following four standard properties, usually referred to by the acronym ACID −

* **Atomicity**− Ensures that all operations within the work unit are completed successfully; otherwise, the transaction is aborted at the point of failure and previous operations are rolled back to their former state.

* **Consistency** − Ensures that the database properly changes states upon a successfully committed transaction.

* **Isolation** − Enables transactions to operate independently of and transparent to each other.

* **Durability** − Ensures that the result or effect of a committed transaction persists in case of a system failure.

## Transaction Control
The following commands are used to control transactions −

* **BEGIN TRANSACTION** − To start a transaction.

* **COMMIT** − To save the changes, alternatively you can use **END TRANSACTION** command.

* **ROLLBACK** − To rollback the changes.

Transactional control commands are only used with the DML commands INSERT, UPDATE and DELETE only. They cannot be used while creating tables or dropping them because these operations are automatically committed in the database.

## The BEGIN TRANSACTION Command
Transactions can be started using BEGIN TRANSACTION or simply BEGIN command. Such transactions usually persist until the next COMMIT or ROLLBACK command is encountered. But a transaction will also ROLLBACK if the database is closed or if an error occurs.

The following is the simple syntax to start a transaction −
```sql
BEGIN;

or

BEGIN TRANSACTION;
```
## The COMMIT Command
The COMMIT command is the transactional command used to save changes invoked by a transaction to the database.

The COMMIT command saves all transactions to the database since the last COMMIT or ROLLBACK command.

The syntax for COMMIT command is as follows −
```sql
COMMIT;

or

END TRANSACTION;
```

## The ROLLBACK Command
The ROLLBACK command is the transactional command used to undo transactions that have not already been saved to the database.

The ROLLBACK command can only be used to undo transactions since the last COMMIT or ROLLBACK command was issued.

The syntax for ROLLBACK command is as follows −
```sql
ROLLBACK;
```
