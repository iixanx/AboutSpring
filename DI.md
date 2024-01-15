# DI

Dependency Injection 의존성 주입

IoC 실현을 위한 핵심 매커니즘

다른 객체와 의존성을 맺기 위해 의존성을 외부에서 주입받는 것

## DI가 필요한 이유

- 객체 간 결합도 하락, 인터페이스에 의존하도록 설계 가능
- 해당 객체를 다른 곳에서도 쉽게 활용 가능
- 테스트 시 의존 객체를 직접 생성하는 대신 가짜 객체를 주입하여 테스트 환경 제어 가능

## new Keyword VS DI

```Java
// 기존의 new를 이용한 객체 생성

/* Student.java */
public class Student {
    // ...
}

/* User.java */
public class User {
    private Student student;
    
    public User() {
        student = new Gun();
    }
}
```
해당 클래스에 직접적으로 의존 -> 클래스 간 강한 결합 유발, 코드 수정의 어려움

```Java
// DI 활용

/* Student.java */
@Component
public class Student {
    // ...
}

/* User.java */
public class User {
    @Autowired
    private Student student
}
```
어노테이션을 이용해 주입받을 의존성을 자동으로 관리 가능

-> 객체 간의 결합도를 낮추는 설계를 위한 개념

SRP와 DIP를 지켜 유지보수가 유연한 시스템을 개발할 수 있도록 함

---

## DI의 방식 3가지

### 생성자 주입 Constructor Injection

의존 객체를 해당 클래스의 **생성자 매개변수**로 전달하여 의존성을 주입

스프링에서는 생성자에 `@Autowired`라는 어노테이션을 통해 의존성을 자동 주입하도록 지원

### 세터 주입 Setter Injection

Setter 메소드를 이용 : 해당 클래스에 setter 메소드를 정의, 스프링 컨테이너가 해당 메소드를 호출 -> 의존성을 주입하도록 함

객체를 생성한 이후에도 의존성 변경 가능 -> 동적으로 의존성을 주입 / 변경해야 하는 상황에 유용

### 필드 주입 Field Injection

해당 클래스의 멤버 변수로 의존성을 직접 주입하는 방식

간편하게 DI를 처리할 수 있으나 테스팅 시 모의 객체를 주입하기 어렵고 객체 생성 시점에 의존성을 명시적 설정하지 않아 객체 불변성 침해 우려

-> 꼭 필요한 경우에만 사용 권장