 _Def_ Problem is intractable = unlikely to be solved efficiently 
 (in time polynomial to the input size)
 
 NP = class of all search problems
 
 Search problem - rough definition - problem where we can efficiently verify solutions
 
 P = class of search problems that are solvabe in polynomial time
 
 P < NP
 
 Search Problem form:
 
 Given instance I
        -find a solution S for I if one exists
        - output No if I has no solutions
        
Examples of an NP-problem: 

-SAT (search problem, we can verify solutions in polynomial time)
-MST

Knapsack not known to be in NP nor P
        
NP = nondeterministic polynomial time = problems that can be solved in polynomial time
on a nondeterminstic (allowed to guess at each step) machine

P = polynomimal time 

NP-complete problems = hardest problems to solve in NP class

If we could solve a NP complete problem in polynomial time - proof that all NP problems lie in P & P = NP
  
 To prove NP completenes one needs to prove: 
 
 1. That problem belongs to NP
 2. That if we solved that problem in P, all NP problem could be solved in P (other problems could be reduced to that problem)
 
 For step 2 just take any known NP-comlete problem and reduce it to the new problem