Sub Rosa ( described in [this paper](https://arxiv.org/pdf/1512.01402) ) is a system of quasiperiodic rhombic substitution tilings with 2n-fold rotational symmetry, for any n. Sub Rosa takes care of the case of even n, however it leaves open the case of odd n. In this post, I describe in outline a method for transforming a Sub Rosa tiling, reducing the rotational symmetry by a factor of two, thus yielding a system of quasiperiodic rhombic substitution tilings with n-fold rotational symmetry for any n.

To transform a tiling, we need to transform the substitution rules. Within a Sub Rosa tiling, we find roses with 2n-fold rotational symmetry, as well as some roses with n-fold rotational symmetry.

Some terminology: We refer to a "broken" rose as a rose with the inner-most two rows of petals reversed, as illustrated in the following diagram. As you can see, while a rose has 2n-fold rotational symmetry, a broken rose has only n-fold rotational symmetry. We will also encounter "partially broken" roses ( see diagram ) which have no rotational symmetry.

Roses: (from left) original, broken and partially broken.

![roses-7](/assets/images/2024-12-16/roses-7.png "roses-7") 

Our strategy then is to modify the substitution rules, removing all roses, and replacing them with broken roses or partially broken roses. If we succeed in removing all roses, then we will no longer have 2n-fold rotational symmetry, and if we succeed in adding at least some broken roses, we will achieve the goal of reaching n-fold rotational symmetry. One assumption I have made is that there is at least one rose appearing in the center of a tile, or at the very least a patch which already displays n-fold rotational symmetry.

Based on my observations of the examples in the Sub Rosa paper, roses appear either at the center of a super-rhombus or in the middle of at edge, or at the corners. In each case, we can break either the whole rose or part of a rose by working around it, rotating the petals in pairs in turn, until we run out of petals around the rose.

## Examples

To illustrate the process, I present the modified substitution rules, and a tile patch for n=5 and n=7.

### n=5

![rules-5](/assets/images/2024-12-16/rules-5.png "rules-5") 

![patch-5](/assets/images/2024-12-16/patch-5.png "patch-5") 

### n=7

![rules-7](/assets/images/2024-12-16/rules-7.png "rules-7") 

![patch-7](/assets/images/2024-12-16/patch-7.png "patch-7") 

