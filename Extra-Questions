- Find the 4 highest salary

```
SELECT name, salary
FROM Employee e1
WHERE N-1 = (
  SELECT COUNT (DISTINCT salary)
  FROM Employee e2
  WHERE e1.salary < e2.salary
  )
```
- Clauses that are used in SQL:
  - SELECT - column
  - FROM - table
  - WHERE - rows 
  - GROUP BY - rows
  - HAVING - 
  - LIKE

- Print the count of employee whose name starts with letter A
```
SELECT COUNT(name)
FROM employee
WHERE name LIKE 'A%';
```
- Print the name of employee whose name ends with letter 'y' and the length of name is 5 letters.
```
SELECT name
FROM employee
WHERE name LIKE '____y';
```
```
SELECT name FROM employee
WHERE name LIKE '%y'
	AND LENGTH(name) = 5
  ```

- Write a SQL query to fetch project-wise count of employees sorted by project's count in descending order
```
SELECT project, COUNT(EmpId)
FROM EmployeeSalary
  GROUP by project
  ORDER by project DESC
```

- Write a query to fetch employee names and salary records. Return employee details even if the salary record is not present for the employee
```
SELECT FullName, Salary
FROM
  EmployeeDetails LEFT JOIN EmployeeSalary
  ON EmployeeDetails.EmpId = EmployeeSalary.EmpId
```
- Write a query to fetch all Employees who are also managers from EmployeeDetails table
```
SELECT FullName
FROM
  EmployeeDetails as em1 JOIN EmployeeDetails as em2
  ON em1.EmpId = em2.ManagerId
```
