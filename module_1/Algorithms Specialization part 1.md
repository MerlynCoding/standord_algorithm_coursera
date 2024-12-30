# Algorithms Specialization part 1

This document provides a comprehensive overview of the first module of the "Design and Analysis of Algorithms" course, covering foundational principles, techniques, and examples. It includes integer multiplication, merge sort, and asymptotic analysis concepts like Big-O, Omega, and Theta notation.

---

## About the Course

### Course Topics

1. **Vocabulary for Algorithm Analysis:**
   - Introduction to Big-O notation.
   - Sweet spot for reasoning about algorithms.

2. **Divide-and-Conquer Paradigm:**
   - Applied to problems like integer multiplication, sorting, and matrix multiplication.
   - General analysis methods like the Master Theorem.

3. **Randomization in Algorithms:**
   - Examples include QuickSort, primality testing, and graph partitioning.

4. **Graph Reasoning Primitives:**
   - Connectivity, shortest paths, and social network structures.

5. **Data Structures:**
   - Heaps, balanced binary search trees, and hashing techniques.

### Skills You'll Gain

- Become a better programmer and sharpen analytical skills.
- Learn "thinking algorithmically" and gain literacy in foundational computer science concepts.
- Ace technical interviews and apply algorithms to large-scale problems.

---

## Integer Multiplication

### Traditional Multiplication
- Multiplies each digit of one number with every digit of the other.
- Complexity: \(O(n^2)\).

### Karatsuba Multiplication
- **Method:** Uses divide-and-conquer to reduce the problem size.
- **Steps:**
  1. Compute products of smaller numbers (e.g., \(ac\), \(bd\), and \((a+b)(c+d)\)).
  2. Use Gauss' trick to compute \((a+b)(c+d) - ac - bd\).
- **Complexity:** Approximately \(O(n^{\log_2 3}) \approx O(n^{1.59})\).
- **Significance:** Reduces the number of multiplications compared to the traditional method.

---

## Merge Sort

### Motivation and Example
Merge Sort is a foundational divide-and-conquer algorithm, breaking down problems into smaller subproblems, solving them recursively, and combining the solutions.

#### Steps:
1. Divide the array into two halves.
2. Recursively sort each half.
3. Merge the two sorted halves into one sorted array.

### Pseudocode

1. **Base Case:** If the array has one or zero elements, it is already sorted.
2. **Recursive Case:**
   - Divide the array.
   - Sort each half recursively.
   - Merge the two halves.

### Merge Step
- Traverse two sorted arrays simultaneously.
- Compare elements and append the smaller one to the output array.
- Complexity of merging: \(O(n)\).

### Analysis
- **Divide Step:** Constant work to split the array.
- **Conquer Step:** Recursively solves subproblems of size \(n/2\).
- **Combine Step:** Merges two sorted arrays in linear time.

**Total Time Complexity:** \(O(n \log n)\).

---

## Guiding Principles for Algorithm Analysis

1. **Worst-Case Analysis:**
   - Ensures guarantees for all inputs, even the most challenging ones.

2. **Ignore Constants and Lower-Order Terms:**
   - Focuses on the dominant growth rate.
   - Simplifies comparisons between algorithms.

3. **Focus on Large Inputs:**
   - Efficiency is crucial for large input sizes.

---

## Asymptotic Notation

### Big-O Notation (O)
- **Definition:** \(T(n) \in O(f(n))\) if there exist constants \(c > 0\) and \(n_0\) such that \(T(n) \leq c \cdot f(n)\) for all \(n \geq n_0\).
- Represents an upper bound on growth.
- Focuses on worst-case performance.

#### Example
For \(T(n) = 6n \log n + 6n\):
1. Drop lower-order terms (\(+6n\)).
2. Ignore constant factors (\(6\)).
3. Result: \(O(n \log n)\).

### Omega Notation (Ω)
- **Definition:** \(T(n) \in \Omega(f(n))\) if there exist constants \(c > 0\) and \(n_0\) such that \(T(n) \geq c \cdot f(n)\) for all \(n \geq n_0\).
- Represents a lower bound on growth.
- Focuses on best-case performance.

### Theta Notation (Θ)
- **Definition:** \(T(n) \in \Theta(f(n))\) if \(T(n)\) is both \(O(f(n))\) and \(\Omega(f(n))\).
- Represents a tight bound on growth.

### Little-O Notation (o)
- **Definition:** \(T(n) \in o(f(n))\) if for every constant \(c > 0\), there exists \(n_0\) such that \(T(n) < c \cdot f(n)\) for all \(n \geq n_0\).
- Represents stricter upper bounds than Big-O.

---

## Examples

### Example 1: Linear Search
#### Problem
Search for an integer in an array of size \(n\):
```python
for i in range(n):
    if array[i] == target:
        return True
return False
```
#### Analysis
- In the worst case, all \(n\) elements are checked.
- Running time: \(O(n)\).

### Example 2: Nested Loops
#### Problem
Check if two arrays have a common element:
```python
for i in range(len(A)):
    for j in range(len(B)):
        if A[i] == B[j]:
            return True
return False
```
#### Analysis
- Two nested loops iterate over arrays of size \(n\): \(n^2\).
- Running time: \(O(n^2)\).

---

## Summary of Notations

| Notation | Meaning                        | Example |
| -------- | ------------------------------ | ------- |
| \(O\)     | Upper bound (worst case)       | \(O(n \log n)\) |
| \(\Omega\) | Lower bound (best case)        | \(\Omega(n)\) |
| \(\Theta\) | Tight bound (average case)     | \(\Theta(n \log n)\) |
| \(o\)     | Strictly less than growth rate | \(o(n^2)\) |

---

## Historical Context
- Asymptotic notation was popularized by Donald Knuth in 1976.
- Originates from number theory in the 19th century.

---

## Practical Tips

1. **Abstract Away Details:**
   - Focus on the algorithm, not implementation specifics.

2. **Reverse Engineer Proofs:**
   - Identify constants \(c\) and \(n_0\) by working backwards.

3. **Prioritize Upper Bounds:**
   - Emphasize Big-O for worst-case guarantees.

---

## Conclusion
Asymptotic notation is a critical tool for understanding and comparing algorithm performance. Mastery of Big-O, Omega, and Theta notation enables efficient algorithm design and clear communication in computational problems. With these concepts, you are equipped to analyze and optimize algorithms for scalability and efficiency.

