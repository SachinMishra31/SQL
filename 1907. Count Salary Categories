SELECT category, 
       COUNT(a.account_id) AS accounts_count
FROM (
    SELECT 'Low Salary' AS category
    UNION ALL
    SELECT 'Average Salary'
    UNION ALL
    SELECT 'High Salary'
) AS categories
LEFT JOIN Accounts a
ON (category = 'Low Salary' AND a.income < 20000)
   OR (category = 'Average Salary' AND a.income BETWEEN 20000 AND 50000)
   OR (category = 'High Salary' AND a.income > 50000)
GROUP BY category;
