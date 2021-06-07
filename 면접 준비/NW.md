# Network

<details>
    <summary><strong> Q) Rest API가 뭔가요? </strong></summary></br>

자원을 이름으로 구분하여 해당 자원의 상태, 정보를 주고 받는 모든 것을 의미    

</details></br>

<details>
    <summary><strong> Q) 브라우저에서 naver.com 쳤을때 과정을 설명해주세요 </strong></summary></br>

웹 서비스는 HTTP를 이용한 시스템이다. 즉 브라우저의 주소창에 URL을 적고 서버로부터 데이터를 얻어오기 위해서 가장 중요한 역할을 하는 프로토콜이 HTTP인것이다.  

1. 브라우저의 주소창에 URL을 입력한다.
2. 입력한 URL에서 Domain부분을 DNS서버에 넘겨주어 IP주소를 얻는다.
3. 얻은 IP주소를 이용해 서버에 데이터를 요청하는데, 이 과정에서 HTTP와 TCP/IP가 사용된다.
4. 먼저 HTTP 요청메세지를 만들고
5. TCP에서 3-way handshake 방식을 이용해 사전에 세션을 수립후 요청메세지를 보낸다.
6. 서버에서 HTTP 요청메세지를 받고, HTTP 응답메세지를 만들어 클라이언트에게 전송한다.
7. 데이터의 전송이 끝나면 TCP에서 4-way handshake 방식을 이용해 연결을 닫고, 클라이언트의 브라우저에 서버가 보내온 데이터를 출력한다.

</details></br>