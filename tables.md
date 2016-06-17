### Table 1
- Contains user ID's who have posted content by day

date | userid | content_posted
----| --- | ----
2016-01-01 | 1 | photo
2016-01-01 | 1 | video
2016-01-01 | 1 | comment
2016-02-01 | 1 | photo
2016-02-01 | 2 | comment
2016-02-23 | 2 | photo

### Table 2
- Contains All user ID's by country and region

userid | country | region
--- | --- | ----
1 | USA | North America
3 | USA | North America
5 | Cananda | North America


-------

#### Find the number of monthly unique users

```sql
SELECT 
