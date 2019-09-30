## MySQL

로그인 -  mysql -u root -p  
root 위치에 다른 계정 가능, 명령어를 치면 password를 입력하라고 함.

유저정보 확인 - select host,user,password from mysql.user;

데이터베이스 확인 - show databases;

데이터베이스 선택 - use test;  
확인한 데이터베이스를 선택할 수 있음.


### 외부 접근 계정 추가 하기

CREATE USER 계정이름@'아이피.%' IDENTIFIED BY '비밀번호';  
%를 붙이면 포함된 모든 IP에서 접근가능, EX ) '192.168.%'  

권한 부여  
GRANT ALL PRIVILEGES ON test.* TO root@'192.168.%';  
test 는 데이터 베이스 이름

적용하기  
FLUSH PRIVILEGES; 


특정 계정으로 원하는 data base에 접근 가능함.