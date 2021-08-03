# RateLimiter
Q. Building a rate limiter using redis. Ex : Limiting user calls to 10 requests per min

Sol- Maintain a sorted set in Redis, where each request has expiration time of 60secs attached to it, with the key with closest expiration time on priority. As soon as a key expires, decrement its count by 1. When a new request is made, check for the number of requests made by that user in the last 60secs. If the count is less that 10, add a new entry in the sorted set, with expiration time set to 60secs and process the request of the user, else it will not be processed.
