## LP Geometry

Optimum of LP is achieved at a vertex of the feasible region except if

a) infeasible = feasible region is empty
b) unbounded = optimal is arbitrarily large - depends on the objective function

How to check if infeasible?

Add parameter z to the original constraint function: Ax + z <=b
This is trivial to solve because z can be -Infinity. So we know this new region is feasible. 
Then try to maximise z - if it's positive we know original constraint is feasible. Also
gives us a starting point for simplex algorithm.