# CMPS 2200 Recitation 04
## Answers

**Name:**_________________________
**Name:**_________________________


Place all written answers from `recitation-04.md` here for easier grading.

- **4) (2 pts)** Assume that a word `w` appears `n` times. What is the **work** and **span** of `word_count_reduce` for this word, assuming a parallel implementation of the `reduce` function?

The code splits a list of size $n$ into 2 sub-problems of size $\frac{n}{2}$

This gives $W(n) = 2W(\frac{n}{2}) + 1$, and $S(n) = S(\frac{n}{2}) + 1$

Work:

Each level has 2 sub-problems of size $\frac{n}{2}$

However, the last level does not have work from combining

So if $n = 8$; $1 + 2 + 4 = 7 = n - 1$ 

So $W(n) = n - 1 = \Theta(n)$ 

Span:

The longest chain of dependency is the height

The base case is reached once $log_2n = 1$, which is the height

So, $S(n) = log_2n = \Theta(logn)$

- **5) (2 pts)** What is the problem that prevents us from easily parallelizing this solution?

Different branches working at the same time in parallel would be able to edit eachothers values, so parallelizing wouldn't be safe

