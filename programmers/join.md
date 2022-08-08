https://school.programmers.co.kr/learn/courses/30/lessons/59045

```mysql
SELECT I.ANIMAL_ID, I.ANIMAL_TYPE, I.NAME
FROM ANIMAL_INS I
JOIN ANIMAL_OUTS O
ON I.ANIMAL_ID = O.ANIMAL_ID
WHERE I.SEX_UPON_INTAKE != O.SEX_UPON_OUTCOME
ORDER BY ANIMAL_ID;
```

- 조건을 잘 읽고 어렵게 생각하지 말자
- 들어올 때는 중성화 되지 않았지만, 나갈 때는 중성화된 것을 찾으려면 그냥 값이 변한 게 있는지 찾으면 됨