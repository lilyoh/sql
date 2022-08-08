https://school.programmers.co.kr/learn/courses/30/lessons/59040

```mysql
-- ANIMAL_TYPE이 같은 것들끼리 묶어서 조회하기 위해 GROUP BY 사용
SELECT ANIMAL_TYPE, COUNT(ANIMAL_TYPE)
FROM ANIMAL_INS
GROUP BY ANIMAL_TYPE
ORDER BY ANIMAL_TYPE;
```

- ~별로 개수를 집계 할 때는 group by 를 사용하자  
- 나는 group by 를 왜 이렇게 이해하기 어려워하고 못 쓰는 걸까  
- 계속 해보면 되지 ^-^