# 📘 ω (Little-Omega) Notation — Strict Lower Bound

## 1️⃣ What is ω (Little-Omega)?

**ω (little-omega)** describes a **strict lower bound** on an algorithm’s time complexity.

In simple terms:

> The algorithm grows **strictly faster** than `f(n)`.

That means `f(n)` is **too small** to describe the algorithm’s growth — it will eventually be dominated.

---

## 🧠 Intuition (How to Think About ω)

If we say:

```
T(n) ∈ ω(f(n))
```

It means:

* The runtime **eventually exceeds any constant multiple** of `f(n)`
* No matter how large the constant is

So unlike Ω (which allows equality up to constants), **ω requires strict separation**.

---

## 📌 Formal Definition

An algorithm is **ω(f(n))** if:

```
For every constant c > 0,
there exists n₀ such that
T(n) > c · f(n) for all n ≥ n₀
```

Meaning:

* `T(n)` grows faster than `f(n)` by **more than any constant factor**

---

## 🔍 Key Difference: Ω vs ω

| Notation | Meaning                          |
| -------- | -------------------------------- |
| Ω(f(n))  | Lower bound (can be tight)       |
| ω(f(n))  | Strict lower bound (never tight) |

Example:

* `n² ∈ Ω(n²)` ✅
* `n² ∈ ω(n²)` ❌ (not strictly faster)
* `n² ∈ ω(n)` ✅

---

## 💻 Examples

### Example 1️⃣

```
T(n) = n²
```

Valid statements:

* `T(n) ∈ ω(n)` ✅
* `T(n) ∈ ω(log n)` ✅
* `T(n) ∈ ω(n²)` ❌

---

### Example 2️⃣

```
T(n) = n log n
```

Valid statements:

* `T(n) ∈ ω(n)` ❌ (grows faster, but not strictly by definition — dominated only by a log factor)
* `T(n) ∈ ω(log n)` ✅

---

## 🚀 Real-World NLP / Systems Example

### Self-Attention vs Linear Attention

* Self-Attention: `Θ(n²)`
* Linear Attention: `Θ(n)`

We can say:

```
Self-Attention ∈ ω(n)
```

Meaning:

* Quadratic attention grows **strictly faster** than any linear-time method
* This is why scaling context length is hard

---

## 🧠 Relationship Summary (All Notations)

| Notation | Question Answered                              |
| -------- | ---------------------------------------------- |
| O(f(n))  | What is the maximum growth?                    |
| Ω(f(n))  | What is the minimum guaranteed growth?         |
| Θ(f(n))  | What is the exact growth?                      |
| ω(f(n))  | What is a function that grows strictly slower? |
| o(f(n))  | What is a function that grows strictly faster? |

⚠️ Common confusion:

* **ω** compares against *slower* functions
* **o** compares against *faster* functions

---

## 📌 When Is ω Used?

ω is mostly used in:

* Theoretical computer science
* Proving **impossibility of optimization**
* Separating complexity classes

It is **rare in production discussions**, but very common in:

* Algorithms research
* Complexity proofs
* Graduate-level CS

---

✅ **Key Insight:**

If an algorithm is proven to be in **ω(f(n))**, then:

> No optimization can ever make it run in `O(f(n))`.

This is how you **prove hard limits**, not just measure performance 💪
