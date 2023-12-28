---
title: "Introduction to the Theory of Elliptic Curves"
author: "Christian Testa"
date: "2017-03-18"
include-in-header:
  text: |
    <script type="text/javascript" src="http://mbostock.github.com/d3/d3.js?2.6.0"></script>
    <script type="text/javascript" src="/assets/js/2017-03-18-D3js2.js"></script>
categories: [mathematics]
---

<!-- I learned how to set up the extra-css and extra-js from
this stackoverflow post:
https://stackoverflow.com/questions/14113559/how-to-tune-layout-for-a-particular-page-post-in-jekyll
I made the SVG responsive following instructions here
http://soqr.fr/testsvg/embed-svg-liquid-layout-responsive-web-design.php
This example was incredibly helpful
http://bl.ocks.org/MoritzStefaner/1377729
Symbols were sourced from here:
http://www.dionysia.org/html/entities/symbols.html
https://en.wikipedia.org/wiki/Blackboard_bold
-->
<div id="container" class="svg-container">
<!-- <svg id="chart" width="1050px" height="700"></svg> -->
</div>


<!--  
Sources:
- Fluid Flow: https://web.stanford.edu/~cantwell/Difficult_to_find_publications/Elliptic_Curves_and_3D_flow_patterns_Cantwell_2000.pdf
- Sphere Packing: http://www.jmilne.org/math/Books/ectext5.pdf
- String Theory: Husemöller's Text on Elliptic Curves
- History of Curves
- http://www.math.vt.edu/people/brown/doc/dioellip.pdf
- http://livetoad.org/Courses/Documents/132d/Notes/history_of_elliptic_curves.pdf
- https://projecteuclid.org/download/pdf_1/euclid.bams/1183533964

-->

Elliptic curves are a subject, simple to construct and ubiquitous, that have found
themselves at the forefront of Number Theory and Algebraic Geometry research.
The subject has roots in some of the oldest Mathematics, and its modern
connections tie it to an incredible span of research including
fluid flow, sphere packing, modular forms, and string theory. Elliptic curves
are the degree three nonsingular algebraic plane curves with at least one
rational point.

<center>
![](/assets/img/2017-03-05/three-example-curves.png)
</center>

Their existence was considered by Diophantus in the 2nd century a.d. in
his text *Arithmetica*. The question he originally posed has been rephrased
in modern language: "To divide a given number into two numbers such that their
product is a cube minus its side." That is, given $a \in \mathbb N$ find
$x,y \in \mathbb Z$ such that
$$y(a-y) = x^3 - x.$$

<!--more-->

Elliptic curves were the topic of my undergraduate thesis, which you can download
<a href="/assets/Undergraduate Thesis - Christian Testa.pdf">
here.</a>

Most individuals are familiar with the plane conics, the degree
two nonsingular algebraic curves. Elliptic curves, in some sense,
are their slightly more complicated, yet seemingly infinitely more subtle,
older sibling. This will be realized later through the concept of genus.

Elliptic curves are contemporarily thought of as plane curves,
however they originally arose in the context of calculating arc-lengths
of ellipses. It is these arc-lengths
of ellipses which in part created elliptic curve's early ubiquity.
These are the elliptic integrals

$$ \int R(t,\sqrt{P(t)}) dt, $$

where $P(t)$ is a degree three or four nonsingular polynomial and $R$ is a 
rational function of $\sqrt{P(t)}$ and $t$. An example
might be derived from the pendulum, such as:

$$ \int \frac{d\theta}{\sqrt{C + \cos \theta}} =
- \int \frac{dx}{\sqrt{(1-x^2)(C+x)}} =
\int \frac{dx}{y}, \text{ where } y^2 = (1-x^2)(C+x).$$

Apollonius first considered calculating the arc-length of an ellipse
around 200 b.c. and found that he was unable to do it. This problem
defied progress until the 17th century when Euler and others found
infinite series expressions for arc-lengths. Further, Euler discovered
as surprising group law for these infinite series.

$$ \int_{\infty}^{x_1} \frac{dx}{y} + \int_{\infty}^{x_2} \frac{dx}{y} =
\int_{\infty}^{x_3} \frac{dx}{y}.$$

In 1687 Newton wrote down the majority of Bezout's Theorem, which
states that given two irreducible degree curves their intersection
counting multiplicity has the product of the degrees of the curves. This gave
algebraic motivation for what had already been observed: there is group structure
to the rational points of an elliptic curve.

<center>
<div style="display: block; margin: auto">
<img height='35%' width='35%' alt='Point Addition' src="/assets/img/2017-03-17/ch2-point-addition.png" />
<img height='35%' width='35%' alt='Point Multiplication' src="/assets/img/2017-03-17/ch2-point-multiplication.png" />
<br>
Point Addition and Multiplication
</div>
</center>

Elliptic integrals, before connecting to elliptic curves,
were inverted and considered as elliptic functions by mathematicians such
as Abel, Gauss, Jacobi, and notably Weierstraß. The motivation for doing
so is that the inverse of $\int \frac{dx}{\sqrt{1-x^2}} = \arcsin(x)$
is significantly more friendly a function.  

