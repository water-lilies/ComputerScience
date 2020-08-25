## WAS

> web application server

- 웹 애플리케이션과 서버 환경을 만들어 동작시키는 기능을 제공하는 소프트웨어 프레임워크

- 인터넷상에서 HTTP를 통해 사용자 컴퓨터나 장치에 애플리케이션을 수행하는 미들웨어(소프트웨어 엔진)

  

- 동적 서버 콘텐츠를 수행하는 것으로, 일반적인 웹 서버와 구별된다. 

- 주로 DB서버와 같이 수행

-  JSP Servlet 구동 환경 제공 -> 컨테이너, 웹컨테이너, 서블릭컨테이너라고도 불린다.

  *JSP, Servlet을 실행시킬 수 있는 소프트웨어 = 컨테이너

  - JSP(Java Server Page) : java기반의 server side 스크립트언어 => HTML코드 안에 java코드
  - Servlet : 웹 기반의 요청에 대한 동적인 처리가 가능한 server side에서 돌아가는 java Program

  

### 기능 

- 프로그램 실행 환경과 데이터베이스 접속 기능 제공
- 여러개의 트랜젝션 관리
- 업무를 처리하는 비지니스 로직 수행



### 동작 프로세스

1. 웹서버로부터 요청이 오면 컨테이너가 받아서 처리

2. 컨테이너는 web.xml을 참조하여 해당 서블릿에 대한 쓰레드 생성하고 httpServletRequest와 httpServletResponse 객체를 생성하여 전달한다.

3. 컨테이너는 서블릿을 호출한다.

4. 호출된 서블릿의 작업을 담당하게 된 쓰레드(2번에서 만든 쓰레드)는 doPost()또는 doGet()을 호출한다.

5. 호출된 doPost(), doGet() 메소드는 생성된 동적 페이지를 Response객체에 담아 컨테이너에 전달한다.

6. 컨테이너는 전달받은 Response객체를 HTTPResponse형태로 바꿔 웹서버에 전달하고 생성되었던 쓰레드를 종료하고 httpServletRequest, httpServletResponse 객체를 소멸시킨다.



출처: https://jeong-pro.tistory.com/84 [기본기를 쌓는 정아마추어 코딩블로그]



## 톰캣(Tomcat)

- WAS중 하나. 동적인 웹을 만들기 위한 웹 컨테이너

- 8080포트로 처리
- DB연결, 데이터 조작, 다른 응용프로그램과 상호 작용 가능