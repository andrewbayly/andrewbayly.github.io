In this post I present a novel mathematical tool for developing quasiperiodic tilings which I call Extended Substitution Tilings (EST). EST may be used to solve certain problems which are unsolvable using a standard substitution tiling.

In a standard substitution tiling, inflation proceeds by applying the substitution rules n times. As n tends toward infinity, so the tiling expands to fill the entire plane. In an EST there are two sets of substitution rules, termed recursive(R) and terminal(T). Inflation proceeds in two corresponding phases: recursive and terminal. In the recursive phase R is applied n times. Then in the terminal phase T is applied just once. As n tends toward infinity, the tiling expands to fill the entire plane. 

Both R and T have the same set of prototiles, but the set of tiles used within the prototiles may be different. Provided some basic preconditions are met, an EST generates a tiling that is quasiperiodic. 

## Example

The example I've chosen to illustrate this concept is a tiling I call Hexagon Boat. For more detail on how I found this tiling see my upcoming blog post. 

### Recursive Rule

![Recursive Rule](/assets/images/2026-04-03/rules_R.png "Recursive Rule")

### Terminal Rule

![Terminal Rule](/assets/images/2026-04-03/rules_T.png "Terminal Rule")

### Patch

![Patch](/assets/images/2026-04-03/patch.png "Patch")


## Preconditons

For an EST to be considered mathematically and logically valid, it must satisfy these four preconditions:

   1. **The Symmetry Mirroring Precondition**
   The geometry of the sub-tiling must strictly reflect the underlying logical state. If the EST produces two different shapes (e.g., a "Left" and "Right" version of a rhomb), those shapes must be mutually locally derivable (MLD) from the logical labels. The Failure State: If you use a reflected shape to represent a phase shift, but the matching rules don't actually allow for a global reflection of the patch, you’ve created a "false visual promise."

   2. **Matching Rule Preservation**
      The new boundaries created by "cutting" the original tiles into a sub-tiling must be able to host the same (or an equivalent) set of matching rules as the original tiles. You cannot "lose" information in the extraction. If the original tiles required a specific parity to tile the plane, the EST boundaries must enforce that same parity.
   
   3. **Substitution Consistency**
      The inflation/deflation rules must be well-defined for the new sub-tiles. If you inflate an EST tile, it must decompose into an integer number of other EST tiles. If the "edges" of the sub-tiling don't align perfectly with the hierarchy of the parent tiling, the system is aperiodically unstable.

   4. **The "Cognitive Honesty" Precondition**
   For an EST to be valid in a research context, it should clarify the math, not obscure it. If the EST uses geometry as a "hack" or an "adornment" to represent what is actually a modular phase shift, it can be seen as an impurity. If the labels ($0, 1, 2...$) do the work, the EST shouldn't be used to "simulate" a symmetry that isn't functionally present in the substitution logic.









  
  
