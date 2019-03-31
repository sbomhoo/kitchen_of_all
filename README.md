# kitchen_of_all
 모두의 주방(SpringMVC + mybatis + oracleDB 를 이용한 레시피 공유 사이트)


## KOA_ver1.zip
- 기능만 구현 ( 로그인, 회원가입, CRUD게시판 )

## KOA_ver2.zip
 - 패치 노트  
>1. viewResolver추가  
>2. 댓글 기능 추가  
>3. 좋아요 기능 추가(Ajax로 구현)  
>4. 댓글 갯수, 좋아요 갯수 bordList에서 보이게 수정  


## KOA_ver3.zip
 - 패치 노트
> 1. viewResolver 한개 더 사용을 위해 servlet-context.xml(=presentation-layer2.xml) 한 개 더 만듦   
>    presentation-layer.xml => board에 관련된 요청만 처리(*.do)  
>    presentation-layer2.xml => user에 관련된 요청만 처리(*.userdo)  
>    따라서 index, header , footer를 제외한 모든 jsp는 WEB-INF 밑에 각각 폴더로 정리해 놓음 
> 2. 회원가입 폼에서 hibernate-validator를 이용해여 유효성 검사하도록 수정 
> 3. getboardList.jsp => 사진 형식으로 바꿈  
> 4. css 적용 (index, 로그인폼, 회원가입 폼, 글리스트)
     
