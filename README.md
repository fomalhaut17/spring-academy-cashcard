# Building a REST API with Spring Boot

[English](README.md) | [한국어](README.ko.md)

This repository documents the learning process of building a REST API by following the course from Spring Academy.

---

## Work in Progress

> A record of what is currently being learned and developed.

### (Planned Version: v0.1.0) Completion of Spring Academy Course Content

* **Key Implementation Features**
    * Using Java `record` for data objects
    * Implementing a Repository interface using Spring Data JPA
    * Creating a REST controller using `@RestController`
    * Implementing a single resource retrieval API using `@GetMapping`
    * Implementing a new resource creation API using `@PostMapping`
    * Writing JSON serialization/deserialization tests using `@JsonTest`
* **Concepts and Learning Points**
    * [API Contract-First Development](https://spring.academy/courses/building-a-rest-api-with-spring-boot/lessons/data-contracts)
      * The practice of defining the API's request/response JSON structure first and developing while verifying it with `@JsonTest`.
    * [TDD (Test-Driven Development) Cycle](https://spring.academy/courses/building-a-rest-api-with-spring-boot/lessons/test-first)
      * The cycle of: failing test (red) -> minimal code to pass the test (green) -> code refactoring.
    * Immutability of Java Records
      * Data objects created using `record` are immutable, which enhances data consistency and stability.
    * Why the [CashCardController](src/main/java/example/cashcard/CashCardController.java) class is not `public`
      * Component scanning uses reflection, so it can be registered as a bean even if it's not `public`.
      * If used only within the same package, it can have the effect of encapsulating the code more internally.
    * Why the [CashCardController.findById](src/main/java/example/cashcard/CashCardController.java#L21-L27) method is `private`
      * Spring uses reflection to find methods with request mapping annotations like `@GetMapping` and `@PostMapping`.
      * It clearly expresses the intent that "this method should only be called by Spring's Dispatcher Servlet".
* **References**
    * [Building a REST API with Spring Boot](https://spring.academy/courses/building-a-rest-api-with-spring-boot)
    * [Jayway JsonPath](https://github.com/json-path/JsonPath)
    * [DirtiesContext Annotation](https://docs.spring.io/spring-framework/reference/testing/annotations/integration-spring/annotation-dirtiescontext.html#page-title)

---

## Development History

> Records of completed work and learning points at that time.
