---
layout: post
title: Pivots and fixed points
author: Rohit Vaish
published: true
comments: true
date:   2017-01-21 17:51:59 +0530
---

 *What do the simplex algorithm, Sperner's lemma, and Scarf's lemma have in common?*

In his 2013 [paper][M03] titled *Computing and Proving with Pivots*, Meunier showed that all of these seemingly disparate algorithms <!--(and others such as [Lemke-Howson algorithm][Lemke-HowsonWiki] and [colorful linear programming][B97ColorfulLP])--> can be understood in terms of a single combinatorial idea called *pivoting*. This blog post aims to provide an exposition of Meunier's paper. We start by revisiting Sperner's lemma, followed by abstracting out.., and finish by showing how all the algorithms are instantiations of ....

### Sperner's lemma

Recall the statement of [Sperner's lemma][SpernerWiki].

> Every Sperner coloring of a triangulation of a $n$-dimensional simplex consists of an odd number of elementary rainbow simplices. In particular, there is at least one.

It is convenient to talk about this for $n=2$.

![Sperner](/assets/pivots-and-fixed-points/Sperner.png){:class="img-responsive"}

Proof for the three dimensional case by a walk argument (show that this proof is actually due to [Scarf][S67Approx]).
Add picture of triangle.

Here's an [application][SpernerNYTimes] of Sperner's lemma to fair division of rent among roommates.

### Abstracting out the essentials

Revisit the above proof.

Point out the essentials ingredients used in our argument
item 1: ability to move from one member of the set family to another, and yet stay in the family
item 2: moving from one color-excess to another color-excess
Q. Does finiteness (or the lack of it) of the size of the family of sets play a role? This is important in the resolution of triangulation.

Abstract out the definition of simplicial complexes
A family of sets with the "downward closed" property.
[*abstract simplicial complex*](https://en.wikipedia.org/wiki/Abstract_simplicial_complex)

> An **abstract simplicial complex** is a family of finite sets such that all subsets of any given set in the family also belong to the family.
Examples: Simplicial complexes used in the applications to come.

A pseudomanifold/primoid/duoid is ...
Revisit the above examples of simplicial complexes.

### Pivoting

Abstract out the definition of pivoting
Example: Also include Gaussian elimination, if possible.
Informally, pivoting can be thought of a *walk* from one set to another, by removing an element and adding a different element, such that the new set also belongs to the set family. The hope is that pivoting in this manner is improving some underlying objective. Due to finiteness, we will reach the optimum.

Historical note: It is important to point that the idea of *pivoting* is not new---it goes back all the way to Gauss.
This is not Meunier's discovery, however his survey on this is the most accessible one.

Provide pseudocode for pivot-in and pivot-out routines

Argue that this suffices modulo a proof of termination, which is often ad hoc and problem specific.

### Beyond pseudomanifolds: Complementary Pivoting

### Simplex algorithm

### Scarf's lemma


<!-- Table generated using http://www.tablesgenerator.com/markdown_tables -->

|    Algorithm    | Simplicial Complex | Pivoting | Proof of termination |
|:---------------:|:------------------:|:--------:|:--------------------:|
|     Simplex     |                    |          |                      |
| Sperner's lemma |                    |          |                      |
|  Scarf's lemma  |                    |          |                      |




[M03]: http://www.rairo-ro.org/articles/ro/abs/2013/04/ro130042/ro130042.html
[SpernerWiki]: https://en.wikipedia.org/wiki/Sperner's_lemma
[SpernerNYTimes]: https://www.nytimes.com/2014/04/29/science/to-divide-the-rent-start-with-a-triangle.html?_r=0
[S67Approx]: http://epubs.siam.org/doi/abs/10.1137/0115116
[T74CompPiv]: https://people.orie.cornell.edu/miketodd/toddgencomppiv.pdf
[Lemke-HowsonWiki]: https://en.wikipedia.org/wiki/Lemke%E2%80%93Howson_algorithm
[B97ColorfulLP]: https://ie.technion.ac.il/~onn/Selected/MOR97.pdf
[Dantzig]: Citation to Dantzig's paper (or any other paper that proposed the simplex algorithm)
