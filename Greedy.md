# Greedy Algorithms – Detailed Explanation

## 1. What is a Greedy Algorithm?

A **Greedy Algorithm** is an algorithmic paradigm that builds a solution **step by step**, always choosing the **locally optimal choice** at each step, with the hope that these local choices lead to a **globally optimal solution**.

Core idea:

> Make the best choice **right now**, without reconsidering past decisions.

---

## 2. Why Do We Use Greedy Algorithms?

Greedy algorithms are used because they:

* Are simple to design and implement
* Are very fast
* Often produce optimal solutions for specific problem classes

They are especially useful when:

* The problem size is large
* A dynamic programming solution is too slow or memory-heavy

---

## 3. Key Properties of Greedy Algorithms

For a greedy algorithm to be correct, the problem must satisfy **both** properties:

### 3.1 Greedy Choice Property

A globally optimal solution can be reached by making a locally optimal choice.

### 3.2 Optimal Substructure

An optimal solution contains optimal solutions to its subproblems.

> If either property is missing, a greedy approach may fail.

---

## 4. General Structure of a Greedy Algorithm

1. Sort or prioritize the input (optional)
2. Iterate through choices
3. Pick the best local option
4. Never change the decision

---

## 5. Classic Greedy Problems

| Problem                        | Greedy Strategy                         |
| ------------------------------ | --------------------------------------- |
| Activity Selection             | Pick activity with earliest finish time |
| Fractional Knapsack            | Pick item with highest value/weight     |
| Huffman Coding                 | Merge lowest-frequency nodes            |
| Minimum Spanning Tree          | Pick smallest edge (Kruskal / Prim)     |
| Coin Change (specific systems) | Pick largest denomination               |

---

## 6. Code Examples

### 6.1 Activity Selection Problem (Python)

```python
def activity_selection(activities):
    activities.sort(key=lambda x: x[1])  # sort by finish time
    count = 1
    last_end = activities[0][1]

    for i in range(1, len(activities)):
        if activities[i][0] >= last_end:
            count += 1
            last_end = activities[i][1]

    return count
```

---

### 6.2 Fractional Knapsack (Python)

```python
def fractional_knapsack(items, capacity):
    items.sort(key=lambda x: x[0] / x[1], reverse=True)
    total_value = 0

    for value, weight in items:
        if capacity == 0:
            break
        take = min(weight, capacity)
        total_value += take * (value / weight)
        capacity -= take

    return total_value
```

---

### 6.3 Coin Change (Greedy – TypeScript)

```ts
function coinChange(coins: number[], amount: number): number {
    coins.sort((a, b) => b - a);
    let count = 0;

    for (let coin of coins) {
        while (amount >= coin) {
            amount -= coin;
            count++;
        }
    }

    return amount === 0 ? count : -1;
}
```

---

## 7. Asymptotic Notations (Complexity Analysis)

### 7.1 Time Complexity

Greedy algorithms typically involve:

* Sorting: **O(n log n)**
* Single pass selection: **O(n)**

Overall complexity:

```
O(n log n)
```

---

### 7.2 Space Complexity

* Usually **O(1)** or **O(n)** depending on implementation
* No DP tables or recursion stacks

---

## 8. Greedy vs Dynamic Programming

| Greedy                  | Dynamic Programming                 |
| ----------------------- | ----------------------------------- |
| Local optimal decisions | Global optimization                 |
| Faster                  | Slower                              |
| Simple implementation   | Complex state design                |
| Not always correct      | Always correct if designed properly |

---

## 9. When Greedy Fails

Greedy algorithms fail when:

* Local optimum ≠ global optimum
* Decisions affect future choices

Classic counterexample:

* 0/1 Knapsack
* Coin Change with arbitrary denominations

---

## 10. How to Identify a Greedy Problem

Ask these questions:

* Can I make a choice and never regret it?
* Does sorting by a key help?
* Is there a known proof of greedy correctness?

---

## Summary

Greedy algorithms trade **optimality guarantees** for **speed and simplicity**, and they are powerful when applied to the right problems.

> Greedy works not because it tries everything, but because the problem structure allows it to be confident early.
