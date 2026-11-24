
# Vertex Cover Problem – NP-Completeness Proof

## 1. Definition of Vertex Cover

A **Vertex Cover** of an undirected graph G = (V, E) is a subset of vertices V' ⊆ V such that **at least one endpoint of every edge belongs to V'**.

**In simple words:**
- Select some vertices from the graph.
- Every edge in the graph must have at least one of its endpoints selected.
- The selected vertices form the vertex cover.

### Types of Vertex Cover

1. **Optimization Version:** Find a vertex cover containing the minimum possible number of vertices.
2. **Decision Version:** Given a graph G = (V, E) and an integer k, determine whether a vertex cover of size at most k exists.

---

## 2. Proof that Vertex Cover is NP-Complete

To prove that Vertex Cover is NP-Complete, we must prove two conditions:

1. Vertex Cover belongs to NP.
2. Vertex Cover is NP-Hard.

### Step 1: Prove Vertex Cover belongs to NP

A problem belongs to NP if a given solution can be verified in polynomial time using a deterministic algorithm.

**Verifier Input:**

⟨G = (V, E), k, V'⟩

Where:
- G = Given graph.
- V = Set of vertices.
- E = Set of edges.
- k = Maximum allowed number of selected vertices.
- V' = Proposed vertex cover.

**Verification Algorithm:**

1. Initialize `count = 0`.
2. For each vertex v ∈ V':
   - Remove all edges incident to vertex v from the edge set E.
   - Increment `count` by 1.
3. Check whether `count ≤ k` and the edge set E is completely empty.
4. If both conditions are satisfied, ACCEPT.
5. Otherwise, REJECT.

**Explanation:**

- Removing edges incident to selected vertices means those edges are covered.
- If no edges remain, every edge has at least one selected endpoint.
- If the selected vertex count does not exceed k, the solution is valid.

**Time Complexity:** O(|V| + |E|).

Therefore, Vertex Cover belongs to NP.

### Step 2: Prove Vertex Cover is NP-Hard

To prove NP-Hardness, we reduce the known NP-Complete **Clique Problem** to the Vertex Cover Problem.

CLIQUE ≤p VERTEX COVER

This means we convert an instance of Clique into an instance of Vertex Cover in polynomial time.

**Reduction Algorithm:**

1. Take an instance of the Clique Problem with graph G = (V, E) and integer k.
2. Construct the **complement graph** G' = (V, E').
3. In the complement graph, an edge exists between two vertices if and only if that edge does not exist in the original graph.

   (u, v) ∈ E' ⇔ (u, v) ∉ E

4. Set the required vertex cover size to:

   k' = |V| - k

5. The equivalence property is:

   G has a clique of size k
   **if and only if**
   G' has a vertex cover of size at most |V| - k.

**Explanation:**

- A clique in the original graph means every pair of selected vertices is connected.
- In the complement graph, those same selected vertices have no edges between them.
- Therefore, all edges in the complement graph must have at least one endpoint outside that selected set.
- Hence, the remaining vertices form a vertex cover.

Constructing the complement graph takes polynomial time.

Since Clique is NP-Complete, this reduction proves that Vertex Cover is NP-Hard.

### Step 3: Conclusion

We have proved that:

1. Vertex Cover belongs to NP.
2. Vertex Cover is NP-Hard.

Therefore,

**VERTEX COVER IS NP-COMPLETE.**

---

## 3. Important Points to Remember

| Concept | Meaning |
|---|---|
| Vertex Cover | Every edge must have at least one selected endpoint |
| Optimization | Find the minimum-size vertex cover |
| Decision | Check whether a vertex cover of size at most k exists |
| NP Proof | Verify the given vertex cover in polynomial time |
| NP-Hard Proof | Reduce Clique to Vertex Cover |
| Complement Graph | Contains exactly the edges missing in the original graph |
| Final Result | Vertex Cover is NP-Complete |

---

## 4. Quick Revision

- **Vertex Cover:** Select vertices so that every edge is covered.
- **NP:** A proposed solution can be verified in polynomial time.
- **NP-Hard:** Proved using polynomial-time reduction from Clique.
- **Complement Graph:** Contains edges that are absent in the original graph.
- **Reduction:** CLIQUE ≤p VERTEX COVER.
- **Conclusion:** Vertex Cover is NP-Complete.
