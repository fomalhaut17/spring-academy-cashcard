# Spring Boot로 REST API 만들기

[English](README.md) | [한국어](README.ko.md)

Spring Academy의 강좌를 참고하여 REST API를 구축하는 학습 과정을 기록합니다. 

---

## 현재 진행 중인 작업

> 현재 학습하고 개발 중인 내용에 대해 자유롭게 기록하는 공간. 작업이 완료되고 태그가 생성되면 '개발 이력'으로 이동함.

### (예정 버전: v0.1.0) Spring Academy 강좌 내용 완료

* **주요 구현 기능**
    * 데이터 객체를 위한 java record 사용
    * Spring Data JPA를 이용한 Repository 인터페이스 구현
    * @RestController를 이용한 REST 컨트롤러 생성
    * @GetMapping을 이용한 단일 리소스 조회 API 구현
    * @PostMapping을 이용한 신규 리소스 생성 API 구현
    * @JsonTest를 이용한 JSON 직렬화/역직렬화 테스트 작성
* **개념 및 학습 포인트**
    * [API 계약 기반 개발](https://spring.academy/courses/building-a-rest-api-with-spring-boot/lessons/data-contracts)
      * API의 요청/응답 JSON 구조를 먼저 정의하고, @JsonTest를 통해 이를 검증하며 개발을 진행하는 방식
    * [TDD (Test-Driven Development) 사이클](https://spring.academy/courses/building-a-rest-api-with-spring-boot/lessons/test-first)
      * 실패하는 테스트(red) -> 테스트를 통과하는 최소한의 코드 작성(green) -> 코드 리팩토링(refactor) 과정
    * Java Record의 불변성(Immutability)
      * record를 사용하여 생성된 데이터 객체는 변경이 불가능하므로, 데이터의 일관성과 안정성을 높일 수 있음
    * [CashCardController](src/main/java/example/cashcard/CashCardController.java) 클래스가 public이 아닌 이유
      * 컴포넌트 스캔은 리플렉션을 사용하므로 public이 아니어도 빈으로 등록됨
      * 같은 패키지 내에서만 사용된다면 코드를 좀 더 내부적으로 캡슐화하는 효과를 줄 수 있음
    * [CashCardController.findById](src/main/java/example/cashcard/CashCardController.java#L21-L27) 메소드가 private인 이유
      * @GetMapping, @PostMapping 같은 요청 매핑 어노테이션이 붙은 메서드를 찾을 때 리플렉션을 사용함
      * "오직 스프링의 디스패처 서블릿(Dispatcher Servlet)에 의해서만 호출되어야 한다"는 의도를 명확히 드러냄
* **참고 자료**
    * [Building a REST API with Spring Boot](https://spring.academy/courses/building-a-rest-api-with-spring-boot)

---

## 개발 이력

> 완료된 작업 및 해당 시점의 학습 기록