While it may be that Diophantus considered solutions to the equation
describing an elliptic curve, their modern formulation rests on their
analytic construction as the doubly periodic functions over $\mathbb C$.
These are Weierstraß' elliptic functions

$$\wp:\mathbb C \to \mathbb C / \Lambda \text{ for some } \Lambda \cong
\mathbb Z\omega_1 +\mathbb Z\omega_2,$$

$$ \wp(z \; \omega_1,\omega_2) = \frac{1}{z^2} + \sum_{n^2+m^2 \ne 0} \left( \frac{1}{(z+m\omega_1+n\omega_2)^2} -\frac{1}{\left(m\omega_1+n\omega_2\right)^2} \right)
,$$

$$\wp(z) = \frac{1}{z^2} + \sum_{\omega \in \Lambda - \{ 0\} } \left( \frac{1}{(z-\omega)^2} -\frac{1}{\omega}^2 \right),$$

where $\omega_1$ and $\omega_2$ generate the complex lattice
$\Lambda = \{ \mathbb Z \omega_1 + \mathbb Z \omega_2 \}$, or if
$\omega_2$ is normalized to 1, simply $\Lambda = \mathbb Z \omega + \mathbb Z$.

<center>
<div style="display: block; margin: auto">
<img height='15%' width='15%' alt='Wikipedia Lattice Construction' src="https://upload.wikimedia.org/wikipedia/commons/thumb/d/d5/Lattice_torsion_points.svg/450px-Lattice_torsion_points.svg.png" />
<img height='15%' width='15%' alt='Wikipedia Lattice Construction' src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/5a/Weierstrass_p.svg/150px-Weierstrass_p.svg.png" />
<img height='15%' width='15%' alt='Wikipedia Lattice Construction' src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/07/Weierstrass_elliptic_function_P.png/1280px-Weierstrass_elliptic_function_P.png" />
<br>
<a href="https://en.wikipedia.org/wiki/Weierstrass%27s_elliptic_functions">Weierstraß' $\wp$ function.</a>
</div>
</center>

Indeed, what these mathematicians surrounding the 18th Century had discovered
is that calculating arc-lengths of ellipses naturally involved thinking
about the problem in an algebraically closed field such as the
complex numbers $\mathbb C$, where the problem is translated to one with
doubly periodic structure. This structure is isomorphic to that of a torus.
One way to think of this is by "identifying edges." If $z$ drifts of the top
of the fundamental parallelogram, its image re-appears on the bottom
of the parallelogram under a doubly periodic function, and similarly for drifting over the side.
This is stating that as a Riemann surface an elliptic function have a topology with a single hole,
like a torus, and that it has genus $g = 1$. This suggests a major separation
in the theory of elliptic curves from those of conics, since the
conics are genus zero curves.

Weierstraß discovered that all doubly periodic functions could be expressed
through his $\wp$ function, and that it followed the differential
equation:

$$ \wp' (z)^2 = 4 \wp^3 (z) -g_4 \wp (z) - g_6,$$

where $g_4 = 60G_4$ and $g_6 = 140G_6$ and $G_n$ is Eisenstein's series given by
$$ G_n = \sum_{\omega \neq 0} \frac{1}{\omega^n}.$$

Corresponding to this complex doubly periodic structure,
Weierstraß had found a way to classify the equations of elliptic curves.
Any degree three nonsingular algebraic plane curve over a field $k$
can be transformed to Weierstraß form:

$$y^2 = x^3 + ax + b, \text{ provided } \text{characteristic}(k) \neq 2,3,$$

$$\text{ and always at least } y^2 + a_1 xy + a_3y = x^3 + a_2x^2 + a_4 x + a_6 \text{ even if } \text{characteristic}(k) = 2,3. $$

Indeed, Elliptic Curves defined over the complex numbers $\mathbb C$
are isomorphic to complex lattices given by $\mathbb C / \Lambda$ for a lattice
$\Lambda$. Startling connections were born of this fact.

The Eisenstein series are examples of modular forms, which are
incredibly deep number theoretical objects, described by complex functions which
satisfy certain invariance properties under their arguments translation
by particular matrix groups. Elliptic Curves are a seemingly simple class
of curves, with a natural group law
arising from Bezout's theorem
and Algebra-Geometric arguments, and yet we have found that they are
tied into Number Theory in profound and unanticipated ways.

To a Weierstraß equation is associated two useful invariants:
the $j$-invariant and the $\Delta$ discriminant. Klein's $j$-Invariant is
among other things, a representative of the elliptic curve's isomorphism
class over the algebraically closure, and the discriminant is a polynomial
defined as a product such that when a polynomial has factors with
multiplicity it vanishes, that is to say $\Delta = 0$ when the
curve is singular.

These are found to have the following equations

$$ \Delta=g_2^3-27g_3^2, $$

$$ j(\tau) = 1728 \frac{g_2^3}{\Delta}. $$

