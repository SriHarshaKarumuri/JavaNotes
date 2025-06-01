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

### ✅ Key Topics
- `GET` vs `@RequestMapping`
- `@RestController` vs `@Controller`
- Pagination: `Pageable`, `offset`, `limit`
- `String` vs `StringBuilder` vs `StringBuffer`
- `equals()` and `hashCode()` contract
- Variable Arguments (`varargs`)
- `String[] args` vs `String... args` in `main` method
- Calling static methods via `null` object reference

### ❓ Questions
- What is the difference between `GET` and `@RequestMapping`?
- Can you override a static method in Java?
- Can you call a static method using an object?
- What is the difference between `String`, `StringBuilder`, and `StringBuffer`?
- What is the contract between `equals()` and `hashCode()`?

---

## 🔁 Threads & Concurrency

### 🔹 Key Topics
- What is multithreading?
- Thread states: `NEW`, `RUNNABLE`, `BLOCKED`, `WAITING`, `TIMED_WAITING`, `TERMINATED`
- Thread creation:
  - `extends Thread`
  - `implements Runnable`
  - `implements Callable`
  - Executor Framework
- Keywords: `volatile`, `transient`, `synchronized`
- Preventing memory leaks:
  - `WeakHashMap`
  - Avoid static misuse
  - Profiling: VisualVM, JProfiler
- `HashMap` vs `ConcurrentHashMap` vs `Hashtable`

### ❓ Questions
- How do you achieve synchronization in Java threads?
- What is the purpose of the `volatile` keyword in Java?
- What are the different states in a Java thread lifecycle?
- How do you create a thread in Java?

---

## 📦 Collections & Internals

### 📌 Key Topics
- How `HashMap` works internally
- What is hashing?
- `TreeSet` behavior with `null`
- Marker Interface & Custom Marker Interfaces

### ❓ Questions
- What are the main types of Java collections?
- What is the difference between `ArrayList`, `HashSet`, and `HashMap`?
- How does a `HashMap` work in Java?
- Can a `HashMap` have null keys or values?

---

## 🧠 Java Memory Model

### 💡 Key Topics
- Heap vs Stack
- Garbage Collection
- Memory leaks and prevention

### ❓ Questions
- What is the Java Memory Model (JMM)?
- How can memory leaks be prevented in Java?

---

## ⚠️ Exception Handling

### 🚨 Key Topics
- Try-Catch-Finally blocks
- Global Exception Handling:
  - `@ControllerAdvice`
  - `@RestControllerAdvice`
- Behavior of `finally` with `return` or `System.exit()`

### ❓ Questions
- How do you handle exceptions globally in Spring Boot?
- What is the use of `@ExceptionHandler`?
- What is `ResponseEntityExceptionHandler` and how is it used?

---

## 🌿 Java 8 Features

### 🌱 Key Topics
- `Optional` class
- Method References
- Functional Interfaces
- Default vs Static methods in interfaces
- `A.super.method()` usage for diamond problem
- `private` methods in interfaces

### ❓ Questions
- What are functional interfaces in Java 8?
- Can a functional interface be empty?
- What are default methods and how do they differ from static methods?

---

## 🗄️ Database Concepts

### 🗂️ Key Topics
- `JOIN` vs Subquery
- `HAVING` vs `WHERE`
- Views vs Tables
- Stored Procedures vs Views
- Clustered vs Non-clustered Index

### ❓ Questions
- What is the difference between a clustered and non-clustered index?
- When would you use a view instead of a table?
- How are `JOIN` and subqueries different?

---

## 🧩 Interfaces & OOP

### 🧱 Key Topics
- Abstract class vs Base class
- Marker Interfaces and their uses
- Functional Interfaces

### ❓ Questions
- What is the difference between method overriding and overloading?
- Can we omit abstract methods in a functional interface?
- What is a marker interface and how is it used?

---

## 🌱 Spring Boot

### 🟢 Key Topics
- Creating Spring Boot applications
- Profiles (`@Profile`, `application-{profile}.yml`)
- Spring Boot Actuator
- Exception Handling with `@ControllerAdvice`
- Spring JPA and its annotations
- SQL logging configuration
- Caching with Redis
- Interceptors and AOP

### ❓ Questions
- How do you handle exceptions in Spring Boot?
- What is the use of `@Profile` annotation?
- How do you enable and use caching in Spring Boot?
- What is an interceptor and how does it work?
- What is AOP and how is it implemented in Spring?

---

## 🏗️ Microservices Architecture

### 🧩 Key Topics
- Key components of microservices
- Circuit Breaker (Resilience4j, Hystrix)
- Fault tolerance and isolation
- REST API design
- Kafka integration
- Service communication

### ❓ Questions
- What is Rate Limiting and how do you implement it?
- How do microservices communicate with each other?
- What is Kafka and how does it work in microservices?

---

## 📦 Build Tools: Maven vs Gradle

### ⚙️ Key Topics
- Maven vs Gradle comparison
- Maven lifecycle: validate → compile → test → package → install → deploy
- Maven Plugins
- Role of `settings.xml`

### ❓ Questions
- What is the difference between Maven and Gradle?
- What are the different phases in Maven's build lifecycle?

---

## 🧪 Testing & Code Quality

### 🧪 Key Topics
- Unit Testing (JUnit, Mockito)
- Integration Testing
- Code Coverage (JaCoCo)
- Performance Testing (JMeter)

### ❓ Questions
- What is the difference between unit and integration testing?
- How do you test a Spring Boot application?

---

## 🛡️ Web Security

### 🔐 Key Topics
- SQL Injection
- XSS, CSRF
- Authentication and Authorization

### ❓ Questions
- What are common web vulnerabilities and how do you prevent them in Spring Boot?

---

## 📌 Advanced Questions & Notes

- Complex SQL in JPA (JPQL, Native)
- WAR vs JAR
- Spring Boot Pros & Cons
- Real-time architecture trade-offs

---

## 💡 Coding Exercise

> We have a list of employees where each has a list of departments. Count the number of employees in each department using Java Streams.

```java
Map<String, Long> departmentCounts = employees.stream()
    .flatMap(emp -> emp.getDepartments().stream())
    .collect(Collectors.groupingBy(
        dept -> dept, Collectors.counting()
    ));
