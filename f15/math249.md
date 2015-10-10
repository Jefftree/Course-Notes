<!--Multiset Definiton-->
$$\def\multiset#1#2{\left(\!\left({#1\atopwithdelims..#2}\right)\!\right)}$$

# MATH 249

Combinatorics include enumeration and graph theory.

## Enumeration

The **cardinality** of a set $A$, denoted as $|A|$ is the number of elements it contains if it is finite, or something else if it's infinite.

The **Cartesian power** $A^k$ is the set of all ordered $k$-tuples of elements from $A$.

$$A^k:= \{a_1,a_2,\dots,a_k\}: a_1.a_2,\dots,a_k \in A \}$$

$\lbrack n \rbrack$ is the set of all positive integers from $1$ to $n$, inclusive. This is represented as $\{1,...,n\},\,\forall n \geq 1$.

A $k$-subset of $\lbrack n \rbrack$ is simply a subset of it that contains $k$ elements. For example, there are $6$ $2$-subsets of $\lbrack 4 \rbrack$, namely $\{1,2\},\{1,3\},\{1,4\},\{2,3\},\{2,4\},\{3,4\}$.

**Example** The number of $k$-subsets of $\lbrack n \rbrack$ is $n \choose k$ for $n = 0,1,...,$ and $k=0,1,...,n$

**Proof**: Let $x$ be the number of $k$-subsets of $\lbrack n \rbrack$. $x$ can be determined indirectly by setting up an equality involving the permutation of $\lbrack n \rbrack$. For any permutation $a_1...a_n$ and any fixed $k=0,..,n$, the elements in $a_1,...a_k$ form a $k$-subset of $\lbrack n \rbrack$, denoted as $\alpha$. Then the elements in $a_{k+1},...,a_n$ form the complement, $\bar{alpha}$, of $\alpha$ with respect to $\lbrack n \rbrack$. For each fixed $\alpha$, there are $k!$ choices of $a_1...a_k$ since it is just a permutation of $\alpha$, and $(n-k)!$ choices of $a_{k+1}...a_n$. Since there are $x$ choices for $\alpha$, then the number of permutations of $\lbrack n \rbrack$ is

$$k!(n-k)!x = n!$$

Rearranging gives $x= {n\choose k}$.

## Bijections
A **bijection** is a function that maps a set $S$ to another set $T$, and is one to one and onto.

One to one means that the function has a unique element of $T$ for every value of $S$. That is $|T| \geq |S|$.
Onto means that the function has a unique element $S$ for every value of $T$, and therefore $|S| \geq |T|$.

Therefore it is a function that maps a set's elements to the elements of another set of the exact same size. It is often easier to prove that a bijection has an inverse rather than proving one to one and onto.

### Bijection Inverse Theorem

**Proposition:** a function is a bijection if and only if it has an inverse.

The **inverse** of $f: S \rightarrow T$ is a function $f^{-1}$ such that $\forall x \in S, f^{-1}(f(x)) = x$ and $\forall y \in T, f(f^{-1}(y)) = y$. It reverses a mapping backwards from $T$ to $S$.

# Fun stuff

## The Twelve Fold Ways
How many ways are there to place $k$ balls in $n$ boxes, assuming

Restrictions:

1. No restrictions
2. At most one ball per box
3. At least one ball per box

Distinguishability:

- A. Balls distinguishable, boxes distinguishable
- B. Balls indistinguishable, boxes distinguishable
- C. Balls distinguishable, boxes indistinguishable
- D. Balls indistinguishable, boxes indistinguishable

Each way is a function $f: K \rightarrow N$ where $|K| = k$ and $|N|=n$.

**Restrictions**:

1. no restrictions on $f$
2. $f$ is injective
3. $f$ is surjective

Distinguishability:

- A. $f \sim g \iff f = g$
- B. $f \sim g \iff $ there is a bijection $\alpha: K \rightarrow K$ such that $f = g \circ a$
- C. $f \sim g \iff$ there is a bijection $\beta : N \rightarrow N$ such that $f = b \circ g$
- D. $f \sim g \iff$ there is a bijection $\alpha : K \rightarrow K$ and bijection $\beta: N \rightarrow N$ such that $f = \beta \circ g \circ a$

**Notation:**

$$x^{\underline k} = x(x-1)(x-2)\dots(x-k+1)$$

$$x^{\bar k} = x(x+1)(x+2)\dots(x+k-1)$$

$$k! = k^{\underline k}$$

## 1A: No restrictions and balls and boxes are distinguishable

**Answer:** $n^k$

## 2A: At most one ball per box, balls and boxes distinguishable

**Answer:** $\frac{n!}{(n-k)!} = n^{\underline k}$

## 2C: At most one ball per box, boxes indistinguishable.

$1$ if $k \leq n, 0$ otherwise

## 2D. At most one ball per box, balls and boxes both indistinguishable

$1$ if $k \leq n, 0$ otherwise

## 2B. At most one ball per box, balls indistinguishable.

**Theorem:** $n \choose k$

**Proof:** Let $N,K$ be sets with $|N| = n, |K| = k$.
Let $X=\{K \rightarrow N |f \text{ is injective}\}$. Let $f \sim g$ if there exists a bijection $\alpha: K \rightarrow K$ such that $f = g \circ \alpha$. Let $Y$ be the set of equivalence classes of the equivalence relation $\sim$. Then $|Y|$ is the answer to the problem.

We saw $|X| = n^\underline{k}$

Also $|X| = \sum_{C \in Y} |C|$ since $Y$ is a set of disjoint sets whose union $X$

Suppose $C \in Y, g \in C$ Then
$$ C = \{f \in X | f = g \circ \alpha \text{ for some bijection } \alpha: K \rightarrow K\}$$
$$ = \{g \circ \alpha | \alpha: K \rightarrow K \text{ is a bijection}\}$$

Since $g$ is injective, $g \circ a = g \circ a' \text{ iff } a = a'$
Therefore $|C| =$ # of bijections $= K \rightarrow K = k!$

Putting it all together

$n^\underline{k} = |X| = \sum_{C \in Y} |C| = k!|Y|$

$|Y| = \frac{n^\underline{k}}{k!} = {n \choose k}$

**Interpretation** If $n,k$ are integers, then $n \choose k$ is the number of $k$-element subsets of an $n$-element subset.

## 1B: No restriction, balls indistinguishable

**Interpretation**: $k$-element multisets from an $n$-element set.

