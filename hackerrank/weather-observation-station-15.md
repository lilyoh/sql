```mysql
SELECT ROUND(LONG_W, 4) FROM STATION
WHERE LAT_N < 137.2345
ORDER BY LAT_N DESC 
LIMIT 1;
```

- 최대값을 구할 때 다른 조건이 있을 경우에는 max가 아니라 내림차순 정렬한 다음 1번째 값을 구하면 됨
```mysql
-- 이 부분
ORDER BY LAT_N DESC 
LIMIT 1;
```