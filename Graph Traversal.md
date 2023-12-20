#compsci 

## Breadth-first search (BFS)
Visits all vertices within a distance $d$ from starting vertex before visiting vertices a distance $d+1$ ($d$ starting at 0). We need to keep track of visited edges and vertices (it is useful to define a label for each that we can trigger)
```
fun BFS(G, v) 
	Queue q
	SetLabel(v, VISITED)
	q.enqueue(v)
	while (!q.empty) 
		q.pop(v)
		for w in G.AdjacentVertices(v) 
			if (GetLabel(w) = UNVISITED) 
				SetLabel((v,w), EXPLORED)
				SetLabel(w, VISITED)
				q.enqueue(w)
			// if edge unvisited but vertex known
			else if (GetLabel((v,w), UNEXPLORED)) 
				SetLabel((v,w), CROSS)
```
For a full traversal it is sufficient to do:
```
for v in G.vertices()
	if (GetLabel(v) = UNVISITED)
		BFS(G, v)
```
The discovered edges form a *spanning tree* (see [[Graphs]])

### Complexity
The `while` loop *should* happen once per vertex with $O(n)$ complexity, the for loop (in the total search) happens to run for the number of edges (times 2) resulting in a complexity of $O(m)$. Thus total graph traversal happens in $O(n+m)$ (whichever is larger)

## Depth-first search (DFS)
The setup is the same as above. The algorithm itself happens *recursively* (or with a [[Stack (data structure)|stack]]):
```
fun DFS(G, v)
	SetLabel(v, VISITED)
	for w in G.AdjacentVertices(v)
		if (GetLabel(w) = UNVISITED)
			SetLabel((v,w), EXPLORED)
			DFS(G, w)
		else if (GetLabel((v,w)) = UNEXPLORED)
			SetLabel((v,w), BACK) // ?
```

The explored edges form a [[Trees (data structure)|tree]] structure. Similarly, the *back* edges point to a common ancestor in the vertices.

On a *connected* graph with $m$ edges and $n$ vertices, the algorithm produces $m - n + 1$ back edges (?)

### Complexity
We visit each neighbor exactly once for each vertex (similar as above), the total complexity of the algorithm is *also* $O(n+m)$.

