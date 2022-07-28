https://www.hackerrank.com/challenges/weather-observation-station-8/problem?isFullScreen=true

```SQL
SELECT DISTINCT city
FROM station
WHERE
    LEFT(CITY, 1) IN ('A', 'E', 'I', 'O', 'U')
    AND RIGHT(CITY, 1) IN ('A', 'E', 'I', 'O', 'U');
```


정규식 사용한 풀이방법 #정규식
```SQL
SELECT DISTINCT city
FROM station
WHERE city REGEXP '[aeiou]$' and city REGEXP '^[aeiou]';
```

$는 끝을 의미  
^는 시작을 의미