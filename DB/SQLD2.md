# SQLD 시험준비
## 2. SQL 기본 및 활용

### Q. 1
> 다음중 DDL(Data Definition Language)에 해당되지 않은 것은?
  1. ALTER TABLE
  2. CREATE INDEX
  3. DROP TABLE
  4. REVOKE
  
답 : 4
```txt
  REVOKE는 권한을 삭제하는 것으로 DCL에 해당된다.
```
### Q. 2
> 다음중 트랜잭션(Transaction)에 대한 설명이다. 올바르지 않은 것은?
  1. 트랜잭션은 데이터베이스에서 독립적으로 처리될 수 있는 최소 단위 연산이다.
  2. 트랜잭션의 수행결과는 Commit 혹은 Rollback을 수행해야 한다. (원자성)
  3. A 트랜잭션이 실행하는 도중에 B 트랜잭션이 끼어들어 결과 값을 변경하여 데이터를 이상하게 만들수있다. (격리성X)
  4. 트랜잭션은 가급적 빠르게 처리되어야 한다. 
  
답 : 3
```txt
  트랜잭션은 데이터베이스에서 연산을 처리하는 것으로 원자성, 일관성, 격리성, 지속성의 특징을 가지며
  고립성은 완료되지 않은 트랜잭션의 처리 결과를 다른 트랜잭션이 접근할 수가 없다.
```
### Q. 3
> 다음의 설명으로 올바른 것은?

```txt
  조인되는 N개의 테이블을 모두 정렬한 후에 조인을 수행한다.
```

  1. Hash Join
  2. Sort Merge
  3. Nested Loop Join
  4. Inner Join
  
답 : 2
```txt
  Sort Merge Join은 테이블을 정렬(Sort)한 후에 정렬된 테이블을 병합(Merge)하면서 조인을 실행한다.
```

### Q. 4 
> SELECT문의 처리 순서는?
```txt
  1. SELECT
  2. FROM
  3. WHERE
  4. GROUP BY
  5. ORDER BY
```
답 : FROM -> WHERE -> GROUP BY -> SELECT -> ORDER BY

### Q. 5
> 다음은 null 값에 대한 설명이다. 올바른 것은?
  1. 데이터베이스의 null 값의 의미는 DBMS 종류별로 다르게 해석한다
  2. MSSQL에서 null 값은 0이다.
  3. Oracle에서 null은 TRUE 혹은 FALSE의 의미이다.
  4. null 값은 아직 알려지지 않은 미지의 값이다.
  
답 : 4

### Q. 6
> 다음의 SQL문을 보고 올바르지 않은 것은?
```txt
가. 실제 데이터
  DEPTNO      SAL
-------------------
    10         
    10        1000
    10        2000
    20        
    20        1500
나. SELECT문
SELECT DEPTNO, SUM(NVL(SAL,0)) FROM
DEPT GROUP BY DEPTNO
```
  1. SELECT문에 WHERE 조건이 없으므로 연산에 참여하는 총 행수는 5개이다.
  2. NVL(SAL,0)문에서 NVL은 NULL에 대한 합계오류를 예방한다.
  3. DEPTNO 10의 합계는 3000이고 20의 합계는 1500이다.
  4. 부서별 합계를 계산할 때 NULL 값을 만나면 0으로 치환한다.

답 : 2
```txt
  집계함수에서는 null 값을 나오면 무시하고 null이 아닌것만 처리를 한다. 
  즉, 집계함수 내부에는 NVL함수가 필요가 없다.
```

### Q. 7
> 다음의 PL/SQL에 대한 설명이다. 올바르지 않은 것은?
  1. PL/SQL은 절차형 언어이다.
  2. PL/SQL에서 테이블을 생성할수는 없다.
  3. PL/SQL에서 조건문은 IF~THEN~ELSEIF~END IF 또는 CASE WHEN을 사용한다.
  4. PL/SQL에서 name이라는 변수에 'aaa'를 대입할 경우 ":="을 사용한다.
  
답 : 2
```txt
  PL/SQL은 절차형 언어로 PL/SQL 내부에서 테이블을 생성할 수 있다.
  종류로는 프로시저, 함수, 트리거가 있다.
```

