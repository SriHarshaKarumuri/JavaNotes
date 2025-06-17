# Collection

### Firstly Collection and Collections both are different

| Feature     | `Collection`                     | `Collections`                      |
| ----------- | -------------------------------- | ---------------------------------- |
| Type        | Interface                        | Final utility class                |
| Purpose     | Defines core collection behavior | Provides static helper methods     |
| Examples    | `List`, `Set`, `Queue`           | `sort()`, `reverse()`, `shuffle()` |
| Inheritance | Implemented by data structures   | Cannot be extended or instantiated |


## What is Collections and why introduced ?
Collections are data structures that used to group multiple elements into a single unit. They are used to store, retrieve, manipulate and communicate aggregate data.

They are introduced to solve problems like with arrays where those are static size allocation and collections have vast no of functions and classes which helps us ti maintain data efficiently.

## Types of Collections

                     Iterable(Root Interface)
                        |
                  Collection (interface)
                      |
        -----------------------------------
        |               |                 |
      List            Set              Queue
        |               |                 |
  -----------     ------------       ------------
  |         |     |          |       |          |
ArrayList LinkedList HashSet LinkedHashSet PriorityQueue ArrayDeque

                    Map (interface)
                      |
        --------------------------------
        |                              |
     HashMap                      TreeMap / LinkedHashMap

**Here Map is not a part of Collections but we generally say with along them as the purpose is same**
**The Collection interface represents a group of individual elements (like a List, Set, or Queue), where you deal with just values.**

**A Map, on the other hand, represents a mapping between unique keys and values — it’s not a collection of individual elements, but a collection of entries (key-value pairs).**


Chart for the Collection Overview

| **Category**         | **Type**           | **Key Characteristics**                      | **Example Use Cases**            |
| -------------------- | ------------------ | -------------------------------------------- | -------------------------------- |
| **List**             | Ordered collection | Allows duplicates, maintains insertion order | To-do list, playlist, cart items |
| **Set**              | Unordered, unique  | No duplicates, may not maintain order        | Tags, user roles, unique IDs     |
| **Queue**            | FIFO structure     | First-In-First-Out, may allow duplicates     | Task scheduling, print queue     |
| **Deque**            | Double-ended queue | Allows insertion/removal from both ends      | Undo/redo stack, browser history |
| **Map / Dictionary** | Key-value pairs    | Keys must be unique, values can duplicate    | Phone book, cache, lookup tables |


## Collection Explanations

✅ 1. List – Ordered, allows duplicates

| Class        | Description                                                                                               |
| `ArrayList`  | - Resizable array implementation. <br> - Fast random access, slow insertion/removal in middle.                     |
| `LinkedList` | - Doubly-linked list. <br> - Fast insert/delete at start/middle, slower access.                                    |
| `Vector`     | - Like `ArrayList` but synchronized (thread-safe). <br> - Generally avoided in favor of `ArrayList` + manual sync. |
| `Stack`      | - LIFO (Last-In, First-Out) stack based on `Vector`. <br> - Deprecated in favor of `Deque` for stack behavior.     |


✅ 2. Set – Unordered, no duplicates

| Class           | Description                                                                            |
| --------------- | -------------------------------------------------------------------------------------- |
| `HashSet`       | - Stores elements in hash table. <br> - No guaranteed order. <br> - Fast lookup.       |
| `LinkedHashSet` | - HashSet + remembers insertion order.                                                 |
| `TreeSet`       | - Stores elements in sorted (natural or custom) order. <br> - Based on Red-Black Tree. |


✅ 3. Queue / Deque – FIFO or double-ended

| Class           | Description                                                                                          
| `PriorityQueue` | - Elements are ordered based on priority (natural or comparator). <br> - Not thread-safe.                                                         |
| `ArrayDeque`    | - Resizable array, faster than `Stack`/`LinkedList` for stack/queue operations. <br> - Can be used as stack (`push/pop`) or queue (`offer/poll`). |


✅ 4. Map – Key-value pairs (not part of Collection)

| Class               | Description                                                                                 |
| ------------------- | ------------------------------------------------------------------------------------------- |
| `HashMap`           | - Stores key-value pairs using hash table. <br> - Allows `null` key/value. <br> - No order. |
| `LinkedHashMap`     | - Maintains insertion order.                                                                |
| `TreeMap`           | - Sorted map based on keys. <br> - Implements `NavigableMap`.                               |
| `Hashtable`         | - Synchronized version of `HashMap`. <br> - No `null` keys or values. (Legacy)              |
| `ConcurrentHashMap` | - Thread-safe version of `HashMap`, better performance than `Hashtable`.                    |

