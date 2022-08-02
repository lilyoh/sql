```mysql
SELECT 
    CEIL(AVG(Salary) - AVG(REPLACE(Salary, 0, "")))
FROM EMPLOYEES;
```

- CEIL : 올림하는 메소드
- REPLACE : 어떤 값을 어떤 값으로 대체하는 메소드
  `REPLACE(Salary, 0, '')`  
   -> 0을 ''으로 대체함으로써 0을 없애는 코드