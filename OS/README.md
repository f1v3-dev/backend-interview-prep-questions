# ⚙️ OS

### 운영체제란?
<details>
<summary>🔎 Answer</summary>
<div markdown="1">

시스템의 자원과 동작을 관리하는 소프트웨어로서 프로세스, 저장장치, 네트워킹, 사용자, 하드웨어를 관리합니다.

</div>
</details>

---

### 프로세스의 메모리 구조에 대해 설명해보세요. 
<details>
<summary>🔎 Answer</summary>
<div markdown="1">

메모리는 4가지 영역으로 코드, 데이터, 힙, 스택 영역이 있습니다.

코드 영역은 실행할 프로그램의 코드가 들어가는 부분이고
데이터 영역은 전역 변수와 정적 변수가 할당되는 영역입니다.
힙 영역은 사용자(프로그래머)가 할당/해제 하는 메모리 공간으로 동적으로 할당되며,
스택 영역은 함수의 호출 정보, 지역 변수와 매개 변수들이 저장되게 됩니다.

</div>
</details>

---

### 프로세스 vs 스레드
<details>
<summary>🔎 Answer</summary>
<div markdown="1">

> 프로그램: 컴퓨터가 이해할 수 있는 명령어의 집합체로 정적인 상태이다.

프로세스는 프로그램을 실행시킨 상태 즉, 실행중인 프로그램이며
스레드는 프로세스 안에서 실행되는 흐름의 단위이다.

프로세스는 OS 내부에서 메모리 영역을 할당받고 독립된 영역을 가지지만,
스레드는 프로세스 내부에서 메모리의 코드, 데이터, 힙 영역을 공유해서 사용하며 스택 영역만 별도로 할당을 받는다.

</div>
</details>

---

### CPU 스케줄러란?
<details>
<summary>🔎 Answer</summary>
<div markdown="1">

> 선점형: 다른 프로세스를 빼앗아 먼저 처리하도록 함.
> 비선점형: 다른 프로세스를 뺏지 않고 자신의 차례까 올 때까지 대기함.


준비 큐(Ready Queue)에 있는 프로세스에 대해 CPU를 할당하는 방식으로, 
FCFS, SJF, SRT, RR, Priority Scheduling 5가지 방식이 존재합니다.

```markdown

*비선점형 스케줄링*
FCFS(First Come First Served, FIFO)**: 먼저 CPU를 요청하는 프로세스를 먼저 처리
**SJF(Shortest Job First)**: CPU 사용 시간이 작은 것 먼저 처리 -> 대기 시간을 최소화!

*선점형 스케줄링*
SRT(Shortest Remaining Time):** 최단 잔여시간을 우선 처리 -> 선점형 SJF
**RR(Round Robin):** 모든 프로세스가 같은 우선순위를 가지고, time slice 기반으로 스케줄링 (컨텍스트 스위칭이 많이 일어남.)

**Priority Scheduling:** 우선순위가 높은 프로세스에 CPU 할당 
```

</div>
</details>


---

### 가상 메모리란?
<details>
<summary>🔎 Answer</summary>
<div markdown="1">

모든 프로세스에게 메모리를 할당하기엔 메모리의 한계가 있기 때문에 
프로세스에서 사용하는 부분만 메모리에 올리고 나머지는 디스크에 보관하는 기법을 말합니다.

</div>
</details>

---

### 데드락이란? (발생조건)
<details>
<summary>🔎 Answer</summary>
<div markdown="1">

데드락이란, 프로세스가 자원을 얻지 못해 다음 작업을 하지 못하는 상태를 말합니다.

데드락의 발생 조건

```markdown

상호 배제: 자원은 한 번에 한 프로세스만 사용할 수 있어야 한다.
점유 대기: 최소한 하나의 자원을 점유하고 있으면서 다른 프로세스에 할당되어 있는 자원을 추가로 점유하기 위해 대기하는 프로세스가 있어야 한다.
비선점: 다른 프로세스에 할당된 자원은 사용이 끝날 떄까지 강제로 빼앗을 수 없다.
순환 대기: 프로세스 집합에서 P0 -> P1, P1 -> Pn, Pn -> P0 자원을 요구하는 상황

```

</div>
</details>