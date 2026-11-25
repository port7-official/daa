# Comparison of Ordinary Matrix Multiplication and Strassen's Matrix Multiplication

## 1. Comparison Table

| Feature | Ordinary Matrix Multiplication | Strassen's Matrix Multiplication |
|---|---|---|
| **Design Strategy** | Iterative (three nested loops) or ordinary Divide and Conquer | Divide and Conquer |
| **Sub-matrix Multiplications** | Performs 8 recursive multiplications | Performs only 7 recursive multiplications |
| **Recurrence Relation** | \(T(n) = 8T(n/2) + O(n^2)\) | \(T(n) = 7T(n/2) + O(n^2)\) |
| **Time Complexity** | \(O(n^3)\) | \(O(n^{\log_2 7}) \approx O(n^{2.81})\) |
| **Scalar Operations** | Requires \(n^3\) scalar multiplications and approximately \(n^3\) additions | Reduces multiplications but requires additional matrix additions and subtractions |
| **Memory Usage** | Requires less auxiliary memory | Requires more memory for temporary sub-matrices |
| **Numerical Stability** | More numerically stable | Comparatively less stable due to intermediate additions and subtractions |

## 2. Ordinary Matrix Multiplication

- It uses three nested loops to multiply two matrices.
- Each element of the resulting matrix is calculated using the row of the first matrix and the column of the second matrix.
- It requires \(n^3\) scalar multiplications and approximately \(n^3\) scalar additions.
- Its time complexity is **\(O(n^3)\)**.
- It requires less additional memory.

## 3. Strassen's Matrix Multiplication

- It is a Divide and Conquer algorithm.
- It divides the matrices into four smaller sub-matrices.
- It performs only **7 recursive sub-matrix multiplications** instead of 8.
- It uses additional matrix additions and subtractions to reduce the number of multiplications.
- Its recurrence relation is:

  \[
  T(n) = 7T(n/2) + O(n^2)
  \]

- Its time complexity is:

  \[
  O(n^{\log_2 7}) \approx O(n^{2.81})
  \]

- It requires more auxiliary memory to store temporary sub-matrices.

## 4. Which Method Is Better?

The better method depends on the size of the matrices.

**For Small Matrices: Ordinary Matrix Multiplication is Better**
- It has less computational overhead.
- It requires less additional memory.
- It avoids the overhead of recursive function calls and extra matrix operations.

**For Large Matrices: Strassen's Method is Better**
- It performs fewer recursive multiplications.
- Its time complexity is approximately \(O(n^{2.81})\), which is lower than \(O(n^3)\).
- It is generally more efficient for sufficiently large matrices.

**Practical Approach:**
- A hybrid approach can be used.
- Strassen's method is used for large matrices.
- Ordinary matrix multiplication is used when the sub-matrices become small.

## 5. Conclusion

Strassen's matrix multiplication is asymptotically faster than ordinary matrix multiplication for large matrices because it reduces the number of recursive multiplications from 8 to 7. However, ordinary matrix multiplication is generally preferred for small matrices due to its simplicity and lower overhead.

**Therefore, Strassen's method is better for sufficiently large matrices, while ordinary matrix multiplication is better for small matrices.**
