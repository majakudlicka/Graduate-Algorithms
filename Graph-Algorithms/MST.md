**MST problem** (miminum spanning tree)

Given undirected graph G=(V,E) with edge weights w(e)

Goal: Find minimal size connected subgraph (spanning tree) of min weight

*Tree properties*

Tree = connected ACYCLIC graph

1. Tree of n vertices has n-1 edges (otherwise would be cyclical)
2. In a tree, there is exactly one path between every pair of vertices
3. Any connected G=(V,E) with |E| = |V| - 1 is a tree

*Kruskal's algorithm*

Input: Undirected graph G=(V,E) with weights

1. Sort by weight (O(m X logn)
2. Set x = null
3. For e=(v,w) ∈ E (go through in order) if x ∪ e doesn't have a cycle
   then x x∪e (We are tyring to add as many edges as we can, minimizing
   the weights, without creating a cycle)

Cut - set of edges that go between S and S'

There are many possible MSTs


