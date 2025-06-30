# Task-5-SQL-Joins-Inner-Left-Right-Full-

-- Creating table with name of employees with following columns..
create table employees (
    emp_id INT primary key,
    emp_name varchar(50),
    dept_id int
);

-- Creating a table with name of departments with following columns...
create table departments (
    dept_id INT primary key,
    dept_name varchar(50)
);

-- Insert into employees
INSERT INTO employees (emp_id, emp_name, dept_id) VALUES
(1, 'Alice', 101),
(2, 'Bob', 102),
(3, 'Charlie', 103),
(4, 'David', NULL),
(5, 'Eva', 105);

-- Insert into departments
INSERT INTO departments (dept_id, dept_name) VALUES
(101, 'HR'),
(102, 'Engineering'),
(104, 'Marketing');

-- INNER JOIN - which is used to get matching results from both tables...
select e.emp_name, d.dept_name
from employees e
join departments d on e.dept_id = d.dept_id;
 
-- LEFT JOIN - To get all the vlaues from left and matching columns from right tables...
 select e.emp_name, d.dept_name
from employees e
left join departments d on e.dept_id = d.dept_id;

-- RIGHT JOIN - To get all the values from right and matching columns from left tables...
 select e.emp_name, d.dept_name
from employees e
right join departments d on e.dept_id = d.dept_id;


-- FULL JOIN - To get the all matching values from the table along with nulls....
 select e.emp_name, d.dept_name
from employees e
left join departments d on e.dept_id = d.dept_id

union

 select e.emp_name, d.dept_name
from employees e
right join departments d on e.dept_id = d.dept_id;
