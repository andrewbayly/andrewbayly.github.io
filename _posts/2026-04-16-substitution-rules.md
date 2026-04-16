
# The Generalized Weave: Topological Covers and the State-Space of Substitution Tilings.

## Abstract 

We introduce a universal operator, the Generalized Weave ($W$), which acts upon any edge-to-edge aperiodic substitution rule to generate an infinite family of topologically distinct tilings. By cloning prototiles and permuting child-parent relationships via a winding vector, we demonstrate that a single substitution rule defines a multidimensional state-space of non-MLD covers. This result suggests that the current catalog of aperiodic tilings represents only the origin points of vast, unexplored topological manifolds.

## Background

Substitution rules are important in the study of aperiodic tilings since they provide a compact method to rigorously define a tiling, and to generate the tiling. There is some variation in the way that substitution rules are defined, with edge-to-edge rules being the most well-behaved and standard. Often, if a rule exists which is not edge-to-edge, it may be modified, either by removing some tiles from the prototiles, or by cutting tiles that appear on the edge, so that the resulting tiling is edge-to-edge. 

In the study of aperiodic tilings, mutual local derivability (mld) is used as a classifier. If two tilings are mld they are said to belong to the same mld class. If a tiling is discovered that is non-mld with existing known tilings, then it is thought of as a novel aperiodic tiling of the plane.

A tiling $A$ is locally derivable from tiling $B$ if given a patch of the tiling of finite radius $r$, the tile that appears at the same place in $B$ can be derived from the tile that appears there in $A$. And vice versa. 

While a substitution rule generates one tiling, it is shown below that there exists an operator $W$ (informally called the Generalized Weave), that generates an infinite set of substitution rules from any given rule, and thus creates an infinite set of tilings which, after a process of deduplication, belong to distinct MLD classes. 

The weave operates by cloning the prototiles within the rule, and weaving together the prototile-tile relationships. It is called the generalized weave because it operates on any edge-to-edge substitution rule. 


## Theory

We adopt the following notation: 
  
  $W(S, E, C, V)$
  
where $W$ is the Generalized Weave Operator, which generates a set of substitution rules, and hence tilings, given the following. $S$, the original substitution rule, $E$, the expansion factor, $C$, the cloning number, and $V$, the winding vector, where $E$ and $C$ are natural numbers and $V$ is a mapping $V: \{1, \dots, M\} \to \{0, \dots, C-1\}$, where $M$ is the number of child tiles in the expanded substitution $S^E$


$W$ is defined as follows: Beginning with $S$, $S$ is applied to itself $E$ times, meaning that the new inflation factor is $S$ times the original inflation factor.

To preserve topological consistency under the operator $W$, the prototiles are endowed with an orientation vector, ensuring that the weaving is applied relative to the tile's local coordinate system.

The tiles within the prototiles are marked with a number - by convention from top to bottom and then from left to right.

The prototiles within $S$ are then cloned $C$ times, marking the prototiles with new colors. We say that the prototiles form a matrix, with the original prototiles occupying the first column, and each succesive clone of prototiles occupying a subsequent column.

Having cloned, and assigned colors, all relationships between prototiles and tiles are within a column. 

The winding numbers are applied as follows: each tile numbered $i$ in column $j$ is replaced by the corresponding tile in column $(j + V[i]) \pmod C$.

### Theorem

Given the operator $W(S, E, C, V)$, the resulting set of substitution rules, when culled, generates tilings which are non-MLD with $S$, and also pairwise non-MLD. 

Culling means to remove duplicates which may arise for the following two reasons: 

1. The tiling graph may collapse into a disjoint graph, meaning that the tiling is not woven, and hence will be MLD with a lesser value of $C$. 

2. The tiling may be isomorphic with another tiling.

## Proof

First we prove, by construction, that the tilings exist.

The method described above, when applied to a substitution rule with edge-to-edge matching rules, generates an infinite set of substitution rules which are as valid as the original. The fact that they are edge-to-edge means that all edges within a row of the matrix have identical geometry, even though they may be composed of different tiles.

And now consider the non-MLD property of the tilings. 

Because the substitution is aperiodic, the "path" from a tile back to the common ancestor of a neighbor can be arbitrarily long. If the winding vector $V$ creates a "non-trivial cycle" through the clones, then a local observer at radius $r$ cannot know the "phase" of the weave without knowing the "index" of the tile in the infinite hierarchy.

Since the hierarchy is infinite, the information required is non-local. This is the definition of Non-MLD.

For any finite radius $r$, there exists a generation $G$ such that the local patch is contained within a single super-tile. However, the 'phase' of the weave at that patch is determined by the sequence of choices made at every generation $g > G$. Since an aperiodic substitution possesses no global period, this 'ancestral path' cannot be determined by local observation, proving $S_2$ is not locally derivable from $S_1$.

## Examples

We consider some examples, displaying patches of the resulting tilings. As examples we use Penrose P3 and Ammann-Beenker A5.  

1. A simple example: $W(P3, 1, 2, [1,0,0,0,0] )$

2. $W(P3, 2, 6, [2, 3, 0, 0, 0])$

3. $W(A5, 1, 2, [1, 0, 0, 0, 0,0,0,0,0,0,0,0])$

## Conclusion

While we have shown the existence of an infinite companion set of tilings for any edge-to-edge substitution rule, it follows from Goodman-Strauss[ref] that a corresponding tileset exists. 







