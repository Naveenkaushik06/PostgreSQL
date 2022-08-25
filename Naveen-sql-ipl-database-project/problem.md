## 1. Number of matches played per year for all the years in IPL.
```
SELECT season, count(*) FROM matches
GROUP BY season
ORDER BY season;
```
## 2. Number of matches won per team per year in IPL.
```
SELECT winner, COUNT(winner)
FROM matches
GROUP BY winner
ORDER BY COUNT(winner) DESC;
```
## 3. Extra runs conceded per team in the year 2016
```
SELECT bowling_team, sum(extra_runs) FROM deliveries
INNER JOIN matches
ON matches.id=deliveries.match_id
WHERE matches.season=2016
GROUP BY bowling_team;
```
## 4. Top 10 economical bowlers in the year 2015

