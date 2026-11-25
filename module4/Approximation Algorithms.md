
# Approximation Algorithms

## 1. Introduction and Definition

**Approximation Algorithms** are polynomial-time algorithms used to find near-optimal feasible solutions for computationally difficult problems, especially NP-Hard and NP-Complete optimization problems.

Finding the exact optimal solution for these problems may require a very long time. Therefore, approximation algorithms find a good solution in less time, even if it is not always the best possible solution.

**In simple words:**
- Some problems are very difficult to solve exactly.
- Finding the perfect solution may take exponential or factorial time.
- Approximation algorithms find a solution that is close to the optimal solution.
- They run in polynomial time.

**Example:** In the Bin Packing Problem, instead of spending a long time finding the minimum possible number of bins, an approximation algorithm finds a near-optimal arrangement quickly.

---

## 2. Key Properties of Approximation Algorithms

### 1. Polynomial Time Execution

- Approximation algorithms run in polynomial time.
- They are faster than exact algorithms for many computationally difficult optimization problems.
- Exact algorithms for NP-Hard problems may require exponential or factorial time, such as O(2^n) or O(n!).
- Approximation algorithms provide solutions more efficiently.

**Easy Understanding:** They find a good solution quickly instead of spending too much time finding the perfect solution.

### 2. Guaranteed Solution Quality

- Approximation algorithms provide a feasible solution.
- Their solution quality is guaranteed to be within a specified bound of the optimal solution.
- The result is compared with the actual optimal solution to measure its quality.

**Easy Understanding:** The algorithm may not give the perfect answer, but it guarantees how far its answer can be from the optimal answer.

---

## 3. Approximation Ratio (Performance Ratio)

The **Approximation Ratio** measures how close the solution produced by an approximation algorithm is to the optimal solution.

It compares the result obtained by the approximation algorithm with the optimal result.

Where:
- C = Cost or value of the solution produced by the approximation algorithm.
- C* = Cost or value of the optimal solution.

### 1. For Minimization Problems

In minimization problems, the objective is to find the smallest possible value.

Since the approximation algorithm may produce a solution with a higher cost than the optimal solution:

C* ≤ C

**Formula:**

Approximation Ratio = C / C*

**Example:**

- Optimal solution (C*) = 10
- Approximation algorithm solution (C) = 12

Approximation Ratio = 12 / 10 = 1.2

This means the approximation algorithm produces a solution that is 1.2 times the optimal cost.

### 2. For Maximization Problems

In maximization problems, the objective is to find the largest possible value.

Since the approximation algorithm may produce a value smaller than the optimal solution:

C ≤ C*

**Formula:**

Approximation Ratio = C* / C

**Example:**

- Optimal solution (C*) = 100
- Approximation algorithm solution (C) = 80

Approximation Ratio = 100 / 80 = 1.25

This means the approximation algorithm achieves a value that is below the optimal value.

---

## 4. Important Rules of Approximation Ratio

1. **Approximation Ratio is always greater than or equal to 1:**
   - The ratio is never less than 1.
   - A ratio closer to 1 indicates a better approximation.

2. **1-Approximation Algorithm:**
   - An algorithm with an approximation ratio of 1 produces the exact optimal solution.

3. **K-Approximation Algorithm:**
   - An algorithm with a guaranteed approximation ratio of at most K is called a K-approximation algorithm.
   - It guarantees that the solution is within a factor of K of the optimal solution.

4. **Time and Solution Quality:**
   - In general, obtaining a solution closer to the optimal solution may require more computation time.
   - There can be a trade-off between execution time and solution quality.

---

## 5. Applications and Examples of Approximation Algorithms

Approximation algorithms are commonly used in NP-Hard optimization problems.

### 1. Bin Packing Problem
- The objective is to pack all items into the minimum number of bins without exceeding the capacity of each bin.
- Algorithms such as First Fit (FF), Next Fit (NF), Best Fit (BF), and First Fit Decreasing (FFD) are used to find near-optimal solutions.

### 2. Vertex Cover Problem
- The objective is to select a minimum number of vertices such that every edge has at least one selected endpoint.
- Approximation algorithms are used to find a near-optimal vertex cover.

### 3. Travelling Salesman Problem (TSP)
- The objective is to find the shortest possible route that visits every city exactly once and returns to the starting city.
- Approximation algorithms can find near-optimal routes efficiently under suitable conditions.

### 4. 0/1 Knapsack Problem
- The objective is to select items with maximum total value without exceeding the given weight capacity.
- Approximation algorithms are used to find solutions close to the maximum possible value.

---

## 6. Conclusion

Approximation algorithms are polynomial-time algorithms used to solve computationally difficult optimization problems by finding near-optimal feasible solutions.

They provide guaranteed solution quality and are useful for NP-Hard problems where finding the exact optimal solution is computationally expensive.

The quality of an approximation algorithm is measured using the approximation ratio.

**Important Points for Revision:**
- Definition: Finds near-optimal solutions in polynomial time.
- Main properties: Polynomial-time execution and guaranteed solution quality.
- Minimization ratio: C / C*
- Maximization ratio: C* / C
- Ratio is always ≥ 1.
- Ratio of 1 means an optimal solution.
- Examples: Bin Packing, Vertex Cover, TSP and 0/1 Knapsack.
