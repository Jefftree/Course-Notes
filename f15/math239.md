
$\{b_n\}_{n \geq 0}$ defined by $b_n - 3b_{n+1} + 4b_{n-3} = 3 (2)^n$

Guess a relation? Try $A$, $Bn$, $Cn^2$

$Cn^2$ gives $cn^2 2^n - 3C(n-1)^2 2^{n+1} + 4C(n-3)^3 2^{n-3} = 3C2^n$

Select $C = 1$. QED

Eg.

Sequence $\{a_n\}_{n \geq 0}$ defined by $a_n - 5a_{n-1} + 6a_{n-3} = 3^n$

Multiply by $x^n$ and sum over $n \geq 2$

$\sum_{n \geq 2} (a_n - 5a_{n-1} + 6a_{n-3})x^n = \sum_{n \geq 2} 3^nx^n = 9x^2 \sum_{n \geq 0} 3^n x^n = \frac{9x^2}{1-3x}$

$\sum_{n \geq 2} a_n x^n - 5x \sum_{n \geq 2} a_{n-1}x^{n-1} + 6x^2 = \sum_{n \geq 2} a_{n-2} x^{n-2} = \frac{9x^2}{1-3x}$

Let $g(x) = \sum_{n \geq 0} a_n x^n$


## Graph Fun

Graph consists of a finite set of vertices, and finite set of edges. Each edge is a subset of the vertex at $V$ of size 2.

Multigraph incorporates multisets for edges.

Edge incident to vertex means edge contains vertex.

Degree of a vertex is the number of edges it includes.

Vertex of degree 0 is an isolated vertex.

An **isomorphism** from a graph $G$ to a graph $H$ is a bijection $f:V(A) \rightarrow V(H)$ with the additional property that $VW$ is an edge of $G$ iff $f(V)f(W)$ is an edge of $H$. (Look the same except with different labels as vertices)

$G$ is isomorphic to $H$ iff there exists an isomorphism from $G$ to $H$.

To show isomorphism, define a bijection between two graphs, and redraw graph to look similar to show edges match.

A **r-regular graph** is one where all vertices have degree $r$.

No $3$-regular graph on $5$ vertices.

**Theorem**

$$\sum_{v \in V(G)} \text{deg}(G) = 2 | E(G) |$$

Each edge contributes $2$ ti the sum of the degrees.

Sum of degrees in any graph must be even.

**Handshake Lemma**: The number of vertices of odd degree in a graph is even.

The degree sequence of a graph $G$ is a list of all $|V(G)|$ degrees of vertices in $G$ in increasing order.

If graphs $G$ and $H$ have different degree sequences, then they are not isomorphic.

Same degree sequence does not imply isomorphism.

The **complete** graph $K_p$ is the graph with $p$ vertices and all possible edges. Every pair of vertices are connected by an edge.

$|E(K_p)| = {p \choose 2}$

A graph $G$ is bipartite if $V(G)$ has a partition $A \cap B$ such that every edge has one vertex in $A$ and one vertex in $B$.

The complete bipartite graph $K_{p,m}$ is the bipartite graph with $|A| = p$, $|B| =m$ and $E(K_{p,m}) = \{ab: a \in A, b \in B\}$

The n-cube $Q_n$ has vertex set $\{0,1\}^n$. The set of all binary strings of length $n$. Two binary strings are joined by an edge of $Q_n$ if and only if they differ in exactly one position. (eg $(0,1),(1,1)$)

The 3-cube $Q_3$ is bipartite because you can partition the vertices to $A$ and $B$ such that the definition follows.

$Q_n$ is bipartite with

$$A = \{ \sigma \in \{0,1\}^n: \sigma \text{ has an even number of $1$s}\}$$

$$B = \{ \sigma \in \{0,1\}^n: \sigma \text{ has an odd number of $1$s}\}$$

## Kneser graph

The Kneser graph with parameters $n$ and $k$ has vertex set: The set of all $k$-subsets of $\lbrack n \rbrack$

Two subsets $U$ and $V$ are adjacent if and only if $U \cap V = \emptyset$

Number of vertices for this graph is $n \choose k$

A Kneser graph is regular for every $n$ and $k$ with degree $n - k \choose k$.

Number of edges is $\frac{1}{2} {n \choose k} {n - k \choose k}$

**Example:** Make a list of all bipartite graphs with $4$ vertices up to isomorphism.

Start with $4$ vertices in $A$ and $0$ vertices in $B$, and connect the dots. Decrease vertices in $A$ and add vertices to $B$. Don't include any isomorphic graphs.

Only need to go up to $2$ vertices in both $A$ and $B$ because $1$ in $A$ and $3$ in $B$ Will be isomorphic to $3$ in $A$ and $1$ in $B$.

**Definition:** A **walk** in a graph $H$ is a sequence of vertices and edges. $v_0 e_1 v_1 e_1 \cdots e_n v_n$. Usually just write list of vertices because edges are determined by them.

