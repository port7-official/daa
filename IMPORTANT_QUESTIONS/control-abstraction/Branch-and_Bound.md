# Control Abstraction in Branch and Bound

## Definition

Control abstraction in Branch and Bound is a general procedure that describes how to search the state space tree to find an optimal solution.

It controls the selection and expansion of live nodes using a bounding function to avoid exploring non-promising nodes.

The main purpose is to find the optimal solution efficiently by reducing unnecessary searches.

## Algorithm: LC Search

```text
Algorithm LCSearch(t)

1. If t is an answer node, output t and return.

2. Set E = t.
   // Root node is the first E-node

3. Initialize the list of live nodes as empty.

4. Repeat:
      a. Generate all children of E.

      b. For each child x:
            If x is an answer node:
                Output the path from x to t.
                Return.

            Add x to the list of live nodes.
            Set the parent of x as E.

      c. If there are no live nodes:
            Print "No answer node".
            Return.

      d. Set E = Least().
         // Select the least-cost live node.

5. Continue until an answer is found.
```

## Explanation of Important Terms

1. **E-node (Expanding Node):** The node that is currently being expanded by generating its children.

2. **Live Node:** A generated node that has not yet been expanded but may be explored later.

3. **Dead Node:** A node that has already been expanded or will not be explored further.

4. **Add(x):** Adds a newly generated node to the list of live nodes.

5. **Least():** Selects and removes the live node with the least estimated cost. This node becomes the next E-node.

6. **Parent Pointer:** Stores the parent of each node to trace the solution path from the answer node to the root.

## Types of Search Strategies

The control abstraction remains the same, but the method of storing and selecting live nodes changes.

| Search Strategy | Data Structure | Node Selection |
|---|---|---|
| FIFO Branch and Bound | Queue | First inserted node |
| LIFO Branch and Bound | Stack | Last inserted node |
| LC Branch and Bound | Min-Heap / Priority Queue | Least-cost node |

## Conclusion

Control abstraction provides a common framework for Branch and Bound. Different search strategies are obtained by changing how live nodes are stored and selected.
