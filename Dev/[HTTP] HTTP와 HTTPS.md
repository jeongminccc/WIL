# HTTP

인터넷 상에서 서버/클라이언트 모델로 __텍스트형태로 데이터를 주고받기 위한 프로토콜__ 이다. (80번 포트를 사용)  

HTTP는 어플리케이션 레이어의 프로토콜로 TCP/IP 위에서 작동한다. Stateless와 Connectionless의 특성을 갖고 있으며 Method, Path, Version, Headers, Body등으로 구성된다.  

<img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbkdJ4Q%2FbtqK6AXLEtC%2FjBZzMuJBWzdLYmqILo5Ri1%2Fimg.png"><br/>

__하지만__, HTTP는 암호화가 되지 않은 평문 데이터를 전송하는 프로토콜이였기 때문에, HTTP로 비밀번호나 주민등록번호등을 주고 받으면 제 3자가 정보를 조회할 수 있었다. 이러한 문제를 해결하기 위해 __HTTPS__ 가 등장하게 되었다.  

# HTTPS

HTTP + "over Secure Socket Layer", "over TLS", "over SSL", "Secure" 등으로 불린다. 즉, __HTTP에 데이터 암호화가 추가된 프로토콜__ 이다. HTTPS는 HTTP와 다르게 433번 port를 사용하며, 네트워크 상에서 중간에 제3자가 정보를 볼 수 없도록 __공개키 암호화__ 를 지원하고 있다.  

__[공개키 / 개인키]__ 

- 공개키 암호화 : 공개키로 암호화를 하면 개인키로만 복호화할 수 있기 때문에, 개인키를 가지고 있는 사람만 볼 수 있다. __정보의 안전성__  
- 개인키 암호화 : 개인키로 암호화를 하면 내가 보낸 데이터라는 것을 입증할 수 있으므로 __신뢰성__ 을 보장할 수 있다.  

## HTTPS의 동작 과정

HTTP는 __SSL과 같은 프로토콜을 사용하여 공개키/개인키 기반으로 데이터를 암호화__ 한다.  

서버는 클라이언트가 요청을 보낼 때 암호화를 하기 위한 공개키를 생성해야 하는데, 일반적으로는 인증된 기관에 공개키를 전송하여 인증서를 발급받고 있는데 과정은 아래와 같다.  

```
1. A기업은 HTTP 기반의 어플리케이션에 HTTPS를 적용하기 위해 공개키/개인키를 발급
2. CA(Certificate Authority) 기업에게 돈을 지불하고, 공개키를 저장하는 인증서의 발급을 요청
3. CA 기업은 'CA의 기업의 이름', '서버의 공개키', '서버의 정보' 등을 기반으로 인증서를 생성하고 CA 기업의 개인키로 암호화 하여 A기업에게 이를 제공
4. A기업은 클라이언트에게 암호화된 인증서를 제공
5. 브라우저는 CA기업의 공개키를 미리 다운받아 갖고 있어, 암호화된 인증서를 복호화함
6. 암호화된 인증서를 복호화하여 얻은 A기업의 공개키로 데이터를 암호화하여 요청을 전송
```

<center><img src="https://t1.daumcdn.net/cfile/tistory/99F6BB335B78E2F610"><br/></center>
1. 클라이언트는 HTTPS를 사용하는 서버에 통신을 요청한다. (클라이언트와 서버는 지원 가능한 암호화 알고리즘을 주고받고, 무엇을 사용할지 결정)  
<center><img src="https://t1.daumcdn.net/cfile/tistory/99D6E5355B78E30D1F"><br/></center>
2. 서버는 HTTPS적용을 위해 서버 인증서(자신의 공개키를 CA의 개인키로 암호화시킨 것) 를 클라이언트에게 보낸다.  
<center><img src="https://t1.daumcdn.net/cfile/tistory/99A9F53E5B78E32618"><br/></center>>
3. 신뢰할수 있을만한 CA이기에 공개키가 알려져있고, 클라이언트는 이 공개키를 사용해 서버의 인증서를 복호화하여 서버가 보낸 공개키를 얻는다.
<center><img src="https://t1.daumcdn.net/cfile/tistory/99C8F8385B78E33F0F"><br/></center>
4. 클라이언트는 랜덤한 대칭키를 만들어 서버가 보낸 공개키로 암호화 하여 서버에게 전송한다.  
<center><img src="https://t1.daumcdn.net/cfile/tistory/99C27F3D5B78E3592D"><br/></center>
<center><img src="https://t1.daumcdn.net/cfile/tistory/99BF81375B78E3760F"><br/></center>
5. 서버는 자신의 개인키로 복호화 한 뒤 대칭키를 얻고, 이 대칭키를 이용해 클라이언트와 데이터를 주고 받는다.  

### 출처
- https://mangkyu.tistory.com/98
- https://run-it.tistory.com/28