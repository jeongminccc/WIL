# Java

<details>
    <summary><strong> Q) 객체지향에 대해 설명해주세요 </strong></summary></br>

프로그램의 로직을 객체 단위로 나누어 프로그래밍하는 것이다. 절차 지향 프로그래밍에 비해 처음 설계시 많은 시간과 노력이 든다는 단점이 있지만 모듈화를 이루어 유지보수를 용이하게 할 수 있다는 장점이있습니다.

</details></br>

<details>
    <summary><strong> Q) 클래스와 인스턴스에 대해 설명해주세요 </strong></summary></br>

클래스란 데이터에 대한 정보와 행동을 변수와 메서드로 정의한 것이고, 인스턴스란 클래스에서 정의한 것을 토대로 실제 메모리 상에 할당한 것을 말합니다.  

</details></br>

<details>
    <summary><strong> Q) 추상화란 무엇인가요 </strong></summary></br>

객체의 속성 중 중요한 정보, 핵심적인 기능만을 간추리는 것을 말합니다. 추상화를 통해 코드의 가독성을 높일 수 있고 생산성을 높일 수 있다.  

</details></br>

<details>
    <summary><strong> Q) 캡슐화란 무엇인가요 </strong></summary></br>

정보와 행동의 모음을 클래스에 분류하여 넣는것을 말합니다. 캡슐화를 통해 코드의 재활용을 용이하게 할 수 있다.  

</details></br>

<details>
    <summary><strong> Q) 상속이란 무엇인가요 </strong></summary></br>

부모클래스의 속성과 기능을 그대로 이어받아 사용할 수 있게 하고, 필요시 기능의 일부분을 다시 수정하여 사용할 수 있게 하는것을 상속이라 합니다. 코드의 재활용을 용이하게 할 수 있다.    

</details></br>

<details>
    <summary><strong> Q) 다형성이란 무엇인가요 </strong></summary></br>

하나의 변수명, 함수명 등이 상황에 따라 다른 의미로 해석 될 수 있는것  

- 오버라이딩 : 부모 클래스의 메서드와 같은 이름, 매개변수를 재정의
- 오버로딩 : 함수의 이름은 같지만 매개변수의 타입 혹은 개수가 다른것 (가독성, 메서드 이름 절약)

</details></br>

<details>
    <summary><strong> Q) 객체란 무엇인가요 </strong></summary></br>

객체란 __정보와 행동을 가지고 있는 데이터__ 이다.  

```
Ex) 자동차 -> 정보(차량 번호, 제조사 정보, 차량 크기) + 행위(앞으로 이동, 멈춤)
    Python에서의 문자 'a' -> 정보(생성한 타입) + 행위(method(문자열 함수 join, upper등))
```

</details></br>

<details>
    <summary><strong> Q) 컴포넌트란 무엇인가요 </strong></summary></br>

독립적인 모듈이다. 소프트웨어 시스템에서 독립적인 업무 또는 기능을 수행하는 '모듈'로서 시스템을 유지 보수 하는데 있어 교체 가능한 '부품'의 역할을 한다.  

</details></br>

<details>
    <summary><strong> Q) JVM 메모리 구조에 대해 설명해주세요 </strong></summary></br>

메서드 영역, 힙 영역, 스택 영역, pc 레지스터, 네이티브 메서드 스택

메서드 영역엔 JVM이 .class 파일을 읽고 클래스에 대한 정보를 저장하고, static 멤버와 메소드도 이 영역에 저장이 된다.  

힙 영역은 new 키워드로 생성된 객체와 배열이 저장되는 영역이다.  

스택 영역은 지역 변수, 매개 변수, 리턴 값등이 생성되는 영역이다.  

PC 레지스터는 현재 스레드가 실행되는 부분의 주소와 명령을 저장하는 영역이다.  

네이티브 메서드 영역 자바 외 언어로 작성된 네이티브를 위한 메모리 영역이다.

</details></br>

<details>
    <summary><strong> Q) Garbage Collector 과정을 말해주세요 </strong></summary></br>

GC는 사용하지 않는 객체를 메모리에서 제거하는 작업인데, JVM에서는 각각의 객체의 오래됨을 표현하기 위해 힙 영역을 eden, 서바이버 1, 2, 올드로 구성합니다.  

GC는 마이너 GC와 메이저 GC로 나뉘는데, 마이너 GC는 이든, 서바이버 영역에서 일어나는 GC이고 메이저 GC는 old 영역에서 일어나는 GC 입니다.  

객체가 메모리를 할당 받으면 eden에 생성, 가득 차면 마이너 GC가 발생 참조되고 있지 않은 객체들은 메모리에서 제거되고 살아남은 객체들은 서바이버 영역으로 옮겨진다. 마이너 GC가 발생할 떄 마다 서바이버 1에서 2로, 2에서 1로 객체가 이동하게 되며 이때 또한 참조되지 않는 객체는 메모리에서 제거된다. 마이너 GC가 발생하는 동안 서바이버 영역을 오가며 살아남은 객체들은 최종적으로 Old 영역에 옮겨지며, Old 영역에 있다가 미사용된다고 식별되는 객체들은 메이저 Gc를 통해 메모리에서 제거 된다.

</details></br>

<details>
    <summary><strong> Q) Java언어의 장점과 단점을 말해주세요 </strong></summary></br>

JVM에서 동작하므로 특정 운영체제에 종속적이지 않다. 객체지향 언어로써 상속, 다형성, 캡슐화, 추상화등을 지원한다. GC에 의해 사용하지 않는 메모리를 자동으로 수거한다.  

바이트 코드로 컴파일 후 인터프리터 방식으로 동작하여 실행 속도가 느리다.  

</details></br>

<details>
    <summary><strong> Q) Java8과 11의 차이를 말해주세요 (미완성)</strong></summary></br>

8에서 기억에 남는 부분은 람다 표현식을 통해 함수형 프로그래밍이 가능하게 한것이고  

</details></br>

<details>
    <summary><strong> Q) JDK, JRE, JVM에 대해 설명해주세요 </strong></summary></br>

JDK는 JRE와 개발에 필요한 도구를 포함합니다.  

JRE는 JVM과 자바 프로그램을 실행시킬때 필요한 라이브러리 파일들을 포함합니다.

JVM은 자바 소스코드를 컴파일하여 만든 바이트 코드를 실행할 수있습니다.  

</details></br>

<details>
    <summary><strong> Q) JVM 구조에 대해 설명해주세요 (미완성)</strong></summary></br>

Class loader / Execution engine / GC / runtime data area(JVM 메모리 영역)  

</details></br>