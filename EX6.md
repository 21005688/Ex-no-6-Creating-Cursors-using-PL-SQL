# Ex. No: 5 Creating Cursors using PL/SQL

### AIM: To create a cursor using PL/SQL.

### Steps:
1. Create employee table with following attributes (empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);
2. Create a cursor named as employee_cursor
3. Using cursor read each record and display the result
4. Close the cursor

### Program:
### Create employee table
```
CREATE TABLE employee9 (empid NUMBER,empname VARCHAR(10),dept VARCHAR(10),salary NUMBER);
INSERT INTO employee9 VALUES (1, 'mei', 'IT', 80000);
INSERT INTO employee9 VALUES (2, 'sonu', 'marketing', 70000);
INSERT INTO employee9 VALUES (3, 'madhu', 'hr', 90000);
``` 

### PLSQL Cursor code
```
set serveroutput on
declare
cursor employee9_cursor is
select empid,empname,dept,salary
from employee9;
emp_id number;
emp_name varchar(20);
emp_dept varchar(20);
emp_salary number;
begin
open employee9_cursor;
loop
fetch employee9_cursor into emp_id,emp_name,emp_dept,emp_salary;
exit when employee9_cursor%NOTFOUND;
DBMS_OUTPUT.PUT_LINE('Employee ID: ' || emp_id);
DBMS_OUTPUT.PUT_LINE('Employee Name: ' || emp_name);
DBMS_OUTPUT.PUT_LINE('Department: ' || emp_dept);
DBMS_OUTPUT.PUT_LINE('Salary: ' || emp_salary);
end loop;
close employee9_cursor;
end;
/
```
### Output:
![output](https://github.com/21005688/Ex-no-6-Creating-Cursors-using-PL-SQL/assets/94747031/0810f88a-954b-42e1-b611-81e8c68b464f)
### Result:
Creating a cursor using SQL/PL has been executed successfully.
