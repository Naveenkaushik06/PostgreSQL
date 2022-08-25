# ACID
In order to maintain consistency in a database, before and after the transaction, certain properties are followed. These are called ACID properties.
## ACID properties:
**Atomacity:** The entire transaction takes place at once or doesn’t happen at all.

**Consistency:** The database must be consistent before and after the transaction.

**Isolation:** Multiple transactions occur independently without interference.

**Durability:** The changes of a successful transaction occurs even if the system failure occurs.
```
Property        Responsibility for maintaining properties

Atomicity	    Transaction Manager

Consistency	    Application programmer

Isolation   	Concurrency Control Manager

Durability  	Recovery Manager
```
1) **Atomicity:** The term atomicity defines that the data remains atomic. It means if any operation is performed on the data, either it should be performed or executed completely or should not be executed at all. It further means that the operation should not break in between or execute partially. In the case of executing operations on the transaction, the operation should be completely executed and not partially.

2) **Consistency:** The word consistency means that the value should remain preserved always. The integrity of the data should be maintained, which means if a change in the database is made, it should remain preserved always. In the case of transactions, the integrity of the data is very essential so that the database remains consistent before and after the transaction. The data should always be correct.

4) **Isolation:** The term 'isolation' means separation. Isolation is the property of a database where no data should affect the other one and may occur concurrently. In short, the operation on one database should begin when the operation on the first database gets complete. It means if two operations are being performed on two different databases, they may not affect the value of one another. In the case of transactions, when two or more transactions occur simultaneously, the consistency should remain maintained. Any changes that occur in any particular transaction will not be seen by other transactions until the change is not committed in the memory.

5) **Durability:** The term durability ensures that the data after the successful execution of the operation becomes permanent in the database. The durability of the data should be so perfect that even if the system fails or leads to a crash, the database still survives. However, if gets lost, it becomes the responsibility of the recovery manager for ensuring the durability of the database. For committing the values, the COMMIT command must be used every time we make changes.

