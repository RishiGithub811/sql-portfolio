create database testsql;
use testsql;

-- Display highest and lowest salary corresponding to each Department. 
-- Schema setup
```sql
CREATE TABLE employees (
    id INT PRIMARY KEY,
    name VARCHAR(100),
    dept VARCHAR(50),
    salary DECIMAL(10, 2)
);


INSERT INTO employees (id, name, dept, salary) VALUES
(1, 'Alice Johnson', 'Finance', 65000.00),
(2, 'Bob Smith', 'Engineering', 85000.00),
(3, 'Carol Lee', 'Marketing', 72000.00),
(4, 'David Kim', 'Engineering', 88000.00),
(5, 'Eva Brown', 'Human Resources', 60000.00),
(6, 'Frank Harris', 'Finance', 67000.00),
(7, 'Grace Patel', 'Sales', 71000.00),
(8, 'Henry Zhao', 'Engineering', 90000.00),
(9, 'Irene Clark', 'Marketing', 69000.00),
(10, 'Jack Wilson', 'Sales', 73000.00);
```

select * from employees;

-- Solution Query
```sql
select *,
MAX(salary) over (partition by dept order by salary DESC) as highest_salary,
MIN(salary)over (partition by dept order by salary DESC
range between unbounded preceding and unbounded following) as  lowest_salary
from employees;
```

