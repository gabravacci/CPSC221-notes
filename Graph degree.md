The *degree* of a vertex $v \in V$ (**Graphs.md**) is denoted $\mathrm{deg}(v)$ and represents the number of *edges* incident on $v$, that is:
$$
\mathrm{ deg}(v) = |I(v)|
$$
## Handshaking lemma
If $G = (V,E)$ is an *undirected* graph, then:
$$
\sum_{v \in V} \mathrm{ deg}(v) = 2|E|
$$
## Directed cases
For a directed graph, we may also define the *in-degree* of a vertex $\mathrm{deg}^{-}(v)$, the number of edges *entering* $v$. Similarly, the *out-degree* $\mathrm{ deg}^{ +}(v)$ are the edges leaving $v$. Then it stands that:
$$
\mathrm{deg}(v) = \mathrm{ deg}^{+}(v) + \mathrm{ deg}^{-}(v)
$$
And from the handshaking lemma:
$$
\sum_{v\in V} \mathrm{ deg}^{-}(v) = \sum_{v \in V} \mathrm{ deg}^{+}(v) = |E|
$$
