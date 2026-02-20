# 🌳 Tree Data Structure — Complete Deep Explanation

The **Tree** is a non-linear hierarchical data structure used to represent parent–child relationships between elements.

Unlike linear structures such as arrays or linked lists, a tree models hierarchical systems such as file systems, organization charts, expression trees, and syntax trees.

---

## 1️⃣ Formal Definition

A **Tree** is:

> A connected, acyclic graph with a distinguished root node.

This implies:

- Connected → Every node is reachable from the root  
- Acyclic → No cycles  
- Single root → Exactly one starting node  

If a tree has **N nodes**, then it has exactly **N − 1 edges**.

---

## 2️⃣ Basic Terminology

- **Root** → The topmost node.
- **Parent** → A node that has children.
- **Child** → A node derived from another node.
- **Leaf** → A node with no children.
- **Sibling** → Nodes sharing the same parent.
- **Degree** → Number of children of a node.
- **Depth** → Number of edges from root to a node.
- **Height** → Longest path from a node to a leaf.
- **Subtree** → A tree formed by any node and its descendants.

---

## 3️⃣ Types of Trees

### 3.1 Binary Tree
Each node has at most two children.

Example:

        A
       / \
      B   C

---

### 3.2 Full Binary Tree
Each node has either:
- 0 children  
- or 2 children  

---

### 3.3 Complete Binary Tree
- All levels are completely filled  
- Except possibly the last level  
- The last level is filled from left to right  

---

### 3.4 Perfect Binary Tree
All levels are fully filled.

If height = h:

Number of nodes = 2^(h+1) − 1

---

### 3.5 Binary Search Tree (BST)

Ordering property:

Left Subtree < Root < Right Subtree

Time Complexity (Balanced):

- Search → O(log n)  
- Insert → O(log n)  
- Delete → O(log n)  

Worst case (skewed tree):

- O(n)

---

### 3.6 AVL Tree
Self-balancing Binary Search Tree.

Balance condition:

| height(left) − height(right) | ≤ 1

Maintains balance using rotations.

---

### 3.7 Red-Black Tree
Self-balancing BST using coloring rules to maintain approximate balance and logarithmic operations.

---

### 3.8 Heap (Binary Heap)
A complete binary tree used for Priority Queues.

Max Heap:
Parent ≥ children

Min Heap:
Parent ≤ children

---

### 3.9 Trie (Prefix Tree)
Used for:
- Autocomplete
- Dictionary lookup
- NLP token search

Each level represents a character.

---

## 4️⃣ Tree Representation in Memory

### 4.1 Linked Representation

```cpp
struct Node {
    int data;
    Node* left;
    Node* right;
};
```

Flexible and dynamic.

---

### 4.2 Array Representation (Common for Heaps)

For index i:

Left child  = 2i + 1  
Right child = 2i + 2  
Parent      = (i − 1) / 2  

---

## 5️⃣ Tree Traversals

### Depth-First Search (DFS)

**Inorder**  
Left → Root → Right  
(In BST, produces sorted order)

**Preorder**  
Root → Left → Right  
(Used in serialization and copying)

**Postorder**  
Left → Right → Root  
(Used in deletion and bottom-up computation)

---

### Breadth-First Search (BFS)

Level Order Traversal  
Implemented using a Queue.

---

## 6️⃣ Time Complexity Summary

| Operation | Balanced Tree | Worst Case |
|------------|---------------|------------|
| Search | O(log n) | O(n) |
| Insert | O(log n) | O(n) |
| Delete | O(log n) | O(n) |

Worst case occurs when the tree becomes skewed like a linked list.

---

## 7️⃣ Real-World Applications

- Databases → Indexing (B-Trees)
- Operating Systems → File Systems
- AI → Decision Trees
- Compilers → Abstract Syntax Trees (AST)
- Networking → Routing
- NLP → Parse Trees

---

## 8️⃣ Example: BST Insert

```cpp
Node* insert(Node* root, int val) {
    if (!root)
        return new Node{val, NULL, NULL};

    if (val < root->data)
        root->left = insert(root->left, val);
    else
        root->right = insert(root->right, val);

    return root;
}
```

---

## 9️⃣ Common Interview Problems

- Tree Diameter
- Lowest Common Ancestor (LCA)
- Check if Balanced
- Serialize / Deserialize
- Maximum Path Sum
- Level Order Traversal
- Zigzag Traversal

---

## 🧠 Why Trees Are Important

Trees:

- Model hierarchical systems  
- Enable efficient search (when balanced)  
- Support recursive algorithm design  
- Form the foundation of advanced structures such as:
  - Heaps
  - Segment Trees
  - Fenwick Trees
  - B-Trees
  - Tries

---

## 🏁 Final Summary

A Tree is:

- Hierarchical  
- Recursive by nature  
- Efficient when balanced  
- Foundational in algorithms and system design  

Mastering Trees is essential for mastering data structures and algorithms.
