# Best, Worst and Average Case Analysis of Binary Search

## 1. Introduction

- **Binary Search** is an efficient searching algorithm based on the **Divide and Conquer** technique.
- It works only on a **sorted array** of elements.
- In each step, the target element (`x`) is compared with the middle element (`a[mid]`).

**Working:**

1. If `x = a[mid]`, the element is found and the search stops.
2. If `x < a[mid]`, the search continues in the left half.
3. If `x > a[mid]`, the search continues in the right half.
4. In each step, approximately half of the remaining elements are eliminated.

## 2. Best-Case Analysis

- **Condition:** The best case occurs when the target element is present at the **middle position** of the array.
- **Number of Comparisons:** Only **1 comparison** is required.
- **Time Complexity:** **Θ(1)** – Constant Time.

**Example:** If the array is `[10, 20, 30, 40, 50, 60, 70]` and the key is `40`, it is found in the first comparison.

## 3. Worst-Case Analysis

- **Condition:** The worst case occurs when the target element is found at the deepest level of the search or when the element is **not present** in the array.
- **Number of Comparisons:** The search repeatedly divides the array into half until the element is found or no elements remain.
- **Maximum Number of Comparisons:** Approximately `log₂(n) + 1`.

**Derivation:**

Let `n` be the number of elements.

After each comparison, the search space is reduced to half.

- After 1 comparison: `n / 2`
- After 2 comparisons: `n / 2²`
- After k comparisons: `n / 2ᵏ`

When only one element remains:

`n / 2ᵏ = 1`

Therefore,

`n = 2ᵏ`

`k = log₂(n)`

Hence, the time complexity is **Θ(log n)** – Logarithmic Time.

## 4. Average-Case Analysis

- **Condition:** Average-case analysis considers the average number of comparisons required to search for an element at different positions in the sorted array.
- Each position is assumed to be equally likely to contain the target element.
- **Number of Comparisons:** Approximately `log₂(n)` comparisons.
- **Time Complexity:** **Θ(log n)** – Logarithmic Time.

**Example:** For an array of 9 elements, the number of comparisons varies depending on the position of the target element. The average number of comparisons is approximately 2.77 for a successful search under the standard middle-element search tree.

## 5. Summary Table

| Case | Condition | Comparisons Required | Time Complexity |
|---|---|---|---|
| Best Case | Element at middle position | 1 | Θ(1) |
| Average Case | Element at an arbitrary position | Approximately log₂(n) | Θ(log n) |
| Worst Case | Element at deepest level or not present | Approximately log₂(n) + 1 | Θ(log n) |

## 6. Conclusion

- Binary Search has **Θ(1)** best-case time complexity.
- Its average-case and worst-case time complexities are **Θ(log n)**.
- It is more efficient than Linear Search for large sorted arrays because it eliminates half of the remaining elements in every step.
