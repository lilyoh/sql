https://www.hackerrank.com/challenges/what-type-of-triangle/problem?isFullScreen=true

```mysql
SELECT 
CASE
    WHEN A>=B+C OR B>=C+A OR C>=A+B THEN 'Not A Triangle'
    WHEN A=B AND B=C THEN 'Equilateral'
    WHEN (A=B OR B=C OR C=A) THEN 'Isosceles'
    ELSE 'Scalene'
END AS Type
FROM TRIANGLES;
```

새로 알게 된 것
- 삼각형은 한 변의 길이가 다른 두 변을 합한 것보다 크거나 같으면 안됨