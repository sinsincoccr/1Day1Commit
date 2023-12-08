## 기본 명령어  <br/>
1. 데이타 조작어(DML : Data Manipulation Language) <br/>
 insert, update, delete, merge <br/>
2. 데이타 정의어(DDL : Data Definition Language) <br/>
 create, alter, drop, rename, truncate <br/>
3. 데이타검색 <br/>
 select <br/>
 
4. 트랜젝션제어 <br/>
 commit, rollback, savepoint <br/>
5. 데이타 제어어(DCL : Data Control Language) <br/>
 grant, revoke <br/>


## 기초 <br/>
1. select문 <br/>
```
SELECT : 테이블에서 데이터 질의하는 키워드 
FROM : 데이터를 조회하고 싶은 테이블의 이름을 정하는 키워드
WHERE : 데이터를 조회하는 조건을 적는 키워드
GRUOP BY : 특정 속성을 기준으로 그룹화 하여 검샋할 때 속성 키워드
HAVING : 그룹 함수를 포함한 조건 키워드
ORDER BY : 정렬시 사용하는 키워드
```

ex1) employees테이블의 모든 사원의 사원번호, 이름(last_name), 급여 검색 <br/>
```
select employee_id, last_name, salary 
from employees;
```

ex2 GROUP BY) 급여(salary)를 기준으로 그룹화한 결과와 같은 급여를 출력 <br/>
```
SELECT salary, COUNT(*) as employee_count
FROM employees
GROUP BY salary;
```

ex3 ORDER) 급여(salary)를 오름차순으로 정렬 <br/>
```
select last_name, department_id, hire_date
from employees
order by 2 desc, 3 asc;
// 부서코드 내림차순으로 정렬 후,
// 부서코드가 같은 항목들 끼리 입사일기준 오름차순으로 다시 정렬
```

ex4 HAVING) 급여(salary)가 5500 이상인 그룹만 출력 <br/>
```
SELECT salary
FROM employees
GROUP BY salary
HAVING salary >= 5500;
```


2. distinct문 (중복제거) <br/>
```
select distinct department_id from employees;
```


3. LIKE문 (포함된 문자 찾기) <br/>
```
'%d' : d로 끝나는
'a%' : a로 시작하는
'%test% : test가 포함되어있는
'_a%' : 두번째 글자가 a로 시작하고 나머지는 무시
'__a%' : 세번째 글자가 a로 시작하고 나머지는 무시 
```

ex1) 업무ID에 MAN이 포함되어있는 사원들의 이름, 업무ID, 부서ID를 출력 <br/>
```
select last_name, job_id, department_id
from employees
where job_id like '%MAN%';
```

ex2) 업무ID에 M으로 시작하는 사원들의 이름, 업무ID, 부서ID를 출력 <br/>
```
select last_name, job_id, department_id
from employees
where job_id like '%M';
```

