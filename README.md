### learning_api
# 스프링 개발환경 세팅
***
### **1-1. IntelliJ Community 버전 설치**

개발환경은 IntelliJ Community 버전에서 진행하였습니다.

IntelliJ Community 다운로드 ( https://www.jetbrains.com/idea/download/?section=windows )


### **1-2. Debeaver 설치 및 DB Connection**

MariaDB를 사용할 것이므로 MariaDB 설치 후,   

디비버 접속 및 커뮤니티 버전 다운로드 ( https://dbeaver.io/ )

### 1-3. Spring MVC 환경설정 & API PING 

IntelliJ Community 버전에서는 톰캣을 제공하지 않으므로, 현재 과정에서는 톰캣을 대신하여 Jetty를 사용하여 설정을 진행하였습니다.

Maven을 이용하였습니다.

- 새로운 Maven Project를 생성
- 제너레이터에서 maven 원형을 선택
- 이름 : mvc-practice
- 위치 : spring_project라는 파일에 spring mvc 프로젝트를 만들어 둠 (위치는 원하는 곳에 저장 가능함)
- JDK 버전의 경우 11 로 진행하며, Azul 11로 진행함. (Azul / correto / openjdk 중 다운로드 받아 진행)
---
**< Dependency 추가 >**
- pom.xml 파일 수정  ( dependency 위에 properties를 정의한다 )
- properties 추가
- dependency 추가
- jetty build 문 추가
- Spring 설정을 위한 web.xml 수정
- web 설정을 위한 작업
**<PingController> 작성**
**< jetty 실행 설정 >**

**< 실행 및 Ping Test >**
Jetty 실행 후 아래와 같은 Started Jetty 라는 메시지를 확인 할 수 있습니다.

![image](https://github.com/user-attachments/assets/209fe5ff-1e60-4bce-89a9-e6ce8cbb6c43)


http://localhost:9080/ping 을 호출하면


![image](https://github.com/user-attachments/assets/755e762e-fb96-4290-826c-3f4f56d75e3c)

### **1-4. datasource & mybatis 연동**


- datasource 연동을 진행합니다.
- datasource xml은 따로 정의합니다.

  1. **Pom.xml 추가**
- DB 설정을 위한 dependency를 추가합니다.


  2. **applicationContext-datasource.xml 을 resources 아래에 생성합니다.**
- 해당문서에는 db 설정 정보와 mybatis 사용을 위한 mapper 경로가 들어있습니다.

  3. **applicationContext-webapp.xml에 위 설정파일을 import 합니다.**
 
  4. **mapper 경로와 test mapper xml 파일을 추가합니다.**
 
  5. **DB 실행을 위한 dao / controller / service 코드를 작성해였습니다.**

<최종 파일 구조>

![image](https://github.com/user-attachments/assets/5111728a-63ce-48a2-8fbc-39115a5ba887)



<설정 후 구동결과>


![image](https://github.com/user-attachments/assets/d4d68680-7d93-4efc-8b03-cb46d37fa757)

![image](https://github.com/user-attachments/assets/d7952f9d-7892-44ba-a83b-4b019a96ab39)



  



  

