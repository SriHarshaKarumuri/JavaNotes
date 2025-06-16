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

## What is the load factor in HashMap?
The load factor is a measure that controls when the HashMap should increase its capacity (resize) to maintain efficient performance.
The load factor is a float value between 0 and 1.
It represents the threshold of how full the HashMap can get before it automatically increases its capacity (rehashes).
The default load factor in Java's HashMap is 0.75.

## Can a Map contain a null key or value?

| Implementation  | `null` Key | `null` Value |
| --------------- | ---------- | ------------ |
| `HashMap`       | Yes (1)    | Yes          |
| `Hashtable`     | No         | No           |
| `TreeMap`       | No\*       | Yes          |
| `LinkedHashMap` | Yes (1)    | Yes          |

**TreeMap can accept null keys only if a custom comparator is used that can handle null.**

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
4. Use synchronized blocks manually (not ideal)

## When would you use a LinkedHashMap instead of a HashMap?
| Feature              | `HashMap`                                       | `LinkedHashMap`                         |
| -------------------- | ----------------------------------------------- | --------------------------------------- |
| **Ordering**         | No guaranteed order                             | Maintains insertion or access order     |
| **Performance**      | Slightly faster (no overhead of order tracking) | Slightly slower (due to order tracking) |
| **Null keys/values** | Allows 1 null key, many null values             | Same behavior                           |
| **Use in LRU Cache** | Not suitable                                    | Ideal with access-order flag            |