Example: If $n=2,k=4$, there are $5$ $k$-element multisets from $N={a,b}:$
$$\{a,a,a,a\},\{a,a,a,b\},\{a,a,b,b\},\{a,b,b,b\},\{b,b,b,b\}$$

**Notation:** Define $\multiset{n}{k}= \frac{n^\underline{k}}{k!}= {n+k-1 \choose k}$

**Theorem**: Answer to 1B is $\multiset{n}{k}$

**Proof:** Assume that $N = {1,2,...,n}$. Let $X$ be the set of $k$-element multisets from ${1,2,...,n}$. Let $Y$ be the set of $k$-element subset of ${1,2,...,n+k-1}$.
Since we know that $|Y| = {n+k-1 \choose k}$, we can prove the result by finding a bijection $f: X \rightarrow Y$.

If $A \in X$, we can write $A = {a_1,a_2,...,a_k}$, where
$$a_1 \leq a_2 \leq ... \leq a_k$$

$$f(A) = \{a_1,a_2 + 1, a_3 + 2,...,a_k + k -1\}$$

Finishing the proof:

- $f(A) \in Y$
- $f$ is a bijection

## 3B. At least one ball per box, balls indistinguishable

**Interpretation**: Compositions of an integer

How many ways are there to write
$$k=c_1 + c_2 + ... + c_n$$
where $c_1,...,c_n$ are positive integers.

**Idea**: $c_i$ is the number of balls in the i-th box
Since there is at least one ball per box, $c_i$ is a positive integer
Note: 1B can be interpreted in a similar war.

## 3D At Least one ball per box, balls and boxes indistinguishable
**Interpretation**: Partitions of an integer

How many ways are there to write
$$k = c_1 + c_2 + ... + c_n$$
where $c_i,...,c_n$ are positive integers and $c_1 \geq ... \geq c_n$

**Idea**: $c_1$ is the number of balls in the box with the larger number of balls, and so on. (because balls are indistinguishable)

1D is related to this as well

## 3A At least one ball per box, balls and boxes distinguishable

**Interpretation**: Surjective functions

## 3C. At least one ball per box, boxes indistinguishable

**Interpretation:** Set partitions
Example: $\{\{1,4\},\{2,5,6\},\{3\},\{7\}\}$ is a partition of $\{1,2,3,4,5,6,7\}$ into four subsets.

1C is related

## Notation
$N = Z_{ \geq 0}$ - non negative integers

### Degenerate cases
$$x^\underline{0} = x^\bar{0} = 1, 0! = 1, {x \choose 0} = 1$$

An empty product (no terms) is always $1$.

An empty sum (no terms) is always $0$.

$$\lbrack 0 \rbrack = \{\}$$

$$0^0=1$$ (indeterminate form)

If $n$ is a negative integer, then
$\frac{1}{n!} = 0$, and ${x \choose n} = 0$

## Combinatorics vs Algebra

**Theorem**: ${n \choose k} = {n-1 \choose k} + {n-1 \choose k-1}$ for $k,n \in N$

**Proof 1**: (Combinatorics), Let $X = \{$ k-elem subsets of $\lbrack n \rbrack\}.$ Let $Y = \{ k$ or $(k-1)$ elem. subsets of $\lbrack n-1 \rbrack\}.$ Then LHS = $|X|$ and RHS = $|Y|$. We prove the identity by giving a bijection between X and Y.

Define $f: X \rightarrow Y$ as follows. Given $A \in X$, a $k$-elem subset of $\lbrack n \rbrack$. Let $f(A) = A \setminus \{n\}$. Then $f(A) \subseteq \lbrack n-1 \rbrack$ has a $k$ or $k-1$ elements so $f(A) \in Y$.

Define $g: Y \rightarrow X$ as follows. Given $B \in Y$, let

$g(B) = B$ if $|B| =k$

$g(B) = B \cup \{n\}$ if $|B| = k-1$

In either case $|g(B)| = k$, and $g(B) \subseteq \lbrack n \rbrack$, so $g(B) \in X$.

Verify that $g(f(A)) = A$, for $A \in X$

Case 1: $n \not\in A$, then $f(A) = A \setminus \{n\} = A$, and $|f(A)| = k$, so $g(f(A)) = A$

Case 2: $n \in A$, then $|f(A)| = k-1$, so $g(f(A)) = (A \setminus \{n\}) \cup \{n\} = A \cup \{n\} - A$

Verify that $f(g(B)) = B$, for $B \in Y$
Case 1: $|B| = k$, then $g(B) = B$, and $n \not\in B$, so $f(g(B)) = f(B) = B$

Case 2: $|B| = k-1$, since $n \not\in B$, we have $f(g(B)) = (B \cup \{n\}) \setminus \{n\} = B \setminus \{n\} = B$

Thus $f$ and $g$ are mutually inverse bijections, as required.

**Proof 2**: (Algebraic). Recall the binomial theorem, which states that for $|x| < 1$, and $a \in R$, we have

$$(1+x)^a = \sum_{j \geq 0} {a \choose j}x^j$$

**Notation**: If $A(x) = \sum_{j \geq a} a_j x^j$, is a polynomial or power series, then
$\lbrack x^k \rbrack A(x) = a_k$. "The coefficient of $x^k$ in $A(x)$ is $a_k$"

The binomial theorem can be restated as

$\lbrack x^k \rbrack (1+x)^a = {a \choose k}$  for all $k \in N$

Consider $(1+x)^{n-1} = \sum_{j \geq 0} {a - 1 \choose j} x^j$

Multiply both sides by $(1+x)$

$$(1+x)^n = (1+x) \sum_{j \geq 0} {a - 1 \choose j} x_j$$
$$=\big\lbrack \sum_{k \geq 0} {a - 1 \choose k} x^k \big\rbrack + x \big\lbrack \sum_{j \geq 0} { a - 1 \choose j} x^j \big\rbrack$$

$$= \big\lbrack \sum_{k \geq 0} {a-1 \choose k} x^k \big\rbrack + \big\lbrack \sum_{j \geq 0} {a - 1 \choose j} x^{j+1}\big\rbrack$$

$$ = \big\lbrack \sum_{k \geq 0} {a - 1 \choose k} x^k \big\rbrack + \big\lbrack \sum_{k \geq 1} {a-1 \choose k-1} x^k \big\rbrack$$

$$= \big\lbrack 1+ \sum_{k \geq 1} {a - 1 \choose k} x^k \big\rbrack + \big\lbrack \sum_{k \geq 1} {a - 1 \choose k - 1} x^k \big\rbrack$$

