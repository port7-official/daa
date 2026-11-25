
# Approximation Algorithms – Bin Packing Problem

## 1. Problem Definition

The **Bin Packing Problem** is an NP-Hard optimization problem in which we are given a set of items with different sizes and an unlimited number of bins, each having a fixed capacity.

The objective is to pack all items into the **minimum possible number of bins** without exceeding the capacity of any bin.

**In simple words:**
- We have multiple items of different sizes.
- Each bin has a fixed capacity.
- We must place all items inside the bins.
- The total size of items in a bin must not exceed its capacity.
- Our goal is to use as few bins as possible.

**Example:**

Suppose:
- Bin capacity = 10 units.
- Item sizes = 2, 5, 4, 7, 1, 3, 8.

One possible packing is:

- Bin 1: 2 + 5 + 3 = 10
- Bin 2: 4 + 1 = 5
- Bin 3: 7
- Bin 4: 8

The objective is to minimize the number of bins used.

---

## 2. Why are Approximation Algorithms Used?

Bin Packing is an NP-Hard optimization problem. Finding the exact optimal solution can take a long time for large inputs.

Therefore, approximation algorithms are used.

**Approximation Algorithm:** An algorithm that produces a near-optimal solution in polynomial time instead of finding the exact optimal solution.

---

## 3. Approximation Ratio (Performance Ratio)

The approximation ratio measures how close the solution produced by an approximation algorithm is to the optimal solution.

For Bin Packing:

Approximation Ratio = C / C*

Where:
- C = Number of bins used by the approximation algorithm.
- C* = Minimum number of bins required by the optimal solution.

**Important Points:**
- The optimal solution always uses the minimum possible number of bins.
- An approximation algorithm may use more bins than the optimal solution.
- Therefore, the approximation ratio is always greater than or equal to 1.

C / C* ≥ 1

A ratio closer to 1 indicates a better approximation.

---

## 4. Common Bin Packing Approximation Algorithms

There are four important algorithms:

### 1. First Fit (FF)

**Strategy:**

First Fit places each item into the first existing bin that has enough remaining capacity.

If no existing bin can accommodate the item, a new bin is opened.

**Steps:**

1. Take the items in the given order.
2. Check the bins one by one, starting from the first bin.
3. Place the item in the first bin that has sufficient remaining capacity.
4. If no bin can accommodate the item, open a new bin.
5. Repeat until all items are packed.

**Performance Bound:**

FF(I) ≤ ⌈1.7 × OPT(I)⌉

- Asymptotic approximation ratio: 1.7.

**Easy Understanding:** Always try the first available bin that can accommodate the current item.

### 2. Next Fit (NF)

**Strategy:**

Next Fit considers only the most recently opened bin when placing a new item.

If the current bin has enough space, the item is placed in it. Otherwise, the current bin is closed, and a new bin is opened.

**Steps:**

1. Open the first bin.
2. Take the next item.
3. Check whether it fits in the current bin.
4. If it fits, place it in the current bin.
5. Otherwise, close the current bin and open a new bin.
6. Repeat until all items are packed.

**Performance Bound:**

NF(I) ≤ 2 × OPT(I)

- Approximation ratio: 2.

**Easy Understanding:** Only check the latest bin. If the item does not fit, open another bin. Never return to previously closed bins.

### 3. Best Fit (BF)

**Strategy:**

Best Fit places each item into the bin that has the smallest remaining capacity among all bins that can accommodate the item.

In other words, it chooses the bin where the item fits most tightly.

If no existing bin can accommodate the item, a new bin is opened.

**Steps:**

1. Take the next item.
2. Check all existing bins.
3. Find the bin with the least remaining space that can still accommodate the item.
4. Place the item in that bin.
5. If no bin can accommodate it, open a new bin.
6. Repeat until all items are packed.

**Performance Bound:**

- Asymptotic approximation ratio: 1.7.

**Easy Understanding:** Choose the bin that leaves the least unused space after placing the item.

### 4. First Fit Decreasing (FFD)

**Strategy:**

First Fit Decreasing first sorts all items in decreasing order of size and then applies the First Fit algorithm.

This means larger items are packed before smaller items.

**Steps:**

1. Sort all items in decreasing order of size.
2. Take the largest item first.
3. Apply the First Fit strategy.
4. Place each item in the first bin that has sufficient remaining capacity.
5. If no bin can accommodate the item, open a new bin.
6. Repeat until all items are packed.

**Performance Bound:**

FFD(I) ≤ (11/9) × OPT(I) + 1

11/9 ≈ 1.22

- Asymptotic approximation ratio: 11/9 (approximately 1.22).

**Easy Understanding:** Arrange items from largest to smallest and then use First Fit. Packing larger items first generally reduces wasted space.

---

## 5. Difference Between Bin Packing Algorithms

| Algorithm | Strategy | Approximation Ratio |
|---|---|---|
| First Fit | First bin with enough space | 1.7 |
| Next Fit | Only the latest bin | 2 |
| Best Fit | Bin with least remaining space after placement | 1.7 |
| First Fit Decreasing | Sort decreasingly, then First Fit | 11/9 ≈ 1.22 |

**Note:** These are asymptotic approximation guarantees, not exact ratios for every individual input.

---

## 6. Example to Understand the Four Algorithms

Suppose the bin capacity is 10 and the items arrive in this order:

Items = [4, 8, 1, 4, 2, 1]

- **First Fit:** Searches from the first bin and chooses the first bin where the item fits.
- **Next Fit:** Checks only the most recently opened bin.
- **Best Fit:** Searches all bins and chooses the tightest fit.
- **First Fit Decreasing:** First sorts the items as [8, 4, 4, 2, 1, 1], then applies First Fit.

This is the key difference between the four algorithms.

---

## 7. Conclusion

The Bin Packing Problem is an NP-Hard optimization problem in which the objective is to pack all items into the minimum number of bins without exceeding bin capacity.

Approximation algorithms provide near-optimal solutions in polynomial time.

The commonly used algorithms are:

1. First Fit.
2. Next Fit.
3. Best Fit.
4. First Fit Decreasing.

Among these, First Fit Decreasing provides a better approximation guarantee than the other listed heuristics.

---

## 8. Quick Revision

- **Bin Packing:** Pack all items into the minimum number of bins.
- **Approximation Algorithm:** Finds a near-optimal solution in polynomial time.
- **Approximation Ratio:** C / C*.
- **First Fit:** Places the item in the first bin with enough space.
- **Next Fit:** Checks only the current bin.
- **Best Fit:** Chooses the bin with the least remaining space after placement.
- **First Fit Decreasing:** Sorts items from largest to smallest, then applies First Fit.
- **Best Approximation Guarantee Among These:** First Fit Decreasing (11/9 asymptotically).
