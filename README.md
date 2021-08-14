# Long Range Planning LTL Tasks

Contains 112 LTL tasks referencing cities in the Northeastern United States.

Each task is structured as a tuple: `(LTL formula, mapping from atomic proposition(s) -> location name)`

The **a** proposition always represents the goal state, and the **b**, **c**, and **d** propositions represent constraints.

**Distance** is the straight-line start-to-goal distance from the start location we used in testing *(41.82616165, -71.40328014)* to the task's goal state. This measure can be used as a unique identifier for accessing all tasks that reach a given goal state.

Here's one interpretation of the LTL formulae:
- *F(a)*: go to **a**
- *F(a) & G(!b)*: go to **a** and always avoid **b**
- *F(b & F(a))*: go through **b** on the way to **a**
- *~b U a*: avoid **b** on the way to **a**
- *F(b & F(a)) & G(!c)*: go through **b** on the way to **a** and always avoid **c**
- *(!c U b) & F(b & F(a))*: avoid **c** on the way to **b** and go through **b** on the way to **a**
- *(!c U b) & F(b & F(a)) & G(!d)*: avoid **c** on the way to **b**, go through **b** on the way to **a**, and always avoid **d** 
