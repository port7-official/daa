# Best, Worst and Average Case Analysis of Linear Search

## 1. Introduction

- **Linear Search** is a searching technique in which each element of an array is checked sequentially, starting from the first element.
- The search continues until the required element (key `x`) is found or all elements have been checked.

## 2. Best-Case Analysis

- **Condition:** The best case occurs when the required element is present at the **first position** of the array.
- **Number of Comparisons:** Only **1 comparison** is required.
- **Time Complexity:** **O(1)** – Constant Time.

**Example:** If the array is `[10, 20, 30, 40, 50]` and the key is `10`, it is found in the first comparison.

## 3. Worst-Case Analysis

- **Condition:** The worst case occurs when the required element is at the **last position** or is **not present** in the array.
- **Number of Comparisons:** The algorithm checks all `n` elements, requiring **n comparisons**.
- **Time Complexity:** **O(n)** – Linear Time.

**Example:** If the array is `[10, 20, 30, 40, 50]` and the key is `50` (or `60`), all 5 elements must be checked.

## 4. Average-Case Analysis

- **Condition:** Average-case analysis assumes that the required element is present and is equally likely to be at any position in the array.
- **Number of Comparisons:** On average, approximately `(n + 1) / 2` comparisons are required.
- **Time Complexity:** **O(n)** – Linear Time.

**Example:** If the array contains `n` elements, the search requires approximately `n/2` comparisons on average.

## 5. Summary Table

| Case | Condition | Number of Comparisons | Time Complexity |
|---|---|---|---|
| Best Case | Element at first position | 1 | O(1) |
| Average Case | Element at any position | (n + 1) / 2 | O(n) |
| Worst Case | Element at last position or absent | n | O(n) |

## 6. Conclusion

- Linear Search has **O(1)** best-case time complexity.
- Its average-case and worst-case time complexities are **O(n)**.
- Therefore, the searching time increases linearly with the number of elements in the array.
