Identify at least 3 real-world applications and specify:
Which type of database they use (SQL / NoSQL / In-memory)
Why that database is suitable

1. Instagram
- SQL -> PostgreSQL : 
  * Suitable for handling user data like profiles and account information with strong consistency
- NoSQL -> Cassandra :
  * Handles larger amaount of data such as posts, comments and likes while supporting high availability
- In-memory db :
  * Redis is used for caching responses and caching session timelines that makes the application faster

2. Amazon shopping
- SQL: MySQL
  * For storing structured data as customer accounts, orders, payments and invoices. Moreover, it supports ACID transactional properties, making it ideal for managing finances and transactions.
- NoSQL: DynamoDB : 
  * Stores product catalog, carts, etc.; handles millions of requests with low latency, and scales accordingly as per number of users.
- In-memory : Redis :
  * Caches frequently viewed products and search results, reduces load on db and improves response time.

3. LinkedIn
- SQL: Oracle Db :
  * Suitable for structured user profile, company and job data, acid transactions for reliability;Supports high availability for millions of usrs
- NoSQL: Voldemort : 
  * Has distributed key-value database; designed for horizontal scalibility and lowm latency lookups
- In-memory : Memcached : 
  * Suitable for user session caching, frequently accessed profiles