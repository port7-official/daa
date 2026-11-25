
# Difference Between Las Vegas and Monte Carlo Algorithms

| Feature | Las Vegas Algorithm | Monte Carlo Algorithm |
|---|---|---|
| **Definition** | A randomized algorithm that always produces the correct result, but its execution time may vary. | A randomized algorithm that runs within a fixed or bounded time but may produce an incorrect result with a small probability. |
| **Correctness** | Always produces the correct answer. | May produce an incorrect answer with a certain probability. |
| **Running Time** | Running time varies depending on random choices. | Running time is generally fixed or bounded. |
| **Main Focus** | Guarantees correctness while aiming for good expected running time. | Guarantees bounded running time while allowing a small probability of error. |
| **Error Probability** | Zero probability of an incorrect result. | Has a small probability of an incorrect result. |
| **Repetition** | Repetition may change the execution time but does not affect correctness. | Repeating independent runs can reduce the probability of error. |
| **Example** | Randomized Quick Sort. | Rabin-Miller Primality Test. |

## Easy Way to Remember

- **Las Vegas:** Always correct, but execution time may vary.
- **Monte Carlo:** Execution time is bounded, but the answer may sometimes be incorrect.

## Conclusion

Las Vegas algorithms guarantee the correctness of the result, whereas Monte Carlo algorithms provide a bounded running time with a small probability of error.
