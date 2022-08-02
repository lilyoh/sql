```mysql
SET @TEMP:= 21;
SELECT REPEAT('* ', @TEMP := @TEMP - 1)
FROM INFORMATION_SCHEMA.TABLES;
```

아직 잘 모르겠지만
- SET @변수명:= 값;
- REPEAT(반복할 수 혹은 문자, @변수명:= @변수명 - 줄어들만큼)
- FROM INFORMATION_SCHEMA.TABLES;

```mysql
SET @TEMP:= 0;
SELECT REPEAT("* ", @TEMP:= @TEMP + 1)
FROM INFORMATION_SCHEMA.TABLES
WHERE @TEMP < 20;
```
- TEMP를 0으로 하고 0 ~ 19까지 돌리는 것