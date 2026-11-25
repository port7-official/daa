
# Las Vegas Algorithms

## 1. Definition

A **Las Vegas Algorithm** is a randomized algorithm that always produces the correct result, but its running time may vary depending on the random choices made during execution.

**In simple words:**
- It uses random choices while executing.
- It always gives the correct answer.
- However, the time taken to produce the answer may change.
- Its performance is measured using expected running time.

**Example:** Randomized Quick Sort.

---

## 2. Key Characteristics of Las Vegas Algorithms

### 1. 100% Correctness

- A Las Vegas algorithm always produces the correct output.
- It never produces an incorrect answer.
- Regardless of the random choices made, the final result is always correct.

**Easy Understanding:** Whatever random choice the algorithm makes, the final answer will always be correct.

### 2. Probabilistic Running Time

- The running time of a Las Vegas algorithm depends on the random choices made during execution.
- Therefore, the execution time may vary for different runs.
- Its running time is considered a random variable.
- The analysis mainly focuses on minimizing the expected running time.

**Easy Understanding:** The algorithm always gives the correct answer, but sometimes it may take more time and sometimes less time.

### 3. Difference from Monte Carlo Algorithms

- Las Vegas algorithms always produce correct results, but their running time varies.
- Monte Carlo algorithms have a fixed or bounded running time, but may produce incorrect results with a small probability.

---

## 3. Example – Randomized Quick Sort (RquickSort)

Randomized Quick Sort is a well-known example of a Las Vegas algorithm.

### A. Working Principle

- Randomized Quick Sort is a modified version of the normal Quick Sort algorithm.
- It randomly selects a pivot element from the given array or subarray.
- The array is divided into two parts based on the selected pivot:
  1. Elements smaller than the pivot.
  2. Elements greater than the pivot.
- Both parts are sorted recursively.

### B. Why is it a Las Vegas Algorithm?

**1. Correctness:**
- It always produces a correctly sorted array.
- Even if a poor pivot is selected, the final sorted result remains correct.

**2. Running Time:**
- The running time depends on the randomly selected pivot.
- A good pivot produces balanced partitions and faster execution.
- A poor pivot produces unbalanced partitions and slower execution.

### C. Time Complexity

| Case | Time Complexity |
|---|---|
| Best Case | O(n log n) |
| Expected / Average Case | O(n log n) |
| Worst Case | O(n²) |

**Expected Running Time:** O(n log n).

---

## 4. Difference Between Las Vegas and Monte Carlo Algorithms

| Feature | Las Vegas Algorithm | Monte Carlo Algorithm |
|---|---|---|
| Correctness | Always produces the correct result. | May produce an incorrect result with a small probability. |
| Running Time | Varies depending on random choices. | Fixed or bounded running time. |
| Main Goal | Always provide a correct result while optimizing expected running time. | Complete within bounded time while controlling error probability. |
| Example | Randomized Quick Sort | Rabin-Miller Primality Test |

**Easy way to remember:**

- Las Vegas = Always correct, time varies.
- Monte Carlo = Time is bounded, answer may be incorrect.

---

## 5. Conclusion

Las Vegas algorithms are randomized algorithms that always produce the correct result, but their running time varies depending on the random choices made during execution.

Randomized Quick Sort is a common example of a Las Vegas algorithm. Its expected running time is O(n log n).

---

## 6. Quick Revision

- **Definition:** Randomized algorithm that always gives the correct answer.
- **Correctness:** 100% guaranteed.
- **Running Time:** Variable and probabilistic.
- **Performance Measure:** Expected running time.
- **Example:** Randomized Quick Sort.
- **Expected Time Complexity:** O(n log n).
- **Worst-Case Time Complexity:** O(n²).
