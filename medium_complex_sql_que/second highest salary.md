'''sql
CREATE TABLE Employee (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    salary INT
);

INSERT INTO Employee (name, salary) VALUES
('Amit', 50000),
('Ravi', 60000),
('Priya', 75000),
('Neha', 80000),
('Vikram', 75000),
('Kiran', 95000),
('Anil', 60000);

select * from Employee ;


-- Solution

select max(salary) from Employee
where salary < (select max(salary) from Employee); 

-- query to find nth salary. 

select salary from 
Employee
ORDER BY salary desc
limit 1
offset 5;
'''
