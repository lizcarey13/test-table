### Table 1
- Contains user ID's who have posted content by day

date_posted | userid | content_posted
----| --- | ----
2016-01-01 | 1 | photo
2016-01-01 | 1 | video
2016-01-01 | 1 | comment
2016-01-01 | 1 | photo
2016-01-01 | 2 | comment
2016-01-23 | 2 | photo
2016-01-25 | 7 | photo


### Table 2
- Contains All user ID's by country and region

userid | country | region
--- | --- | ----
1 | USA | North America
2 | USA | North America
3 | USA | North America
4 | Mexico | North America
5 | Cananda | North America
7 | Iran | Middle East
8 | Iraq | Middle East


-------

#### Find the number of monthly unique users by country and region

```sql 
SELECT month(date_posted), year(date_posted), country, region, COUNT (distinct a.userid) 
FROM table1 a 
JOIN table2 b ON 
(a.userid = b.userid)
GROUP BY month(date_posted), year(date_posted), country, region
;

--- Less taxing count distinct query
SELECT mnth, yr, country, region, count(userid) from
(SELECT DISTINCT month(date_posted) as mnth, year(date_posted) as yr, country, region, a.userid 
FROM table1 a 
JOIN table2 b ON 
(a.userid = b.userid)) x
GROUP BY mnth, yr, country, region
;
```
