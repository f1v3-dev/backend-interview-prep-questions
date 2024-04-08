# ☕ Java


### Java란 무엇인가요?
<details>
<summary>🔎 Answer</summary>
<div markdown="1">

- 객체 지향 프로그래밍 언어
- JVM 위에서 동작하여 운영체제에 독립적이다.
- Garbage Collection(가비지 컬렉션)을 통해 불필요한 메모리를 알아서 정리한다.



</div>
</details>

---

### 객체 지향 프로그래밍(OOP)의 특징은?



<details>
<summary>🔎 Answer</summary>
<div markdown="1">

객체 지향 프로그래밍이란, 프로그래밍에서 `객체`를 사용하는 언어를 말합니다. 여기서의 `객체`는 고유한 속성과 동작을 갖는 데이터로 정의될 수 있습니다.

**객체 지향 기법**
- 캡슐화 : 데이터 보호
    - 정보 은닉
    - 결합도가 낮아지고 재사용이 높아짐
- 상속 : 코드 재사용
    - 상위 클래스의 특징과 기능을 물려 받음
    - 중복 코드를 줄일 수 있음.
- 다형성 : 객체 변경 용이
    - Overloading, Overriding
- 추상화 : 핵심 부분만 표현


**객체 지향 설계 원칙(SOLID)**

- SRP
- OCP
- LSP
- ISP
- DIP

</details>

---

### Garbage Collection이 뭔가요?

<details>
<summary>🔎 Answer</summary>
<div markdown="1">

- 프로그램에서 더 이상 참조되지 않는 메모리를 식별하고 해제하는 프로세스를 의미합니다.

- Java에서의 객체는 `new`를 통해 Heap Memory에 동적으로 할당이 되는데, 해당 객체에 대한 모든 참조가 사라지면 가비지 컬렉션의 대상이 됩니다.

- 메모리 누수 (Memory leaks)를 방지할 수 있어 메모리 관리가 자동화되어 개발자가 명시적으로 메모리를 할당하고 해제할 필요가 없습니다.

> [Garbage Collection - 망나니개발자](https://mangkyu.tistory.com/118)

</div>
</details>

---


### Java 실행 과정에 대해 설명해주세요.

<details>
<summary>🔎 Answer</summary>
<div markdown="1">

1. 소스 코드 (`*.java`)가 자바 컴파일러(javac)에 의해 컴파일 됩니다.

2. 컴파일 되는 과정에서 소스 코드는 JVM(Java Virtual Machine)이 이해할 수 있는 바이트 코드(byte code) 형태로 번역이 됩니다.

3. 만약, 컴파일이 정상적으로 완료되었다면 `*.class`와 같은 확장자를 가진 바이트 코드 파일이 생성됩니다.

4. JVM은 컴파일된 바이트 코드 파일을 클래스 로더를 사용하여 파일을 JVM 내 Runtime Data Aread로 로드합니다. 이 때 필요한 클래스 파일들을 JVM 내로 로드하고 클래스 간의 의존성을 해결합니다.

5. 로딩된 클래스 파일을 Execution Engine을 통해 해석 및 실행합니다.


<br/>

> ***요약하자면,***
> 1. 소스 코드(`*.java`)가 Java Compile에 의해 클래스 파일(`*.class`)로 변환
> 2. 클래스 파일이 Class Loader로 인해 JVM에 로딩
> 3. JVM 내의 Execution Engine(인터프리터와 JIT 컴파일러)에 의해 변환된 코드가 실행


 ![Java 실행 과정](./img/compile_sequence.png)

> - [Compilation and Excution of a Java Program - geeksforgeeks](https://www.geeksforgeeks.org/compilation-execution-java-program/)
> - [자바의 동작 과정 - KoB](https://kingofbackend.tistory.com/123)
</div>
</details>

---