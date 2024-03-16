# JVM
JVM이란 Java Virtual Machine의 약자로, 자바 가상 머신이라고 불린다. <br />
Java의 바이트 코드를 해석하고 실행하는 역할을 한다. <br />
어떠한 OS에서든 실행할 수 있다는 것이 장점이다.

## JVM 실행 순서
1. .java 파일을 컴파일러를 통해 .class 파일로 변환한다.
2. .class 파일을 JVM의 ClassLoader에게 보낸다.
3. 클래스로더에서 JVM 런타임 영역으로 로딩해 메모리에 올린다.

![image](https://github.com/woneee99/TIL/assets/87613419/83e398d9-917f-4cf4-a074-141b0224bfc8)
## JVM 런타임 데이터 영역
1. Static Area(Method Area) : 클래스별로 전역, 정적 변수, 메소드 정보들 저장
2. Heap Area : 런타임 중 생성되는 객체들이 동적으로 할당되는 곳
3. Stack Area : 호출된 메소드의 매개변수, 지역변수, 리턴정보들이 저장
4. PC Register : 현재 수행중인 JVM 명령어가 들어가있음
5. Native Method Stack : Java 외의 언어인 C나 C++ 같은 것들을 수행하기 위한 영역

## Java 메모리 영역
1. **Heap** 영역
    - new 키워드로 객체를 생성할 때 저장된다.
2. **Stack** 영역
    - 호출된 메소드의 매개변수, 지역변수, 리턴정보들이 저장된다.
    - Heap 영역에 생성된 데이터의 참조값이 할당된다.
3. **Method**(Static) 영역
    - 클래스 변수나 static으로 선언된 것들이 해당 영역에 저장된다.
