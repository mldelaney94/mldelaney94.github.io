---
author: Matthew Delaney
---

Queries, subqueries, correlation, non-correlated.

#Query

What is a query in SQL? Its basic function is to return information matching the query constraints in a new table. And they all start with select.

##Subquery

A subquery is a query inside a query, like a nested loop.

```{SQL}
SELECT MAX(price) FROM asx 
WHERE price < ( SELECT MAX(price) FROM asx);
```

This subquery excludes the max salary from the data set and then finds the max salary. It is not correlated because it does not depend on the outer query and could run as a standalone query.

#Correlation

A correlated subquery is a query that uses information from the outer query. It is evaluated once for each row processed by the outer query, and thus is likely to be slow. 

Now lets find the nth max salary using a correlated subquery


```{SQL}
SELECT Id, Salary
FROM Employee e
WHERE 2=(SELECT COUNT(DISTINCT Salary) 
	FROM Employee p
	WHERE e.Salary<=p.salary)
```

So this subquery loops through every row in Id Salary and counts the distinct number of salaries that are greater than or equal to it in that same table. If it returns 2, then it returns the row. Which means that it will have one salary greater than it and one salary equal to itself (i.e. itself). For the case of multiple same salaries the distinct keyword is used. This query took 1 minute 13 seconds to return on its first run, whilst the non-correlated query above took 75ms.


