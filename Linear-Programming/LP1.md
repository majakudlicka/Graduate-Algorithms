**Max-flow via LP**

Input: Directed G=(V,E) with capacities ce > 0 for e ∈ E

LP: m variables f(e) for ever e ∈ E OA→ 

Objective function: Σ f(sv)
                    sv→ ∈ E
                    
**Simple example**

Company makes A & B - how many to maximise profit?

Each unit of A makes profit 1; each unit of B makes profit 6

Demand: <= 300 units of A & <=200 of B

Supply: <=700 hours, A takes 1 h and B takes 3

x1 = number of units of A to produce per day
x2 = same for B

Demand: 0 <= x1 <= 300; 0<= x2 <= 200
Supply: x1+ 3x2 <=700

_Key issues_

- Optimum may be non-integer
- Linear Programming optimises over entire feasible set (not just integers)
 and runs in polynomial time (∈P)
- Integer LP is NP-complete
- Solution lies on a vertex = corner
- Feasible region is convex (if we take any two points in the region and connect them,
entire line belogs to the region) --> optimal point always at vertex

**LP expressed in Linear Algabra View**

x1 <=300
x2 <=200
x1+3x2+2x3<=1000
x2+3x3<=500
x1,x2,x3>=0

**Objective function (vector)**

c = [[ 1 ],
     [ 6 ],
     [ 10 ]]

**Constraint matrix**

A = [[ 1, 0, 0 ],
     [ 0, 1, 0 ],
     [ 1, 3, 2 ],
     [ 0, 1, 3 ]]

**Constraint values (vector)**

b = [[ 300 ],
     [ 200 ],
     [ 1000 ],
     [ 500 ]]
     
_Converting_

- Min instead of max? -> Multiply by -1
- a1x1+...+anxn >= b instead of <=b? Also multiply by -1!
- Equality constraint- we can convert to two inequality constraints
- Strict inequality -> NOT ALLOWED in LP (not well defined)

_Geometric View_

- n variables -> n dimensions
- n+ m constraints
- feasible region = intersection satysfying n+m halfspaces = convex polyhedron
- vertices = points satisfying n constraisnt with '='; m constrains with '<='

_Simplex algorithm_

- Worst case: exponential time
- Widely used on HUGE LPs

1. Start at x=0
2. Look for neighbouring vertex with higher objective value
3. Then move there and repeat (2) - else output (x)
                     