# Dynamic Programming – Detailed Explanation

## 1. What is Dynamic Programming?

**Dynamic Programming (DP)** is an algorithmic technique used to solve complex problems by **breaking them down into simpler overlapping subproblems** and **storing their results** to avoid redundant computations.

Core idea:

> Solve each subproblem **once**, store its result, and reuse it when needed.

---

## 2. Why Do We Use Dynamic Programming?

Dynamic Programming is used when:

* The problem can be divided into overlapping subproblems
* The problem has optimal substructure
* A naive recursive solution is too slow

Benefits:

* Significant performance improvement
* Converts exponential-time solutions into polynomial-time
* Essential for optimization problems

---

## 3. Key Properties of Dynamic Programming

### 3.1 Overlapping Subproblems

The same subproblems are solved multiple times in naive recursion.

Example:

```
Fibonacci:
F(n) = F(n-1) + F(n-2)
```

---

### 3.2 Optimal Substructure

An optimal solution to a problem can be constructed from optimal solutions of its subproblems.

Example:

* Shortest path
* Knapsack problem

---

## 4. Approaches to Dynamic Programming

### 4.1 Top-Down (Memoization)

* Uses recursion
* Stores results in a cache (memo table)

```
Recursive + Memory
```

### 4.2 Bottom-Up (Tabulation)

* Uses iteration
* Builds solutions from smallest subproblems

```
Iterative + Table
```

---

## 5. Classic Dynamic Programming Problems

| Problem                        | Category           |
| ------------------------------ | ------------------ |
| Fibonacci                      | 1D DP              |
| Climbing Stairs                | 1D DP              |
| Coin Change                    | Unbounded Knapsack |
| 0/1 Knapsack                   | Knapsack           |
| Longest Common Subsequence     | String DP          |
| Longest Increasing Subsequence | Sequence DP        |
| Matrix Chain Multiplication    | Interval DP        |

---

## 6. DP State Design

A DP solution is defined by:

```
DP State + Transition + Base Case
```

### Example (Fibonacci)

```
dp[i] = dp[i-1] + dp[i-2]
```

---

## 7. Code Examples

### 7.1 Fibonacci – Top-Down (Memoization)

```python
memo = {}

def fib(n):
    if n <= 1:
        return n
    if n in memo:
        return memo[n]
    memo[n] = fib(n-1) + fib(n-2)
    return memo[n]
```

---

### 7.2 Fibonacci – Bottom-Up (Tabulation)

```python
def fib(n):
    if n <= 1:
        return n
    dp = [0] * (n + 1)
    dp[1] = 1
    for i in range(2, n + 1):
        dp[i] = dp[i-1] + dp[i-2]
    return dp[n]
```

---

### 7.3 Climbing Stairs (TypeScript)

```ts
function climbStairs(n: number): number {
    if (n <= 2) return n;
    let dp: number[] = new Array(n + 1);
    dp[1] = 1;
    dp[2] = 2;
    for (let i = 3; i <= n; i++) {
        dp[i] = dp[i - 1] + dp[i - 2];
    }
    return dp[n];
}
```

---

## 8. Asymptotic Notations (Complexity Analysis)

### 8.1 Time Complexity

| Approach            | Time Complexity |
| ------------------- | --------------- |
| Naive Recursion     | O(2^n)          |
| Dynamic Programming | O(n)            |

---

### 8.2 Space Complexity

| Approach        | Space Complexity |
| --------------- | ---------------- |
| Memoization     | O(n)             |
| Tabulation      | O(n)             |
| Space Optimized | O(1)             |

---

## 9. Space Optimization in DP

Many DP problems only depend on **previous states**.

Example:

```
dp[i] depends only on dp[i-1] and dp[i-2]
```

Optimization:

```
Use variables instead of array
```

---

## 10. Common DP Patterns

* 1D DP (Fibonacci, Stairs)
* 2D DP (Grid problems, LCS)
* Knapsack Pattern
* Interval DP
* Bitmask DP

---

## 11. When NOT to Use Dynamic Programming

Avoid DP when:

* Subproblems do not overlap
* Greedy solution exists
* Problem size is too large for memory

---

## Summary

Dynamic Programming is a **systematic optimization technique** that trades memory for speed and is essential for solving complex algorithmic problems efficiently.

> If recursion is slow, Dynamic Programming is usually the answer.
