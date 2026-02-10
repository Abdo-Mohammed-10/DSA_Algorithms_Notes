# 📘 o (Little-o) Notation — Strict Upper Bound

## 1️⃣ What is o (Little-o)?

**o (little-o)** notation describes a **strict upper bound** on an algorithm’s time complexity.

In simple terms:

> The algorithm grows **strictly slower** than `f(n)`.

That means `f(n)` is **too large** to tightly describe the algorithm — the algorithm will eventually be dominated by `f(n)`.

---

## 🧠 Intuition (How to Think About o)

If we say:

```
T(n) ∈ o(f(n))
```

It means:

* The runtime grows **slower than any constant multiple** of `f(n)`
* No matter how small the constant is

So unlike **O** (which allows equality up to constants), **o requires strict separation**.

---

## 📌 Formal Definition

An algorithm is **o(f(n))** if:

```
For every constant c > 0,
there exists n₀ such that
T(n) < c · f(n) for all n ≥ n₀
```

Meaning:

* `T(n)` eventually becomes **smaller than any scaled version** of `f(n)`

---

## 🔍 Key Difference: O vs o

| Notation | Meaning                          |
| -------- | -------------------------------- |
| O(f(n))  | Upper bound (can be tight)       |
| o(f(n))  | Strict upper bound (never tight) |

Examples:

* `n ∈ O(n)` ✅
* `n ∈ o(n)` ❌
* `n ∈ o(n²)` ✅

---

## 💻 Examples

### Example 1️⃣

```
T(n) = n
```

Valid statements:

* `T(n) ∈ o(n²)` ✅
* `T(n) ∈ o(n log n)` ✅
* `T(n) ∈ o(n)` ❌

---

### Example 2️⃣

```
T(n) = n log n
```

Valid statements:

* `T(n) ∈ o(n²)` ✅
* `T(n) ∈ o(n log n)` ❌

---

### Example 3️⃣

```
T(n) = log n
```

Valid statements:

* `T(n) ∈ o(n)` ✅
* `T(n) ∈ o(√n)` ✅

---

## 🚀 Real-World NLP / Systems Example

### Linear vs Quadratic Attention

* Linear Attention: `Θ(n)`
* Self-Attention: `Θ(n²)`

We can say:

```
Linear Attention ∈ o(n²)
```

Meaning:

* Linear attention grows **strictly slower** than quadratic attention
* This is why it scales better for long context windows

---

## 🧠 Relationship Summary

| Notation | Comparison Meaning         |
| -------- | -------------------------- |
| O(f(n))  | At most f(n)               |
| o(f(n))  | Strictly less than f(n)    |
| Ω(f(n))  | At least f(n)              |
| ω(f(n))  | Strictly greater than f(n) |
| Θ(f(n))  | Exactly f(n)               |

---

## 📌 When Is o Used?

Little-o is commonly used in:

* Asymptotic proofs
* Algorithm comparisons
* Showing one algorithm is **asymptotically faster** than another

It is less common in production discussions, but very common in:

* Theory-heavy interviews
* Research papers
* Graduate-level CS

---

✅ **Key Insight:**

If an algorithm is in **o(f(n))**, then:

> It is asymptotically faster than any algorithm in Θ(f(n)).

This is how you formally prove **one algorithm strictly dominates another** in scalability 💪