The length of the walk is $n$. (Starting vertex is not counted)

**Definition:** A **path** in $G$ is a walk in which all the vertices are distinct. Other properties same as walk.

**Definition**: A **cycle** in $G$ is a path that ends at the starting vertex.

Cannot have cycle of length $1$ and $2$

## Showing graphs are not isomorphic

- Find a property of graphs that is independent of the vertex labelling on which the two graphs differ
    + Eg: # of vertices and edges
    + Degree sequence
    + Cycle length
    + Subgraphs

A subgraph $H$ of $G$ is called **spanning** if $V(H) = V(G)$

A spanning cycle is called a Hamilton cycle.

A graph $G$ is said to be **connected** if for all $x,y \in V(G)$ there is a path on $G$ from $x$ to $y$.

If a graph is not connected, it is **disconnected**.

A maximal connected subgraph of $G$ is called a **component**:

- $H$ is connected
- $H$ is a subgraph of $G$
- $H$ is not contained in a larger connected subgraph of $G$

**NOTE:** If $G$ is connected, then its only component is itself.

**Lemma:** Suppose $x$ and $y$ are vertices in graph $G$ and there exists a walk from $x$ to $y$. Then there exists a path from $x$ to $y$.

**Proof:** Induction. If $W = v_0v_1\cdots v_n$ is a walk from $x = v_0$ to $y=v_n$, then there exists a path from $x$ to $y$

BC: At $x=0$, $x=y$ and there is a path of length $0$ from $x$ to $y$.

IH: If there is a walk of length $<n$ from $x$ to $y$, then there is a path from $x$ to $y$

IC: Let $w=v_0 v_1 \cdots v_n$ be awalk from $x$ to $y$. If $w$ is a path, we're done. Otherwise there is a repeated vertex $v_i = v_j$ from $i < j$. Then $w = v_1 v_i v_{j+1} \cdots v_n$ is a walk of length $<n$ from $x$ to $y$.

By IH, there exists a path from $x$ to $y$

**Corollary:** If there is a path from $x$ to $y$ and a path from $y$ to $z$, then there is a path from $x$ to $z$.

-----------------

To show a graph is connected, show that every pair $x,y$ of vertices in $G$ are joined by a path

To show a graph $G$ is not connected, show there exists a proper subset $X \in V(G)$ that introduces an empty set.

An Euleran circuit in a graph $G$ is a walk such that $w$ contains every edge of $G$ exactly once.

Note that if $G$ has an Euleran circuit $w$, then $w$ defines a pairing of the edges to each vertex.

**Definition:** A graph $G$ is called even if every vertex has even degree.

**Theorem:** A connected graph $G$ has an Euleran circuit if and if if it is even.

**Proof:** Prove by induction on $m = | E(G)|$ that every even connected graph $G$ with $m$ edges has an Euleran circuit.

BC: $m=0$ Then $G$ has at most one vertex and no edges. This is an Euleran circuit of length $0$.

IH: Assume $m \geq 1$, and every even connected graph $G$ with fewer than $m$ edges has an Euleran circuit.

IC: Let $G$ be an even connected graph with $m$ edges. Since $G$ is connected, $deg(v) \geq 1$ for every $v \in G$

Since $G$ is even and $deg(v) \geq 1$, then $deg(v) \geq 2$

Then $G$ contains a cycle $C$.

Then the graph $G - E(C)$ obtained by removing the edges of $C$ from $G$

The graph obtained from this is still even and contains fewer than $m$ edges. Then each of the components $U_1 \cdots U_t$ of $G - E(C)$ is a connected even graph with fewer than $m$ edges.

Hence each $U_i$ has an Euleran circuit $w_i$ by IH. Since $G$ is connected, each $U_i$ shares a vertex $a_i$ with $C$. Then we can form an Euleran circuit  for $G$ by inserting $w_i$ at $a_i$ in $C$ for each $i$.

**NOTE:** This is an efficient algorithm to find an Euleran circuit.

**Definition:** Let $G$ be a connected graph. An edge $e$ of $G$ with property that $G-e$ is disconnected, is called a **bridge** of $G$.

**Lemma:** Let $G$ be a connected graph where the bridge $xy$. Then $G - xy$ has exactly two components. They are $C_x$ containing $x$ and $C_y$  containing $y$.

**Proof:** Let $C_x$ denote the component of $G=xy$ containing $x$. By definition of a bridge. $G-xy$ has at least two components.

Suppose $z \in V(G)$ is not in $G_x$ There was a path in $G$ from $x$ to $z$, but there is no path in $G - xy$ from $x$ to $z$.

Then this path $P$ must have contained the edge $xy$. Therefore $yv_1v_2\cdots z$ shows that $z$ is in the same component as $y$ in $G-xy$. Hence $G-xy$ has two components $C_x, C_y$.