$$= 1 + \sum_{ k \geq 1} \big\lbrack{a-1 \choose k} + {a - 1 \choose l - 1} \big\rbrack x^k$$

Therefore $\big\lbrack x^k \big\rbrack (1+x)^n = {n - 1 \choose k} + {n - 1 \choose k - 1}$ for $k \geq 1$

But we already saw that $\big\lbrack x^k \big\rbrack = {n \choose k}$. Therefore $n \choose k$ = ${n-1 \choose k} + {n-1 \choose k-1}$ for $k \geq 1$

To finish, check $k = 0$ case.

This works for all $n \in R$ and not just $n \in N$.

## Placeholder

Consider the following:

$a - 1 \choose 0$, $a-1 \choose 1$, $a-1 \choose 2$, $a-1 \choose 3$, $\dots$

Instead, consider the power series

$A(x) = {a - 1 \choose 0}$+ $a-1 \choose 1$ $x$+ $a-1 \choose 2$ $x^2$+ $a-1 \choose 3$ $x^3$+ $\dots$

$xA(x) = {a - 1 \choose 0}x$+ $a-1 \choose 1$ $x^2$+ $a-1 \choose 2$ $x^3$+ $a-1 \choose 3$ $x^4$+ $\dots$

$\lbrack x^k \rbrack (A(x)) + xA(x)) = {a-1 \choose k} + {a-1 \choose k - 1} =$ RHS

$\lbrack x^k \rbrack (A(x)) + xA(x)) =$ LHS.

## Variations on the binomial theorem

$$(1+x)^a = \sum_{k \geq 0} {a \choose k} x^k,\,a \in R, |x| < 1$$

$$(1+x)^n = \sum_{k=0}^n {n \choose k} x^k,\,n \in N$$

Sometimes it's easier to do algebraic manipulations with infinite series.

**Negative binomial theorem:**

$$(1-x)^{-a} = \sum_{k \geq 0} \multiset{a}{k} x^k,\,a \in R, |x| < 1$$

Fibonacci Sequence:

Consider the series $F(x) = f_0 + f_1 x + f_2 x^2 + f_3 x^3 + \cdots$

To relate three consecutive terms, consider $F(x), -xF(x), -x^2 F(X)$

$F(x) = f_0 + f_1 x + f_2 x^2 + f_3 x^3 +  f_4 x^4\cdots$

$-xF(x) = -f_0 x + -f_1 x^2 + -f_2 x^3 + -f_3 x^4 + \cdots$

$-x^2F(x) = -f_0x^2 + -f_1 x^3 + -f_2 x^4 + \cdots$

Summing both sides:

$$F(x) - xF(x) - x^2F(x) = x$$

$$F(x) = \frac{x}{1-x-x^2}$$

Partial fractions: $1 - x - x^2 = (1-\frac{1 + \sqrt{5}}{2} x)(1- \frac{1-\sqrt 5}{2} x)$

$$F(x) = \frac{A}{(1-\frac{1 + \sqrt{5}}{2} x)} + \frac{B}{(1- \frac{1-\sqrt 5}{2} x)}$$

$A = \frac{1}{\sqrt 5}$, $B= - \frac{1}{\sqrt 5}$

Geometric series formula

$$F(x) = \sum_{n \geq 0} \frac{1}{\sqrt 5} \Big(\frac{1 + \sqrt 5}{2}\Big)^n x^n - \sum_{n \geq 0} \frac{1}{\sqrt 5} \Big(\frac{1 - \sqrt{5}}{2}\Big)^n x^n$$

$$f_n = \lbrack x^n \rbrack F(x) = \frac{1}{\sqrt 5} \Big(\frac{1 + \sqrt 5}{2}\Big)^n - \Big(\frac{1 - \sqrt 5}{2}\Big)^n$$

## Lattice Paths

A lattice path of length $r$ is a sequence $P_0,P_1,\dots,P_r \in Z^2 \subset R^2$ of points in the plane such that $P_i - P_{i-1} \in \{(0,1),(1,0)\}$.

**Theorem:**  The number of lattice paths from $(0,0)$ to $(m,n)$ is $m + n \choose n$.

**Proof:** Each path is represented by a string $s_1s_2\dots s_{m+n}$ with $m$ E's and $n$ N's. Let $\alpha = \{i \in \lbrack m + n \rbrack | s_i = E\}$. Then $\alpha$ is an $m$-element subset of $\lbrack m + n \rbrack$.

Verify that this defines a bijection between our lattice paths and $m$-elements subsets of $\lbrack m + n \rbrack$.

## Dyck Paths

A **Dyck** path or Catalan path is a lattice path $P_0,P_1,\dots,P_{2n}, n \in N$, from $(0,0)$ to $(n,n)$ with the property that $P_i = (x_1,y_i)$, where $x_i \leq y_i$.

Path is entirely on or above the line $y=x$. Endpoints on the line.

The trivial path $P_0 = (0,0)$ is a Dyck path (of length $0$).

Another interpretation is using N as left brackets and E as right brackets. The brackets are always balanced and will never have a right bracket as the first element in the set.

**Theorem:** The number of Dyck paths of length $2n$ is $\frac{1}{n+1}{2n \choose n}$.

The numbers $\frac{1}{n+1}{2n \choose n}$,$n \in N$ are called the Catalan numbers.

**Outline of proof**

1. Combinatorial argument. Let $c_n$ be the number of Dyck paths of length $2n$. Obtain a recurrence relation.
2. Algebraic formulation. Consider the series $C(x) = \sum_{m \geq 0} c_n x^n$. Convert the recurrence relation into an algebraic equation involving $C(x)$.
3. Algebraic extraction. Perform algebraic manipulations on $C(x)$ to compute $c_n$.

**Complete proof:**

Consider a Dyck path $\pi$ of length $2n, n \geq 1$. The first step must be N. $\pi$ must end on the line $y=x$. Consider the first time $\pi$ returns to the line $y=x$. Suppose this is after $2k+2$ steps. Then the $(2k+2)^{th}$ step of $\pi$ is E. Let $\pi '$ be the first path of the path before returning to the $y=x$ line, and $\pi ''$ be the second part after returning to the $y=x$ line. Write $\pi=N\pi ' E \pi ''$, where $\pi '$ has length $2k$,$\pi ''$ has length $2(n-k-1)$

