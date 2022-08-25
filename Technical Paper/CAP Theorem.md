# The CAP theorem
The CAP theorem states that it is impossible for a distributed computing system to simultaneously provide all three of the following guarantees:

* **Consistency:** All clients see the latest data even in the case of updates.

* **Availability:** All clients can find a replica of some data even in the case of a node failure. This means that even if some part of the system goes down, the clients can still access the data.

* **Partition tolerance:** The system continues to work regardless of arbitrary message loss or failure of part of the system.

## Consistency in databases
Consistent databases should be used when the value of the information returned needs to be accurate.

Financial data is a good example. When a user logs in to their banking institution, they do not want to see an error that no data is returned, or that the value is higher or lower than it actually is. Banking apps should return the exact value of a user’s account information. In this case, banks would rely on consistent databases.

Examples of a consistent database include:

* Bank account balances
* Text messages

Database options for consistency:

* MongoDB
* Redis
* HBase

## Availability in databases
Availability databases should be used when the service is more important than the information.

An example of having a highly available database can be seen in e-commerce businesses. Online stores want to make their store and the functions of the shopping cart available 24/7 so shoppers can make purchases exactly when they need.

Database options for availability:

* Cassandra
* DynamoDB
* Cosmos DB
