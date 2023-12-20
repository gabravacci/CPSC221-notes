
We define $n$ as the number of vertices and let $m$ be the number of edges in a [[Graphs|graph (math)]]. Mathematically: $|V| = n,\, |E| = m$. 

## Edge-vertices relationships
### Lower bounds
For a *connected* graph we have a minimum $n-1$ edges. Naturally, if it’s not connected we can have *no* edges. 

A graph is *minimally* connected if it has exactly $n-1$ edges.
### Upper bounds
For upper bounds we require knowledge on graph *simplicity*. If a graph is simple the maximum number of edges is $n(n-1)/2$. If the graph is *not* simple we have no upper bound on number of edges. A graph then is *complete* if it has exactly $n(n-1)/2$ edges.

Thus we can notice that for practicality we need our implementations to be simple and connected graphs. 
## Implementations
### Adjacency Matrix
The **adjacency matrix** implementation gives the following time complexities for the functions:
- `insertVertex(V v)`: $O(1)$ (best) $\Theta(n^2)$ (worst) or $O(n)$ (amortized)
- `removeVertex(V v)`: Similar as above (because of resizing) with best case $O(n)$
- `areAdjacent(V v, V u)`: $O(1)$
- `incidentEdges(V v)`: $O(n)$

### Adjacency list
With an **adjacency list** representation we have $\Theta(n+m)$ space usage, and the functions become:
- `insertVertex(V v)`: $O(1)$ (best) $\Theta(n^2)$ (worst) or $O(n)$ (amortized)
- `removeVertex(V v)`: Similar as above (because of resizing) with best case $O(n)$
- `areAdjacent(V v, V u)`: $O(1)$
- `incidentEdges(V v)`: $O(n)$

### Summary of performance

| $n$ vertices $m$ edges | Edge list | Adjacency list                                   | Adjacency matrix |
| ---------------------- | --------- | ------------------------------------------------ | ---------------- |
| Space                  | $n+m$     | $n+m$                                            | $n^2$            |
| `IncidentEdges(v)`     | $m$       | $\mathrm{deg}(v)$                                | $n$              |
| `areAdjacent(v,w)`     | $m$       | $\mathrm{min}(\mathrm{deg}(v), \mathrm{deg}(w))$ | $1$              |
| `insertVertex(v)`      | $1$       | $1$                                              | $n$ (amortized)  |
| `insertEdge(v,w,o)`    | $1$       | $1$                                              | $1$              |
| `removeVertex(v)`      | $m$       | $\mathrm{deg}(v)$                                | $n$ (amortized)  |
| `removeEdge(e)`        | $1$       | $1$                                              | $1$              |                                                 |                  |