$\pi '$ starts and ends on the line $y=x+1$, and never goes below.

$\pi ''$ starts and ends on the line $y=x$, and never goes below.

Hence we have decomposed $\pi = N \pi ' E \pi ''$ where $\pi ', \pi ''$ are Dyck paths. This decomposition is unique.

There are $c_k$ possibilities for $\pi '$, and $c_{n-k-1}$ possibilities for $\pi ''$. Summing over all possibilities for $k$, we obtain the recurrence

$$c_n = \sum_{k=0}^{n-1} c_k c_{n-k-1}, \text{ for } n \geq 1$$.

2. Consider the series $C(x) = \sum_{m \geq 0} c_n x^n$.

**Claim**: $xC(x)^2 - C(x) + 1 = 0$

**Proof of Claim:**

Let $n = j + k + 1$

$$ \begin{align}
xC(x)^2 &= x\left(\sum_{j \geq 0} c_j x^j\right)\left(\sum_{k \geq 0} c_k x^k\right) = \sum_{j \geq 0} \sum_{k \geq 0} c_j c_k x^{j+k+1} \\
&=\sum_{n \geq 1} \left(\sum_{k = 0} c_k c_{n-k-1}\right) x^n = \sum_{n \geq 1} c_n x^n \\
&= C(x) - 1
\end{align}$$

3. Use the quadratic formula to solve for $C(x)$

$$C(x) = \frac{1 \pm \sqrt{1-4x}}{2x} = \frac{1 \pm (1 - 4x)^{\frac 1 2}}{2x}$$

Use the binomial theorem to expand $(1-4x)^{1/2}$

$$(1-4x)^{1/2} = 1 + \sum_{k \geq 1} {1/2 \choose k} (-4)^k x^k$$

$$\begin{align} {1/2 \choose k} (-4)^k &= \frac{\frac 1 2 -\frac 1 2 -\frac 3 2 ...(-\frac{2k-3}{2})}{k!} \cdot (-1)^k \cdot 2^k \cdot 2^k \\
&= - \frac{1 \cdot 3 \cdot 5 \cdots (2k-3)}{k!} \cdot 2^k \\
&= - \frac{1 \cdot 3 \cdot 5 \cdots (2k-3)}{k!} \cdot \frac{2 \cdot 4 \cdot 6 \cdots (2k-2)}{(k-1)!} \cdot 2 \\
&= - \frac{(2k-2)!}{k!(k-1)!} \cdot 2 = - \frac{2}{k} {2k - 2 \choose k - 1} \end{align}$$

$$C(x) = \frac{1 \pm (1 - \sum_{k \geq 1} \frac{2}{k}{2k-2 \choose k-1} x^k)}{2x}$$

$$= \frac{1}{2x} \pm \left(\frac{1}{2x} - \sum_{k \geq 1} \frac{1}{k} {2k-2 \choose k - 1} x^{k-1}\right)$$

The $+$ solution cannot be correct since it gives $\frac{1}{x}$ in $C(x)$. Therefore the $-$ solution is correct.

$$= \sum_{k \geq 1} \frac{1}{k} {2k-2 \choose k - 1} x^{k-1} = \sum_{n \geq 0} \frac{1}{n+1} {2n \choose n} x^n$$

Therefore $c_n = \frac{1}{n+1} {2n \choose n}$.

## Combinatorial Proofs

**Theorem**: The number of Dyck paths of length $2n$ is $\frac{1}{n+1} {2n \choose n}$.

**Combinatorial Proof:** Let $D_n$ be the set of Dyck paths of length $2n$ and let $P_n$ be the set of all lattice paths from $(0,0)$ to $(n,n)$. We give a bijection $f: P_n \rightarrow D_n \times \lbrack n + 1 \rbrack$.

$s_0 s_1 ... s_{2n-2} s_{2n-1}$

$s_1 s_2 ... s_{2n-2} s_{2n-1} s_2n$

$s_2 s_3... s_{2n-1} s_2n s_0$

$\vdots$

$s_{2n} s_0 \cdots s_{2n-3} s_{2n-2}$

Cross out all paths that aren't in $P_n$ to get a list of $n + 1$ paths.

**Claim:** Exactly one path $\pi$ on this list is a Dyck path. If $\pi$ is the $k^{th}$ path on the list, let $f(s_1 s_2 ... s_{2n}) = (\pi,k)$.

From $(\pi,k)$, the path can be cyclically shifted to obtain a path in $P_n$.

**Example:** For the path $NNEENNE$, the list is

NNEENN, NEENNE, EENNEN, ENNENN, NNENNE, **NENNEE**, ENNEEN

so $f(NEENNE) = (NNENEE,3)$.

Each path in the list is a substring of $NNEENNENNEEN$.

----------------------------------------------------
Reach Gouden's notes for complete proof
----------------------------------------------------

**Theorem:** For $0 \leq a \leq b$, the number of lattice paths from $(0,0)$ to $(a,b)$ that are entirely on or above the line $y=x$ is

$${a + b \choose a} - {a + b \choose a - 1}$$

**Combinatorial Proof**: Let $X$ be the set of lattice paths from $(0,0)$ to $(A,b)$ that have at least one point strictly below the line $y=x$. If we can show that $|X| = {a + b \choose a - 1}$, we'll be done. To do this, let $Y$ be the set of lattice paths from $(1,-1)$ to $(a,b)$. We give a bijection between $X$ and $Y$.

Let $s_1s_2 \cdots s_{a+b} \in X$. Since $X$ has at least one point below the line $y=x$, there must be at least one point on the line $y=x-1$. Suppose the first such point is after $2k-1$ steps. Define
$$f(s_1 s_2 \cdots s_{a+b}) = \bar{s_1} \bar{s_2} \cdots \bar{s_{2k-1}} s_{2k} \cdots s_{a+b}$$
where the bar means $\bar{s_{i}} = N$ if $s_i = E$, and vice versa.

**Exercise:** Show that this is a bijection.

## Framework for Generating Functions

**Ingredients:**

- A set $S$ of "combinatorial objects".
- A function $w: S \rightarrow N$ called the weight function. For $\sigma \in S$, $w(\sigma)$ is called the weight of $\sigma$

General counting problem: for $n \in N$, determine the number of objects in $S$ that have weight $n$.

For example: Determine $\# \{\sigma \in S | w(\sigma) = n \}$.

**Note:** The $\#$ represents cardinality $|S|$.

A weight function is good if the answer is finite numbers for all $n$.

