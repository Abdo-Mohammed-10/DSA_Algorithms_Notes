# Heap (Priority Queue)

## 🔷 What is a Heap?

A **Heap** is a special type of **Binary Tree** that satisfies two main properties:

### 1) Shape Property

* It is a **Complete Binary Tree**
* This means:

  * All levels are fully filled
  * The last level is filled from left to right

---

### 2) Heap Property

There are two types:

#### 🔹 Max Heap

* Each node ≥ its children
* The largest element is always at the root

#### 🔹 Min Heap

* Each node ≤ its children
* The smallest element is always at the root

---

## 🔷 Structure Example (Max Heap)

```
        50
       /  \
     30    40
    / \   /
  10  20 35
```

---

## 🔷 Array Representation

Instead of using a tree structure, heaps are usually stored in an array:

```
Index:   0   1   2   3   4   5
Value:  50  30  40  10  20  35
```

### Relationships:

* Parent: `(i - 1) // 2`
* Left Child: `2*i + 1`
* Right Child: `2*i + 2`

---

## 🔷 Core Operations

### 1) Insert

Steps:

1. Add the element at the end of the array
2. Perform **Heapify Up**

Example:

```
Before:
[50, 30, 40, 10, 20, 35]

Insert 45:
[50, 30, 40, 10, 20, 35, 45]

Heapify:
[50, 30, 45, 10, 20, 35, 40]
```

---

### 2) Extract (Remove Highest Priority)

For Max Heap → remove the largest element

Steps:

1. Remove the root
2. Move the last element to the root
3. Perform **Heapify Down**

Example:

```
[50, 30, 45, 10, 20, 35, 40]

Remove 50:
[40, 30, 45, 10, 20, 35]

Heapify:
[45, 30, 40, 10, 20, 35]
```

---

### 3) Peek

* Returns the top element without removing it
* Time Complexity: O(1)

---

## 🔷 Time Complexity

| Operation | Complexity |
| --------- | ---------- |
| Insert    | O(log n)   |
| Extract   | O(log n)   |
| Peek      | O(1)       |

---

## 🔷 What is a Priority Queue?

A **Priority Queue** is an abstract data structure where:

* Each element has a priority
* Elements are removed based on priority (not insertion order)

### Difference:

| Heap           | Priority Queue     |
| -------------- | ------------------ |
| Data structure | Abstract concept   |
| Implementation | Behavior/interface |

---

## 🔷 C++ Example

```cpp
#include <iostream>
#include <queue>
using namespace std;

int main() {
    priority_queue<int> pq;

    pq.push(10);
    pq.push(30);
    pq.push(20);

    cout << pq.top() << endl; // largest element

    pq.pop();

    cout << pq.top() << endl;

    return 0;
}
```

---

## 🔷 Use Cases

### 1) Graph Algorithms

* Shortest path algorithms
* Pathfinding

### 2) Scheduling

* Task scheduling
* CPU scheduling

### 3) Streaming Data

* Top-K elements

### 4) AI / Machine Learning

* Beam Search
* Priority-based sampling

---

## 🔷 Heap vs Sorting

| Heap                       | Sorting                |
| -------------------------- | ---------------------- |
| Partial order              | Full order             |
| Efficient for dynamic data | Better for static data |

---

## 🔷 Summary

* Heap = Tree + Ordering property
* Fast way to access max/min element
* Priority Queue = concept
* Heap = best implementation
