## Types of Communication

### Synchronous (Strong coupling)
1. HTTP (REST/GraphQL)
2. Websocket (Debatable if sync or async)

### Asynchronous (Weak Coupling)
1. Messaging queues
2. Pub subs
3. Server-Side Events
4. Websocket (Debatable)(The initial handshake is synchronous, using HTTP to establish the connection; however, once established, data transmission is handled asynchronously)


## Harikat-Leetcode-system-design
[Leetcode-system-design](/assets/leetcode-harikat.png)

### my thoughts on leetcode

LeetCode uses HTTP(**polling**- means asking from server again and again that if my submission done) instead of WebSockets primarily for cost savings. If LeetCode were to use WebSockets, their primary server would need to be scaled up to handle a high volume of WebSocket connections from browsers. Additionally, they would need to scale their worker servers to match. Essentially, they opt for polling to avoid the higher costs associated with scaling WebSocket infrastructure.

### REDIS - It's an open-source, in-memory data structure used as a database, cache, and message broker.

[redis](/assets/redis.png)

**Scenario**: Your application has a high-traffic endpoint like `/track` that retrieves tracking information from PostgreSQL. When 1000 requests hit this endpoint, the load on your PostgreSQL database increases significantly, potentially leading to performance issues.

**Solution**: Cache the results of `/track` in Redis to reduce the load on PostgreSQL and speed up response times.


### Caching with Redis for Endpoint `/track`

1. **Request Handling:**
   - **Check Redis:** Look up `/track` data in Redis first.
   - **If Cached:** Return data from Redis, avoiding PostgreSQL.
   - **If Not Cached:** Query PostgreSQL for data.

2. **Caching Result:**
   - Store the data from PostgreSQL in Redis with an expiration time (TTL).

3. **Cache Invalidation:**
   - Use TTLs or update mechanisms to invalidate the cache when data changes.


### Q. what if admin update the /track. so first  clear the redis cache. then write updated data to postgres

### Q. Since Redis is an in-memory database, what happens if it goes down or if the process is terminated? How can the risk of data loss be mitigated?
- **RDB (Redis Database Backup)**: Redis can take periodic snapshots (like 1hr) of your data and save them to disk.
- **AOF (Append Only File):**  Redis writes every action (like adding or changing data) to a log file. This log file is saved on disk and can be used to rebuild the data if Redis restarts.
- **No persistence:** You can disable persistence completely. This is sometimes used when caching.
- **RDB + AOF:** You can also combine both AOF and RDB in the same instance. With this setup, you can configure Redis to create RDB snapshots (backups) at regular intervals (e.g., every hour). If data is lost between these snapshots, the AOF log will have a record of all changes since the last snapshot. 


Where are queue stored ? ====>  Redis, RabbitMQ
