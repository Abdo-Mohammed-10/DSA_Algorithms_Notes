# 📘 Ω (Omega) Notation — Lower Bound Complexity

## 1️⃣ What is Ω (Omega)?

**Ω (Omega) notation** describes the **lower bound** of an algorithm’s time complexity.

In simple terms:

> It tells you the **best-case guaranteed performance** — the minimum time an algorithm will take **no matter what**.

If Big-O answers:

> ❓ *What is the maximum time this algorithm might take?*

Then Ω answers:

> ❓ *What is the minimum time this algorithm must take at least?*

---

## ❓ Why Do We Care About Ω?

Ω helps us understand:

* The **best possible scenario**
* The **theoretical limit** of optimization
* Whether further optimization is **even possible**

If an algorithm is already Ω(n), you **cannot** make it faster than linear in the general case.

---

## 📌 Core Idea (Formal Definition)

An algorithm is **Ω(f(n))** if:

```
There exist constants c > 0 and n₀ such that
T(n) ≥ c · f(n) for all n ≥ n₀
```

Meaning:

* Runtime will **never go below** `f(n)` after a certain input size

---

## 💻 Code Examples

### 1️⃣ Ω(1) — Constant Lower Bound

```python
def get_first_element(arr):
    return arr[0]
```

* Best case = Worst case = Ω(1)
* You **must** access at least one element

---

### 2️⃣ Ω(n) — Linear Lower Bound

```python
def find_max(arr):
    max_val = arr[0]
    for x in arr:
        if x > max_val:
            max_val = x
    return max_val
```

* You must check **every element at least once**
* Even the best case is Ω(n)

---

### 3️⃣ Searching Example (Classic Interview Case)

```python
def linear_search(arr, target):
    for i in arr:
        if i == target:
            return True
    return False
```

| Case       | Complexity                   |
| ---------- | ---------------------------- |
| Best Case  | Ω(1) (target at first index) |
| Worst Case | O(n)                         |

---

## 🚀 Real-World NLP Example

### Tokenization

Given a text with `n` characters:

* You **must** read every character at least once

➡️ Tokenization has a **lower bound of Ω(n)**

No tokenizer can do better than linear time.

---

## 🧠 Relationship Between O, Ω, and Θ

| Notation    | Meaning                            |
| ----------- | ---------------------------------- |
| **O(f(n))** | Upper bound (worst case)           |
| **Ω(f(n))** | Lower bound (best guaranteed case) |
| **Θ(f(n))** | Tight bound (both upper & lower)   |

If:

```
O(n) and Ω(n)
```

Then:

```
Θ(n)
```

---

## 📊 Quick Comparison Example

| Algorithm     | Ω    | O        |
| ------------- | ---- | -------- |
| Array Access  | Ω(1) | O(1)     |
| Linear Search | Ω(1) | O(n)     |
| Find Max      | Ω(n) | O(n)     |
| Binary Search | Ω(1) | O(log n) |

---

✅ **Key Insight:**
Ω tells you the **best you can ever hope for**.

If a problem has a lower bound of Ω(n), any algorithm claiming to solve it faster is either:

* Making assumptions
* Using extra information
* Or simply wrong

This is how you **think like an algorithm designer**, not just a coder 💪
