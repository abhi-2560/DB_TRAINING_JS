- Database normalization is an approach to organize fields and tables of a database to minimize data redundancy and safeguard data integrity.


- The primary goal of normalization is to ensure that every piece of data is stored in exactly one place.
 * Reduces Storage Space: Eliminating duplicate data keeps the database lean.
 * Ensures Data Consistency: If a piece of data changes (like a customer's phone number), you only have to update it in one single row rather than hundreds of rows across the system.
 * Improves Query Efficiency: Well-structured tables with clear relationships allow the database engine to search and join tables much faster.
  
## Problems That Occur Without Normalization

When a database is not normalized, it suffers from data synchronization issues known as anomalies. These fall into three main categories:
1. Update Anomalies:
If the same data is duplicated in multiple rows, updating that data requires changing every single row where it appears. If a row is missed, you end up with inconsistent data (e.g., a customer having two different addresses simultaneously in the same database).

2. Insertion Anomalies
This happens when you cannot insert certain facts into the database because other unrelated facts are missing. For example, if you store course information in the same table as student enrollments, you cannot add a *new course* to the system until at least one student actually registers for it.

3. Deletion Anomalies
This is the accidental loss of data. If you delete a specific record, you might inadvertently destroy other crucial data. For example, if a table combines customer info and order info, deleting a customer's only order would completely erase that customer's entire account profile from your history.

<br>

Converting Your Data to First Normal Form (1NF):

The rule for First Normal Form (1NF) states that all attribute values must be atomic. This means a single cell cannot contain a comma-separated list or a collection of multiple values (like your Products column containing "Laptop, Mouse"). Each row must contain only one value per attribute.


Normalized to 1NF:

To bring this to 1NF, we split the multi-valued data into separate, individual rows:

| Order_ID | Customer_Name | Product |
|---|---|---|
| 101 | Rahul | Laptop |
| 101 | Rahul | Mouse |

