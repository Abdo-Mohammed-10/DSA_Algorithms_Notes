# 📘 Θ (Theta) Notation — Tight Bound Complexity

## 1️⃣ What is Θ (Theta)?

**Θ (Theta) notation** describes the **exact (tight) bound** of an algorithm’s time complexity.

In simple terms:

> Θ tells you that an algorithm’s runtime grows **at the same rate** in both the best and worst cases (up to constants).

If:

* **Big-O** = upper bound (worst case)
* **Omega (Ω)** = lower bound (best guaranteed case)

Then:

> **Theta (Θ)** = upper **and** lower bound together.

---

## ❓ Why Is Θ Important?

Θ answers the most practical question:

> *How does this algorithm really scale?*

It gives:

* Precise growth rate
* Predictable performance
* Clear comparison between algorithms

If an algorithm is Θ(n), you **know exactly** how it behaves asymptotically.

---

## 📌 Formal Definition

An algorithm is **Θ(f(n))** if:

```
There exist constants c₁, c₂ > 0 and n₀ such that
c₁ · f(n) ≤ T(n) ≤ c₂ · f(n) for all n ≥ n₀
```

Meaning:

* Runtime is **sandwiched** between two constant multiples of `f(n)`
* Growth rate is tightly bounded

---

## 💻 Code Examples

### 1️⃣ Θ(1) — Constant Time

```python
def get_last_element(arr):
    return arr[-1]
```

* Best case = Worst case = Θ(1)

---

### 2️⃣ Θ(n) — Linear Time

```python
def sum_array(arr):
    total = 0
    for x in arr:
        total += x
    return total
```

* Must traverse all elements
* Best case = Worst case = Θ(n)

---

### 3️⃣ Θ(n log n) — Divide & Conquer

```python
def merge_sort(arr):
    if len(arr) <= 1:
        return arr
    mid = len(arr) // 2
    left = merge_sort(arr[:mid])
    right = merge_sort(arr[mid:])
    return merge(left, right)
```

* Same asymptotic behavior regardless of input
* Θ(n log n)

---

## 🚀 Real-World NLP Example

### Vocabulary Building

When building a vocabulary from a corpus of `n` tokens:

* You must read every token
* Hash-table insert/lookups are Θ(1) on average

➡️ Total complexity = **Θ(n)**

This is both the best and worst asymptotic case.

---

## 🧠 Relationship Between O, Ω, and Θ

| Scenario            | Result           |
| ------------------- | ---------------- |
| O(f(n)) and Ω(f(n)) | Θ(f(n))          |
| Only O known        | Upper bound only |
| Only Ω known        | Lower bound only |

Example:

```
O(n) and Ω(n)  ⇒  Θ(n)
```

---

## 📊 Comparison Table

| Algorithm     | O          | Ω          | Θ          |
| ------------- | ---------- | ---------- | ---------- |
| Array Access  | O(1)       | Ω(1)       | Θ(1)       |
| Find Max      | O(n)       | Ω(n)       | Θ(n)       |
| Linear Search | O(n)       | Ω(1)       | Θ(?)       |
| Merge Sort    | O(n log n) | Ω(n log n) | Θ(n log n) |

⚠️ Note:
Linear Search has **no Θ bound** because best and worst cases differ.

---

✅ **Key Insight:**
Θ is the **most informative notation**.

When you can prove Θ(f(n)), you fully understand the algorithm’s scalability.

This is the level expected when:

* Designing systems
* Writing production algorithms
* Answering senior-level interviews 💪
