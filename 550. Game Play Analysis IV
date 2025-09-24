WITH FirstLogin AS (
    SELECT 
        player_id,
        MIN(event_date) AS first_login_date
    FROM Activity
    GROUP BY player_id
),
ConsecutiveLogin AS (
    SELECT 
        f.player_id
    FROM FirstLogin f
    JOIN Activity a
      ON a.player_id = f.player_id
     AND DATEDIFF(a.event_date, f.first_login_date) = 1
)
SELECT 
    ROUND(
        (SELECT COUNT(DISTINCT player_id) FROM ConsecutiveLogin) * 1.0 
        / (SELECT COUNT(DISTINCT player_id) FROM Activity),
        2
    ) AS fraction;
