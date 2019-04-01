# 모두의 주방(Kitchen Of All)
 - 모두의 주방(SpringMVC + hibernate-validator + mybatis + oracleDB 를 이용한 레시피 공유 사이트)
 - 레시피 공유 사이트 , 해쉬 태그를 이용하여 가지고 있는 재료나 먹고 싶은 음식을 검색할 수 있다.

모두의 주방(Kitchen Of All) 구현 기능
-------------
-  로그인
-  회원가입(hibernate-validator를 이용한 유효성 검증)
-  사진 형식의 게시글 입력,수정,삭제
-  글 입력시 사진 업로드
-  댓글 입력
-  좋아요 구현(Jquery Ajax 사용)

개발 환경 및 기술
-------------
- eclipse
- apache-tomcat-8.0.46
- oracle 11g:xe
- Spring Framework 4.2.4.RELEASE
- mybatis 3.4.6 /  mybatis-spring 1.3.2
- hibernate-validator 4.2.0.Final
- javaScript
- EL / JSTL
- w3.css
- jquery Ajax


게시판 table db 쿼리문
-------------
<pre><code>
create table board_modu(
bno number(5) primary key,
id varchar2(30) not null,
title varchar2(100) not null,
content varchar2(2000),
readcount number(4) default 0,
img varchar2(100),
writedate DATE DEFAULT sysdate,
comment_count number(10) default 0,
like_it number(10) default 0,
hashtag varchar2(100)
);

create sequence board_modu_seq start with 1 increment by 1;
</code></pre>


회원 table db 쿼리문
-------------
<pre><code>
create table modu_member(
name varchar2(30) ,
id varchar2(30) primary key,
pwd varchar2(30) not null,
email varchar2(30),
phone varchar2(30)
);
</code></pre>


댓글 table db 쿼리문
-------------
<pre><code>
create table modu_comment(
comment_num number(5) primary key,
bno number(5),
id varchar2(30),
content varchar2(600),
writedate DATE DEFAULT sysdate
);

create sequence modu_comment_seq start with 1 increment by 1; 
</code></pre>


버전 관리
-------------
### KOA_ver1.zip
- 기능만 구현 ( 로그인, 회원가입, CRUD게시판 )

### KOA_ver2.zip
 - 패치 노트 (3/30)
>1. viewResolver추가  
>2. 댓글 기능 추가  
>3. 좋아요 기능 추가(Ajax로 구현)  
>4. 댓글 갯수, 좋아요 갯수 bordList에서 보이게 수정  


### KOA_ver3.zip
 - 패치 노트 (3/31)
> 1. viewResolver 한개 더 사용을 위해 servlet-context.xml(=presentation-layer2.xml) 한 개 더 만듦   
>    presentation-layer.xml => board에 관련된 요청만 처리(*.do)  
>    presentation-layer2.xml => user에 관련된 요청만 처리(*.userdo)  
>    따라서 index, header , footer를 제외한 모든 jsp는 WEB-INF 밑에 각각 폴더로 정리해 놓음 
> 2. 회원가입 폼에서 hibernate-validator를 이용해여 유효성 검사하도록 수정 
> 3. getboardList.jsp => 사진형List로 바꿈  
> 4. css 적용 (index, 로그인폼, 회원가입 폼, 글리스트)
     
### KOA_final.zip
 - 패치 노트 (4/1)
> 1. 프로젝트 최종본 
> 2. CSS 모두 적용 
     
