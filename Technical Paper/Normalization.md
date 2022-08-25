# Normalization
Normalization is the process to eliminate data redundancy and enhance data integrity in the table. Normalization also helps to organize the data in the database. It is a multi-step process that sets the data into tabular form and removes the duplicated data from the relational tables.

**1st Normal Form (1NF):**
* A table is referred to as being in its First Normal Form if atomicity of the table is 1.

* Here, atomicity states that a single cell cannot hold multiple values. It must hold only a single-valued attribute.

* The First normal form disallows the multi-valued attribute, composite attribute, and their combinations.

**Second Normal Form (2NF):**
* The first condition for the table to be in Second Normal Form is that the table has to be in First Normal Form. The table should not possess partial dependency. The partial dependency here means the proper subset of the candidate key should give a non-prime attribute.

**Third Normal Form (3NF):**
* The first condition for the table to be in Third Normal Form is that the table should be in the Second Normal Form.

* The second condition is that there should be no transitive dependency for non-prime attributes, which indicates that non-prime attributes (which are not a part of the candidate key) should not depend on other non-prime attributes in a table. Therefore, a transitive dependency is a functional dependency in which A → C (A determines C) indirectly, because of A → B and B → C (where it is not the case that B → A).

* The third Normal Form ensures the reduction of data duplication. It is also used to achieve data integrity.

**Boyce CoddNormal Form (BCNF):**
* Boyce Codd Normal Form is also known as 3.5 NF. It is the superior version of 3NF and was developed by Raymond F. Boyce and Edgar F. Codd to tackle certain types of anomalies which were not resolved with 3NF.

* The first condition for the table to be in Boyce Codd Normal Form is that the table should be in the third normal form. Secondly, every Right-Hand Side (RHS) attribute of the functional dependencies should depend on the super key of that particular table.
