# sql-challenge

/*
--1. List the employee number, last name, first name, sex, and salary of each employee.
SELECT sal.emp_no, emp.last_name, emp.first_name, emp.sex, sal.salary FROM employees AS emp
	INNER JOIN salaries AS sal
	ON sal.emp_no = emp.emp_no
	ORDER BY sal.emp_no;


-- 2. List the first name, last name, and hire date for the employees who were hired in 1986.
SELECT emp_no, last_name, first_name, hire_date FROM employees 
	WHERE EXTRACT (year FROM hire_date) = 1986
	ORDER BY last_name;


-- 3. List the manager of each department along with their department number, department name, employee number, last name, and first name.
SELECT dept_manager.dept_no, departments.dept_name, dept_manager.emp_no, employees.last_name, employees.first_name FROM dept_manager 
	INNER JOIN departments ON dept_manager.dept_no= departments.dept_no
	INNER JOIN employees ON dept_manager.emp_no = employees.emp_no
	ORDER BY dept_manager.dept_no

-- 4. List the department number for each employee along with that employee’s employee number, last name, first name, and department name.
SELECT emp.emp_no, emp.last_name, emp.first_name,dep.dept_name FROM employees AS emp
	LEFT JOIN dept_emp AS dept ON emp.emp_no = dept.emp_no
	INNER JOIN departments AS dep ON dept.dept_no = dep.dept_no
	ORDER BY emp.emp_no

-- 5. List first name, last name, and sex of each employee whose first name is Hercules and whose last name begins with the letter B.
SELECT emp.last_name, emp.first_name FROM employees AS emp
	WHERE (emp.first_name = 'Hercules') AND (LOWER(emp.last_name) LIKE 'b%')
	ORDER BY emp.last_name;
	

-- 6. List each employee in the Sales department, including their employee number, last name, and first name.
SELECT emp.emp_no, emp.last_name, emp.first_name, dep.dept_name FROM employees AS emp
	INNER JOIN dept_emp AS dept ON emp.emp_no = dept.emp_no
	INNER JOIN departments AS dep ON dept.dept_no = dep.dept_no
	WHERE LOWER(dep.dept_name) = 'sales'
	ORDER BY emp_no;
	


-- 7. List each employee in the Sales and Development departments, including their employee number, last name, first name, and department name.
SELECT emp.emp_no, emp.last_name, emp.first_name, dep.dept_name FROM employees AS emp
	INNER JOIN dept_emp AS dept ON emp.emp_no = dept.emp_no
	INNER JOIN departments AS dep ON dept.dept_no = dep.dept_no
	WHERE (LOWER(dep.dept_name) = 'sales') OR (LOWER(dep.dept_name) = 'development')
	ORDER BY emp_no;


-- 8. List the frequency counts, in descending order, of all the employee last names (that is, how many employees share each last name).
SELECT last_name, COUNT(last_name) AS frequency FROM employees GROUP BY last_name
ORDER BY frequency DESC;
*/
