
### Histogram of Tweets [Twitter SQL Interview Question]

```SQL
# creating CTE Table to count the tweet ids
WITH tweet_counts AS (
SELECT COUNT(tweet_id) as tweet_user_count, user_id
FROM tweets
WHERE tweet_date >= '2022/01/01' AND tweet_date <= '2022/12/31'
GROUP BY user_id)

# creating buckets 
SELECT tweet_user_count as tweet_bucket, COUNT(user_id) AS users_num
FROM tweet_counts
GROUP BY tweet_user_count
```

### Data Science Skills [LinkedIn SQL Interview Question]

```SQL
SELECT candidate_id 
FROM candidates
WHERE skill='Python' OR skill='Tableau' OR skill = 'PostgreSQL'
GROUP BY candidate_id
HAVING COUNT(skill)>=3
ORDER BY candidate_id ASC

```

### Page With No Likes [Facebook SQL Interview Question]


```SQL
SELECT p.page_id
FROM pages p 
LEFT JOIN page_likes pl ON pl.page_id = p.page_id
WHERE pl.user_id IS NULL
ORDER BY p.page_id ASC

```


```SQL
SELECT part, assembly_step
FROM parts_assembly
WHERE finish_date IS NULL;

```

```SQL
SELECT 
SUM(CASE WHEN device_type = 'laptop' THEN 1 ELSE 0 END) AS laptop_views,
SUM(CASE WHEN device_type IN ('tablet', 'phone') THEN 1 ELSE 0 END) AS mobile_views
FROM viewership;


```
### Average Post Hiatus (Part 1) [Facebook SQL Interview Question]

```SQL

SELECT user_id, EXTRACT(day FROM (MAX(post_date)-MIN(post_date)) ) as days_between
FROM posts
WHERE post_date BETWEEN '2021-01-01' AND '2021-12-31'
GROUP BY user_id
HAVING COUNT(user_id)>1;
```

### Teams Power Users [Microsoft SQL Interview Question]


```SQL
SELECT sender_id , COUNT(sender_id) as message_count
FROM messages
WHERE sent_date BETWEEN '08-01-2022' AND '08-30-2022'
GROUP BY sender_id
ORDER BY message_count DESC
LIMIT 2;

```

```SQL
WITH duplicates AS (
SELECT company_id, title, COUNT(job_id) AS count_jobs
FROM job_listings
GROUP BY company_id, title
HAVING COUNT(job_id)>1)


SELECT COUNT(count_jobs) AS duplicate_companies
FROM duplicates


```
