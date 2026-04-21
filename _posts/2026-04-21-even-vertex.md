# The Companion Identity of Even-Vertex Aperiodic Tilings

## Abstract

This paper identifies a hidden topological property within the class of even-vertex aperiodic tilings, such as Penrose P3 and Ammann-Beenker A5 systems. We prove that these tilings possess a global parity state that is non-locally derivable from the tiling's local geometry. We present two primary results: first, a transformation $\Phi$ that generates a distinct, non-MLD "companion" tiling by mapping vertex parity to face color; and second, a constructive algorithm for deriving the corresponding companion tileset. By analyzing the "Ordering and Resolution" of matching rules, we demonstrate why certain systems (P3) generate these companions while others (P2) remain degenerate. Finally, a computational search within a generalized search space suggests that this single parity bit represents the exhaustive non-MLD companion state for this class of systems.

## Background

In the study of aperiodic tilings, mutual local derivability (mld) is used as a classifier. If two tilings are mld they are said to belong to the same mld class. If a tiling is discovered that is non-mld with existing known tilings, then it is thought of as a novel aperiodic tiling of the plane.

A tiling $A$ is locally derivable from tiling $B$ if given a patch of the tiling of finite radius $r$, the tile that appears at the same place in $B$ can be derived from the tile that appears there in $A$. And vice versa.

In this paper we focus on a particular class of tilings - even vertex tilings - where every tile in the tiling has an even number of vertices. The key finding is that, subject to certain preconditions, any such tiling has a non-mld companion. Examples of even-vertex tilings are Penrose P3, Hexagon-Boat-Star(HBS) and Ammann-Beenker(A5). We will use Penrose P3 throughout as a worked example. 

## Tiling

Formally we present the finding as a theorem: 

### Theorem 1 

Let $Q$ be a quasiperiodic tiling composed of tiles with an even number of vertices. There exists a transformation $\Phi$ that maps $Q$ to a distinct quasiperiodic tiling $Q'$ by applying a parity-dependent coloring to its faces, provided that the bipartite 2-coloring of the vertices of $Q$ is non-locally derivable from the vertex types.

### Proof

1. The Graph Property
Since all tiles in $Q$ have an even number of vertices, every closed path (cycle) in the edge-graph of $Q$ has an even length. Therefore, the graph of $Q$ is bipartite and admits a global 2-coloring of its vertices $\{0, 1\}$.

2. The Reference Mapping
For every prototile $P$ in the tileset of $Q$, we designate a specific vertex as the reference vertex $v_{ref}$. For any tile $T$ in the actual tiling $Q$, let $f$ be the isometry that placed it. The location of the reference vertex in the global graph is $f(v_{ref})$.

3. The Coloring Transformation $\Phi$
We define the mapping $\Phi: Q \to Q'$ such that the color of the face of tile $T$ is determined by the bipartite mark $(0 \text{ or } 1)$ at the coordinate $f(v_{ref})$.

4. The Existence of the Split
The transformation $\Phi$ produces two distinct colors in $Q'$ if and only if there exist two tiles $T_i, T_j$ of the same prototile $P$ such that the bipartite marks at $f_i(v_{ref})$ and $f_j(v_{ref})$ are different.

### Note

The following table shows for which tilings the theorem implies that a non-MLD companion exists.  

| Tiling System | Even-Vertex? | Bipartite/Vertex-Type Alignment | Result of $\Phi$ |
| :--- | :---: | :--- | :--- |
| **Standard P3 (Penrose Rhomb)** | Yes | **Misaligned** (Non-Local) | **Distinct Companion** ($Q' \neq Q$) |
| **Standard P2 (Kite & Dart)** | Yes | **Aligned** (Local/MLD) | **Identity** ($Q' = Q$) |
| **Socolar Rhomb-Square-Hexagon** | Yes | **Misaligned** (Non-Local) | **Distinct Companion** ($Q' \neq Q$) |
| **A5 (Ammann-Beenker)** | Yes | **Misaligned** (Non-Local) | **Distinct Companion** ($Q' \neq Q$) |

### Example

Figure 1 shows a picture of the transformed P3 tiling: 

| ![P3 Patch](/assets/images/2026-04-21/P3_patch.png "P3 Patch") | 
|:--:| 
| **Figure 1**. Patch of the P3' tiling. |

## Tileset

If the tiling Q exists, there may be a corresponding tileset T. In that case, there exists a companion tileset T'. Formally: 

### Theorem 2 
For any even-vertex aperiodic tileset $T$, where there exists a substitution rule S, the transformation $\Phi$ produces a companion aperiodic tileset $T'$.
 * Trivial Outcome: The tile-transition graph is disjoint (reflecting a tile is a choice, not a requirement).
 * Non-Trivial Outcome: The tile-transition graph is connected (reflecting a tile is a structural necessity).

By tile-transition graph we mean the following. Within $S$, we create a vertex for each prototile. The edge $A \to B$ exists if the prototile $A$ includes the tile $B$.

### Proof ( by construction )

To construct the new tileset: 

1. Identify edges of the tileset, using the integer marking rules - using only odd numbers. Separate the sign from the natural number. The signs will all remain the same during the process, and only the number will change. 

2. Beginning with the substitution rule mark the vertices on the prototiles alternating $0$ and $1$. 

3. Mark the prototiles as $L$ (Left).

4. Clone them and mark the clones as $R$ (Right), and flip the matching rules on the Right prototiles. ( By flip, we mean to transform by an increment/decrement operator (e.g.  $2n-1 \leftrightarrow 2n$) ).

5. Within the expansion of each prototile, mark the vertices as $0$ and $1$, by choosing a starting vertex as $0$, and marking alternating vertices $0$ or $1$ as appropriate so that each edge spans a $0$ and a $1$.

6. Mark the tiles within the expansion as $L$ or $R$ depending on whether they match the orientation of the prototile shape ($L$) or not. 

7. Assign a numerical order to the Left prototiles. The first prototile in order is deemed immediately correct.

8. For each of the Left prototiles in order, check the prototile expansion to see if the edge is matched ( $L$ meets $L$ or $R$ meets $R$ ) or mismatched ($L$ meets $R$). If mismatched, then flip the corresponding matching rule on the prototile. When checking the prototile, consider first the internal edges of the prototile, and then the external, and then the internal and external of the expansion etc. until the mismatches are resolved. 

9. If no mismatches were found in step 8, then this case is trivial. 

### Example

Figure 2 shows the tileset derived from Penrose P3.

| ![P3 Tileset](/assets/images/2026-04-21/P3_tilesets.png "P3 Tileset") | 
|:--:| 
| **Figure 2**. Tilesets: P3 on the left, and P3' on the right. Edge Markings are integers, where the matching rule is that the integers on edges that meet must sum to zero.  |

## Discussion

Having found these non-MLD companions, I naturally asked: are there any more? To answer this question, I generalized the process of developing the substitution rules, and performed a computational search to find other solutions. I found either that the symmetry collapses, or if it doesn't collapse then the solution is MLD with either the original tiling or its companion. This suggests that this one parity-bit is all that is hidden in the original tiling.  

## Conclusion

We have shown that the members of the class of even-vertex tilings permit companions which, except in degenerate cases, are non-MLD with their originals. Likewise for tilesets, a non-MLD tileset exists.

