A graph is a collection of *vertices* (or nodes) connected by *edges*. Formally, we define a graph as a pair of sets:
$$
G = (V,E)
$$
Where $V$ is the set of all vertices:
$$
V = \left\{ v_{1},v_{2},\dots,v_{n} \right\}
$$
And $E$ is the set of all edges:
$$
E = \left\{ e_{1}, e_{2}, \dots, e_{m} \right\}
$$
Note how each element in $E$ is a pair of vertices, thus $e_i\in V \times V$. If each edge is ordered, then the graph is *directed*.

## Vocabulary
### Elementary subsets
The vertices *adjacent* to a vertex $v$ are in the set:
$$
N(v) = \left\{ u:(u,v) \in E \right\}
$$
The edges *incident* to $v$ are (edges that connect to the adjacent vertices)
$$
I(v) = \left\{ (u,v): u \in N(v) \right\}
$$
### Paths
A *path* is a sequence of vertices connected by edges. A path is *simple* if it has no repeated vertices. The path is also *cyclic* if it ends at the same vertex it started. 

### Graph categorizations
A graph is *simple* if it has no loops or multi edges.

A subgraph of a graph $G$ is:
$$
(V,E):(V’ \subseteq V,\, E’ \subseteq E ) \wedge (u,v) \in E’ \implies u,v \in V’
$$
A graph is *complete* if it has the maximum number of edges. 

A graph is *connected* if there is a path for every pair of vertices. The *connected component* of the graph is the largest connected subgraph.

The spanning tree of $G = (V,E)$ is the *acyclic* and *connected* graph with vertex set $V$.






#math #compsci