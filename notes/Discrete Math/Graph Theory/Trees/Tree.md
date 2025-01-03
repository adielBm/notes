- A **tree** (or **free tree**) is an undirected graph $G=(V,E)$ that satisfies any of the following equivalent conditions:
	- $G$ is connected, acyclic (contain no cycles)
- Let $G=(V,E)$ be an undirected graph with finite number of vertices.
	- Any two of the following statements imply the third:
		- $G$ is connected
		- $G$ is acyclic
		- $|E|=|V|-1$
	- The following statements are equivalent:
		- $G$ is **tree**
		- $G$ has no simple cycles, and $|E|=|V|-1$
		- $G$ is connected, and $|E|=|V|-1$
- A **rooted tree** is a tree in which one vertex has been designated as the **root**
	- A vertex $v$ is the **parent** of a vertex $u$ if the edge $(v,u)$ is in the path from the root to $u$, In this case $u$ is a **child** of $v$.
	- A vertex $w$ is a **descendant** of a vertex $v$ if $v$ is in the path from the root to $w$. In this case, $v$ is an **ancestor** of $w$.
	- A **leaf** is a vertex of degree 1 that is not the root. Equivalently, a leaf is a vertex that has no descendants.

- (q2.3) A tree with at least 2 vertices has at least 2 leaves
- Every tree is bipartite

# Forest

- **forest** is an acyclic graph
- **forest** is an graph in which any two vertices are connected by at most one path
- every of component in forest is tree
- $k$ is number of components (trees) in forest

$$k=|V|-|E| \text{ or } |E|=|V|-k$$

# Labeled Tree

- A **labeled tree** is a tree in which each vertex is given a unique label. (typicallyintegers from 1 to $n$, where $n=|V|$)
- (2.9, **Cayley's formula**) the number of labeled trees with $n$ vertices is $n^{n−2}$

## Prüfer sequence

- **Prüfer sequence** of a labeled tree is a unique sequence associated with the tree. The sequence for a tree on $n$ vertices has length $n−2$
- There is **Bijection between Prüfer Sequences and Labeled Trees.** That is, every labeled tree has a unique Prüfer sequence that defines it, and every Prüfer sequence defines just one labeled tree. 
- The labels that appear in the Prüfer sequence are **not leaves**, and their deggree is the number of **appearances in the sequence** $+1$.
- The labels that **not appear** in the sequence are **leaves**, that is their deggree is 1.

## Prüfer Sequence to Labeled Tree 

Given a Prüfer sequence, it is possible to generate a finite labeled tree corresponding to that sequence.

Let $P=(a_1,a_2,\ldots,a_{n−2})$ be a Prüfer sequence. This will be called **the sequence**.

It is assumed the sequence is not empty.

1. Draw the $n$ nodes of the tree we are to generate, and label them from $1$ to $n$. This will be called the tree.
2. Make a list of all the integers $(1,2,…,n)$. This will be called **the list**.
3. If there are two numbers left in **the list**, connect them with an edge and then **stop**. Otherwise, continue on to **step 4**.
4. Find the **smallest number in the list** which is *not* in **the sequence**, and also the **first number in the the sequence**. Add an edge to the tree connecting the nodes whose labels correspond to those numbers.
5. Delete the first of those numbers from **the list** and the second from **the sequence**. This leaves a smaller **list** and a shorter **sequence**. Then return to **step 3**.

## Labeled Tree to Prüfer Sequence

Given a finite labeled tree, it is possible to generate a Prüfer sequence corresponding to that tree.

Let $T$ be a labeled tree of order $n$, where the labels are assigned the values $1$ to $n$.

1. If there are two (or less) nodes in $T$, then **stop**. Otherwise, continue on to **step 2**.
2. Find all the nodes of $T$ of degree $1$. There are bound to be some, from Finite Tree has Leaf Nodes. Choose the one $v$ with the lowest label.
3. Look at the node $v'$ adjacent to $v$, and assign the label of $v'$ to the first available element of the Prüfer sequence being generated.
4. Remove the node $v$ and its incident edge. This leaves a smaller tree $T'$. Go back to **step 1**.

