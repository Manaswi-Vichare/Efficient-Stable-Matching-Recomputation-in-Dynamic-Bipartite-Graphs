# Efficient-Stable-Matching-Recomputation-in-Dynamic-Bipartite-Graphs

**Problem Statement:** \
Let G= ((A, B), E) be a bipartite graph. Every vertex v∈V(G) ranks all its neighbors. Let ≻<sub>v</sub> denote the ordered set of neighbors of v. We say that v prefers u over u′ if u is before u′ in ≻<sub>v</sub>. Let μ be a matching in G. We say that μ is a stable matching if there is no edge uv /∈μ such that, \
i. u prefers v over μ(u) (matched partner of u), and \
ii. v prefers u over μ(v) (matched partner of v) \
A stable matching can be found in polynomial time using the Gale Shapley algorithm. Suppose that an edge from G is deleted. Design an algorithm to recompute a stable matching efficiently. Further, design an algorithm when a subset of edges from G is deleted.

**Modifications in the Gale-Shapley Algorithm:** \
i. User Interaction. \
ii. Validation of Edge Deletions: The code checks whether the specified edges for deletion are part of the initial matching. Only valid edges are deleted. \
iii. Updating the Matching: When an edge is deleted, the code frees the involved Set-A and Set-B and modifies their preferences to reflect the deletion. The Set-B becomes free, and the Set-A reverts to being free as well. The preferences of both individuals are updated to remove the deleted partner.

**Output:**

For the given input.txt, the following output is achieved for multiple edge deletion: 

Stable Matchings: \
Matchings: \
Node 1 (Set-A) --> Node 5 (Set-B) \
Node 0 (Set-A) --> Node 6 (Set-B) \
Node 3 (Set-A) --> Node 7 (Set-B) 

Free nodes in Set-A: node 2 \
Free nodes in Set-B: node 4 

Delete a set of nodes from the stable matching \
Enter the number of edges to be deleted: 2

Delete Edge [Set-A -> Set-B]: [1, 5] \
Delete Edge [Set-A -> Set-B]: [0, 6] 

Matchings: \
Node 0 (Set-A) --> Node 4 (Set-B) \
Node 2 (Set-A) --> Node 6 (Set-B) \
Node 3 (Set-A) --> Node 7 (Set-B) 

Free nodes in Set-A: node 1 \
Free nodes in Set-B: node 5 

**Time Complexity:**

| Aspect | Amortized Time Complexity |
| -- | -- |
| Initialization of Preferences (if we do not pass an input file) | O(N<sup>2</sup>) (One-time) | 
| Gale-Shapley Algorithm (Worst Case) | O(N<sup>2</sup>) |
| Edge Deletions (Approximate Complexity) | O(N) |
| Overall Amortized Time Complexity | O(N<sup>2</sup>) + O(N<sup>2</sup>) + O(N) = O(N<sup>2</sup>) |
