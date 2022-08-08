# pivot table
- 행으로 적혀있는 데이터를 열로 만들어 보여줌


# 풀이 과정
## 모든 값을 직업별로 총 4개의 열로 보여줌
- 이때는 값이 순서없이 들어가있음
- 우리는 위에서부터 알파벳 순서대로 값을 보여줘야 하고, null 이 맨 마지막에 와야 함
```mysql
SELECT CASE WHEN occupation = 'Doctor' THEN name END AS Doctor,
       CASE WHEN occupation = 'Professor' THEN name END AS Professor,
       CASE WHEN occupation = 'Singer' THEN name END AS Singer,
       CASE WHEN occupation = 'Actor' THEN name END AS Actor
FROM occupations
ORDER BY name;
```

## 각 값이 각 직업별로 몇 번째 값인지 확인
- 몇 번째 값인지 확인하면 1번 값부터 오름차순으로 값을 보여줄 수 있음
- null 값은 맨 아래에 나올 것
- 각 직업별로 변수를 선언해주고, 값을 찾을건데 찾을 때마다 변수값을 1씩 올리면서 인덱싱 해줌
```mysql
SET @D=0, @P=0, @S=0, @A=0;

SELECT name, occupation,
    CASE 
    WHEN occupation = "Doctor" THEN (@D:= @D+1)
    WHEN occupation = "Professor" THEN (@P:= @P+1)
    WHEN occupation = "Singer" THEN (@S:= @S+1)
    WHEN occupation = "Actor" THEN (@A:= @A+1)
    END AS rownumber
FROM occupations;
```

## 위의 두개 합치기
```mysql
SET @D=0, @P=0, @S=0, @A=0;

SELECT CASE WHEN Occupation = 'Doctor' THEN Name END AS Doctor,
       CASE WHEN Occupation = 'Professor' THEN Name END AS Professor,
       CASE WHEN Occupation = 'Singer' THEN Name END AS Singer,
       CASE WHEN Occupation = 'Actor' THEN Name END AS Actor,
       CASE
       WHEN Occupation = 'Doctor' THEN (@D:=@D+1)
       WHEN Occupation = 'Professor' THEN (@P:=@P+1)
       WHEN Occupation = 'Singer' THEN (@S:=@S+1)
       WHEN Occupation = 'Actor' THEN (@A:=@A+1)
       END AS RowNumber
FROM Occupations
ORDER BY Name;
```

## rownumber 라는 새로운 파생컬럼을 기준으로 그룹핑한 후 각 직업별 name 들의 최솟값을 출력
```mysql
-- 각 직업별 Index를 세기 위한 변수 설정
SET @D=0, @P=0, @S=0, @A=0;

-- 문자열의 알파벳순서에서 최솟값(MIN)은 A(a)로 시작하는 것을 추출해줌!
SELECT MIN(Doctor), MIN(Professor), MIN(Singer), MIN(Actor)
FROM (SELECT CASE WHEN Occupation = 'Doctor' THEN Name END AS Doctor,
             CASE WHEN Occupation = 'Professor' THEN Name END AS Professor,
             CASE WHEN Occupation = 'Singer' THEN Name END AS Singer,
             CASE WHEN Occupation = 'Actor' THEN Name END AS Actor,
             CASE
             WHEN Occupation = 'Doctor' THEN (@D:=@D+1)
             WHEN Occupation = 'Professor' THEN (@P:=@P+1)
             WHEN Occupation = 'Singer' THEN (@S:=@S+1)
             WHEN Occupation = 'Actor' THEN (@A:=@A+1)
             END AS RowNumber
       FROM Occupations
       ORDER BY Name) sub
GROUP BY RowNumber;
```