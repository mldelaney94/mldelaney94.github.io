---
author: Matthew Delaney
output: pdf_document
---

This blog post deals strictly with the idea of correlation and non-correlation in SQL.

#Correlation
A correlated subquery runs once for each row returned by the outer query. That sounds extremely slow.

The classic example is as follows:

```{SQL}
SELECT employee_number, name
FROM employess emp
WHERE salary > (
	SELECT AVG(salary)
		FROM employees
		WHERE department = emp.department);
```

The inner query, to find the average salary of a department, will be executed for every employee. Now yes, you could save the AVG(salary) and then it would only need to be executed once per department, but the idea here is to introduce a use case and explain why they might be slow.

You don't need to have a correlated subquery only in the WHERE clause, they can appear in SELECT too:

```{SQL}
SELECT employee_number
	,name
	,(SELECT AVG(salary)
		FROM employees
		WHERE department = emp.department) AS department_average
	FROM employees emp;
```


