https://school.programmers.co.kr/learn/courses/30/lessons/59413

```mysql
SET @HOUR := -1;

SELECT 
    (@HOUR := @HOUR + 1) AS HOUR,
    (SELECT COUNT(*) FROM ANIMAL_OUTS WHERE HOUR(DATETIME) = @HOUR) AS COUNT
FROM ANIMAL_OUTS
WHERE @HOUR < 23;
```

- set 옆에 변수명과 초기값을 설정 가능
  - @가 붙은 변수는 프로시저가 종료되어도 유지됨
- := 는 비교연산자 = 와 혼동을 피하기 위한 대입연산자
- HOUR의 값은 -1 로 세팅되어 0부터 시작해서 23 전까지 총 23번 돌기