# Java Stream API - Detailed Guide

The **Java Stream API** (introduced in Java 8) allows you to process sequences of elements (such as collections or arrays) in a **functional style**. It provides a high-level abstraction for operations on data such as filtering, mapping, reducing, etc.

This document covers the key methods in the **Stream API**, providing a detailed explanation with **examples**.

---

## 📚 Table of Contents

- [🔹 What is a Stream?](#-what-is-a-stream)
- [🔹 Types of Stream Operations](#-types-of-stream-operations)
  - [Intermediate Operations](#intermediate-operations)
  - [Terminal Operations](#terminal-operations)
- [🔹 Stream Creation](#-stream-creation)
- [🔹 Stream API Methods with Examples](#-stream-api-methods-with-examples)
  - [Filtering](#filtering)
  - [Mapping](#mapping)
  - [Sorting](#sorting)
  - [Distinct](#distinct)
  - [Reduction](#reduction)
  - [Collecting](#collecting)
  - [ForEach](#foreach)
  - [AllMatch, AnyMatch, NoneMatch](#allmatch-anymatch-nonematch)
  - [Min, Max](#min-max)

---

## 🔹 What is a Stream?

A **Stream** is a sequence of elements that can be processed in parallel or sequentially. Streams do not modify the underlying data structure (such as a list or array) but provide a new way to manipulate and process data.

Key characteristics of Streams:
- **Functional**: It supports **map**, **filter**, **reduce**, and other functional operations.
- **Lazy Evaluation**: Intermediate operations are **lazy** and are executed only when a terminal operation is invoked.
- **Non-mutating**: Streams do not modify the original data structure; they generate a new stream after processing.

---

## 🔹 Types of Stream Operations

Stream operations are divided into **two main types**:

1. **Intermediate Operations**:
   - Transform a stream into another stream.
   - **Lazy evaluation**: They are only executed when a terminal operation is triggered.

2. **Terminal Operations**:
   - Produce a result or a side effect.
   - Trigger the actual processing of the stream.

---

## 🔹 Stream Creation

Streams can be created from **collections**, **arrays**, or by generating **custom streams**.

### Example 1: Creating a Stream from a Collection

```java
import java.util.List;
import java.util.stream.Stream;

List<String> names = List.of("Alice", "Bob", "Charlie", "David");

Stream<String> nameStream = names.stream();
nameStream.forEach(System.out::println);  // Output: Alice, Bob, Charlie, David

int[] numbers = {1, 2, 3, 4, 5};
IntStream numberStream = Arrays.stream(numbers);
numberStream.forEach(System.out::println);  // Output: 1 2 3 4 5

🔹 Stream API Methods with Examples
1. Filtering
filter() is an intermediate operation that allows you to filter elements based on a predicate.

Example:
List<Integer> numbers = List.of(1, 2, 3, 4, 5, 6);
numbers.stream()
       .filter(n -> n % 2 == 0)  // Filter even numbers
       .forEach(System.out::println);  // Output: 2, 4, 6
2. Mapping
map() is an intermediate operation that applies a function to each element in the stream, producing a new stream of the transformed elements.

Example:
List<String> words = List.of("apple", "banana", "cherry");
words.stream()
     .map(String::toUpperCase)  // Convert each word to uppercase
     .forEach(System.out::println);  // Output: APPLE, BANANA, CHERRY
3. Sorting
sorted() is an intermediate operation that sorts the elements in the stream.

Example:

List<Integer> numbers = List.of(5, 3, 8, 1);
numbers.stream()
       .sorted()  // Sort the numbers in natural order
       .forEach(System.out::println);  // Output: 1, 3, 5, 8
To sort with a custom comparator:

List<String> words = List.of("apple", "banana", "cherry");
words.stream()
     .sorted((w1, w2) -> w2.compareTo(w1))  // Sort in reverse order
     .forEach(System.out::println);  // Output: cherry, banana, apple
4. Distinct
distinct() is an intermediate operation that removes duplicate elements from the stream.

Example:
List<Integer> numbers = List.of(1, 2, 2, 3, 4, 4, 5);
numbers.stream()
       .distinct()  // Remove duplicates
       .forEach(System.out::println);  // Output: 1, 2, 3, 4, 5

5. Reduction
Reduction is a terminal operation that combines elements in the stream using a binary operator.

reduce() takes two parameters: an identity value and a binary operator.

Example: Sum of Elements
List<Integer> numbers = List.of(1, 2, 3, 4, 5);
int sum = numbers.stream()
                 .reduce(0, (a, b) -> a + b);  // Sum the numbers
System.out.println(sum);  // Output: 15

Example: Find Maximum Value
List<Integer> numbers = List.of(1, 2, 3, 4, 5);
int max = numbers.stream()
                 .reduce(Integer.MIN_VALUE, (a, b) -> a > b ? a : b);
System.out.println(max);  // Output: 5

6. Collecting
collect() is a terminal operation used to collect elements of the stream into a collection such as a List, Set, or Map.

Example: Collect to List
List<String> words = List.of("apple", "banana", "cherry");
List<String> upperCaseWords = words.stream()
                                   .map(String::toUpperCase)
                                   .collect(Collectors.toList());  // Collect as List
System.out.println(upperCaseWords);  // Output: [APPLE, BANANA, CHERRY]

Example: Collect to Set
List<Integer> numbers = List.of(1, 2, 2, 3, 4, 4, 5);
Set<Integer> uniqueNumbers = numbers.stream()
                                    .collect(Collectors.toSet());  // Collect as Set
System.out.println(uniqueNumbers);  // Output: [1, 2, 3, 4, 5]

7. ForEach
forEach() is a terminal operation that performs an action on each element of the stream.

Example:
List<String> words = List.of("apple", "banana", "cherry");
words.stream()
     .forEach(System.out::println);  // Output: apple, banana, cherry

8. AllMatch, AnyMatch, NoneMatch
allMatch(): Checks if all elements satisfy the given condition.

anyMatch(): Checks if any element satisfies the given condition.

noneMatch(): Checks if no elements satisfy the given condition.

Example: All Match
List<Integer> numbers = List.of(2, 4, 6, 8);
boolean allEven = numbers.stream().allMatch(n -> n % 2 == 0);
System.out.println(allEven);  // Output: true

Example: Any Match
List<Integer> numbers = List.of(1, 2, 3, 4);
boolean anyEven = numbers.stream().anyMatch(n -> n % 2 == 0);
System.out.println(anyEven);  // Output: true

Example: None Match
List<Integer> numbers = List.of(1, 3, 5);
boolean noEven = numbers.stream().noneMatch(n -> n % 2 == 0);
System.out.println(noEven);  // Output: true

9. Min, Max
min() and max() are terminal operations that return the minimum or maximum element in the stream, respectively, based on a comparator.

Example: Find Minimum Element
List<Integer> numbers = List.of(1, 2, 3, 4, 5);
Optional<Integer> min = numbers.stream().min(Integer::compareTo);
min.ifPresent(System.out::println);  // Output: 1

Example: Find Maximum Element
List<Integer> numbers = List.of(1, 2, 3, 4, 5);
Optional<Integer> max = numbers.stream().max(Integer::compareTo);
max.ifPresent(System.out::println);  // Output: 5

✅ Conclusion
The Stream API is a powerful tool for processing collections in a functional programming style. By utilizing intermediate operations like filter, map, distinct, and terminal operations like collect, forEach, and reduce, you can write cleaner and more efficient Java code.

With the Stream API, you can:

Filter, transform, sort, and aggregate data more efficiently.

Perform parallel processing for larger datasets, making your applications faster.

Feel free to fork, clone, or contribute! This guide is continually evolving.


