# 운영체제

<details>
    <summary><strong> Q) 커널(kernel)에 대해 설명해주세요</strong></summary></br>

응용 프로그램과 하드웨어 사이에서 인터페이스를 제공하여 응용프로그램이 하드웨어 자원을 사용 할 수 있도록 하는 것. 예를 들어 입출력이나 응용 프로그램의 시스템 콜을 하드웨어가 처리할 수 있도록 하는것 등  

</details></br>

<details>
    <summary><strong> Context Switching에 대해 설명해주세요 </strong></summary></br>

CPU가 어떤 프로세스를 실행시키고 있는 도중 인터럽트의 요청에 의해 다음 우선 순위의 프로세스가 실행되어야 할때, 프로세스의 상태, PC값, 레지스터 값 등을 PCB에 저장 후 다음 프로세스를 실행시키도록 교체하는 작업을 말합니다.  

</details></br>

<details>
    <summary><strong> 인터럽트(Interrupt)에 대해 설명해주세요 </strong></summary></br>

CPU가 프로그램을 실행하고 있을때 예외 상황이 발생하여 처리가 필요한 경우 CPU에게 알리고 예외 상황을 처리할 수 있도록 하는 것  

</details></br>

<details>
    <summary><strong> 시스템 콜(System Call) 대해 설명해주세요 </strong></summary></br>

OS의 커널이 제공하는 서비스에 대해 응용 프로그램이 사용하게 해달라고 요청하는 것  

</details></br>

<details>
    <summary><strong> 프로세스와 스레드에 대해 설명해주세요 </strong></summary></br>

프로세스는 메모리에 적재되어 CPU에의해 실행되고 있는 프로그램입니다. 독립된 메모리 공간 / 인터럽트 발생시 컨텍스트 스위칭  

스레드는 프로세스안에서의 실행 흐름입니다. 스택을 제외하고 공유되는 메모리 / but critical section 문제

</details></br>

<details>
    <summary><strong> Race Condition이 뭔가요? </strong></summary></br>

공유 자원에 대해 여러 프로세스가 동시에 접근할때 결과값에 영향을 줄 수 있는 상태를 말한다.  

</details></br>

<details>
    <summary><strong> Critical Section의 문제를 어떻게 해결할 수 있을까요? (미완성) </strong></summary></br>

스핀락, 뮤텍스, 세마포어, 모니터  

스핀락은   

뮤텍스는 임계영역에 들어갈때 락을 걸어 다른 프로세스가 접근하지 못하도록 하고, 나올때 언락을 하여 다른 프로세스의 접근을 허용하는 방식입니다.  

세마포어는 크게 카운팅 세마포어와 바이너리 세마포어가 있는데 카운팅 세마포어의 경우 설정한 카운트 만큼 쓰레드를 허용하고 그 이상이 접근할 시 락을 거는 방식이고, 바이너리 세마포어는 카운트가 1로, 뮤텍스의 락 & 언락 방식과 비슷하게 사용되는 방식이다.  

모니터란 하나의 프로그램으로 각각의 프로세스가 자원을 사용하는것을 제어하는 역할을 해준다. 모니터의 경계면에서 뮤텍스와 같은 락 & 언락 방식을 사용한 상호배제가 일어난다.  

</details></br>

<details>
    <summary><strong> DeadLock에 대해 설명해주세요 </strong></summary></br>

두개 이상의 작업이 서로 상대의 작업이 끝나기만을 기다리다 아무것도 하지 못하는 상태  

발생조건의 4가지 : 상호 배제 / 비선점 / 점유 대기 / 순환 대기  

DeadLock 예방 : 발생조건의 4가지중 하나를 해결해준다. 오버헤드가 굉장히 큼  

DeadLock 회피 : 자원할당 그래프 알고리즘 / 은행원 알고리즘  

식사하는 철학자 문제  

</details></br>
  
<details>
    <summary><strong> CPU Scheduling에 대해 설명해주세요 </strong></summary></br>


CPU 스케줄링이란 우선순위가 높은 작업을 먼저 처리하는 등 CPU를 효율적으로 처리하기 위해 프로세스를 배정하는것을 말한다.  

CPU 스케줄링은 보통 입출력이 발생했을 때나 더 높은 우선순위의 프로세스가 나타났을때 등 실행이 된다.  

선점과 비선점으로 나뉨 비선점형 스케줄링에는 FCFS, SJF 등이 있고 선점형 스케줄링에는 RR, MQ, MFQ등이 있습니다.  

</details></br>  

<details>
    <summary><strong> 가상메모리에 대해 설명해주세요 </strong></summary></br>

실행중인 프로세스가 가상의 공간을 참조하여 마치 커다란 물리 메모리를 갖고 있는 것처럼 사용할 수 있도록 하는 것, 즉 주기억장치의 메모리가 부족하기때문에, 보조기억장치의 메모리를 마치 주기억 장치처럼 사용하는 것을 말한다.  

</details></br>

<details>
    <summary><strong> 페이징에 대해 설명해주세요 </strong></summary></br>

페이징이란 가상 메모리를 같은 크기의 블록으로 나눈 것을 페이지, 물리 메모리를 페이지와 같은 크기로 나눈 것을 프레임이라고 할때, 사용하지 않는 프레임을 페이지에 옮기고 필요한 메모리를 페이지 단위로 프레임에 옮기는 기법이다.  

페이지 매핑 테이블을 이용해 올바른 위치를 찾아 넣는다. 이를 통해 연속적이지 않은 메모리를 연속적인것처럼 사용할 수 있게되고, 외부 단편화를 해결할 수 있다.  

내부 단편화 또한 페이지의 크기를 줄임으로써 거의 해결할 수 있지만 이렇게 되면 페이지 매핑 테이블의 크기가 너무 커지게 되고, 페이지 폴트또한 많이 일어나게 된다는 단점이 생긴다. 

</details></br> 

<details>
    <summary><strong> 세그멘테이션에 대해 설명해주세요 </strong></summary></br>

페이징에서 같은 크기로 메모리를 나눈것과 달리 세그멘테이션은 필요한 만큼씩 메모리를 나누는 방식이다. 이를 통해 내부단편화를 해결할 수 있지만 크기가 다른 메모리의 할당과 해제가 반복되며 외부단편화가 발생할 수 있다는 단점이 있다.  

</details></br>

<details>
    <summary><strong> 페이지 교체 알고리즘에 대해 설명해주세요 </strong></summary></br>

페이지 교체 알고리즘에는 메모리에 올라온지 가장 오래된 페이지를 교체하는 FIFO방식과, 앞으로 가장 오랫동안 사용되지 않을 페이지를 교체하는 방식인 최적 페이지 교체 방식, 가장 오랫동안 사용되지 않은 페이지를 교체하는 LRU 방식등이 있습니다. 또한 페이지 참조 횟수에 따라 페이지를 교체하는 알고리즘인 LFU와 MFU도 있습니다.  

</br>
<details>
    <summary><strong> LRU에 대해 설명해주세요 (미완성) </strong></summary></br>

</details></br>

<details>
    <summary><strong> FIFO에 대해 설명해주세요 (미완성) </strong></summary></br>

</details></br>

<details>
    <summary><strong> LFU에 대해 설명해주세요 (미완성) </strong></summary></br>

</details></br>

<details>
    <summary><strong> MFU에 대해 설명해주세요 (미완성) </strong></summary></br>

</details></br>

</details></br>