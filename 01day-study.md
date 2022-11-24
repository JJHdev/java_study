# 01day_java_study
# 01day-study (velog에서 github 이동)
w3school
   * 스스로 공부할때에는 w3school 참고하여 공부하면 좋다.

기본적인 작업환경 유지
   * chrome, c,d드라이버 나누기, 알집, PPT 뷰어, 만들기

유튜브에 좋은 (https://fliphtml5.com/hkuy/jhqb/basic)
https://fliphtml5.com/hkuy/jhqb/basic
  * 자바의정석, 이것이자바다 공부 (예습공부는 필수)

(제어문/ 연산자/ 조건문/ 반복문/ 배열/ 6.1(객체지향프로그래밍)/ 40~79번(개정 전)
  * 59~ 100번까지 (개정 후)


HTML 의 정의 (Hyper Text Markup Language)
  * 웹페이지를 만드는 구조 / 웹페이지언어의 가장 기초가 되는 언어
  * <,> 태그라고 한다. , 열다 닫다 /
  * Table, Form(DB에 있는 것을 가져오는것) ★★★

CSS (Cascading Style Sheet)
  * 작업물에 디자인을 입히는 언어 (마우스 클릭시 파란색표시)

javaScript
  * 필수입력, 비번일치, 특수문자등 유효성 체크시 사용되는 언어
  * 부가기능및 편리한 기능 제공

JQuery (javascript Livrary)
  * 이미 만들어진 기능을 사용가능하게 해주는 것

java
  * java가 웹문서에 들어가면 JSP (Html안에 java code가 들어감)
  * servlet (java안에 Html code를 넣음)
  Jsp, seervlet 가 SQL문 사용해서 DB에 가서 자료 조회요청
  SQL에서는 조회 (Select) , 입력(insert), 삭제(delete), 변경/수정(update) 기능이 있으며 이를 통칭적으로 DML이라고 한다. ★★★

MVC (Model view control) 패턴 (개발자들이 웹문서 작성시 여러 패턴을 정형화 해놓은 것)
  * 스프링 프레임 워크 ▶ 작업하는데 편하게 해주는것 (정형화 해놓은것) / 힘든 개발자들을 위해 봄이 오길 바라며 스프링으로 이름을 지음

DB와 DBMS, RDBMS 개념
로그인및 회원가입시 사용되는 기능 설명 (전반적인 흐름)
  * 설계를 한다. (디자인, 정보를 만든다.)
  * Table (표) 데이터 관리시 사용됨 / 표,가로,세로횡구분을 테이블로 표현

Html, Css, Query, Java, Jsp, Servlet, Myquery, Xml, javascript, spring (언어를 공부할 것이다.)
  * 다양한 언어를 공부해야하지만 여러버전도 할줄 알아야 한다.

Java 개발 환경 구축
   * JDK(java Development Kit) = JRE + 개발도구 / 자바 프로그램 개발하고 실행하기 위해
   * JRE(java Runtime Environment) = JVM + 표준 클래스 라이브러리 / 자바 프로그램을 실행 할 경우 설치
    → oracle jdk 다운 → 다른 언어와 연계되어 사용할거라 jdk는 Java SE Development Kit 8u121 다운 
        (기존에 많이 사용) → 설치 하기(JDK설치하기) (바탕화면, 내문서 저장 X) 
        (빙에서 jdk 1.8.121. download) /

    https://www.oracle.com/java/technologies/javase/javase8-archive-downloads.html
    Java Archive Downloads - Java SE 8
    Java SE 8 Archive Downloads (JDK 8u202 and earlier) Go to the Oracle Java Archive The JDK is a development environment for building applications using the Java programming language. The JDK includes tools useful for developing and testing programs written in the Java programming language and running...

www.oracle.com
  * 설치한 파일중 bin에서 javac → 컴파일러 하여 컴퓨터 언어로 번역

13-1. C:\Program Files\Java\jdk1.8.0_121 설치한 주소
자바소스 파일 (컴파일러/javac) → 바이트 코드파일 (자바가상기계/java) → 기계어
* 고급시스템 설정 → 고급 → 환경변수 → 시스템 변수 → 새로 만들기 (변수값에 jdk 설치주소(13.1) 입력/ 변수이름 JAVA_HOME)
* 고급시스템 설정 → 고급 → 환경변수 → 시스템 변수 → path → 편집 → 새로만들기

 →%JAVA_HOME%\bin(맨위로 두기) → 확인
13-2. 설정한 환경이 올바른지는 명령프롬프트에서 java -version에서 확인 가능.

명령프롬프트
* 주소값 상위버전 가기 cd.. / 최상위 버전 cd\ / 원하는 주소가기 cd (주소붙여넣기)
* 절대경로 (전체경로) / 상대경로(하나만 입력)
* 메모장에서 java폴더로 만든 클래스파일은 컴파일 하여 바이트코드로 변경해야함.
  → 파일이 있는 경로로 주소를 변경하고 javac 파일이름.java → class 파일 생성
  → java 파일이름 (실행됨)
