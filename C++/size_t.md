# size_t?

size_t는 __주어진 환경에서 가장 큰 사이즈를 담을 수 있는 unsigned 데이터 타입__ 으로 정의된다.

즉, 32비트 머신에서는 32비트 사이즈의 unsigned 정수형(unsigned int),  
64비트 머신에서는 64비트 사이즈의 unsigned 정수형(unsigned long long)을 typedef로 정의해놓은 것이다.  `typedef unsigned int size_t;`

```
환경에 따라 size_t는 unsigned char, unsigned short, unsigned int, unsigned long, unsigned long long 모두 될 수 있다.
```

보통 `size()` 함수를 사용할때 등, 메모리나 문자열 등의 길이를 구할때에는 size_t 형으로 길이가 반환된다.

## size_t와 unsigned int의 차이

__size_t__ 는 64비트에서는 64비트 사이즈, 32비트에서는 32비트 사이즈를 갖는다.    

마찬가지로 int도 운영체제에 따라 크기가 가변적이다. 하지만 __unsigned int, int__ 는 64 OS라고 해서 무조건 64비트 정수는 아니며, 32비트 정수일 수도 있다.(Window) 이것이 size_t 와 unsigned int의 차이이다.    

# int 와 long의 차이

우리가 보통 알고있는 int 자료형은 32비트의 정보를 기록할 수 있는 자료형으로, 가장 많이 그리고 가장 보편적으로 쓰이는 자료형이다.  

하지만 int가 항상 32비트의 정보를 기록하는 자료형은 아닌데, 이는 int가 __운영체제 환경__ 에 따라 크기가 가변적이기 때문이다.  

즉, 16비트 운영체제에서는 16비트, 32비트 운영체제 에서는 32비트로 환경에 따라 다르게 사용되는 자료형인것이다.  

- 16비트 운영체제에서는 short이 16비트, int가 16비트, long이 32비트로 쓰인다.  
- 32비트 운영체제에서는 short이 16비트, int가 32비트, long이 32비트로 쓰인다.  

그 다음 64비트 운영체제가 쓰이게 될때, int는 64비트로 사용되는것이 맞는데, 그렇게되면 long보다 크기가 커지게 되므로 int를 64비트로 사용하는 것이 아닌 long을 64비트로 사용하게 되었다고 한다.(UNIX)  

(__window에서는 64비트 환경에서도 int, long 둘다 32비트로 사용함__)

-> 그래서 Window, Linux or Unix간의 이식과정에서 에러가 발생하는데, 이를 해결하기 위해 `<stdint.h>`에 정의된 타입들을 ex) int64_t, int32_t 쓰는것을 권장한다.