**Strategy**: Show (almost) every counting problem we encounter into this framework.

**Example:** Fix $m \in N$. Let $S_m = \{0,1\}^m$, the set of binary strings of length $m$. IF $\sigma \in S_m$, define the weight of $\sigma$ to be the number of $1$'s in $\sigma.$

Counting problem becomes: Determine the number of binary strings of length $m$ that have $n$ ones. (Answer: $m \choose n$)

**Example 2:** Let $T$ be the set of all Dyck paths. If $\pi \in T$, define the weight $\pi$ to be the number of $n$ steps in $\pi$.

Counting problem becomes: Determine the number of Dyck paths of length $2n$. (Answer: $\frac{1}{n+1}{2n \choose n}$)

General solution: Define the generating function for $S$ with respect to $w$ to be the power series

$$\phi_S(x) = \sum_{\phi \in S} x^{w(\sigma)}$$

**Proposition:** The nanswer to the counting problem is $\lbrack x^n \rbrack \phi_S(x)$.

Example: $\#\{\sigma \in S | w(\sigma) = n \} =  \lbrack x^n \rbrack \phi_S(x)$.

**Proof:**

$$\lbrack x^n \rbrack \phi_S(x) = \lbrack x^n \rbrack \sum_{\sigma \in S} x^{w(\sigma)} = \lbrack x^n \rbrack \sum_{k \geq 0} \sum_{\sigma \in S , w(\sigma) = k} x^{w(\sigma)}$$

$$i= \lbrack x^n \rbrack \sum_{ k \geq 0} \left(\sum_{\sigma \in S , w(\sigma)=n} x^k \right) =\sum_{\sigma \in S, w(\sigma) = n} 1 = \#\{\sigma \in S | w(\sigma) = k\}$$

**Example 1:** Fix $m \in N$. Let $S_m = \{0,1\}^m$, the set of binary strings of length $m$. IF $\sigma \in S_m$, define the weight of $\sigma$ to be the number of $1$'s in $\sigma.$

Generating function:

$$\phi_{S_m}(x) = \sum_{n = 0}^m {m \choose n} x^n = (1+x)^n$$

**Example 2:** Let $T$ be the set of all Dyck paths. If $\pi \in T$, define the weight $\pi$ to be the number of $n$ steps in $\pi$.

Generating function:

$$\phi_S(x) = \sum_{n=0}^\infty \frac{1}{n+1} {2n \choose n} x^n = \frac{1 - \sqrt{1 - 4x}}{2x}$$

## The sum lemma

**Sum Lemma:** Let $S$ be a set with a weight function $w$, and $A \cup B = S$, then

$$\phi_S(x) = \phi_A(x) + \phi_B(x) - \phi_{A \cap B}(x)$$

**Proof:** For a subset $A \subset S$, let $Z: S \rightarrow Z$ be the indicator function

$Z(\sigma) = 1 $ if $\sigma \in A$, $0$ if $\sigma \not\in A$

Then $Z_A(\sigma) + Z_B(\sigma) - Z_{a \cap B}(\sigma) = 1$ for all $\sigma \in S$, so

$$\phi_A(x) + \phi_B(x) - \phi_{A \cap B} (x)$$

$$= \sum_{\sigma \in S} Z_A(\sigma)x^{w(\sigma)} + \sum_{\sigma \in S} Z_B(\sigma) x^{w(\sigma)} - \sum_{\sigma \in S} Z_{A \cap B} (\sigma)x^{w(\sigma)}$$

Sum lemma is most commonly used in case where $A \cap B = \emptyset$, in which case $\phi_{A\cap B} (x) = 0$.

**Generalization:** If $S$ is a set with a weight function $w$, and $S = U_i A_i, A_i \cap A_j = \emptyset$ for $i \neq j$, then

$$\phi_S(x) = \sum_i \phi_{A_i}(x)$$

## The Product Lemma

**Example:**

Problem A. You have 5 loonies and 3 toonies. How many ways to make \$ 7?

Make a table of all possibilities using the dollar amounts.
x 0 1 2 3 4 5
0 0 1 2 3 4 5
2 2 3 4 5 6 *7*
4 4 5 6 *7* 8 9
6 6 *7* 8 9 10 11

There are three ways to make \$ 7.

Problem B. Compute $\lbrack x^7 \rbrack(1+x+x^2+x^3+x^4+x^5)(1+x^2+x^4+x^6)$

Solution: Multiply each pair of possible terms and draw out a table

Answer: $\lbrack x^7 \rbrack(1+x+x^2+x^3+x^4+x^5)(1+x^2+x^4+x^6) = 3$

**Product Lemma:**

Sets $A,B$, $\alpha$ weight function on $A$, $\beta$ weight function on $B$. $w$ weight function on $A \times B$. $\gamma \in Z$

$w(a,b) = \alpha(A) \beta(B) \in A \times B$

$\phi_{A \times B}(x) = x^{\gamma} \phi_A(x) \phi B(x)$

**Proof:** $\phi_{A \times B}(x) = \sum_{(a,b) \in A \times B} x^{w(a,b)}$

$$\sum_{a \in A} \sum_{b \in B} x^{\alpha(A) + \beta(B) + \gamma}$$

$$= x^\gamma \left(\sum_{a \in A} x^{\alpha(a)} x^{\beta(b)}\right)$$

$$w(a_1,\dots,a_i) = \alpha_i(a_i) + \gamma, \qquad \forall (a,b) \in A \times B$$

then

$$\phi_{A_1 x \dots A_k x}(x) =x^\gamma \prod_{i=1}^k \phi_{A_i}(x)$$

## Compositions of an Integer

Problem: $n,k \in N$. Determine the number of $(c_1,\dots, c_k) \in N$ such that $c_1 + c_2 + \cdots + c_k = n$

$N^k = N\times N \cdots \times N$

Set of objects: $N^k$

Weight function: $w: N^k \rightarrow N$

$$w(c_1,\dots,c_k) = c_1 + \cdots + c_k$$

Define $\gamma: N \rightarrow N$ weight function

$\alpha(i) = i$

Then  $w(a_1, \dots, a_i) = \sum_{i=1}^k \alpha(a_i)$


Then $\phi_N(x) = 1 + x + x^2 + \cdots = (1-x)^{-1}$

Answer = $\lbrack x^n \rbrack \phi_N (x) = \lbrack x^n \rbrack (1-x)^{-k} = \multiset{k}{n} = \multiset{n+k-1}{n}$

