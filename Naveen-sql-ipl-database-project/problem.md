## 1. Number of matches played per year for all the years in IPL.
```sql
SELECT season, count(*) FROM matches
GROUP BY season
ORDER BY season;
```
## 2. Number of matches won per team per year in IPL.
```sql
SELECT winner, COUNT(winner)
FROM matches
GROUP BY winner
ORDER BY COUNT(winner) DESC;
```
## 3. Extra runs conceded per team in the year 2016
```sql
SELECT bowling_team, sum(extra_runs) FROM deliveries
INNER JOIN matches
ON matches.id=deliveries.match_id
WHERE matches.season=2016
GROUP BY bowling_team;
```
## 4. Top 10 economical bowlers in the year 2015
```sql
SELECT bowler,round(SUM(total_runs)/((COUNT(bowler))/6.0),2)
AS economy FROM deliveries
WHERE match_id IN (SELECT id FROM matches WHERE season=2015)
GROUP BY bowler
ORDER BY economy
LIMIT 10;
```
## 5. Find the number of times each team won the toss and also won the match
```sql
SELECT winner, COUNT (winner) FROM matches
WHERE winner=toss_winner
GROUP BY winner;
```
## 6. Find a player who has won the highest number of Player of the Match awards for each season
```sql



```
## 7. Find the strike rate of a batsman for each season
```sql
SELECT delivery.batsman, match.season,
ROUND (((SUM (delivery.batsman_runs)*1.00)/COUNT(delivery.batsman))*100,2) AS strike_rate
FROM deliveries AS delivery inner join matches AS match
ON delivery.match_id = match.id
group by delivery.batsman, match.season
order by delivery.batsman, match.season;
```
## 8. Find the highest number of times one player has been dismissed by another player
```sql
SELECT player_dismissed, bowler, 
COUNT (player_dismissed) AS no_of_times_dismissed
FROM deliveries
GROUP BY player_dismissed, bowler
ORDER BY no_of_times_dismissed DESC
LIMIT 1;
```
## 9. Find the bowler with the best economy in super overs
```sql
SELECT bowler, ROUND (sum(total_runs)/((COUNT(bowler)/6.0)), 2) As economy FROM deliveries
WHERE match_id in (SELECT id FROM matches WHERE over= is_super_over) 
GROUP by bowler                                                      
ORDER by economy 
LIMIT 1;
```
