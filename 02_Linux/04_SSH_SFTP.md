## FTP

> File Transfer Protocol

파일을 전송하는 통신 규약

- 21 포트 : 명령어 전달
- 20(혹은 랜덤)포트 : 데이터 전달
  - Active mode : 클라이언트가 서버에게 포트를 알려줘서 데이터 전달
  - Passive mode : 서버가 클라이언트에게 포트를 알려줘서 데이터 전달



## FTPS

TLS/SSL을 거친다. 즉, 공개키 암호화 방식을 이용하여 통신라인을 거친다.



## SSH

> Secure SHell

- 공개키 암호 방식을 사용하여 원격지 시스템에 접근하여 암호화된 메세지를 전송할 수 있는 시스템

- 원격으로 쉘을 제어할 수 있는 방법

- 웹호스팅을 하거나 리눅스 서버에 접속하기 위해 사용하는 원격 접속 툴

  

### 동작방식



![image-20200821155728694](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20200821155728694.png)

서버에 접속할때 비밀번호 대신 key를 제출하는 방식. 



### PuTTY

- 리눅스나 유닉스 계열의 서버에 원격으로 접속할 수 있는 클라이언트 프로그램



## SFTP 

> Secure File transfer protocol

SSH 파일 전송 프로토콜



SFTP를 사용하기 위해서는 SFTP를 지원하는 서버와 클라이언트가 있어야 한다.

- 클라이언트

  - 알드라이브

  - FileZilla

    





### 쉘(shell)

운영체제 커널과 사용자 사이를 이어주는 역할

사용자의 명령을 해석하고, 커널에 명령을 요청해주는 역할

