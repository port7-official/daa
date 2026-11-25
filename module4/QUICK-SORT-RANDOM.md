
# Randomized Version of Quick Sort Algorithm with Analysis

## 1. Introduction

- **Randomized Quick Sort** is a randomized version of the standard Quick Sort algorithm.
- In normal Quick Sort, the pivot is usually selected using a fixed method, such as choosing the first or last element.
- If the input array is already sorted or nearly sorted, selecting a fixed pivot may produce unbalanced partitions.
- This can lead to a worst-case time complexity of O(n²).
- To reduce this problem, Randomized Quick Sort selects a pivot randomly from the given subarray.

**In simple words:** Instead of always selecting the first or last element as the pivot, Randomized Quick Sort selects a random element. This reduces the chance of repeatedly getting bad partitions.

---

## 2. Algorithm – RquickSort

```text
Algorithm RquickSort(a, p, q)
{
    if (q > p) then
    {
        if ((q - p) > 5) then
            Interchange(a, Random() mod (q - p + 1) + p, p);

        m := Partition(a, p, q + 1);

        RquickSort(a, p, m - 1);

        RquickSort(a, m + 1, q);
    }
}
```

### Explanation of the Algorithm

1. **Check the condition:** Check whether q > p. If true, the subarray contains more than one element and sorting continues.
2. **Random Pivot Selection:** Select a random element from the subarray a[p...q].
3. **Interchange:** Swap the randomly selected element with the first element of the subarray.
4. **Partition:** Apply the Partition operation to place the pivot in its correct sorted position. It returns the pivot position m.
5. **Sort Left Subarray:** Recursively apply Randomized Quick Sort to the left subarray (p to m-1).
6. **Sort Right Subarray:** Recursively apply Randomized Quick Sort to the right subarray (m+1 to q).
7. Repeat until all elements are sorted.

**Note:**
- `Interchange(a, i, j)` swaps the elements at positions i and j.
- `Partition(a, p, q+1)` rearranges the elements around the pivot and returns its final position m.
- `Random()` generates a random number.

---

## 3. Working of Randomized Quick Sort

Consider the following array:

`[8, 3, 5, 2, 9, 1]`

1. Randomly select an element as the pivot. Suppose the pivot is 5.
2. Partition the array into two parts:
   - Left subarray: Elements smaller than 5 → [3, 2, 1]
   - Pivot: 5
   - Right subarray: Elements greater than 5 → [8, 9]
3. Recursively sort the left and right subarrays.
4. Combine the results to get the sorted array.

**Final Sorted Array:**

`[1, 2, 3, 5, 8, 9]`

---

## 4. Performance Analysis

### A. Expected / Average-Case Time Complexity – O(n log n)

- The pivot is selected randomly from the given subarray.
- Random selection reduces the possibility of repeatedly getting highly unbalanced partitions.
- The array is generally divided into reasonably balanced subarrays.
- Each level of partitioning requires O(n) time.
- The expected number of recursion levels is O(log n).

Therefore, the expected running time is:

**O(n log n)**

General recurrence relation:

T(n) = T(i) + T(n-i-1) + Cn

Where:
- T(n) = Total running time.
- i = Number of elements in the left subarray.
- n-i-1 = Number of elements in the right subarray.
- Cn = Time required for partitioning.

### B. Worst-Case Time Complexity – O(n²)

- The worst case occurs when the randomly selected pivot is repeatedly the smallest or largest element.
- This produces highly unbalanced partitions.
- One subarray contains n-1 elements, while the other contains 0 elements.
- Partitioning requires O(n) time at each level.

Worst-case recurrence relation:

T(n) = T(n-1) + Cn

Expanding:

T(n) = T(n-2) + C(n-1) + Cn

The total work becomes:

T(n) = C(1 + 2 + 3 + ... + n)

Therefore, the worst-case time complexity is:

**O(n²)**

**Important:** Although the worst case is possible, repeatedly selecting poor pivots is unlikely when pivots are chosen randomly.

### C. Space Complexity – O(log n)

- Quick Sort sorts the array in place, so it does not require another array for storing sorted elements.
- However, recursive function calls require memory in the recursion stack.
- On average, the recursion depth is O(log n).

Therefore, the expected auxiliary space complexity is:

**O(log n)**

---

## 5. Time and Space Complexity Summary

| Case | Complexity |
|---|---|
| Best Case | O(n log n) |
| Expected / Average Case | O(n log n) |
| Worst Case | O(n²) |
| Expected Auxiliary Space | O(log n) |

---

## 6. Advantages of Randomized Quick Sort

1. Random pivot selection reduces the chance of consistently unbalanced partitions.
2. It performs efficiently for different input arrangements.
3. Its expected running time is O(n log n).
4. It sorts the elements in place without requiring an additional array.

---

## 7. Conclusion

Randomized Quick Sort improves the standard Quick Sort algorithm by selecting the pivot randomly instead of using a fixed selection method.

This reduces the probability of repeatedly obtaining unbalanced partitions and gives an expected time complexity of O(n log n).

It is an example of a **Las Vegas randomized algorithm** because it always produces the correct sorted output, although its running time depends on random pivot selection.
