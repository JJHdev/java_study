## 1. 컬렉션프레임워크 복습. 
 1-1. keySet
 1-2. map
 
##  2. LIFO FIFO
1. LIFO : 후입선출
2. FIFO : 선입선출

## 3. Oracle
- 설치방법
 1. 오라클 사이트 들어가서 로그인 한다.
   // JDK 설치는 사전에 되어있어야한다.
 2. Product → HardWare and Software → Oracle DateBase → 원하는 오라클 설치 
 본강의에서는 11을 설치할 예정이다.
 
 (https://www.oracle.com/database/technologies/xe-prior-release-downloads.html)
 
 3. 위 사이트 들어가면 11버전을 설치 한다. 각자 맞는 운영체제에 맞춰서.
 
 4. 로컬디스크에 DB파일 만든다.  → pg → 압축풀기 → setup 설치하기. → 패스워드 하기(꼭 잊어먹지 않기)
 enter PAssword : asdf123
 ConFirm Password: asdf123
 
 설치완료.
 
 ## 4. Oracle
* Oracle 접속
1.프롬프트접속
실행-cmd입력
>sqlplus
Enter user-name: system
Enter password:


2.SQL*PLUS 접속
Run SQL Command Line실행


* oracle 계정
SYS	: 최상위관리자
SYSTEM	: 관리자


* 또 다른 user로 접속
connect  user명/비번


exit : 종료

* user, 비번 조회
connect  system/asdf123;
select   username, password  
from  dba_users;

* 비번 변경
alter user user명
identified by  새비번;

SQL> alter user system
  2  identified by asdf;
User altered.

* 데이터 저장단위
-물리적 단위 / 논리적 단위
-논리적 단위:(크기순)데이터블록->익스텐트->세그먼트->테이블스페이스

* 테이블스페이스란? 
-table들을 담을 커다란 공간.
하나 또는 여러개의 파일로 구성된 논리적 데이터 저장 공간.
정의된 크기만큼 테이블스페이스가 생성되면
데이터가 그 크기를 넘길 때 까지
지정된 크기를 유지.
만약 데이터가 그 크기보다 많이 입력되면 자동으로 확장.


* 테이블스페이스 생성하기
문법>
create tablespace 테이블스페이스명
datafile '/경로/테이블스페이스파일명.dbf'
size 초기용량(100m,1g 등)
[autoextend on]  --자동확장여부
[next 자동증가용량]
[maxsize unlimited];

* 계정생성시 기본tablespace를 미지정하면 System tablespace로 저장된다
참고>System tablespace란?
데이터베이스 운영에 필요한 기본 정보를 담는 Data Dictionary table이 저장되는 공간.
일반 user들의 오브젝트를 저장하지 않는 것을 권장

    
* 테이블스페이스 삭제방법
drop tablespace 테이블스페이스명
    
ex)
SQL> create tablespace myts
  2  datafile 'C:\DBStudy\oradata\myoracle\myts.dbf'
  3  size 100m
  4  autoextend on
  5  next 5m;
Tablespace created.    

 *query문(질의어)

 * SQL*Plus 명령어
 ; 생량가능
 단어축약
 conn[ect] :다른 user로 접속
 ed[it] : 버퍼에 저장된 쿼리문 불러와 편집
 exit : 종료
 show user : 접속중인 유저명 조회
 / : 실행(run)
 @ : ~에  (@C:\DBstudy\scott.sql) 이경로에 있는 scott.sql을 실행
 insert into 테이블명 values : 테이블명에 데이터 입력.
 commit : 커밋
 desc 테이블명 : 테이블의 구조 구격 조회
 
  *user 생성
 문법 > create user 유저명
 identified by 비밀번호
 [default tablespace 기본테이블스페이스명]
 [temporary tablespace];  --임시테이블스페이스명 뜻
 
 ex)
 create user ora_user
 identified by hong
 default tablespace myts
 temporary tablespace temp;
    
* 권한부여(아이디 생성에 관한)
  role : 권한들의 집합,모음
  문법 > grant 권한,권한,... 
   	    to 계정명(or 롤명)

  - dba(dba 권한), connect(db연결관련 등), resource(객체생성, 변경, 제거 등)
  
    
    ---- table 조회
    
    ★★★★★
    *조회
    select { *or |or 1컬럼명,2컬럼명}
    from 테이블
    []
    []
    []
    [];
    
    ex)
    select *  (모든 컬럼명)
    from tab; (모든테이블 보여줘)
    
TNAME               |        TABTYPE
--------------------|-----------------------
BONUS (보너스)       |        TABLE(테이블타입)
DEPT  (부서명)     	|		 TABLE(테이블타입)
EMP  (사원)         |        TABLE    (테이블타입) 
SALGRADE (급여)     |         TABLE (테이블타입) 
