# Sorting Algorithms – Detailed Explanation

## 1. What is Sorting?

**Sorting** is the process of arranging elements in a specific order, most commonly:

* Ascending order
* Descending order

Example:

```
Unsorted: [5, 2, 9, 1]
Sorted:   [1, 2, 5, 9]
```

Sorting is a core operation in computer science because it enables efficient searching, optimization, and data analysis.

---

## 2. Why Do We Need Sorting?

Sorting is used to:

* Speed up searching (Binary Search)
* Organize data for readability
* Detect duplicates
* Optimize other algorithms
* Prepare data for aggregation and analytics

---

## 3. Classification of Sorting Algorithms

Sorting algorithms are commonly classified by:

* Time complexity
* Space complexity
* Stability
* In-place vs Out-of-place

---

## 4. Common Sorting Algorithms

### 4.1 Bubble Sort

**Idea:** Repeatedly swap adjacent elements if they are in the wrong order.

```python
def bubble_sort(arr):
    n = len(arr)
    for i in range(n):
        for j in range(0, n - i - 1):
            if arr[j] > arr[j + 1]:
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
```

Time Complexity:

* Best: O(n)
* Average: O(n²)
* Worst: O(n²)

---

### 4.2 Selection Sort

**Idea:** Select the minimum element and place it at the beginning.

```python
def selection_sort(arr):
    n = len(arr)
    for i in range(n):
        min_idx = i
        for j in range(i + 1, n):
            if arr[j] < arr[min_idx]:
                min_idx = j
        arr[i], arr[min_idx] = arr[min_idx], arr[i]
```

Time Complexity:

* Best/Average/Worst: O(n²)

---

### 4.3 Insertion Sort

**Idea:** Insert each element into its correct position.

```python
def insertion_sort(arr):
    for i in range(1, len(arr)):
        key = arr[i]
        j = i - 1
        while j >= 0 and arr[j] > key:
            arr[j + 1] = arr[j]
            j -= 1
        arr[j + 1] = key
```

Time Complexity:

* Best: O(n)
* Average/Worst: O(n²)

---

### 4.4 Merge Sort

**Idea:** Divide the array into halves, sort them, and merge.

```python
def merge_sort(arr):
    if len(arr) <= 1:
        return arr
    mid = len(arr) // 2
    left = merge_sort(arr[:mid])
    right = merge_sort(arr[mid:])
    return merge(left, right)
```

Time Complexity:

* Best/Average/Worst: O(n log n)

Space Complexity:

* O(n)

---

### 4.5 Quick Sort

**Idea:** Pick a pivot and partition the array.

```python
def quick_sort(arr):
    if len(arr) <= 1:
        return arr
    pivot = arr[len(arr) // 2]
    left = [x for x in arr if x < pivot]
    middle = [x for x in arr if x == pivot]
    right = [x for x in arr if x > pivot]
    return left + middle + right
```

Time Complexity:

* Best/Average: O(n log n)
* Worst: O(n²)

---

### 4.6 Heap Sort

**Idea:** Use a heap data structure.

Time Complexity:

* Best/Average/Worst: O(n log n)

Space Complexity:

* O(1)

---

## 5. Stability in Sorting

A sorting algorithm is **stable** if it preserves the relative order of equal elements.

Stable:

* Bubble Sort
* Insertion Sort
* Merge Sort

Unstable:

* Quick Sort
* Heap Sort

---

## 6. In-Place vs Out-of-Place

| Type         | Description                |
| ------------ | -------------------------- |
| In-Place     | Uses constant extra space  |
| Out-of-Place | Requires additional memory |

---

## 7. Comparison Summary

| Algorithm | Best       | Avg        | Worst      | Space    |
| --------- | ---------- | ---------- | ---------- | -------- |
| Bubble    | O(n)       | O(n²)      | O(n²)      | O(1)     |
| Selection | O(n²)      | O(n²)      | O(n²)      | O(1)     |
| Insertion | O(n)       | O(n²)      | O(n²)      | O(1)     |
| Merge     | O(n log n) | O(n log n) | O(n log n) | O(n)     |
| Quick     | O(n log n) | O(n log n) | O(n²)      | O(log n) |
| Heap      | O(n log n) | O(n log n) | O(n log n) | O(1)     |

---

## 8. Asymptotic Notations

Sorting performance is analyzed using **Big-O notation**:

```
O(1) < O(log n) < O(n) < O(n log n) < O(n²)
```

---

## 9. When to Use Which Sorting Algorithm

* Small datasets → Insertion Sort
* Large datasets → Merge Sort / Quick Sort
* Memory constrained → Heap Sort
* Stable sorting required → Merge Sort

---

## Summary

Sorting algorithms are fundamental tools for organizing data and improving efficiency across systems.

> Efficient sorting is a cornerstone of performant software systems.
