# CMPS 2200 Recitation 04
## Answers

**Name:**_________________________
**Name:**_________________________


Place all written answers from `recitation-04.md` here for easier grading.

- **4) (2 pts)** Assume that a word `w` appears `n` times. What is the **work** and **span** of `word_count_reduce` for this word, assuming a parallel implementation of the `reduce` function?

The code splits a list of size $n$ into 2 sub-problems of size $\frac{n}{2}$

This gives $W(n) = 2W(\frac{n}{2}) + 1$, and $S(n) = S(\frac{n}{2}) + 1$

Work:

Each level has 2 sub-problems of size $\frac{n}{2}$ giving a work of $n$ each level

The base case is reached when $n = 1$ which will happen when $log_2n = 1$

So $W(n) = n \cdot log_2n = \Theta(nlogn)$ 

Span:

Each level has splits into size $\frac{n}{2}$

The base case is reached when $n = 1$ which will happen when $log_2n = 1$

So $S(n) = \frac{n}{2} \cdot log_2n = \Theta(nlogn)$

- **5) (2 pts)** What is the problem that prevents us from easily parallelizing this solution?

