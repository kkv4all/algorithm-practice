# Dynamic Programming
## Introduction
Dynamic Programming is an algorithmic approach to find the solution for optimization. This paradigm solves a given complex problem by breaking it into subproblems and storing the results of subproblems to avoid computing the same results again. 

In some cases, Solution can be recursive and may end up having redundant function calls. For example let's consider the mathematical function of fibonacci series:

```
	f(n) = f(n-1) + f(n-2), where n >= 2
			and f(1) = 1 and f(0) = 0
```

To solve the problem above, we will not make the redundant calls and store the result in memory.
The methods of storing the result are:
 - Memorization (Top-Down)
 - Tabulation (Bottom-Up)

## Where to use?
There are two properties of problem that suggest the use of dynamic programming.
1. _**Overlapping subproblem property —**_ Problem can be broken down into subproblems which are reused several times or a recursive algorithm for the problem solves the same subproblem over and over rather than always generating new subproblems
2. _**Optimal Substructure property —**_ Optimal solution for main problem can be constructed from optimal solutions of its subproblems

## Memorization & Tabulation
Dynamic Programming and Divide and Conquer has similarity as both paradigms work by combining solutions to sub-problem. Dynamic programming is mainly used when Overlapping subproblem property satisfied. Dynamic programming approach extends divide and conquer approach with two techniques _Memorization_ and _Tabulation_ that both have a purpose of storing and re-using sub-problems solutions that may drastically improve performance.

**Memorization:**
It starts with the highest-level subproblems (the ones closest to the original problem), and recursively calls the next subproblem, and the next. We save time when a subproblem A recurses into a subproblem B that has already been called. Since B and all subproblems below it are memoized, we can avoid repeating the entire recursion tree generated by B, saving a lot of computation. Hence its approach is Top-Down.

It uses following steps to solve the problem:
 - Initialize a lookup array/table with all its elements as NIL
 - Call the recursive function f(n) to solve for n using memorization.
 - At every step i, f(i) performs the following steps:
 	a. checks whether table[i] is NULL or not
 	b. If it's not NIL, f(i) returns the value table[i].
 	c. if it's NIL and i satisfies the base condition, we update the lookup table with the base value and return same.

**Tabulation**
 It starts by solving the lowest level subproblem. The solution then lets us solve the next subproblem, and so forth. We iteratively solve all subproblems in this way until we’ve solved all subproblems, thus finding the solution to the original problem. We save time when a subproblem needs the answer to a subproblem that has been called before, and thus has had its value tabulated. Hence its approach is Bottom-up.

It uses following steps to solve the problem:
 - Initialize a base values for initial iteration.
 - Next, At Every iteration i, we update the value of f(i) in Lookup table by calculating value from previously solved subproblem.
 - Finally we get the value of f(n).

## Pros and Cons
**_Pros_**

 - process of breaking down a complex problem often provides insight to nature of problem.

**_Cons_**

 - its is time consuming and complex in nature.
 - it uses recursive formulas. 

## Application & Examples
 - 0/1 Knapsack Problem
 - Fibonacci Series
 - Shortest Path Problem
 - Longest Common Subsequence
 - Matrix Chain Multiplication
