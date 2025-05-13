
# 📘 Hibernate: What It Is and What It's Used For

**Hibernate** is an **Object-Relational Mapping (ORM)** framework for Java. It allows developers to **map Java objects (POJOs) to relational database tables**, and vice versa, making database interaction **simpler, cleaner, and more maintainable**.

---

## 🔹 What is Hibernate?

Hibernate is a **Java-based ORM tool** that:
- Simplifies database access in Java applications.
- Automatically handles the mapping between **Java classes** and **database tables**.
- Reduces the need for writing complex **JDBC code**, SQL queries, and result set processing.

---

## 🔹 Key Uses of Hibernate

| Feature                        | Description                                                                 |
|-------------------------------|-----------------------------------------------------------------------------|
| ✅ Object-Relational Mapping   | Maps Java objects to database tables and vice versa.                        |
| ✅ Simplifies CRUD Operations | Automates Create, Read, Update, Delete without writing SQL.                 |
| ✅ Portable & Flexible        | Works with many databases (MySQL, PostgreSQL, Oracle, etc.).                |
| ✅ Caching                    | Improves performance with built-in first-level and second-level caching.    |
| ✅ HQL Support                | Hibernate Query Language for object-based querying instead of SQL.          |
| ✅ Transaction Management     | Integrates with JTA, JDBC, and Spring for robust transaction management.    |

---

## 🔹 Hibernate Architecture Overview

- **Configuration**: Reads settings (from `hibernate.cfg.xml` or annotations).
- **SessionFactory**: Creates `Session` objects and is a heavyweight object (one per database).
- **Session**: Provides methods to interact with the database.
- **Transaction**: Manages atomic database operations.
- **Query**: Supports HQL and native SQL queries.

---

## 🔹 Common Hibernate Annotations

| Annotation         | Purpose                                           |
|--------------------|--------------------------------------------------|
| `@Entity`          | Marks a class as an entity (mapped to a table).  |
| `@Table`           | Maps entity to a specific table name.            |
| `@Id`              | Marks a field as the primary key.                |
| `@GeneratedValue`  | Specifies generation strategy for primary key.   |
| `@Column`          | Maps class field to a specific column.           |
| `@OneToOne`, `@ManyToOne`, `@OneToMany`, `@ManyToMany` | For relationships between entities. |

---

##🔹 Why Use Hibernate?
- Reduces boilerplate JDBC code.

- Automatically manages entity states and relationships.

- Handles caching, lazy loading, and connection pooling.

- Integrates well with Spring Framework and JPA (Java Persistence API).

- Makes it easy to switch between different databases.

## 🔹 Simple Example

```java
@Entity
@Table(name = "employee")
public class Employee {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    @Column(name = "name")
    private String name;

    // Getters and setters
}

