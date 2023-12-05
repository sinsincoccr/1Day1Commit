## JOIN <br/>
두 개 이상의 테이블이나 데이터베이스를 연결하여 데이터를 검색하는 방법 <br/>
테이블을 연결하려면, 최소 하나의 칼럼을 서로 공유하고 있어야한다. <br/>

- INNER JOIN  <br/>
![image](https://github.com/sinsincoccr/1Day1Commit/assets/145324925/dcdafa2e-4247-4094-b0bf-7ebb915fbecf) <br/>
교집합으로, 기준 테이블과 join 테이블의 중복된 값을 보여준다. <br/>
```
SELECT
A.NAME, B.AGE
FROM EX_TABLE A
INNER JOIN JOIN_TABLE B ON A.NO_EMP = B.NO_EMP
```

- LEFT OUTER JOIN <br/>
![image](https://github.com/sinsincoccr/1Day1Commit/assets/145324925/5372ec79-ec9b-4275-8b8d-9b8c42ce6fff) <br/>
기준테이블값과 조인테이블과 중복된 값을 보여준다. <br/>
```
SELECT
A.NAME, B.AGE
FROM EX_TABLE A
LEFT OUTER JOIN JOIN_TABLE B ON A.NO_EMP = B.NO_EMP
```

- RIGHT OUTER JOIN <br/>
![image](https://github.com/sinsincoccr/1Day1Commit/assets/145324925/0701ec55-896a-4001-b9d3-c19711f65356) <br/>
LEFT OUTER JOIN과는 반대로 오른쪽 테이블 기준으로 JOIN하는 것이다. <br/>
```
SELECT
A.NAME, B.AGE
FROM EX_TABLE A
RIGHT OUTER JOIN JOIN_TABLE B ON A.NO_EMP = B.NO_EMP
```

- FULL OUTER JOIN <br/>
![image](https://github.com/sinsincoccr/1Day1Commit/assets/145324925/6298927c-2683-4564-b4e8-8e0def7fb6f3) <br/>
합집합을 말한다. A와 B 테이블의 모든 데이터가 검색된다. <br/>
```
SELECT
A.NAME, B.AGE
FROM EX_TABLE A
FULL OUTER JOIN JOIN_TABLE B ON A.NO_EMP = B.NO_EMP
```

- CROSS JOIN <br/>
![image](https://github.com/sinsincoccr/1Day1Commit/assets/145324925/1bcde504-b391-4fe0-ac5d-8d4185e168bd) <br/>
모든 경우의 수를 전부 표현해주는 방식이다. <br/>
A가 3개, B가 4개면 총 3*4 = 12개의 데이터가 검색된다. <br/>
```
SELECT
A.NAME, B.AGE
FROM EX_TABLE A
CROSS JOIN JOIN_TABLE B
```

- SELF JOIN <br/>
![image](https://github.com/sinsincoccr/1Day1Commit/assets/145324925/01edb507-c81d-4f2e-a4d8-cea126a1d20d) <br/>
자기자신과 자기자신을 조인하는 것이다. <br/>
하나의 테이블을 여러번 복사해서 조인한다고 생각하면 편하다. <br/>
```
SELECT
A.NAME, B.AGE
FROM EX_TABLE A, EX_TABLE B
```


