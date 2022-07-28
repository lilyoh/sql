https://www.hackerrank.com/challenges/weather-observation-station-6/problem?isFullScreen=true

```SQL
SELECT DISTINCT CITY FROM STATION
WHERE LEFT(CITY, 1) IN ('A', 'E', 'I', 'O', 'U');
```

문자열을 찾을 때는 따옴표 꼭 붙여줘야 함
아래와 같이 제출해서 빠꾸먹었음

error case
```sql
SELECT DISTINCT CITY FROM STATION
WHERE LEFT(CITY, 1) IN (A, E, I, O, U);
```