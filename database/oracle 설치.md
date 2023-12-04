### 1. 설치 파일 다운로드 <br/>
링크 : https://www.oracle.com/kr/database/technologies/oracle-database-software-downloads.html#19c <br/>

### 2. 다운받은 파일 이동과 압축해제
1) c드라이브나 d드라이브에 oracleinstall 이라는 폴더 생성
2) 그 폴더안에 다운받은 압축파일 이동 시키기
3) 압축 해제하기


### 3. 설치 시작
압축해제한 폴더에서 setup.exe (관리자 권한으로 실행)

### 4. 설치 과정
1) 단일 인스턴스 데이터베이스 생성 및 구성 선택 > 다음
2) 데스크톱 클래스 선택 > 다음
3) 가상 계정 사용 선택 > 다음
4) 모두 그대로 두고, 아래 두 곳만 작성 후 다음 누르기
비밀번호 : 원하는 비번 작성
비밀번호 확인 : 동일하게 작성

### 4.1 SQL Developer 툴 설치
https://www.oracle.com/kr/database/sqldeveloper/ 운영체제 버전에 맞게 다운

### 5. 오라클 접속하여 관리자로 로그인하기
1) 윈도우 시작버튼을 눌러서 프로그램 목록중 Oracle… 관련 폴더 생성되었는지 확인
2) 검색에 sqlplus 입력 혹은 Oracle 폴더안에 SQL Plus 프로그램 찾아서 실행
3) 사용자명 입력 : sys /as sysdba
비밀번호 입력 : 설치시 지정한 비밀번호 입력
비밀번호까지 입력하고 엔터! 
4) 화면에 접속됨 이라고 나오고 프롬프트에 SQL> 이라고 뜨면
정상으로 설치되어 관리자 계정으로 로그인까지 확인 완료!

### sqlplus에서 계정 생성  
[ 사용자 정보 확인 ]  
-- 모든 계정에 대한 정보 확인  
SELECT * FROM ALL_USERS;  
-- 모든 계정에 대한 이름 확인  
SELECT USERNAME FROM ALL_USERS;  
[ 사용자 계정 추가 ]  
ALTER SESSION SET "_ORACLE_SCRIPT"=true;  
-- 사용자 계정 생성  
CREATE USER 계정명 IDENTIFIED BY 비밀번호;  
-- 사용자 계정 생성후 권한 부여하기  
GRANT 권한명, 권한명 TO 계정명;  
-- (EX)  
GRANT CONNECT, RESOURCE TO 계정명;  
-- 테이블 생성등 테이블 스페이스 권한 부여  
ALTER USER 계정명 DEFAULT TABLESPACE USERS QUOTA UNLIMITED ON USERS  
