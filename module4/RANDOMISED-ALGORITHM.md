
# Randomized Algorithms

## 1. Introduction

- **Definition:** Randomized algorithms are algorithms that use random choices during their execution to make decisions.
- They use randomness in operations such as selecting a pivot element or choosing a candidate.
- Randomness can improve the efficiency and simplicity of an algorithm.
- The execution or correctness of the algorithm may depend on the random choices made.

**Example:** Randomized Quick Sort randomly selects a pivot element to divide an array into smaller subarrays.

## 2. Types of Randomized Algorithms

Randomized algorithms are mainly classified into two types based on their correctness and running time:

### A. Las Vegas Algorithm

- A Las Vegas algorithm **always produces the correct output**.
- However, its running time may vary depending on the random choices made.
- Its main goal is to minimize the expected execution time.

**Example: Randomized Quick Sort**
- It selects a pivot randomly.
- Regardless of the pivot selected, it always produces a correctly sorted array.
- However, the time taken to sort the array may vary.

### B. Monte Carlo Algorithm

- A Monte Carlo algorithm has a fixed or bounded running time.
- However, it may produce an incorrect result with a small probability.
- The probability of error can usually be reduced by repeating the algorithm.
- Its main goal is to achieve faster execution while keeping the probability of error within acceptable limits.

**Example: Rabin-Miller Primality Test**
- It checks whether a number is prime or composite.
- It runs within a bounded time but may give an incorrect result with a very small, controllable probability.

### Difference Between Las Vegas and Monte Carlo Algorithms

| Feature | Las Vegas Algorithm | Monte Carlo Algorithm |
|---|---|---|
| Correctness | Always produces the correct output. | May produce an incorrect output with a small probability. |
| Running Time | Varies depending on random choices. | Has a fixed or bounded running time. |
| Main Goal | Minimize expected execution time. | Minimize execution time while controlling the error probability. |
| Example | Randomized Quick Sort | Rabin-Miller Primality Test |

**Remember:**
- Las Vegas = Always correct, running time varies.
- Monte Carlo = Running time is bounded, correctness is probabilistic.

---

## 3. Randomized Quick Sort (RquickSort)

### A. Introduction and Motivation

- Randomized Quick Sort is a randomized version of the standard Quick Sort algorithm.
- It selects a pivot element randomly from the given subarray.
- The selected pivot is used to partition the array into two parts:
  1. Elements smaller than the pivot.
  2. Elements greater than the pivot.
- Both subarrays are then sorted recursively.

**Why is Randomized Quick Sort needed?**

- In normal Quick Sort, choosing the first or last element as the pivot can lead to poor performance.
- For example, if the input array is already sorted, choosing the first or last element repeatedly may produce highly unbalanced partitions.
- This results in a worst-case time complexity of **O(n²)**.
- Randomized Quick Sort reduces the chance of repeatedly selecting a bad pivot by choosing the pivot randomly.

### B. Algorithm: RquickSort

```text
Algorithm RquickSort(a, p, q)
{
    if (p < q) then
    {
        // Select a random element and swap it with the first element
        if ((q - p) > 5) then
            Interchange(a, Random() mod (q - p + 1) + p, p);

        // Partition the array using the selected pivot
        m := Partition(a, p, q + 1);

        // Recursively sort the left subarray
        RquickSort(a, p, m - 1);

        // Recursively sort the right subarray
        RquickSort(a, m + 1, q);
    }
}
```

### C. Working of Randomized Quick Sort

1. Check whether the subarray contains more than one element using `p < q`.
2. Select a random element from the subarray `a[p...q]`.
3. Interchange the selected random element with the first element.
4. Apply the Partition operation using the selected pivot.
5. Partitioning places the pivot in its correct sorted position.
6. Recursively apply Randomized Quick Sort to the left subarray.
7. Recursively apply Randomized Quick Sort to the right subarray.
8. Continue until all elements are sorted.

### D. Analysis and Performance

**1. Avoiding Worst-Case Inputs**
- Random pivot selection reduces the possibility of repeatedly getting highly unbalanced partitions.
- Therefore, a particular input ordering is less likely to cause the worst-case performance.

**2. Expected Time Complexity**
- The expected running time of Randomized Quick Sort is **O(n log n)**.
- This is because random pivot selection generally produces reasonably balanced partitions.

**3. Expected Number of Comparisons**
- The expected number of key comparisons is **O(n log₂ n)**.

**4. Worst-Case Time Complexity**
- Randomized Quick Sort can still have a worst-case time complexity of **O(n²)** if repeatedly poor pivots are selected.
- However, the probability of this happening repeatedly is very small for large inputs.

### E. Time Complexity Summary

| Case | Time Complexity |
|---|---|
| Best Case | O(n log n) |
| Expected / Average Case | O(n log n) |
| Worst Case | O(n²) |

---

## 4. Conclusion

- Randomized algorithms use random choices to improve algorithm performance or simplify decision-making.
- They are classified into Las Vegas and Monte Carlo algorithms.
- Las Vegas algorithms always produce correct results, whereas Monte Carlo algorithms may produce incorrect results with a small probability.
- Randomized Quick Sort uses a randomly selected pivot to reduce the likelihood of worst-case partitioning.
- Its expected running time is **O(n log n)**.