A composition of $n$ with $k$ parts is a $k$-tuple, $(c_1,\dots,c_k) = (N \geq 1)^k$ such that $c_1 + c_2 + \cdots + c_k = n$

- $c_1,\dots,c_k$ are called the parts
- There is a unique composition of $0$, it has $0$ parts.

---------------------------------------------
Problem: Determine the number of compositions in $n$ with $k$ parts.

Set of objects: $(N \geq 1)^k$

Weight function: $w: (N \geq 1) \rightarrow N$
------------------------------------

Consider $1+1+1 \cdots + 1) = n$

Change $k-1$ plus signs into $,$

-------------------------------

Determine all compositions of $n$ with an even number of parts.

Solution: Let $S$ be the set of all compositions with even number parts, and

Define the weight of a composition to be the sm of its parts.

Let $N_{\text{odd}}$ represent the set of all odd numbers.

Then $S = (N_{\text{odd}})^0 \cup (N_{\text{odd}})^2 \cup (N_{\text{odd}})^4 \cup \dots$

$= \bigcup_{k=0}^n (N_{\text{odd}^{2k}})$

$\phi_S(x) = \sum_{k=0}^n \phi_{N_{\text{odd}}^{2k}}(x)$

$=\phi_{N_{odd}}

=\frac{1}{1-x^2(1-x^2)^{-2}}$

$= \lbrack x^n \rbrack \frac{1}{1-x^2(1-x^2)^{-2}}$

-------------------

If $S$ is a finite set, $\phi_S(x)$ is a polynomial

If $S$ is an infinite set, then $\phi_S (x)$ is a power series.

In some problems the radius of convergence could be $0$. In some problems $\phi_S ' (p)$ for $p \in \lbrack 0,1)$ computes an expected value.

## Formal Power Series

Construct a framework to work with power series without worrying about the radius of convergence.

Redefine everything that doesn't include the traditional concept of a limit.

$$A(x) = \sum_{n \geq 0} a_n x^n = a_0 + a_1 x + a_2 x^2 + \cdots$$

where $a_0,a_1,\dots$ are real n umbers

The difference is in the interpretation and allowable operations.

$R\lbrack \lbrack x \rbrack \rbrack$ denotes the set of formal power series with real coefficients.
This a commutative ring returning

$A(X) = \sum_{n \geq 0} a_n x^n \qquad B(x) = \sum_{n \geq 0} b_n x^n$

Addition

$A_(x) + b(x) = \sum_{n \geq 0} (a_n + b_n) x^n$

Multiplication

$A(x)B(X) = \sum_{n \geq 0} \left( \sum_{k=0}^n a_k b_{n-k}\right) x^n$

Additive and multiplicative identities

$0 = \sum_{n \geq 0} 0x^n \qquad 1 = 1 + \sum_{n \geq 1} 0 x^n$

Other operations:

Coefficient extraction:

$\lbrack x^n \rbrack A(x) = a_n$

Scalar multiplication:

$cA(x) = \sum_{N \geq 0} (cA_n) x^n, c \in R$

Formal derivative (satisfies usual derivative rules):

$$\frac{d}{dx} A(x) = \sum_{n \geq 0} na_n x^{n-1} = \sum_{n \geq 0} (n + 1) a_{n+1} x^n$$

Formal integral, satisfies usual anti derivative rules:

$$ I_A A(x) = \sum_{n \geq 0} \frac{a_n}{n+1} x^{n+1} = \sum_{n \geq 1} \frac{a_{n-1}}{n} x^n$$

Sometimes we can substitute. Two cases where $A(B(x))$ is allowed.

1. If $A(x) = \sum_{m=0}^d a_n x^n$ is a polynomial of degree $d$, then we an define

$$A(B(x)) = \sum_{n = 0}^d a_n B(x)^n$$

...which makes sense because we only need to perform finitely many basic operations.

2. If $\lbrack x^0 \rbrack B(x) = 0$, then define

$$A(B(x)) = \sum_{n \geq 0} a_n B(x)^n$$

Key point: IF we want to know $\lbrack x^m \rbrack A(B(x))$, then $B(x)^n$ won't contribute for $n > m$, so $\lbrack x^m \rbrack A(B(x)) = \lbrack x_m \rbrack \sum_{n=0}^m a_n B(x)^n$. Can pretend $A(x)$ is a polynomial.

In all other cases $A(B(x))$ is not defined. Can't substitute numbers.

**Theorem:** $A(X) \in R\lbrack \lbrack x \rbrack \rbrack$ has a multiplicative inverse iff $\lbrack x^0 \rbrack A(x) \neq 0$

**Proof:** First suppose $\lbrack x^n \rbrack A(x) = 0$.  Then $\lbrack x^0 \rbrack A(x) B(x) = 0$ for any $B(x)$, so we can't have $A(x) B(x) = 1$.

Now suppose $\lbrack x^0 \rbrack A(x) = a_0 \neq 0$. Let $f(x) = a_0 - x$. This has a multiplicative inverse $g(x) = \sum_{n \geq 0} a_0^{-n-1} x^n$, ie

$f(x)g(x) = 1$

Let $B(x) = a_n - A(x)$. Since $\lbrack x^0 \rbrack B(x) = 0$, we can substitute $B(x)$ into the equation above to get

$$f(B(x))g(B(x)) = 1$$

But $f(g(x)) = A(x)$ so $g(B(x)) = A(x)^{-1}$

## Catalan Numbers (again)

From Dyck paths, where does the equation $xC(x)^2 - C(x) + 1 = 0$?

Let $S$ be the set of all Dyck paths, with weight function $w: S \rightarrow N$, $w(\pi)$ is the number of $N$ steps in $\pi$. Then $C(x) = \phi_S(x)$

The combinatorial decomposition argument shows that there is a bijection

