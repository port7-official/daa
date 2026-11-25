# Control Abstraction of Divide and Conquer

## 1. Definition

- **Control Abstraction** is a procedure in which the flow of control is clearly defined, but the actual operations are performed by other functions whose implementations are not specified(Control Abstraction is simply a general plan that tells us what steps to follow to solve a problem, without explaining exactly how each step is performed.).
- In the **Divide and Conquer** technique, a large problem is divided into smaller sub-problems, solved recursively, and their results are combined to obtain the final solution.

## 2. General Control Abstraction Algorithm (DANDC)

```text
Algorithm DANDC(P)
{
    if SMALL(P) then
        return S(P);
    else
    {
        divide P into smaller instances
        p1, p2, ..., pk;

        apply DANDC to each subproblem;

        return COMBINE(
            DANDC(p1),
            DANDC(p2),
            ...,
            DANDC(pk)
        );
    }
}
```

## 3. Explanation of Components

1. **P:** Represents the original problem to be solved.

2. **SMALL(P):** A Boolean function that checks whether the problem is small enough to be solved directly without further division.

3. **S(P):** Solves the problem directly when it is small enough. This is called the base case.

4. **Divide Step:** Divides the original problem P into k smaller sub-problems (p1, p2, ..., pk).

5. **Recursive Step:** Each sub-problem is solved by applying the DANDC algorithm recursively.

6. **COMBINE:** Combines the solutions of all sub-problems to obtain the final solution to the original problem.

## 4. Computing Time and Recurrence Relation

If a problem of size n is divided into a sub-problems, each of size n/b, the computing time T(n) is represented by the following recurrence relation:

\[
T(n)=
\begin{cases}
g(n), & \text{if } n \text{ is small}\\
aT(n/b)+f(n), & \text{if } n>1
\end{cases}
\]

**Where:**

- **T(n):** Total computing time required for a problem of size n.
- **g(n):** Time required to solve a small problem directly.
- **a:** Number of sub-problems generated.
- **n/b:** Size of each sub-problem.
- **f(n):** Time required for dividing the problem and combining the solutions.

## 5. Applications of Divide and Conquer

Common algorithms that use the Divide and Conquer technique are:

1. Binary Search
2. Merge Sort
3. Quick Sort
4. Strassen's Matrix Multiplication

## 6. Summary

The Divide and Conquer technique follows three main steps:

1. **Divide:** Break the original problem into smaller sub-problems.
2. **Conquer:** Solve the sub-problems recursively.
3. **Combine:** Combine the solutions to get the final answer.

# Best Case and Worst Case of Divide and Conquer

## 1. Best Case

- The **Best Case** occurs when the problem is divided into smaller sub-problems in the most efficient way.
- The sub-problems are balanced, and the total time required to solve and combine them is minimum.
- It requires the minimum amount of computing time for a given input size.

## 2. Worst Case

- The **Worst Case** occurs when the problem is divided in a less efficient way.
- The sub-problems may become unbalanced, or additional work may be required to solve and combine them.
- It requires the maximum amount of computing time for a given input size.

## 3. Examples

The time complexity depends on the particular Divide and Conquer algorithm.

| Algorithm | Best Case | Worst Case |
|---|---|---|
| Binary Search | O(1) | O(log n) |
| Merge Sort | O(n log n) | O(n log n) |
| Quick Sort | O(n log n) | O(n²) |

## 4. Conclusion

The best-case and worst-case time complexities of Divide and Conquer depend on how the problem is divided into sub-problems and how much time is required to solve and combine them.

**Important for Exam:** Remember the three main operations: Divide, Conquer and Combine, along with the DANDC algorithm and recurrence relation.