**Synchronized/Thread-safe Versions
Collections.synchronizedList(new ArrayList<>());**

## Why can we use only Wrapper data types in Collection
- Collections in Java can only hold objects, not primitive types like int or double.
- Why? Because collections use something called generics that only work with objects.
- Primitive types like int or double are not objects—they are simple values.
- So, to put primitive values in collections, Java uses wrapper classes like Integer for int, Double for double, etc.
- Java automatically converts between primitives and their wrappers behind the scenes—this is called autoboxing.
```
List<Integer> numbers = new ArrayList<>();
numbers.add(5);  // The int 5 is converted to an Integer object automatically
int num = numbers.get(0);  // The Integer is converted back to int automatically
```

## What is Autoboxing?
- Autoboxing is the automatic conversion that Java does from a primitive type to its corresponding wrapper class.
- For example, converting an int to an Integer automatically.
- Integer num = 5;  // Java automatically converts int 5 to Integer object

## What is Unboxing?
- Unboxing is the reverse: Java automatically converts an object of a wrapper class back to its primitive type.
- For example, converting an Integer back to an int.
- int n = new Integer(10);  // Java automatically converts Integer to int

## Difference between HashMap and ConcurrentHashMap?

| Feature                   | `HashMap`           | `ConcurrentHashMap` |
| ------------------------- | ------------------- | ------------------- |
| Thread-safe               | ❌ No                | ✅ Yes               |
| Allows `null` keys/values | ✅ Yes / Yes         | ❌ No / No           |
| Iterator                  | Fail-fast           | Weakly consistent   |
| Performance in threads    | Poor                | High                |
| Suitable for              | Single-threaded use | Multi-threaded use  |



## What is the difference between Comparable and Comparator?

| Feature                | `Comparable`                        | `Comparator`                       |
| ---------------------- | ----------------------------------- | ---------------------------------- |
| **Package**            | `java.lang`                         | `java.util`                        |
| **Purpose**            | Used to define **natural ordering** | Used to define **custom ordering** |
| **Implemented by**     | The class itself                    | A separate class                   |
| **Method**             | `compareTo(Object o)`               | `compare(Object o1, Object o2)`    |
| **Modifies class?**    | Yes (must change source code)       | No (can be external)               |
| **Can have multiple?** | ❌ Only one natural order            | ✅ Multiple comparators possible    |


- ✅ 1. Comparable – natural/default order (only one allowed)
- Used when a class implements the Comparable interface and defines its own default sorting logic.
- We need to implement in class and extend to other class

- Comparator – custom or multiple orders (flexible)
- Used when you want to sort objects in different ways without modifying the class.
- We can directly write in the lambda expression or method references.

## What is fail-fast vs fail-safe in collections?

- Fail fast occurs in collections like ArrayList,HashMap,HashSet, while we try to update the elements of list in between iteration (for-loop or Iterator) it will throws a **ConcurrentModificationException**.
```
List<Integer> list = new ArrayList<>();
list.add(1);
list.add(2);

Iterator<Integer> it = list.iterator();
list.add(3);  // Structural modification after iterator created

it.next();    // Throws ConcurrentModificationException here
```

- Fail Safe means there will be no exception like fail fast when we try to modify elements in the iteration.**But we need to use only ConcurrentHashMap or CopyOnWriteArrayList.**

```
CopyOnWriteArrayList<Integer> list = new CopyOnWriteArrayList<>();
list.add(1);
list.add(2);

Iterator<Integer> it = list.iterator();
list.add(3);  // Modifies the original list, but iterator sees old snapshot

while(it.hasNext()) {
    System.out.println(it.next());  // Will print only 1 and 2
}
```
---

### But while we are using Iterator or ListIterator for iteration the exception wont be triggered in Fail fast if we use built in methods of Iterator like itr.remove(),itr.add() or listItr.set().
```
List<String> list = new ArrayList<>(List.of("A", "B", "C"));
Iterator<String> it = list.iterator();

while (it.hasNext()) {
    String val = it.next();
    if (val.equals("B")) {
        it.remove();  // Safe: modifies list via iterator, no exception
    }
}
```

