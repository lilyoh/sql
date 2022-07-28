https://www.hackerrank.com/challenges/weather-observation-station-5/problem?isFullScreen=true

```SQL
SELECT CITY, LENGTH(CITY) 
FROM STATION
ORDER BY LENGTH(CITY) ASC, CITY ASC
LIMIT 1;

SELECT CITY, LENGTH(CITY) 
FROM STATION
ORDER BY LENGTH(CITY) DESC, CITY ASC
LIMIT 1;
```

결과를 얻기 위해서는 2개의 쿼리로 나눠서 적어도 됨

문자열의 길이를 얻기 위한 함수는 `LENGTH()`

정렬하기 위해서는 `ORDER BY` 를 사용
오름차순은 ASC 내림차순은 DESC
