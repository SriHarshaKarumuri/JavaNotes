# Spring Framework Notes

This document serves as a comprehensive guide to the **Spring Framework** including **Spring AOP**, **Spring MVC**, **Spring Security**, **Spring Boot**, and more. It covers the major features, annotations, configurations, and examples to help you understand and implement them effectively.

---

## 📚 Table of Contents

- [🔹 Introduction to Spring Framework](#-introduction-to-spring-framework)
- [🔹 Spring AOP](#-spring-aop)
  - [AOP Concepts](#aop-concepts)
  - [Annotations for AOP](#annotations-for-aop)
  - [AOP Configuration](#aop-configuration)
- [🔹 Spring MVC](#-spring-mvc)
  - [Controller and Annotations](#controller-and-annotations)
  - [View Resolver](#view-resolver)
  - [Spring MVC Configurations](#spring-mvc-configurations)
- [🔹 Spring Security](#-spring-security)
  - [Security Annotations](#security-annotations)
  - [Spring Security Configuration](#spring-security-configuration)
  - [Authentication and Authorization](#authentication-and-authorization)
- [🔹 Spring Boot](#-spring-boot)
  - [Spring Boot Annotations](#spring-boot-annotations)
  - [Application Properties](#application-properties)
  - [Spring Boot Configurations](#spring-boot-configurations)
- [🔹 Miscellaneous Spring Features](#-miscellaneous-spring-features)
  - [Profiles in Spring](#profiles-in-spring)
  - [Spring Data JPA](#spring-data-jpa)

---

## 🔹 Introduction to Spring Framework

The **Spring Framework** is a powerful framework used to develop Java-based enterprise applications. It provides comprehensive infrastructure support for developing Java applications. The key components of the Spring Framework are:

1. **Inversion of Control (IoC)**: Dependency Injection (DI) helps in decoupling components.
2. **Aspect-Oriented Programming (AOP)**: Separation of concerns, like logging and transaction management.
3. **Spring MVC**: Web framework for building web applications.
4. **Spring Security**: Authentication and Authorization framework.
5. **Spring Boot**: Simplifies Spring application development with embedded servers and default configurations.

---

## 🔹 Spring AOP

### AOP Concepts

- **AOP (Aspect-Oriented Programming)** is a programming paradigm that separates cross-cutting concerns (e.g., logging, security) from the main business logic.
- Key Concepts:
  - **Aspect**: A module that contains cross-cutting concerns.
  - **Join Point**: A point in the execution of the program (e.g., method execution).
  - **Advice**: The action to be taken at a specific join point.
  - **Pointcut**: A predicate that matches join points.
  - **Weaving**: The process of applying aspects to the target code.

### Annotations for AOP

1. **@Aspect**: Used to define an aspect.
2. **@Before**: Executes before a method execution.
3. **@After**: Executes after a method execution.
4. **@AfterReturning**: Executes after a method execution if it completes successfully.
5. **@AfterThrowing**: Executes after a method execution if it throws an exception.
6. **@Around**: Wraps method execution, and can modify arguments, return values, or exceptions.

### AOP Configuration

#### XML-based Configuration:
```xml
<bean id="loggingAspect" class="com.example.LoggingAspect" />
<aop:config>
    <aop:aspect ref="loggingAspect">
        <aop:before method="logBefore" pointcut="execution(* com.example.*.*(..))" />
    </aop:aspect>
</aop:config>
