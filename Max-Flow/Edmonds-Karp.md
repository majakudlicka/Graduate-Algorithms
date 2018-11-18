**Edmonds-Karp**

-  Similar algorithm to Ford-Fullkerson but we do not assume that
   capacitiies are integers
-  We only use BFS (not DFS) to check fot s-t path in G^f^

*Fact*

Every time we find a path and min capacity along the path, we remove at
least one edge (others can be added but it is irrelavant)

BFS input: Directed/ Undirected G=(V,E), no edge weights

Output: Dist(v) = min number of edges s => v
