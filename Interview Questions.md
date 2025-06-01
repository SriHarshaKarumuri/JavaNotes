# 🚀 Java & Spring Boot Interview Preparation Guide

A comprehensive guide covering essential Java, Spring Boot, Microservices, and related concepts. Perfect for interviews, quick revision, or deep dives into core and advanced topics.

---

## 📚 Table of Contents

- [☕ Java Core Concepts](#-java-core-concepts)
- [🔁 Threads & Concurrency](#-threads--concurrency)
- [📦 Collections & Internals](#-collections--internals)
- [🧠 Java Memory Model](#-java-memory-model)
- [⚠️ Exception Handling](#-exception-handling)
- [🌿 Java 8 Features](#-java-8-features)
- [🗄️ Database Concepts](#-database-concepts)
- [🧩 Interfaces & OOP](#-interfaces--oop)
- [🌱 Spring Boot](#-spring-boot)
- [🏗️ Microservices Architecture](#-microservices-architecture)
- [📦 Build Tools: Maven vs Gradle](#-build-tools-maven-vs-gradle)
- [🧪 Testing & Code Quality](#-testing--code-quality)
- [🛡️ Web Security](#-web-security)
- [📌 Advanced Questions & Notes](#-advanced-questions--notes)

---

## ☕ Java Core Concepts

- Difference between `==` and `.equals()`
- String memory management (`String s = new String("abc")`)
- Static blocks, instance blocks, constructors – order of execution
- Remove unnecessary characters from String:  
  _E.g._ `"Dharmala Sr. /i Hari"` → `"Dharmala Sri Hari"`
- IP address validation using regex or Java Streams
- What is a functional interface, and can it extend another one?
- Overriding static and default methods in interfaces
- `hashCode()` and `equals()` importance in HashMap
- `@Autowired` annotation
- `wait()`, `notify()`, `notifyAll()`

---

## 🔁 Threads & Concurrency

- What is `ConcurrentHashMap` and how it differs from `HashMap`
- Use of `synchronized`, `volatile`
- Thread lifecycle
- Thread-safe singleton pattern

---

## 📦 Collections & Internals

- Internal working of `HashMap`
- Difference between `HashMap`, `Set`, `HashSet`
- `TreeSet` and `null` handling
- Marker interfaces
- Collections vs Streams
- Streams coding example:
  - Count male and female employees
  - Filter employee salary > 50,000

---

## 🧠 Java Memory Model

- Heap vs Stack
- String pool and memory behavior (`String s = "abc"; String s2 = new String("abc")`)
- Garbage Collection overview

---

## ⚠️ Exception Handling

- Difference between checked and unchecked exceptions
- Custom exception implementation
- Behavior of `finally` block
- `throws` vs `throw`

---

## 🌿 Java 8 Features

- Lambda expressions vs Method References
- Functional Interfaces and default/static/private methods
- Streams API
- `Optional` class
- Code examples with lambda, filtering, grouping

---

## 🗄️ Database Concepts

- Joins vs Subqueries
- Views vs Tables
- Clustered vs Non-clustered Index
- Stored procedures

---

## 🧩 Interfaces & OOP

- Abstract class vs Interface
- Overriding vs Overloading
- Marker interfaces
- Functional interfaces rules
- Singleton Design Pattern (regular and Spring Bean way)

---

## 🌱 Spring Boot

- `@SpringBootApplication`
- `@EnableAutoConfiguration` – how to exclude for specific class
- `@Profile`, changing active profile at runtime
- `@ControllerAdvice`, `@RestControllerAdvice`
- `@Qualifier`, `@Primary`
- Logging configuration (console, file, SQL logs)
- Interceptor and AOP concepts & usage
- Caching: Redis, `@Cacheable`
- Spring Boot built-in servers (e.g., Tomcat) – how to exclude or replace
- Spring Boot Actuator – monitor health, set thresholds, uptime stats
- Limitations / disadvantages of Spring Boot

---

## 🏗️ Microservices Architecture

- What are microservices and differences from monolithic
- Advantages & disadvantages
- Challenges in implementation
- Circuit Breaker (Resilience4j / Hystrix) – avoid cascading failure
- Service-to-service communication (REST, Feign, Kafka)
- Service discovery (Eureka, Consul)
- API Gateway (Spring Cloud Gateway)
- Rate limiting
- Kafka basics and config
- Feign Client, Load Balancing, Ribbon
- Fault tolerance & retries

---

## 📦 Build Tools: Maven vs Gradle

- Maven Lifecycle
- Maven vs Gradle comparison
- Common plugins
- Use of `settings.xml`

---

## 🧪 Testing & Code Quality

- Unit testing with JUnit/Mockito
- Integration testing with `@SpringBootTest`
- Code coverage tools like JaCoCo
- Performance testing tools (JMeter, Gatling)

---

## 🛡️ Web Security

- Common attacks: SQL Injection, XSS, CSRF
- Spring Security: AuthN/AuthZ
- JWT, OAuth2
- Role-based access control
- API Gateway security strategies

---

## 📌 Advanced Questions & Notes

- JSON handling using `org.json`
- Code: Print JSON using hardcoded org.json object
```java
JSONObject json = new JSONObject();
json.put("name", "John");

JSONArray addressArray = new JSONArray();
JSONObject addr = new JSONObject();
addr.put("city", "New York");
addr.put("zip", "10001");
addressArray.put(addr);

json.put("address", addressArray);
json.put("skills", new JSONArray(Arrays.asList("Java", "Spring")));

System.out.println(json.toString(2));```

---

- @EnableFeignClients and @EnableDiscoveryClient
- Spring Cloud Netflix (Hystrix, Ribbon, Eureka)
- Difference between REST API and Servlet API
- Design e-commerce app using microservices (scenario-based)
- Saga pattern, CQRS, Event Sourcing
- Monitoring: Prometheus, Grafana
- Centralized logging: ELK
- Distributed tracing
- CI/CD: Blue-Green, Canary deployments
- Docker, Kubernetes, IaC (Terraform, Helm)
