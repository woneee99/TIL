# 교착상태(Deadlock)
뮤텍스와 세마포어를 사용해서 상호배제를 달성하더라도 교착상태와 같은 문제가 생길 수 있다. <p />
둘 이상의 프로세스가 자원을 점유한 상태에서 서로 다른 프로세스가 점유하고 있는 자원을 요구하며 무한 대기 하는 상태

<br />

## 발생 조건
아래 4가지 중 하나라도 만족하지 않으면 발생하지 않음 
- 상호 배제: **공유 자원은 하나의 프로세스만** 사용할 수 있음
- 점유 대기: 프로세스가 할당된 자원을 가진 상태에서 다른 프로세스가 **사용중인 자원을 사용하기 위해 대기**하고 있는 상태
- 비선점: 다른 프로세스에 할당된 자원은 사용이 끝날 때까지 **강제로 빼앗을 수 없어야 한다**.
- 순환 대기: 프로세스의 집합에서 P0은 P1이 점유한 자원을 대기하고, P1은 P2가 점유한 자원을 대기하며, Pn은 P0이 점유한 자원을 요구하는 상황으로, 이 점유 대기 관계가 원형으로 이루어지는 현상을 말한다. 

<br />

## 해결 방법
- 예방: 교착상태 발생 조건 중 하나라도 발생하지 않게 하여 예방하는 방법
- 회피: 교착 상태가 발생하기 전에 안전한 상태에서만 자원 요청을 허용하는 방법
- 탐지: 탐지 알고리즘을 사용하여 교착상태가 발생했는지 탐지한다.
- 회복: 교착 상태를 일으킨 프로세스를 종료하거나 할당된 자원을 해제시키는 방법

