# Matrix in Data Structures

## What is a Matrix?

A **matrix** is a two-dimensional data structure consisting of **rows** and **columns**.
It is essentially a **2D array** used to store elements in a grid-like format.

Example matrix:

```
1  2  3
4  5  6
7  8  9
```

Here:

* Number of rows = **3**
* Number of columns = **3**

Accessing an element:

```
matrix[row][column]
```

Example:

```
matrix[1][2] = 6
```

---

# Matrix Representation in Programming

Example in C++:

```cpp
int matrix[3][3] = {
    {1,2,3},
    {4,5,6},
    {7,8,9}
};
```

Access element:

```cpp
cout << matrix[1][2];
```

Output:

```
6
```

---

# Matrix Traversal Algorithm

Traversal means visiting **every element in the matrix**.

Algorithm:

```cpp
for(int i = 0; i < rows; i++){
    for(int j = 0; j < cols; j++){
        cout << matrix[i][j] << " ";
    }
    cout << endl;
}
```

Time Complexity:

```
O(n × m)
```

Where:

* n = number of rows
* m = number of columns

---

# Matrix Addition

Two matrices can be added if they have the **same dimensions**.

Formula:

```
C[i][j] = A[i][j] + B[i][j]
```

Example:

```
A        B        Result
1 2      5 6      6 8
3 4   +  7 8  =  10 12
```

Algorithm:

```cpp
for(int i=0;i<n;i++){
    for(int j=0;j<m;j++){
        C[i][j] = A[i][j] + B[i][j];
    }
}
```

Time Complexity:

```
O(n × m)
```

---

# Matrix Multiplication

Matrix multiplication is possible if:

```
columns of A = rows of B
```

Formula:

```
C[i][j] = Σ (A[i][k] * B[k][j])
```

Algorithm:

```cpp
for(int i=0;i<n;i++){
    for(int j=0;j<p;j++){
        C[i][j] = 0;
        for(int k=0;k<m;k++){
            C[i][j] += A[i][k] * B[k][j];
        }
    }
}
```

Time Complexity:

```
O(n³)
```

---

# Matrix Transpose

Transpose means **converting rows into columns**.

Example:

Original matrix

```
1 2
3 4
```

Transpose

```
1 3
2 4
```

Algorithm:

```cpp
for(int i=0;i<n;i++){
    for(int j=0;j<m;j++){
        transpose[j][i] = matrix[i][j];
    }
}
```

---

# Types of Matrices

## 1. Square Matrix

A matrix where:

```
rows = columns
```

Example:

```
1 2 3
4 5 6
7 8 9
```

---

## 2. Identity Matrix

Diagonal elements = **1**

Other elements = **0**

Example:

```
1 0 0
0 1 0
0 0 1
```

---

## 3. Sparse Matrix

A matrix where **most values are zero**.

Example:

```
0 0 0
5 0 0
0 0 7
```

Sparse matrices are stored in **special formats** to save memory.

---

# Applications of Matrix

Matrices are widely used in computer science:

### 1. Machine Learning

Neural networks rely heavily on **matrix multiplication**.

### 2. Computer Graphics

Images are represented as matrices of pixels.

### 3. Graph Representation

Graphs can be represented using an **Adjacency Matrix**.

Example:

```
  A B C
A 0 1 0
B 1 0 1
C 0 1 0
```

---

# Time Complexity Summary

| Operation      | Complexity |
| -------------- | ---------- |
| Traversal      | O(n × m)   |
| Addition       | O(n × m)   |
| Transpose      | O(n × m)   |
| Multiplication | O(n³)      |

---

# Conclusion

A **Matrix** is one of the most important data structures used in:

* algorithms
* machine learning
* graphics
* graph theory

Understanding matrix operations like **traversal, transpose, addition, and multiplication** is essential for solving many algorithmic problems.