$S \times S \rightarrow S \setminus \{\varepsilon\} \qquad (\pi ',\pi '') \rightarrow N\pi ' E\pi ''$$

where $\varepsilon$ denotes the trivial path of length $0$.

This suggests we should define a weight function $W$ on $S \times S$

$$W(\pi',\pi'') = w(N\pi ' E\pi '')$$

Then from the bijection, we have

$\phi_{S \times S} (x) - \sum_{S \times S} x^{W(\pi ',\pi '')} = \sum_{\pi \in S \setminus \{\varepsilon\}} x^{w(\pi)} = C(x) - 1$

On the other hand, $W(\pi ', \pi '')=w(\pi ') + w(\pi '') + 1$, so we can use the product lemma to obtain

$\phi_{S \times S}(x) = x\phi_S(x)^2 = xC(x)^2$

Putting these together gives $xC(x)^2 = C(x) - 1$

### Steps for using Generating Functions

- Introduce the objects you want to consider, and the weight function (its solution will solve the initial problem)
- Find bijection or decomposition of set
- Define weight functions on any new sets
- Check that the weight of a composite object should be the sum of its weights (to use the product lemma)
- Write corresponding generating function equations
- Solve (Algebra)

## The crazy dice Problem

If you have an ordinary pair of 6 sided dice, the probabilities of rolling any given total can be determined by drawing a table.

**Problem:** Is it possible to replace the numbers on the dice with different positive integers, without affecting this probability table?

Let $S$ be the set of sides of an ordinary 6 sided die. Define the weight of $\pi \in S$ be the number written on the side $\pi$. Then

$\phi_S(x) = x + x^2 + x^3 + x^4 + x^5 + x^6$


The set of possible ways to roll a pair of ordinary dice is $S \times S$. Define the weight to be the total of the two numbers rolled. Then $\phi_{S \times S}(x) = \phi_S(x)^2$. This generating fuction tells us how many ways here are to roll each total, and hence determines the probability table.

Now suppose $A,B$ are the set of sides of two crazy dice, and the weight is the number written on the side. (eg 1,2,4,4,4,9) results in $\phi_S(x) = x+x^2 + 3x^4 + x^9$

In this case, the generating function for rolling the pair is $\phi_A(x) \phi_B(x)$, and this determines the probability table. Therefore, what we're trying to achieve is $\phi_A(x) \phi_B(x) = \phi_S(x)^2$

Now factor $\phi_S(x)^2$ and redistribute the factors.

$\phi_S(x) = x(x+1)(x^2 + x + 1)(x^2 - x + 1)$

Now since all our dice are 6 sided. $\phi_A(1) = \phi_B(1) = 6$. This means that we need a factor of $(x+1)(x^2 + x + 1)$ in both $\phi_A(x)$ and $\phi_B(x)$. Since the numbers on each die must be positive integers, we need a factor of $x$ in both. Therefore the only possibility to try Inverse

$\phi_A(x) = x(x+1)(x^2+x+1) = x + 2x^2 + 2x^3 + x^4$

$\phi_B(x) = x(x+1)(x^2+x+1)(x^2-x+1)^2 = x + x^3 + x^4 + x^5 + x^6 + x^8$

Crazy dice exists. The first die has sides $1,2,2,3,3,4$ and second die has sides $1,3,4,5,6,8$.

## Cyclotomic polynomials

How did I factor $\phi_S(x)$? Using the finite geometric series formula, $\phi_S(x) =x(x^6-1)/(x-1)$.

**Theorem:** There exists polynomials $\phi_B(X) \in Z\lbrack x \rbrack, n \geq 1$, called the cyclotomic polynomials satisfying

- $x^n - 1 = \prod_{d/n} \phi_d(x)$
- $\phi_B(x) = \prod_{d/n} (x^d - 1)^{\mu(n/d)}$, where $\mu(.)$ is the Mobius function
- $\phi_n(x) = \prod_{0 < k < n, gcd(k,n)=1} (x-e^{2\pi(k/n)})$ in $C\lbrack x \rbrack$

**Sketch of Proof:** Use iii as definition. Check that i holds; by Mobius inversion, so does ii. iii shows that $\phi_n(x) \in C\lbrack x \rbrack$, and ii shows that $\phi_n(x)$ is a ratio of moonic polynomials in $Z\lbrack x \rbrack$. Together, these imply $\phi_n(x) \in Z\lbrack x \rbrack$

## Partitions of an Integer

A partition of $n$ with $k$ parts is a $k$-tuple $\lambda = (\lambda_1,\dots,\lambda_) \in (N_{\geq 1})^k$, of positive integers such that

$\lambda_1 \geq \lambda_2 \geq \cdots \geq \lambda_k$

and

$\lambda_1 + \lambda_2 + \cdots + \lambda_k = n$

A partition is a composition in which the parts are in weakly decreasing order.

$n$ is called the size of $\lambda$; we write $\|\lambda| = n$, or $\lambda \vdash n$.
$k$ is called the length of $\lambda$, we write $l(\lambda)=k$

**Problem:** For $m,n\in N$, determine the number of partitions of $n$, in which all parts are $\leq m$.

**Solution:** Let $P_m$ denote the set of all partitions in which all parts are $\geq m$. Define the weight of a partition to be its size:

$w(\lambda) = \lambda_1 + \lambda_2 + \cdots + \lambda_k$

Let $S_m = N \times 2N \times 3N \cdots \times mN$, with weight function

$w:S_n \rightarrow N$, $w(c_1,\dots,c_m) = c_1 + c_2 + \cdots + c_m$

We give a bijection $\phi:P_{\lambda_i \leq m} \rightarrow S_m$. If $\lambda = (\lambda_1,\dots,\lambda_k) \in P_m$ define $\phi(\lambda) = (c_1,\dots,c_m)$ where

$c_i = \sum_{j \in \lbrack k \rbrack, \lambda_j=i} \lambda_j$

Inverse map: $c_i$ is the number of parts equal to $i$ in $\lambda$.

Example $m=7,\lambda=(6,6,6,3,2,2), \phi(\lambda) = 0,4,3,0,0,18,0)$

Note that $w(\lambda) = w(\phi(\lambda))$. $\phi$ is a weight preserving bijection, therefore $\phi_{P_m}(x) = \phi_{S_m} (x)$

To compare a $\phi_{S_m} (x)$, define a weight function $\alpha_i: iN \rightarrow N$, $\alpha_i(c) = c$. Then

$w(c_1,\dots,c_m) = \alpha_1(c_1) + \cdots + a_m (c_m)$

so we can use the product lemma.

$$\phi_{S_m}(x) = \prod_{i=1}^m \phi_{iN}(x) = \prod_{i=1}^m (1-x^i)^{-1}$$

Therefore the number of partitions of $n$ with all parts $\leq m$ is

$$\lbrack x^n \rbrack \prod_{i=1}^m (1-x^i)^{-1}$$

There is no sensible way to simplify this answer.

**Problem 2:** For $m,n \in N$, determine the number of partitions of $n$, with length $\leq m$.

**Solution:** Let $S_m '$ be the set of partitions with length $\leq m$. The weight of a partition is its size.

The ferrers diagram of $\lambda$ is a left justified array of boxes, with $\lambda_j$ boxes in row$j,j \in \lbrack k \rbrack$

Eg: $\lambda=6632$
```
XXXXXX
XXXXXX
XXX
XX
```

The size of $\lambda$ is the number of boxes. The length of $\lambda$ is the number of rows.

In the previous problem, we defined a bijection between $P_m$ and $S_m$ in terms of the Ferrers diagram, $c_i = i \cdot$ #(rows of length $i$). Works because diagram has at most $m$ columns.

In this problem, we use columns of Ferrers diagram instead. Define a bijection between $P_m'$ and $S_m: c_i = i \cdot$ #(columns of length $i$). Works because diagram has at most $m$ rows.

Conclusion: Problem 2 has the same answer as Problem 1.

Alternate argument: There is a weight preserving bijection between $P_m$ and $P_m '$ obtained by reflecting the Ferrers diagram on its diagonal. The partition obtained from $\lambda$ in this way is called the conjugate of $\lambda$, denoted $\bar{\lambda}$. Conjugation does not change the size of a partition.

**Problem 3:** Determine the number of partitions of $n$

**Solution:** Let $m \geq n$. Then every partition of $n$ has all parts $\leq m$ and length $\geq m$. So by Problem 1 or 2, the anwer is

$$\lbrack x^n \rbrack \prod_{i=1}^m (1-x^i)^{-1}$$

Since this is true for every $m \geq n$, we write the answer as

$$\lbrack x^n \rbrack \prod_{i=1}^\infty (1-x^i)^{-1}$$

Informally $\infty$ means any large enough number will give the right answer.

## Infinite products of formal power series

Let $A_1(x),A_2(x),\cdots \in R\lbrack \lbrack x \rbrack \rbrack$. We say that

$$a_n = \lbrack x^n \rbrack \prod_{i=1}^\infty A_i(x)$$

if there exists $n \in N$ such that for all $m \geq N$ we have

$$a_n = \lbrack x^n \rbrack \prod_{i=1}^m A_i(x)$$

If $a_n$ exists for all $n \in N$, we say that $\prod_{i=1}^\infty A_i(X) = \sum_{n \geq 0} a_n x^n$

Example: Compute $\prod_{i=1}^\infty (1+x^{2^{i-1}})$

$\prod_{i=1}^m (1+x^{2^{i-1}}) = 1 + x + x^2 + x^2 + \cdots + x^{2^m - 1}$, so for $m > \log_2(n)$

$\lbrack x^n \rbrack \prod_{i=1}^m (1+x^{2^{i-1}})=1$

Therefore $\prod_{i=1}^\infty (1+x^{2^{i-1}}) = \sum_{n \geq 1} 1x^n = (1-x)^{-1}$

**Example:** Show that the number of partitions of $n$ with all parts odd is equal to the number of partitions of $n$ with all parts distinct.

Let $\sigma$ be the set of partitions with odd parts. Let $D$ be the set of partitions with distinct parts. IN each case, define the weight of a partition to be its size. Using the previous technique:

$\phi_\sigma(x) = \prod_{j=1}^\infty (1-x^{2j-1})^{-1} \qquad \phi_D(x) = \prod_{i=1}^\infty (1+x^i)$

We want to show that $\lbrack x^n \rbrack \phi_\sigma (x) = \lbrack x^n \rbrack \phi_D(x)$. To see this, multiply by $A(x) = \prod_{i=1}^\infty (1-x^{2i})^{-1}$

$$A(x) \phi_D(x) = \prod_{i=1}^\infty (1-x^{2i-1})^{-1} (1-x^{2i})^{-1} = \prod_{j=1}^\infty (1-x^i)^i$$

$$A(x) \phi_D(x) = \prod_{i=1}^\infty \frac{1+x^i}{1-x^{2i}} = \prod_{i=1}^\infty (1-x^i)^{-1}$$

Thus $A(x) \phi_D(x) = A(x) \phi_D(x)$, and hence $\phi_\sigma(x) = \phi_D(x)$

## More than one weight function
Let $S$ be a set of combinatorial objects, and suppose $w_1$ and $w_2$ are two weight functions on $S$. The multivariate generating function for $S$ with respect to $w_1$ and $w_2$ is

$$\phi_S(x,y) = \sum_{\sigma \in S} x^{w_1(\sigma)} y^{w_2(\sigma)}$$

Associated counting problem: For $m,n \in N$, how many objects in $\sigma \in S$ are there with $w_1(\sigma) = m$ and $w_2(\sigma) = n$

There is same as one weight function

- Answer to counting problem is $\lbrack x^m y^n \rbrack \phi_S(x,y)$
- Sum lemma (basically same)
- Product lemma (basically same)
- Specializations (basically same)

Consider $F(x,y) = 1 + 3x + 5xy^2 - yx^2 = 1 + (3 + 5y^2)x - yx^2$

$\lbrack xy^2 \rbrack F(x,y) = 5$

$\lbrack x \rbrack F(x,y) = 3$ or $3 + 5y^2$?

It's legitimately ambiguous, but we define it to mean the latter. If $A(x,y)$ is a formal power series in two variables

$$\lbrack x^n \rbrack A(x,y) = \sum_{m \geq 0} (\lbrack x^n y^m \rbrack A(x,y)) y^m$$

which is a formal power series in one variable.

Use the notation $\lbrack x^n y^0 \rbrack A(x,y)$ to mean the other one.

Sum lemma: Let $S$ be a set with weight functions $w_1$ and $w_2$, and $A \cup B = S$, then

$\phi_S(x,y) = \phi_A(x,y) + \phi_B(x,y) - \phi_{A \cap B} (x,y)$

Product lemma: Suppose $A$ and $B$ are sets and

- $\alpha_1$ and $\alpha_2$ are weight functions on $A$
- $\beta_1$ and $\beta_2$ are weight functions on $B$
- $w_1$ and $w_2$ are weight functions on $A \times B$
- $\gamma_1, \gamma_2 \in Z$ are constants

if $w_1(a,b) = \alpha_i(a) + \beta_i(b) + \gamma_i$ for all $\alpha \in A, \beta \in B, i = 1,2,$ then

$\phi_{A \times B}(x,y) = x^{\gamma_1} y^{\gamma_2} \phi_A(x,y)\phi_B(x,y)$
