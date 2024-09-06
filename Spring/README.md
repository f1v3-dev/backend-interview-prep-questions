# 🌱 Spring

### IoC와 DI란?
<details>
<summary>🔎 Answer</summary>
<div markdown="1">

**IoC(Inversion of Control)**

제어의 역전이라는 말로 제어권이 사용자(개발자)가 아닌 프레임워크가 가지고 있는 것을 의미합니다.

여기서의 '제어'는 프로그램의 흐름과 객체의 라이프사이클을 뜻하며 단순히 개발자는 프레임워크가 제공하는 설정 방법에 따라 코드를 설정만 합니다.
프레임워크는 이 설정을 보고 객체를 생성하고 코드가 동작하는 순서를 결정하여 실행합니다.

이로서 개발자는 비즈니스 로직에 더 집중을 할 수 있는 장점이 존재합니다.

**DI(Dependency Injection)**

의존성 주입(DI)은 객체 간의 의존성을 외부에서 주입하는 방식을 의미합니다.
객체가 필요로 하는 의존 객체를 직접 생성하지 않고, 외부에서 생성된 객체를 주입받아 사용합니다.

</div>
</details>

### DI 종류와 차이점
<details>
<summary>🔎 Answer</summary>
<div markdown="1">

스프링에서는 스프링 컨테이너에 등록된 빈을 사용하게 되는데 생성자 주입, Setter 주입, 필드 주입 방식이 존재합니다.

- 생성자 주입: 생성자 호출 시점에 1번만 호출되는 것을 보장합니다. 불변, 필수 의존 관계에서 사용합니다.
- Setter 주입: 선택, 변경 가능성이 있는 의존 관계에서 사용되며 선택적으로 스프링 빈을 등록할 수 있습니다.
- 필드 주입: '@Autowired' 어노테이션을 사용하여 자동으로 주입하므로 테스트하기 힘들다는 단점이 존재합니다.

스프링 프레임워크에서는 다음과 같은 이유로 생성자 주입을 권장합니다.
 
1. 필수적으로 사용해야하는 의존성 없이는 인스턴스를 만들지 못하도록 강제할 수 있음.
2. NULL 을 주입하지 않는 한 NP가 발생하지 않음.
3. final 을 사용하여 불변성을 보장할 수 있다.
4. 순환 참조가 발생할 경우 컴파일 단계에서 파악할 수 있다.

</div>
</details>


### AOP란? 
<details>
<summary>🔎 Answer</summary>
<div markdown="1">

관점 지향 프로그래밍(Aspect Oriented Programming)으로 관심사의 분리를 위해 사용되는 기술입니다.
AOP의 핵심은 핵심 비즈니스 로직과 관련이 없는 부가적인 기능(트랜잭션, 로깅 등)을 '모듈화'하여 코드의 중복을 줄이고 유지보수성을 향상시키는데 주로 활용됩니다.

</div>
</details>
