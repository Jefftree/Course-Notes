# MATH 249 - Rip

<!--Multiset Definiton-->
$$\def\multiset#1#2{\left(\!\left({#1\atopwithdelims..#2}\right)\!\right)}$$


## 2C: At most one ball per box, boxes indistinguishable.
$1$ if $k \leq n, 0$ otherwise

$$x^{\underline{k}} = x(x-1)(x-2)..(x-k+1)$$

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

Idea: $c_i$ is the number of balls in the i-th box
Since there is at least one ball per box, $c_i$ is a positive integer
Note: 1B can be interpreted in a similar war.

## 3D At Least one ball per box, balls and boxes indistinguishable
**Interpretation**: Partitions of an integer

How many ways are there to write
$$k = c_1 + c_2 + ... + c_n$$
where $c_i,...,c_n$ are positive integers and $c_1 \geq ... \geq c_n$

**Idea**: $c_1$ is the number of balls in the box with the larger number of balls, and so on. (because balls are indistinguishable)

1D is related to this as well

