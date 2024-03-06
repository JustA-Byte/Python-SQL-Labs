## Project description
This project is to outline the understanding of and execution of querying databases using SQL. This document describes the process taken following a set scenario, wherever there is italic text, it is part of the scenario description.

“You are a security professional at a large organization. Part of your job is to investigate security issues to help keep the system secure. You recently discovered some potential security issues that involve login attempts and employee machines.

Your task is to examine the organization’s data in their ```employees``` and ```log_in_attempts``` tables. You’ll need to use SQL filters to retrieve records from different datasets and investigate the potential security issues.”

## Retrieve after hours failed login attempts
“You recently discovered a potential security incident that occurred after business hours. To investigate this, you need to query the ```log_in_attempts``` table and review after hours login activity. Use filters in SQL to create a query that identifies all failed login attempts that occurred after 18:00.”

To retrieve the information in the scenario above I would need to pull all data from the ```log_in_attempts``` table and use filters to pull the failed login attempts after 6pm. To do this I would use the following SQL command:

![image](https://github.com/JustA-Byte/Python-SQL-Labs/assets/161458321/e1179cd7-01bb-4a16-968b-980296d7637b)

Lets break this down:
SELECT * - this selects all data from the specified table
FROM log_in_attempts - this is the table we are pulling data from
WHERE login_time > ‘18:00:00’ AND success = 0; - this is the filter that is specifying in the login_time column the time should be greater than 18:00:00 (or 6pm) AND that the value of the success column is 0 (or false; which in this case is a failed attempt)

This SQL command then filters out the data required:
![image](https://github.com/JustA-Byte/Python-SQL-Labs/assets/161458321/c4e3777b-89c7-4969-b2d7-c7c95311ded7)

## Retrieve login attempts on specific dates
“A suspicious event occurred on 2022-05-09. To investigate this event, you want to review all login attempts which occurred on this day and the day before. Use filters in SQL to create a query that identifies all login attempts that occurred on 2022-05-09 or 2022-05-08.”

To retrieve the required information I need to execute the following command:

![image](https://github.com/JustA-Byte/Python-SQL-Labs/assets/161458321/4ca3ce76-2070-400a-9357-640ff46f3bcf)

Breaking this down;
SELECT * - this selects all data from the specified table
FROM log_in_attempts - this is the table we are pulling data from
WHERE login_date = '2022-05-09' OR login_date = '2022-05-08'; - this filter allows the system to return data where dates can be either of the specified dates 2022-05-09 OR 2022-05-08

## Retrieve login attempts outside of Mexico
“There’s been suspicious activity with login attempts, but the team has determined that this activity didn't originate in Mexico. Now, you need to investigate login attempts that occurred outside of Mexico. Use filters in SQL to create a query that identifies all login attempts that occurred outside of Mexico.”

To retrieve the required information I need to execute the following command:

![image](https://github.com/JustA-Byte/Python-SQL-Labs/assets/161458321/dea83b19-cd08-4619-88b7-3dd15e1ecd26)

Breaking this down;
SELECT * - this selects all data from the specified table
FROM log_in_attempts - this is the table we are pulling data from
WHERE NOT country LIKE 'MEX%'; - this filter specifies that we want data that does NOT start with the term MEX. The % operator is a wildcard that allows for all other characters after MEX. This covers any iteration of the word Mexico for example, this could be written in the database as 2 different versions; MEX and MEXICO.

## Retrieve employees in Marketing
“Your team wants to perform security updates on specific employee machines in the Marketing department. You’re responsible for getting information on these employee machines and will need to query the ```employees``` table. Use filters in SQL to create a query that identifies all employees in the Marketing department for all offices in the East building.”

To retrieve the required data, I can use the following command:

![image](https://github.com/JustA-Byte/Python-SQL-Labs/assets/161458321/f431240b-f8af-4e9f-ad1b-fc9358561167)

To break this down:
SELECT * - this selects all data from the specified table
FROM employees - this is the table we are pulling data from
WHERE department = 'Marketing' AND office LIKE 'EAST%'; - this filter specifies that we want data where the department is specifically Marketing and that the office field is anything beginning with EAST. This is because in the East building there may be multiple offices beginning with EAST, such as 'East-170' or 'East-320'; so the % accounts for any characters after the EAST portion of the data.

## Retrieve employees in Finance or Sales
“Your team now needs to perform a different security update on machines for employees in the Sales and Finance departments. Use filters in SQL to create a query that identifies all employees in the Sales or Finance departments. “

To retrieve the required data, I can use the following command:

![image](https://github.com/JustA-Byte/Python-SQL-Labs/assets/161458321/bb580730-ea12-45c8-a352-dccbbd9541df)

To break this down:
SELECT * - this selects all data from the specified table
FROM employees - this is the table we are pulling data from
WHERE department = 'Finance' OR department = 'Sales'; - this filter specifies that the data to be returned should shown the department as either Finance or Sales, and ignore all other data. Even though I’m searching for data from the same department field, I need to ensure to specify this separately in the filter arguments

## Retrieve all employees not in IT
“Your team needs to make one more update to employee machines. The employees who are in the Information Technology department already had this update, but employees in all other departments need it. Use filters in SQL to create a query which identifies all employees not in the IT department.”

To retrieve the required data, I can use the following command:

![image](https://github.com/JustA-Byte/Python-SQL-Labs/assets/161458321/d02ecb0d-a222-4c24-9054-b0986c5a324a)

To break this down:
SELECT * - this selects all data from the specified table
FROM employees - this is the table we are pulling data from
WHERE NOT department = 'Information Technology'; - this filter specifies that the data returned should NOT show Information Technology in the department field.

## Summary
Throughout this document I have covered multiple different types of operators in how to filter data using SQL queries. This allows me to specify the results for any particular task that I’m assigned to when working in the cyber security field and respond to incidents in a more efficient way.
