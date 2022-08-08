https://school.programmers.co.kr/learn/courses/30/lessons/59041

```mysql
SELECT NAME, COUNT(NAME)
FROM ANIMAL_INS
WHERE NAME IS NOT NULL
GROUP BY NAME
HAVING COUNT(NAME) >= 2
ORDER BY NAME;
```

- name 별로 각 name 이 중복된 횟수를 쿼리할 거기 때문에 group by 사용  
- grouping 하고 난 뒤의 결과를 보고, 그 결과가 (중복된 횟수가) 2 이상인 것을 발라낼거기 때문에 having 사용

https://school.programmers.co.kr/learn/courses/30/lessons/62284

```mysql
SELECT CART_ID FROM CART_PRODUCTS
WHERE NAME IN ('Milk', 'Yogurt')
GROUP BY CART_ID
HAVING COUNT(DISTINCT NAME) = 2;
```

- 많이 나올거 같은 유형 - 복습해~