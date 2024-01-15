# Getter & Setter

객체의 데이터를 객체 외부에서 직접 접근할 경우 무결성이 깨질 수 있다.

이를 대비해 OOP에서는 외부에서의 직접 접근을 방지하고, 메소드를 통해 데이터에 접근하도록 한다.

이러한 방식이 Getter와 Setter이다.

InteliJ에서는 `Cmd + Enter` 단축키로 클래스 내에서 빠르게 Getter & Setter 생성이 가능하다.

## Getter

값을 내부에서 외부로 전달하는 역할

`get{Property}`로 선언하는 게 일반적

## Setter

외부에서 전달받은 값으로 내부 값을 재설정

`set{Property}`로 선언하는 게 일반적