<center>
<div style="display: block; margin: auto">
<img width='50%' height='30%' src="https://upload.wikimedia.org/wikipedia/commons/3/37/KleinInvariantJ.jpg">
<br>
<span class="image-credit"> <a href="https://en.wikipedia.org/wiki/J-invariant">The $j$-Invariant as a modular form</a> </span>
</div>
</center>
<br>


The 20th Century saw great progress in Algebraic-Geometry and as a
result an elliptic curve's rational points, denoted $E(\mathbb Q)$, are
somewhat better understood.
In 1922 the Mordell-Weil Theorem was proven, which states that
all abelian varieties over number fields are finitely generated abelian groups.
Later in 1984 a conjecture by Mordell was proven by Faltings stating
that the genus 0 curves over $\mathbb Q$ have either $\emptyset$ or
infinitely many points, genus 1 curves have $\emptyset$,
finitely many, or infinitely many $\mathbb Q$-points.

However, simultaneous progress was being made in the theory of
Modular Forms. Ramanujan defined his $\tau$ function by the power series
expansion of the discriminant $\Delta$.

$$\sum_{n\geq 1}\tau(n)q^n=q\prod_{n\geq 1}(1-q^n)^{24} =\Delta(z),$$

$$\text{ where } q=\exp(2\pi iz).$$

Ramanujan was able to conjecture powerful number theoretic congruences describing this
$\tau$ function through modular forms. Separately Ramanujan used
Eisenstein series and other modular forms to produce astounding congruences
describing the partition function $p(n)$, the function which counts the
ways a whole number can be partitioned not counting ordering. The following
have been established as theory.

$$ \begin{align}
\tau(mn) = \tau(m) \tau(n) \text{ if } m \text{ and } n \text{ are relatively prime,} \\
\tau(p^{r + 1}) = \tau(p)\tau(p^r) - p^{11}\tau(p^{r - 1}), \\
|\tau(p)| \leq 2p^{11/2} \text{ for primes } p. \\
\end{align} $$

$$ \begin{align}
p(5k+4) & \equiv 0 \pmod 5 \\
p(7k+5) & \equiv 0 \pmod 7 \\
p(11k+6) & \equiv 0 \pmod {11}.
\end{align} $$

<center><a class="info" href="http://www.concinnitasproject.org/portfolio/gallery.php?id=Dyson_Freeman">
<div style="display: block; margin: auto">
<img width='75%' height='30%' src="/assets/img/2017-03-05/Dyson Freeman MacDonald Tau Equation.png">
<br>
<span class="image-credit">
Image Credit: The Concinnitas Project
</span>
</div></a>
</center>
<br>
These are some of the most beautiful congruences in Number Theory and Mathematics.
In a 1972 lecture by Freeman Dyson on the *Missed Opportunities* between Mathematics
and Physics, he begins with the story of the following MacDonald equation for
Ramanujan's Tau Function. The MacDonald Equation is an astonishing formula, but to have also found
connections to physics highlights the depth to which Ramanujan's $\tau$-function,
born out of the discriminant $\Delta$, reaches into the abstract world.

In the early 1990s Andrew Wiles established the Modularity Theorem,
an equivalence between modular forms and the rational structure of
an elliptic curve $E(\mathbb Q)$, and consequently proved Fermat's Last Theorem.
After the 20th Century, Elliptic Curves have found themselves amidst deep
Number Theory whilst being employed in applications from cryptography to
engineering. The Birch and Swinnerton-Dyer conjecture remains open,
and we have yet
to fully understand the rank of the group $E(\mathbb Q)$. Elliptic Curves
may have been with us from the very origins of algebra, but we are
still just beginning to understand their tremendous structure.


### Sources

- [Alice Silverberg : Ranks Cheat Sheet](https://www.math.uci.edu/~asilverb/bibliography/RanksCheatSheet.pdf)
- [Dale Husemöller : Elliptic Curves](https://books.google.com/books?isbn=0387215778)
- [Ezra Brown and Bruce T. Myers : Elliptic Curves from Mordell to Diophantus and Back](http://www.math.vt.edu/people/brown/doc/dioellip.pdf)
- [Freeman Dyson : Missed Opportunities](https://projecteuclid.org/download/pdf_1/euclid.bams/1183533964)
- [J.S. Milne : Elliptic Curves](http://www.jmilne.org/math/Books/ectext5.pdf)
- [Joseph H. Silverman : Advanced Topics in the Arithmetic of Elliptic Curves](https://books.google.com/books?isbn=0387943250)
- [Joseph H. Silverman : Elliptic Curves](https://books.google.com/books?isbn=1475719205)
- [Neal I. Koblitz : Elliptic Curves and Modular Forms](https://books.google.com/books?isbn=1461209099)
- [Silverman and Tate : Rational Points on Elliptic Curves](https://books.google.com/books?isbn=3319185888)
- [Tom M. Apostol : Modular Functions and Dirichlet Series in Number Theory](https://books.google.com/books?id=zkrUBwAAQBAJ)
