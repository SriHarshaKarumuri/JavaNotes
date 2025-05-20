# Collections

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