| Feature                 | Fail-Fast                                                | Fail-Safe                                   |
| ----------------------- | -------------------------------------------------------- | ------------------------------------------- |
| Iterator type           | Throws `ConcurrentModificationException` on modification | Doesn't throw, works on copy                |
| Collection examples     | `ArrayList`, `HashMap`                                   | `ConcurrentHashMap`, `CopyOnWriteArrayList` |
| Concurrent modification | Not allowed during iteration                             | Allowed, but iterator sees snapshot         |
| Performance impact      | Faster, less memory                                      | Slower, higher memory due to copying        |

---

## What is the time complexity for get() and put() in HashMap, TreeMap, and LinkedHashMap?
| Collection      | `get()` Time          | `put()` Time          | Maintains Order?         |
| --------------- | --------------------- | --------------------- | ------------------------ |
| `HashMap`       | O(1) avg / O(n) worst | O(1) avg / O(n) worst | ❌ No                     |
| `TreeMap`       | O(log n)              | O(log n)              | ✅ Sorted order           |
| `LinkedHashMap` | O(1) avg / O(n) worst | O(1) avg / O(n) worst | ✅ Insertion/access order |

---

## How does ConcurrentHashMap achieve thread safety without locking the entire map?
- 1. Fine-Grained Locking (Before Java 8)
  2. The map was internally divided into segments, each a separate hash table with its own lock.
- Only one thread could modify a segment at a time, allowing multiple threads to operate on different segments concurrently.
- 2. Bucket-Level Synchronization (Since Java 8)
  3. The internal structure is a single array of buckets (nodes).Each bucket (or bin) may be:
     - A linked list
     - A tree (Red-Black Tree) for better performance on high hash collisions.
    
---

## What is the difference between Enumeration, Iterator, and ListIterator?

Enumeration is mostly used for legacy like Hashtable and Vectors

**Enumeration and enum both are different** 

| Feature             | `Enumeration`      | `Iterator`      | `ListIterator` |
| ------------------- | ------------------ | --------------- | -------------- |
| Introduced In       | JDK 1.0            | JDK 1.2         | JDK 1.2        |
| Applicable To       | Legacy collections | All collections | Lists only     |
| Traverse Forward    | ✅                  | ✅               | ✅              |
| Traverse Backward   | ❌                  | ❌               | ✅              |
| Remove Element      | ❌                  | ✅               | ✅              |
| Add/Replace Element | ❌                  | ❌               | ✅              |
| Fail-fast           | ❌ (legacy)         | ✅               | ✅              |

---

## Explain the difference between synchronized collections and concurrent collections.
### Need to know about Multithreading Concepts to understand this.
1. Synchronized Collections
What They Are:
Legacy collections (like Vector, Hashtable) or wrappers created using Collections.synchronizedXXX().
- Only one thread can access any method at a time.
- Must manually synchronize during iteration to avoid ConcurrentModificationException.

2. Concurrent Collections
What They Are:
Part of java.util.concurrent package (Java 5+)
Designed for high-concurrency and non-blocking or fine-grained locking.
- Multiple threads access and update collections frequently.
- You need high throughput and better scalability.
- Examples:ConcurrentHashMap,CopyOnWriteArrayList,ConcurrentLinkedQueue,ConcurrentSkipListMap.

| Feature                       | Synchronized Collections                             | Concurrent Collections                      |
| ----------------------------- | ---------------------------------------------------- | ------------------------------------------- |
| Introduced In                 | Java 1.2 (via wrappers)                              | Java 5 (java.util.concurrent)               |
| Locking Mechanism             | Whole object (coarse-grained)                        | Fine-grained or lock-free                   |
| Performance Under Concurrency | Poor                                                 | Excellent                                   |
| Fail-Fast Iteration           | ❌ May throw `ConcurrentModificationException`        | ✅ Safe and weakly consistent                |
| Example Classes               | `Vector`, `Hashtable`, `Collections.synchronizedX()` | `ConcurrentHashMap`, `CopyOnWriteArrayList` |
| Use Case                      | Legacy code or simple multi-threaded needs           | High-performance concurrent applications    |



## What is a HashMap?
 A HashMap in Java is a key-value pair data structure that allows fast access, insertion, and deletion of elements,
 typically in O(1) average time.

 ## 🔍 Internal Working of HashMap
