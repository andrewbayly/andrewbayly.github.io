# On the Chiral Transformation of Even-Vertex Aperiodic Tilings

Abstract: 

We present a fundamental theorem for the chiral transformation of even-vertex quasiperiodic tilings. By identifying the bipartite nature of even-vertex grids, we define a parity-dependent vertex deformation operator, $\Phi$, that maps a tiling $Q$ to a transformed tiling $Q'$. We further provide a universal construction method—the Extended Substitution Tiling (EST)—which utilizes a 'doubling' of the native prototile set to maintain infinite chiral parity. While certain cases (such as Penrose P2) result in trivial MLD-equivalents, we demonstrate that for the broader class of tilings, including Penrose P3 and Ammann-Beenker A5, the transformation produces a geometrically distinct and non-MLD aperiodic universe. This work effectively defines a new class of chiral aperiodic tilesets derived from existing symmetric frameworks.

## Introduction

We begin with a theorem. 

### Theorem 1.
Let Q be a quasiperiodic tiling, composed entirely of tiles with an even number of vertices. There exists a transformation $\Phi$ that maps Q to a distinct quasiperiodic tiling Q' by applying a parity-dependent deformation to its vertices.

We prove the theorem by construction. 

### Proof. 

1. Since all the tiles in Q have an even number of vertices, the vertices and edges of Q form a bipartite graph.

2. Choose one vertex in Q and mark it as Up, then mark all other vertices Up or Down, such that each edge spans one Up and one Down vertex ( 2-coloring ).

3. Rotate the vertices by an angle $\Theta$, clockwise for Up vertices, and anti-clockwise for Down vertices. $\Theta$ must be small enough, and chosen so that none of the tiles collapse from self-intersection.

4. The result is the tiling Q'.

### Discussion

We now consider the most salient question: Is Q' in a distinct MLD class, from Q ?

The answer is that it depends. In some cases Q' is a trivial modification of Q, and they are in the same MLD class, however as shown below the more general case is that they are in distinct classes. The reason is that while it is possible to locally derive Q from Q', it is not generally possible to locally derive Q' from Q - they are not locally indistiguishable. To be more specific, in $Q$, a patch of rhombs is locally identical regardless of the bipartite parity field. In $Q'$, that same patch is expressed as a specific arrangement of $L$ and $R$ shapes. Since the $L/R$ identity is derived from a bipartite field that has two possible global phases (Up/Down or Down/Up), and there is no local feature in $Q$ to distinguish these phases, the mapping $\Phi$ is non-local.

Having said that Q' is in a separate class, the relationship between Q' and Q is such that if Q has an an associated aperodic tileset, then there is also a corresponding aperiodic tileset for Q'. 

## Development

While the theorem claims that Q' exists, it says nothing about how to construct the substitution rule. In this section, we describe a tool - Extended Substitution Tiling - that can be used to generate the rule for Q'. 

### Method 

#### Extended Substitution Tiling

In an Extended Substitution Tiling (EST), there are two phases, Recursive and Terminal. Each has an associated substitution rule, namely R for the Recursive phase, and T for the Terminal Phase.

R is applied n times in succession, just like in a standard substitution rule. Then T is applied just once. As n tends toward infinity, the tiling expands to cover the entire plane.

Note that R and T have the same set of prototile shapes as inputs, and that the output tilings for R and T can be as simple or complex as needed. 

Note further that, provided some basic preconditions are met, the resulting tiling is quasiperiodic. 

The EST preconditions are: 

1. The original substitution rule for $Q$ must be a valid, aperiodic, and primitive substitution. 

2. The bipartite labeling must be consistent across the inflation boundary (i.e., the "Parent" vertex parity must match the "Child" vertex parity at the same coordinates).

3. The linear transformation (rotation of vertices) does not destroy the Long-Range Order.

#### Application

Having established what an EST is, we now describe how to build an EST to generate Q', given that there is a known substitution rule for Q. We will use Penrose P3 as a worked example. 

##### Recursive Phase rule (R)

[ Diagram: ]

1. Make two copies of each prototile shape (input), and mark them as Left(L) and Right(R).

2. Mark the vertices on the Left prototile shapes as Up(U) or Down(D), so that adjacent vertices are different. 

3. Mark the vertices of the Right prototile shapes as the inverse of the Left. 

4. On the Left tiling (output), mark the vertices of the component tiles as U or D, taking care to alternate the vertices. 

5. Mark the component tiles as L or R, using the tile-shapes as the key.

6. Do the same for the Right tiling. The Right tiling should end up as the inverse of the Left. 

##### Terminal Phase rule (T)

[ Diagram ] 

1. Copy the prototile shapes from R. 

2. The output for each prototile is a single shape. Rotate each of the vertices: clockwise for Up vertices, and anti-clockwise for Down, each by an angle theta. As indicated above, theta must be chosen so that the tile does not self-intersect when transformed.

### Examples

A note on naming: In what follows, X' will refer to the tiling generated from X, for example P3' refers to the new tiling generated from the Penrose P3 tiling. 

The tilings we consider below are summarized in the following table: 

| Tiling  | Transformed Tiling Status |
|---------|---------------------------|
| P2      |  Trivial                  | 
| P3      |  Distinct                 |
| Pentas  |  Distinct                 | 
| A5      |  Distinct                 |

#### P2

P2 is a trivial case. By inspecting the tiling (see diagram), and counting the vertices, we may observe that all the kites are congruent, even when labelled with Up's and Down's, and likewise the Darts are also congruent. If we were to proceed with the steps, then we would find that the prototiles fall into two sets, and Uniform Recurrence would be broken.

More specifically: In P2, the bipartite graph is such that all Kites occupy one "color" of the vertex field and all Darts occupy the other. Therefore, the "L/R" choice is fixed by the tile type. If $Tile = Kite$, then $Form = L$. Since the choice is locally determined by the tile's own identity, $Q$ and $Q'$ are MLD

[ Diagram: Patch of original P2 tiling ] 

#### P3

In P3' both tiles form S-shapes with distinct Left and Right forms, a total of 4 tile shapes.

[ Diagram: Rule R ] 
[ Diagram: Rule T ] 
[ Diagram: Patch ]

#### Pentas

In Pentas' both tiles form S-shapes with distinct Left and Right forms, a total of 4 tile shapes. 

[ Diagram: Rule R ] 
[ Diagram: Rule T ] 
[ Diagram: Patch ]


#### A5

The prototiles for A5 are a rhombus and a square. In A5' the rhombus takes Left and Right forms, while the square, because of its symmetry, takes a single hourglass shape.

[ Diagram: Rule R ] 
[ Diagram: Rule T ] 
[ Diagram: Patch ]

## Conclusion

We have proven and demonstrated the existence of a universal chiral transformation for even-vertex aperiodic tilings. Through the Extended Substitution Tiling (EST) method, we have shown that any native substitution rule can be "doubled" to host a global parity state.

While the resulting tilings ($Q'$) are derived from known frameworks, they represent a distinct MLD class in all non-trivial cases (such as P3', Pentas', and A5'). This distinction arises from the necessity of a global parity choice that cannot be derived from local observations of the original tiling. Consequently, this work does not merely describe new patterns, but defines an entire class of previously undocumented aperiodic tilesets.

## Further Work

The application of the $\Phi$ transformation to the broader catalog of even-vertex aperiodic sets (e.g. Ammann, Socolar) remains a promising area for exploration. Additionally, the physical properties of these "Prime" tilings — specifically their diffraction patterns and potential applications in chiral metamaterials — warrant further investigation.

## References etc. 
TODO


















 