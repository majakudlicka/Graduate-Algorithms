 **Max flow with demands**
 
 Input: Flow network- directed G=(V, E) with s,t ∈ V; capacities c(e) > 0 for e ∈ E & demands d(e) >=0 for e ∈ E
 
 Feasible flow is a flow f where: for e ∈ E, d(e) <= f(e) <= c(e)
 
 Reduction overview
 
 Feasible flow -> Max flow problem
 
 Given input G, c(e), d(e) for feasible flow
 - construct input G' c'(e) for max-flow
 
 Vectors s,t become internal vectors - we add new s' and t' outside
 
 c'(e)= c(e) - d(e) (intution- we shift capacities by demand; 0 in new graph corresponds to demand in original graph)
 
 Problem: what is a balanced flow for G' is not necessarily a balanced flow for G
 
 Solution: Add edges from s' to each vertex with total demand into vertex and edges to t' with total demand out of 
 vertex
 
 for v ∈ V, add s'-> v with c' = d(in)(v)
            add v-> t' with c'=d(out)(v) 
            
Problem: Now that s and t are internal vertices, we dont have any inflow into s or any outflow out of t so they are not balanced

Solution: Add edge from s to t with infinite capacity

Say f' is saturating if size (f') = D (total demand in original network)

Lemma: G if feasible flow if and only if G' has a saturating flow

Solution: 

- Find a feasible flow f for G; if one exists

- Augment in residual graph G(f)

Difference to max- flow problem: 
- We start at feasible flow, not at zero flow
- In residual network, backwards edges are defined as flow - demand not full flow


