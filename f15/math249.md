<!--Multiset Definiton-->
$$\def\multiset#1#2{\left(\!\left({#1\atopwithdelims..#2}\right)\!\right)}$$

# MATH 249

Combinatorics include enumeration and graph theory.

## Enumeration

The **cardinality** of a set $A$, denoted as $|A|$ is the number of elements it contains if it is finite, or something else if it's infinite.

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

A. Balls distinguishable, boxes distinguishable
B. Balls indistinguishable, boxes distinguishable
C. Balls distinguishable, boxes indistinguishable
D. Balls distinguishable, boxes indistinguishable

## 2C: At most one ball per box, boxes indistinguishable.
$1$ if $k \leq n, 0$ otherwise

$$x^{\underline{k}} = x(x-1)(x-2)...(x-k+1)$$

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

**Interpretation** If $n,k$ are integers, then $n \choose k$ is the number of $k$-element subseteqs of an $n$-element subseteq.

## 1B: No restriction, balls indistinguishable

**Interpretation**: $k$-element multisets from an $n$-element set.

Example: If $n=2,k=4$, there are $5$ $k$-element multisets from $N={a,b}:$
$$\{a,a,a,a\},\{a,a,a,b\},\{a,a,b,b\},\{a,b,b,b\},\{b,b,b,b\}$$

**Notation:** Define $\multiset{n}{k}= \frac{n^\underline{k}}{k!}= {n+k-1 \choose k}$

**Theorem**: Answer to 1B is $\multiset{n}{k}$

**Proof:** Assume that $N = {1,2,...,n}$. Let $X$ be the set of $k$-element multisets from ${1,2,...,n}$. Let $Y$ be the set of $k$-element subseteq of ${1,2,...,n+k-1}$.
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
Example: $\{\{1,4\},\{2,5,6\},\{3\},\{7\}\}$ is a partition of $\{1,2,3,4,5,6,7\}$ into four subseteqs.

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
$$\frac{1}{n!} = 0$, and ${x \choose n} = 0$$

## Combinatorics vs Algebra

**Theorem**: ${n \choose k} = {n-1 \choose k} + {n-1 \choose k-1}$ for $k,n \in N$

**Proof 1**: (Combinatorics), Let $X = \{$ k-elem subseteqs of $\lbrack n \rbrack\}.$ Let $Y = \{ k$ or $(k-1)$ elem. subseteqs of $\lbrack n-1 \rbrack\}.$ Then LHS = $|X|$ and RHS = $|Y|$. We prove the identity by giving a bijection between X and Y.

Define $f: X \rightarrow Y$ as follows. Given $A \in X, $ a k elem subseteq of $\lbrack n \rbrack$. Let $f(A) = A \\ \{n\}$. Then $f(A) \subseteq \lbrack n-1 \rbrack$ has a $k$ or $k-1$ elements so $f(A) \in Y$.

Define $g: Y \rightarrow X$ as follows. Given $B \in Y$, let

$g(B) = B$ if $|B| =k$

$g(B) = B \cup \{n\}$ if $|B| = k-1$

In either case $|g(B)| = k$, and $g(B) \subseteq \lbrack n \rbrack$, so $g(B) \in X$.

Verify that $g(f(A)) = A$, for $A \in X$

Case 1: $n \not\in A$, then $f(A) = A \\ \{n\} = A$, and $|f(A)| = k$, so $g(f(A)) = A$

Case 2: $n \in A$, then $|f(A)| = k-1$, so $g(f(A)) = (A \\ \{n\}) \cup \{n\} = A \cup \{n\} - A$

Verify that $f(g(B)) = B$, for $B \in Y$
Case 1: $|B| = k$, then $g(B) = B$, and $n \not\in B$, so $f(g(B)) = f(B) = B$

Case 2: $|B| = k-1$, since $n \not\in B$, we have $f(g(B)) = (B \cup \{n\}) \\ \{n\} = B \\ \{n\} = B$

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
$$=\big\lbrack \sum_{k \geq 0} {a - 1 \choose k} x^k \rbrack + x \lbrack \sum_{j \geq 0} { a - 1 \choose j} x^j \rbrack$$

$$= \lbrack \sum_{k \geq 0} {a-1 \choose k} x^k \rbrack + \lbrack \sum_{j \geq 0} {a - 1 \choose j} x^{j+1}\rbrack$$

$$ = \lbrack \sum_{k \geq 0} {a - 1 \choose k} x^k \rbrack + \lbrack \sum_{k \geq 1} {a-1 \choose k-1} x^k \rbrack$$

$$= \lbrack 1+ \sum_{k \geq 1} {n - 1 \choose k} x^k \rbrack + \lbrack \sum_{k \geq 1} {a - 1 \choose k - 1} x^k \rbrack$$

$$= 1 + \sum_{ k \geq 1} \lbrack{a-1 \choose k} + {a - 1 \choose l - 1} \rbrack x^k$$

Therefore $\lbrack x^k \rbrack (1+x)^n = {n - 1 \choose k} + {n - 1 \choose k - 1}$ for $k \geq 1$

But we already saw that $\lbrack x^k \rbrack = {n \choose k}$. Therefore $n \choose k$ = ${n-1 \choose k} + {n-1 \choose k-1}$ for $k \geq 1$

To finish, check $k = 0$ case.
