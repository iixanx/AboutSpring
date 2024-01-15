# BEAN

스프링 컨테이너에 의해 생성 및 관리되는 객체

스프링에서 Bean 등록 객체 -> 일반적으로 POJO 형태의 클래스

스프링부트에서 Bean 등록을 위해서는

- @Component 또는 @Bean 등의 어노테이션 사용 
- 자동 구성 기능을 통해 일부 Bean을 자동 등록, 설정 파일에서 Bean의 속성을 구성 (application.yml / application.properties)

---
## POJO

Plain Old Java Object

특정한 제약 또는 프레임워크에 종속되지 않은 순수 자바 객체