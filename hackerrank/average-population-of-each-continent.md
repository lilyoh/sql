```mysql
SELECT COUNTRY.CONTINENT, FLOOR(AVG(CITY.POPULATION))
FROM CITY
JOIN COUNTRY
    ON CITY.COUNTRYCODE = COUNTRY.CODE
GROUP BY COUNTRY.CONTINENT;
```
<문제 해석>
- 모든 CONTINENT NAME 쿼리
- 각 CONTINENT의 CITY POPULATION 평균 쿼리
- CITY POPULATION은 가장 가까운 정수로 내림함

<풀이>
1. CONTINENT 별로 각 CONTINENT의 CITY 전체의 평균 인구를 구해야 하니, GROUP BY COUNTRY.CONTINENT 해줌
2. 내림은 FLOOR

https://www.hackerrank.com/challenges/average-population-of-each-continent/problem?isFullScreen=true