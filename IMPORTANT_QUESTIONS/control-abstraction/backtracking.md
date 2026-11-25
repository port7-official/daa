# Control Abstraction of Backtracking

## 1. Definition

- **Backtracking** is an algorithm design technique used to solve problems by trying different possible solutions one by one.
- It builds a solution step by step and checks whether each choice can lead to a valid solution.
- If a choice cannot lead to a valid solution, it goes back to the previous step and tries another choice.
- This process is called **backtracking**.

## 2. Solution Representation

- The desired solution is represented as an n-tuple:

  (x1, x2, x3, ..., xn)

- Each xi is selected from a finite set Si.
- The algorithm explores possible combinations to find the required solution.
- The state space tree is represented implicitly, meaning the entire tree is not stored in memory. Only the currently explored path is tracked.

## 3. Key Helper Functions

Two important functions are used in Backtracking:

### A. Generating Function (T)

- The generating function T(x1, x2, ..., xk) generates all possible candidates for the next position x(k+1).
- It generates the possible choices that can be added to the current partial solution.
- When k = n, the generating function returns an empty set because all positions are already filled.

### B. Bounding Function (Bk)

- The bounding function checks whether the current partial solution has a chance of producing a valid solution.
- If it returns TRUE (1), the algorithm continues exploring that path.
- If it returns FALSE (0), the algorithm rejects that path and goes back to the previous step.
- This avoids exploring unnecessary paths.

## 4. Control Abstraction Algorithm (Backtrack)

```text
Algorithm Backtrack(k)
// x[1:k-1] is a path from the root to a problem state.
// Initial call: Backtrack(1)

{
    for each x[k] in T(x[1], ..., x[k-1]) do
    {
        if (Bk(x[1], x[2], ..., x[k]) != 0) then
        {
            if (x[1], x[2], ..., x[k] is a path to an answer node)
                write(x[1:k]);

            if (k < n) then
                Backtrack(k + 1);
        }
    }
}
```

## 5. Working Principle / Explanation of Algorithm

1. **Initialization:** The algorithm starts by calling Backtrack(1).

2. **Candidate Selection:** At level k, the generating function T generates possible values for x[k].

3. **Bounding Check:** Each candidate is checked using the bounding function Bk to determine whether it can lead to a valid solution.

4. **Solution Check:** If the current path reaches an answer node, the solution is printed using write(x[1:k]).

5. **Recursive Step:** If k is less than n, the algorithm calls Backtrack(k+1) to explore the next level.

6. **Backtracking:** If a path cannot lead to a valid solution, it is rejected. The algorithm returns to the previous level and tries another possible choice.

## 6. Applications of Backtracking

Common applications of Backtracking are:

1. N-Queens Problem
2. Sum of Subsets Problem
3. Graph Colouring
4. Hamiltonian Cycles

## 7. Summary

Backtracking follows these main steps:

1. **Generate:** Generate possible choices.
2. **Check:** Check whether the choice is valid using the bounding function.
3. **Explore:** Continue exploring if the choice is promising.
4. **Backtrack:** Go back and try another choice if the current path cannot produce a solution.
5. **Return:** Output the valid solution when an answer node is reached.

**Important for Exam:**
- Generating Function (T) produces possible candidates.
- Bounding Function (Bk) checks whether a path can lead to a solution.
- Backtracking uses recursive exploration and Depth First Search (DFS).
- It avoids unnecessary exploration by rejecting non-promising paths.