**Hashing the Key**
When you insert a key-value pair:
map.put(1,"hello");
1. Java internally does this 
`int hash = hash("John"); // calls key.hashCode()`
Then it determines the bucket index using:
`index = hash % capacity; // mod capacity of internal array`
2. Bucket Array
Internally, HashMap maintains an array of Node<K, V>, called the bucket array:
`Node<K, V>[] table;`
Each index of the array is called a bucket, and it holds a linked list or tree of entries that hash to the same index.
3. Collision Handling
- Two keys may have the same index due to a hash collision.

- Collision resolution strategy:
Before Java 8: Linked List in the bucket.

- Java 8 and later:
If collisions exceed a threshold (TREEIFY_THRESHOLD = 8), the list becomes a balanced binary tree for faster access.

---

## What is the load factor in HashMap?
The load factor is a measure that controls when the HashMap should increase its capacity (resize) to maintain efficient performance.
The load factor is a float value between 0 and 1.
It represents the threshold of how full the HashMap can get before it automatically increases its capacity (rehashes).
The default load factor in Java's HashMap is 0.75.

---

## Can a Map contain a null key or value?

| Implementation  | `null` Key | `null` Value |
| --------------- | ---------- | ------------ |
| `HashMap`       | Yes (1)    | Yes          |
| `Hashtable`     | No         | No           |
| `TreeMap`       | No\*       | Yes          |
| `LinkedHashMap` | Yes (1)    | Yes          |

**TreeMap can accept null keys only if a custom comparator is used that can handle null.**

---

## Is HashMap thread-safe? How can you make it thread-safe?
No, HashMap is not thread-safe.

Why HashMap Is Not Thread-Safe

In a multithreaded environment, if multiple threads access and modify a HashMap concurrently without proper synchronization:
You might get data inconsistency,
It may enter an infinite loop (in older Java versions) due to structure corruption,
And it can even throw runtime exceptions like ConcurrentModificationException.

How to Make HashMap Thread-Safe
Here are several ways to make a HashMap thread-safe:
1. Use Collections.synchronizedMap()
2. Use ConcurrentHashMap (Recommended for High Concurrency)
ConcurrentHashMap is designed for concurrent access with better performance than synchronizing a HashMap.
3. Use Collections.synchronizedMap() with LinkedHashMap
4. Use synchronized blocks manually (not ideal).

---

## When would you use a LinkedHashMap instead of a HashMap?
| Feature              | `HashMap`                                       | `LinkedHashMap`                         |
| -------------------- | ----------------------------------------------- | --------------------------------------- |
| **Ordering**         | No guaranteed order                             | Maintains insertion or access order     |
| **Performance**      | Slightly faster (no overhead of order tracking) | Slightly slower (due to order tracking) |
| **Null keys/values** | Allows 1 null key, many null values             | Same behavior                           |
| **Use in LRU Cache** | Not suitable                                    | Ideal with access-order flag            |

---

## Can you implement your own custom comparator to sort a list of objects?
- Yes we can, As asked custom comparator, if we have Person class we need to create a CustomComparator class which implements Comparator<Employee> then override the compare method.
- And see it asked Objects not integer or String. **Object is a superclass of java so all it can be any datatype**
```
import java.util.*;
class CustomComparator implements Comparator<Person> {
    public int compare(Person p1, Person p2) {
        return Integer.compare(p1.age, p2.age); // Ascending order
        return Integer.compare(p1.age, p2.age); // Descending order
    }
}
```
**For Comparable**
```
class Person implements Compable<Person> {
    public int compareTo(Person p) {
        return this.getSal() - p.getSal(); // Ascending order
        return this.getSal() - p.getSal(); // Desc order
    }
}
```
**Note : as here we use this.getSal() not this.p.getSal() as currently we have person so this is considered as Person object so this.getSal() - p.getSal();**

---

## How do you remove elements from a collection while iterating over it safely?
We can use Iterator or Use CopyOnWriteArrayList

---

## What is an IdentityHashMap? How is it different from a regular HashMap?
An IdentityHashMap in Java is a special implementation of the Map interface that uses reference equality (==) instead of object equality (equals()) for comparing keys (and sometimes values).
- It does not use .equals() and .hashCode() to compare keys.
- 





