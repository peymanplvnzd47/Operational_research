## Graph Coloring Problem (GCP)

The Graph Coloring Problem (GCP) is a classic combinatorial optimization problem with numerous real-world applications in areas such as scheduling, register allocation in compilers, frequency assignment in wireless communication, and many others. The problem can be defined as follows:

### Problem Formulation:

Given an undirected graph \( G = (V, E) \), where \( V \) is the set of vertices (nodes) and \( E \) is the set of edges, the objective is to assign a color to each vertex such that no two adjacent vertices (connected by an edge) share the same color. The goal is to minimize the total number of colors used.

### Mathematical Formulation:

Let \( V = \{1, 2, ..., n\} \) be the set of vertices in the graph.

- Decision Variables:
  - Let \( x_{iv} \) be a binary decision variable, where \( x_{iv} = 1 \) if vertex \( v \) is assigned color \( i \), and \( x_{iv} = 0 \) otherwise. \( i = 1, 2, ..., K \) where \( K \) is the maximum number of colors.

- Objective Function:
  - Minimize \( K \), the number of colors used.

- Constraints:
  - Each vertex must be assigned exactly one color:
    $$ \sum_{i=1}^{K} x_{iv} = 1, \quad \forall v \in V $$

  - Adjacent vertices cannot have the same color:
    $$ x_{iv} + x_{jv} \leq 1, \quad \forall (i, j) \in E, \forall v \in V $$

  - Non-negativity constraint:
    $$ x_{iv} \in \{0, 1\}, \quad \forall i, v $$

### Solution Methodologies:

1. **Exact Algorithms:**
   - **Backtracking:** Enumerate all possible colorings recursively and backtrack when a conflict is encountered.
   - **Branch and Bound:** Prune the search space by bounding the feasible region.
   - **Integer Linear Programming (ILP):** Formulate the problem as an ILP and solve using optimization solvers.

2. **Heuristic Algorithms:**
   - **Greedy Coloring:** Assign colors to vertices sequentially, selecting the lowest available color that does not conflict.
   - **Graph Coloring with Evolutionary Algorithms:** Use genetic algorithms, simulated annealing, or other metaheuristic approaches to find good solutions.

### Complexity:

The GCP is known to be NP-hard, meaning no known polynomial-time algorithm can solve all instances of the problem. The problem complexity depends on the structure of the graph and the number of colors required.
