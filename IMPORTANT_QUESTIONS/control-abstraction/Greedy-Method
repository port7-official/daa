# Control Abstraction of Greedy Method

## 1. Definition

- The **Greedy Method** is an algorithm design technique that solves a problem step by step by selecting the best possible choice at each stage.
- It makes a **locally optimal choice** at every step without changing or going back to previous decisions (no backtracking).
- The aim is to obtain an optimal solution.

## 2. Control Abstraction Algorithm (Greedy)

```text
Algorithm Greedy(a, n)
// a[1:n] contains the n inputs
{
    solution := ∅;

    for i := 1 to n do
    {
        x := select(a);

        if feasible(solution, x) then
            solution := Union(solution, x);
    }

    return solution;
}
```

## 3. Explanation of Components

1. **a[1:n]:** Represents the n input elements given to the algorithm.

2. **solution:** Stores the selected elements that form the final solution. Initially, it is empty (∅).

3. **select(a):** Selects the next element based on the greedy selection rule (e.g., maximum profit, minimum weight or highest profit-to-weight ratio). The selected element is assigned to x and removed from a.

4. **feasible(solution, x):** Checks whether adding the selected element x to the current solution satisfies all the given conditions. It returns TRUE if the selection is valid.

5. **Union(solution, x):** Adds the selected element x to the current solution if it is feasible.

6. **return solution:** Returns the final solution after considering all input elements.

## 4. Greedy Paradigms

The Greedy Method generally works using two paradigms:

### A. Subset Paradigm

- In this approach, elements are selected from the given inputs to construct an optimal subset.
- Examples:
  1. Fractional Knapsack Problem
  2. Job Sequencing with Deadlines
  3. Minimum Cost Spanning Trees (Kruskal's and Prim's Algorithms)

### B. Ordering Paradigm

- In this approach, inputs are arranged in an order based on an optimization criterion.
- The selection depends on the decisions already made.
- Examples:
  1. Single Source Shortest Paths (Dijkstra's Algorithm)
  2. Optimal Storage on Tapes

## 5. Important Points to Remember

- Greedy makes the best choice at each step.
- Each choice is made based on the current situation.
- Previous decisions are not changed.
- Backtracking is not performed.
- The solution is built one element at a time.

## 6. Summary

The Greedy Method follows these steps:

1. **Select:** Choose the best available element.
2. **Check:** Check whether the element is feasible.
3. **Add:** Add the element to the solution if it is feasible.
4. **Repeat:** Continue until all inputs are considered.
5. **Return:** Return the final solution.
