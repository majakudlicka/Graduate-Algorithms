**Dual LP**

Example

Max x1 + 6x2+ 10x3

Constraints
x1 <= 300
x2 <= 200
x1+ 3x2+ 2x3 <=1000
x2 + 3x3 <=500
x1, x2, x3 >=0

Dual LP ("symmetric" to original one)

y1+y3 >=1
y2+3y3+y4>=6
2y3+3y4>=10

Min 300y1+200y2+1000y3+500y4

Number of variables in original (primal) LP -> defines the number of constraints in dual LP
Number of contraints -> defines the number of variables

_General form_

(T) - transposed

max c(T)x -> min b(T)y
Ax <=b A(T)>=c
n vars, m constraints -> m vars, n constraints
x>=0, y>=0

Primal LP needs to be in canonical form (max obj func, <= constraints)

**Weak Duality Theorem**

Feasible x fro primal LP && Feasible y for dual LP

c(T)x (primal LP obj-func) <= b(T)y (dual LP obj. func)

Implication: If we find feasible x & feasible y where c(T)x=b(T)y
then x&y are optimal (works for all LPs except unfeasible/ unbounded)

Implication2: If primal LP is unbounded then dual is infeasible

**Check if LP is unbounded**

1. Check if LP is feasible
2. Check if dual is feasible -> if dual is infeasible then primal is unbounded or infeasible

**Strong Duality Theorem**

Primal LP has optmal x* if and only if dual has optimal y* and

c(T)x* = b(T)y* (their optimums are equal)

Example use case: size of max flow = capacity of min cut
