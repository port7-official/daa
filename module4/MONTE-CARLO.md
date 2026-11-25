
# Monte Carlo Algorithms

## 1. Definition

A **Monte Carlo Algorithm** is a randomized algorithm that runs within a fixed or bounded time but may produce an incorrect result with a small probability.

It uses random choices during execution to solve problems efficiently.

**In simple words:**
- It completes within a fixed time limit.
- It usually produces the correct answer.
- However, there is a small chance of getting an incorrect answer.
- The probability of error can be reduced by repeating the algorithm.

**Example:** Rabin-Miller Primality Test is a Monte Carlo algorithm used to check whether a number is prime or composite.

---

## 2. Key Characteristics of Monte Carlo Algorithms

### 1. Probabilistic Output

- A Monte Carlo algorithm does not guarantee a correct answer 100% of the time.
- It may produce an incorrect answer with a small probability.
- However, the probability of error is bounded and can be controlled.
- It produces the correct answer with high probability.

**Easy Understanding:** The algorithm usually gives the correct answer, but there is a small chance of making a mistake.

### 2. Deterministic / Bounded Running Time

- A Monte Carlo algorithm has a fixed or bounded running time.
- Its execution finishes within a specified time limit.
- Unlike Las Vegas algorithms, its running time does not depend on random choices.

**Easy Understanding:** We know that the algorithm will finish within a certain time, even though its answer may sometimes be incorrect.

### 3. Error Reduction (Error Amplification)

- The probability of error can be reduced by running the algorithm independently multiple times.
- Each repetition provides another opportunity to obtain a correct result.
- If the error probability is less than 1/2, repeating the algorithm reduces the probability of failure exponentially.

**Easy Understanding:** If we repeat the algorithm several times, the chance of getting an incorrect result becomes smaller.

**Example:**

If the probability of error in one execution is 1/4, and the independent repetitions use a suitable majority-voting method, the probability of an incorrect majority decreases as the number of repetitions increases.

### 4. Example – Rabin-Miller Primality Test

- Rabin-Miller Primality Test is a well-known Monte Carlo algorithm.
- It is used to check whether a given number is prime or composite.
- It is commonly used in applications related to RSA cryptography.
- It runs in polynomial time.
- It may produce an incorrect result with a very small, controllable probability.

**Easy Understanding:** It quickly checks whether a number is prime, but there is a very small chance of error.

---

## 3. Types of Monte Carlo Algorithms

Monte Carlo algorithms are classified based on the type of error they can produce.

### 1. One-Sided Error

- The algorithm makes errors in only one type of answer.
- It never makes an error in one direction, but may make an error in the other direction.

**Example:**
- It may never give a false positive.
- However, it may give a false negative with a small probability.

**Easy Understanding:** The algorithm can make only one particular type of mistake.

### 2. Two-Sided Error

- The algorithm may produce incorrect answers for both YES and NO instances.
- However, the probability of producing the correct answer is greater than 1/2.

**Easy Understanding:** The algorithm can make mistakes in both types of answers, but it is more likely to give the correct answer.

---

## 4. Difference Between Monte Carlo and Las Vegas Algorithms

| Feature | Monte Carlo Algorithm | Las Vegas Algorithm |
|---|---|---|
| Correctness | May produce an incorrect result with a small probability. | Always produces the correct result. |
| Running Time | Fixed or bounded running time. | Running time varies depending on random choices. |
| Main Goal | Complete within a bounded time while controlling error probability. | Always produce a correct answer while optimizing expected running time. |
| Example | Rabin-Miller Primality Test | Randomized Quick Sort |

**Remember:**
- Monte Carlo = Bounded time, possible error.
- Las Vegas = Always correct, variable running time.

---

## 5. Conclusion

A Monte Carlo algorithm is a randomized algorithm that provides a solution within a fixed or bounded running time, but may produce an incorrect result with a small probability.

Its error probability can be reduced by repeating the algorithm independently.

Monte Carlo algorithms are classified into:
1. One-Sided Error.
2. Two-Sided Error.

**Example:** Rabin-Miller Primality Test.

---

## 6. Quick Revision

- **Definition:** Randomized algorithm with bounded running time and a small probability of error.
- **Output:** Probabilistic.
- **Running Time:** Fixed or bounded.
- **Error Reduction:** Repeat the algorithm independently.
- **One-Sided Error:** Makes only one type of error.
- **Two-Sided Error:** Can make both types of errors.
- **Example:** Rabin-Miller Primality Test.
