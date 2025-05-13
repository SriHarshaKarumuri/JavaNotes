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

- ✅ `GET` vs `@RequestMapping`
- ✅ `@RestController` vs `@Controller`
- ✅ Pagination: `Pageable`, `offset`, `limit`
- ✅ `String` vs `StringBuilder` vs `StringBuffer`
- ✅ `equals()` and `hashCode()` contract
- ✅ Variable Arguments (`varargs`)
- ✅ `String[] args` vs `String... args` in `main` method
- ✅ Calling static methods via `null` object reference

---

## 🔁 Threads & Concurrency

- 🔹 What is multithreading?
- 🔹 Thread states: `NEW`, `RUNNABLE`, `BLOCKED`, `WAITING`, `TIMED_WAITING`, `TERMINATED`
- 🔹 Thread creation:
  - `extends Thread`
  - `implements Runnable`
  - `implements Callable`
  - Executor Framework
- 🔹 Keywords: `volatile`, `transient`, `synchronized`
- 🔹 Java Memory Model (JMM)
- 🔹 Preventing memory leaks:
  - `WeakHashMap`
  - Avoid static misuses
  - Profiling: VisualVM, JProfiler
- 🔹 `HashMap` vs `ConcurrentHashMap` vs `Hashtable`

---

## 📦 Collections & Internals

- 📌 How `HashMap` works internally
- 📌 What is hashing?
- 📌 `TreeSet` behavior with `null`, e.g., `TreeSet.add(null)`
- 📌 Marker Interface & Custom Marker Interfaces.
- 📌 Every time when we use lamba expressions does it create object as its anonymous class ?

---

## 🧠 Java Memory Model

- 💡 Heap vs Stack
- 💡 Garbage Collection
- 💡 Memory leaks and prevention

---

## ⚠️ Exception Handling

- 🚨 Try-Catch-Finally blocks
- 🚨 Global Exception Handling:
  - `@ControllerAdvice`
  - `@RestControllerAdvice`
- 🚨 Behavior of `finally` with `return` or `System.exit()`

---

## 🌿 Java 8 Features

- 🌱 `Optional` class
- 🌱 Method References (`Class::method`)
- 🌱 Functional Interfaces
  - Can it be empty?
- 🌱 Default vs Static methods in interfaces
- 🌱 Diamond problem in default methods and resolution using `A.super.method()`
- 🌱 `private` methods in interfaces

---

## 🗄️ Database Concepts

- 🗂️ `JOIN` vs Subquery
- 🗂️ `HAVING` vs `WHERE`
- 🗂️ Views vs Tables
- 🗂️ Stored Procedures vs Views
- 🗂️ Clustered vs Non-clustered Index

---

## 🧩 Interfaces & OOP

- 🧱 Abstract class vs Base class
- 🧱 Marker Interfaces and their uses
- 🧱 Functional Interfaces: Can we omit abstract methods?

---

## 🌱 Spring Boot

- 🟢 Creating Spring Boot applications (via Initializr, CLI, manually)
- 🟢 `@RestController` vs `@Controller`
- 🟢 Profiles in Spring (`@Profile`, application-{profile}.yml)
- 🟢 Spring Boot Actuator: Monitoring, Metrics, Health
- 🟢 Exception Handling with `@ControllerAdvice`
- 🟢 Managing version conflicts in Maven

---

## 🏗️ Microservices Architecture

- 🧩 Key Components of Microservices
- 🧩 Circuit Breaker pattern (Resilience4j/Hystrix)
- 🧩 Fault Isolation / Fault Tolerance
- 🧩 REST API design strategies

---

## 📦 Build Tools: Maven vs Gradle

- ⚙️ Maven vs Gradle
- ⚙️ Maven Build Lifecycle: `validate → compile → test → package → install → deploy`
- ⚙️ Maven Plugins
- ⚙️ Purpose of `settings.xml`

---

## 🧪 Testing & Code Quality

- 🧪 Unit Testing in Spring Boot (JUnit, Mockito)
- 🧪 Integration Testing (`@SpringBootTest`)
- 🧪 Code Coverage (JaCoCo)
- 🧪 Performance Testing (JMeter, Gatling)

---

## 🛡️ Web Security

- 🔐 Common Web Vulnerabilities:
  - SQL Injection
  - XSS, CSRF
  - Broken Authentication
- 🔐 Best practices for security in Spring Boot

---

## 📌 Advanced Questions & Notes

- 🧠 Complex SQL in Spring Data JPA (JPQL, Native Queries)
- 🧠 WAR vs JAR & Embedded Containers
- 🧠 Spring Boot Pros & Cons:
  - ✅ Rapid development
  - ❌ Increased memory usage
- 🧠 Real-time use cases and trade-offs

---

## ❓ Doubts & Clarifications

| Concept     | Clarification |
|-------------|----------------|
| `transient` | Field won't be serialized |
| `volatile`  | Guarantees visibility of changes across threads |

---

> 🔍 _Feel free to fork, contribute, or share suggestions! This guide is an evolving knowledge base designed to keep you sharp and interview-ready._

