# Hash Table Data Structure – Detailed Explanation

## 1. What is a Hash Table?

A **Hash Table** is a data structure that stores data in **key–value pairs** and provides **fast insertion, deletion, and lookup** operations by using a **hash function** to map keys to memory locations.

Example:

```
Key   → Hash Function → Index → Value
"id"      h(key)        3      42
```

The core idea is to convert a key into an array index.

---

## 2. Why Do We Use Hash Tables?

Hash Tables are used when:

* Extremely fast lookups are required
* Data is accessed via unique identifiers (keys)
* Order is not important

Advantages:

* Near constant-time operations
* Efficient for large datasets
* Widely used in system design

---

## 3. Applications of Hash Tables

### 3.1 Software Systems

* Dictionaries / Maps
* Caches (LRU Cache)
* Symbol tables in compilers

### 3.2 Databases & Backend

* Indexing
* Session storage
* Key–value stores (Redis)

### 3.3 Algorithms

* Two Sum problem
* Frequency counting
* Duplicate detection

### 3.4 AI & NLP

* Vocabulary lookup
* Token frequency maps
* Feature indexing

---

## 4. Hash Table Components

### 4.1 Key

A unique identifier used to access a value.

### 4.2 Hash Function

A function that maps a key to an integer index.

Properties of a good hash function:

* Deterministic
* Uniform distribution
* Fast computation

### 4.3 Buckets

Array slots where values are stored.

---

## 5. Collision Handling Techniques

A **collision** occurs when two keys map to the same index.

### 5.1 Chaining

Each bucket stores a linked list (or dynamic array).

```
Index 2 → (key1,value1) → (key2,value2)
```

### 5.2 Open Addressing

Store elements directly in the array.

Types:

* Linear Probing
* Quadratic Probing
* Double Hashing

---

## 6. Basic Operations

### 6.1 Insert

```
hash(key) → index → store value
```

### 6.2 Search

```
hash(key) → index → compare keys
```

### 6.3 Delete

Requires careful handling to preserve structure.

---

## 7. Code Examples

### 7.1 C++ (unordered_map)

```cpp
#include <iostream>
#include <unordered_map>
using namespace std;

int main() {
    unordered_map<string, int> mp;
    mp["apple"] = 3;
    mp["banana"] = 5;

    cout << mp["apple"];
}
```

---

### 7.2 Python (dict)

```python
mp = {}
mp["apple"] = 3
mp["banana"] = 5

print(mp["apple"])
```

---

### 7.3 TypeScript (Map)

```ts
let mp = new Map<string, number>();
mp.set("apple", 3);
mp.set("banana", 5);

console.log(mp.get("apple"));
```

---

## 8. Asymptotic Notations (Complexity Analysis)

### 8.1 Average Case Time Complexity

| Operation | Complexity |
| --------- | ---------- |
| Insert    | O(1)       |
| Search    | O(1)       |
| Delete    | O(1)       |

---

### 8.2 Worst Case Time Complexity

| Operation | Complexity |
| --------- | ---------- |
| Insert    | O(n)       |
| Search    | O(n)       |
| Delete    | O(n)       |

Worst case happens when many keys collide.

---

### 8.3 Space Complexity

* **O(n)** where `n` is the number of key–value pairs
* Extra space for buckets and collision handling

---

## 9. Load Factor

```
Load Factor = Number of Elements / Number of Buckets
```

* Controls performance
* High load factor → more collisions
* Resizing (rehashing) improves efficiency

---

## 10. Hash Table vs Array

| Hash Table          | Array              |
| ------------------- | ------------------ |
| Key-based access    | Index-based access |
| O(1) average lookup | O(1) direct access |
| Unordered           | Ordered            |
| Extra overhead      | Minimal overhead   |

---

## 11. When Not to Use Hash Tables

Avoid when:

* Order matters
* Range queries are required
* Memory is extremely constrained

Alternatives:

* TreeMap / Balanced BST
* Arrays
* Tries (for strings)

---

## Summary

Hash Tables provide **fast key-based access** and are one of the most important data structures in computer science.

> A well-designed hash table offers O(1) performance for most real-world workloads.
