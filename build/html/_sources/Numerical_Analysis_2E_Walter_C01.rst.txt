Numerical_Analysis_2E_Walter_C01
================================

	 		 		 	 	 		
			
				
					
In this second edition, the outline of chapters and sections has been preserved. The subtitle “An Introduction”, as suggested by several reviewers, has been deleted. The content, however, is brought up to date, both in the text and in the notes. Many passages in the text have been either corrected or improved. Some biographical notes have been added as well as a few exercises and computer assignments. The typographical appearance has also been improved by printing vectors and matrices consistently in boldface types.
					
With regard to computer language in illustrations and exercises, we now adopt uniformly Matlab. For readers not familiar with Matlab, there are a number of introductory texts available, some, like Moler [2004], Otto and Denier [2005], Stanoyevitch [2005] that combine Matlab with numerical computing, others, like Knight [2000], Higham and Higham [2005], Hunt, Lipsman and Rosenberg [2006], and Driscoll [2009], more exclusively focused on Matlab.
					
The major novelty, however, is a complete set of detailed solutions to all exercises and machine assignments. The solution manual is available to instructors upon request at the publisher’s website http://www.birkhauser-science.com/978-0-8176- 8258-3. Selected solutions are also included in the text to give students an idea of what is expected. The bibliography has been expanded to reflect technical advances in the field and to include references to new books and expository accounts. As a result, the text has undergone an expansion in size of about 20%.
				
			
		
	 	 		 		 	 	 		
			
				
Prologue
--------

**P1 Overview**

Numerical Analysis is the branch of mathematics that provides tools and methods
for solving mathematical problems in numerical form. The objective is to develop
detailed computational procedures, capable of being implemented on electronic
computers, and to study their performance characteristics. Related fields are Sci-
entific Computation, which explores the application of numerical techniques and
computer architectures to concrete problems arising in the sciences and engineering;
Complexity Theory, which analyzes the number of “operations” and the amount of
computer memory required to solve a problem; and Parallel Computation, which
is concerned with organizing computational procedures in a manner that allows
running various parts of the procedures simultaneously on different processors.

The problems dealt with in computational mathematics come from virtually
all branches of pure and applied mathematics. There are computational aspects
in number theory, combinatorics, abstract algebra, linear algebra, approximation
theory, geometry, statistics, optimization, complex analysis, nonlinear equations,
differential and other functional equations, and so on. It is clearly impossible
to deal with all these topics in a single text of reasonable size. Indeed, the
tendency today is to develop specialized texts dealing with one or the other
of these topics. In the present text we concentrate on subject matters that are
basic to problems in approximation theory, nonlinear equations, and differential
equations. Accordingly, we have chapters on machine arithmetic, approximation
and interpolation, numerical differentiation and integration, nonlinear equations,
one-step and multistep methods for ordinary differential equations, and boundary
value problems in ordinary differential equations. Important topics not covered
in this text are computational number theory, algebra, and geometry; constructive
methods in optimization and complex analysis; numerical linear algebra; and the
numerical solution of problems involving partial differential equations and integral
equations. Selected texts for these areas are enumerated in Sect. P3.

We now describe briefly the topics treated in this text. Chapter 1 deals with
the basic facts of life regarding machine computation. It recognizes that, although
present-day computers are extremely powerful in terms of computational speed,
reliability, and amount of memory available, they are less than ideal – unless
supplemented by appropriate software – when it comes to the precision available,
and accuracy attainable, in the execution of elementary arithmetic operations. This
raises serious questions as to how arithmetic errors, either present in the input
data of a problem or committed during the execution of a solution algorithm,
affect the accuracy of the desired results. Concepts and tools required to answer
such questions are put forward in this introductory chapter. In Chap. 2, the central
theme is the approximation of functions by simpler functions, typically polynomials
and piecewise polynomial functions. Approximation in the sense of least squares
provides an opportunity to introduce orthogonal polynomials, which are relevant
also in connection with problems of numerical integration treated in Chap. 3. A large
part of the chapter, however, deals with polynomial interpolation and associated
error estimates, which are basic to many numerical procedures for integrating
functions and differential equations. Also discussed briefly is inverse interpolation,
an idea useful in solving equations.

First applications of interpolation theory are given in Chap. 3, where the tasks
presented are the computation of derivatives and definite integrals. Although the
formulae developed for derivatives are subject to the detrimental effects of machine
arithmetic, they are useful, nevertheless, for purposes of discretizing differential
operators. The treatment of numerical integration includes routine procedures, such
as the trapezoidal and Simpson’s rules, appropriate for well-behaved integrands, as
well as the more sophisticated procedures based on Gaussian quadrature to deal
with singularities. It is here where orthogonal polynomials reappear. The method of
undetermined coefficients is another technique for developing integration formulae.
It is applied to approximate general linear functionals, the Peano representation
of linear functionals providing an important tool for estimating the error. The
chapter ends with a discussion of extrapolation techniques; although applicable to
more general problems, they are inserted here since the composite trapezoidal rule
together with the Euler–Maclaurin formula provides the best-known application –
Romberg integration.

Chapter 4 deals with iterative methods for solving nonlinear equations and
systems thereof, the pi`ece de r´esistance being Newton’s method. The emphasis here
lies in the study of, and the tools necessary to analyze, convergence. The special
case of algebraic equations is also briefly given attention.

Chapter 5 is the first of three chapters devoted to the numerical solution of
ordinary differential equations. It concerns itself with one-step methods for solving
initial value problems, such as the Runge–Kutta method, and gives a detailed
analysis of local and global errors. Also included is a brief introduction to stiff
equations and special methods to deal with them. Multistep methods and, in
particular, Dahlquist’s theory of stability and its applications, is the subject of
Chap. 6. The final chapter (Chap. 7) is devoted to boundary value problems and their
solution by shooting methods, finite difference techniques, and variational methods.

**P2 Numerical Analysis Software**

There are many software packages available, both in the public domain and dis-
tributed commercially, that deal with numerical analysis algorithms. A widely used
source of numerical software is Netlib, accessible at http://www.netlib.org.

Large collections of general-purpose numerical algorithms are contained in
sources such as Slatec (http://www.netlib.org/slatec) and TOMS
(ACM Transactions on Mathematical Software). Specialized packages relevant
to the topics in the chapters ahead are identified in the “Notes” to each chapter.
Likewise, specific files needed to do some of the machine assignments in the
Exercises are identified as part of the exercise.

Among the commercial software packages we mention the Visual Numerics
(formerly IMSL) and NAG libraries. Interactive systems include HiQ, Macsyma,
Maple, Mathcad, Mathematica, and Matlab. Many of these packages, in addition
to numerical computation, have symbolic computation and graphics capabilities.
Further information is available in the Netlib file commercial. For more libraries,
and for interactive systems, also see Lozier and Olver [1994, Sect. 3].

In this text we consistently use Matlab as a vehicle for describing algorithms
and as the software tool for carrying out some of the exercises and all machine
assignments.

**P3 Textbooks and Monographs**

We provide here an annotated list (ordered alphabetically with respect to authors)
of other textbooks on numerical analysis, written at about the same, or higher, level
as the present one. Following this, we also mention books and monographs dealing
with topics in computational mathematics not covered in our (and many other) books
on numerical analysis. Additional books dealing with specialized subject areas, as
well as other literature, are referenced in the “Notes” to the individual chapters. We
generally restrict ourselves to books written in English and, with a few exceptions,
published within the last 25 years or so. Even so, we have had to be selective. (No
value judgment is to be implied by our selections or omissions.) A reader with access
to the AMS (American Mathematical Society) MathSci Net homepage will have no
difficulty in retrieving a more complete list of relevant items, including older texts.

**P3.1 Selected Textbooks on Numerical Analysis**

Atkinson [1989] A comprehensive in-depth treatment of standard topics short of
partial differential equations; includes an appendix describing some of the better-
known software packages.

Atkinson and Han [2009] An advanced text on theoretical (as opposed to com-
putational) aspects of numerical analysis, making extensive use of functional
analysis.

Bruce, Giblin, and Rippon [1990] A collection of interesting mathematical prob-
lems, ranging from number theory and computer-aided design to differential
equations, that require the use of computers for their solution.

Cheney and Kincaid [1994] Although an undergraduate text, it covers a broad
area, has many examples from science and engineering as well as computer
programs; there are many exercises, including machine assignments.

Conte and de Boor [1980] A widely used text for upper-division undergraduate
students; written for a broad audience, with algorithmic concerns in the fore-
ground; has Fortran subroutines for many algorithms discussed in the text.

Dahlquist and Bj¨orck [2003, 2008] The first (2003) text – a reprint of the 1974
classic – provides a comprehensive introduction to all major fields of numerical
analysis, striking a good balance between theoretical issues and more practical
ones. The second text expands substantially on the more elementary topics
treated in the first and represents the first volume of more to come.

Deuflhard and Hohmann [2003] An introductory text with emphasis on machine
computation and algorithms; includes discussions of three-term recurrence
relations and stochastic eigenvalue problems (not usually found in textbooks),
but no differential equations.

Fr¨oberg [1985] A thorough and exceptionally lucid exposition of all major topics
of numerical analysis exclusive of algorithms and computer programs.

H¨ammerlin and Hoffmann [1991] Similar to Stoer and Bulirsch [2002] in its
emphasis on mathematical theory; has more on approximation theory and
multivariate interpolation and integration, but nothing on differential equations.

Householder [2006] A reissue of one of the early mathematical texts on the
subject, with coverage limited to systems of linear and nonlinear equations and
topics in approximation.

Isaacson and Keller [1994] One of the older but still eminently readable texts,
stressing the mathematical analysis of numerical methods.

Kincaid and Cheney [1996] Related to Cheney and Kincaid [1994] but more
mathematically oriented and unusually rich in exercises and bibliographic items.
Kress [1998] A rather comprehensive text with a strong functional analysis
component.

Neumaier [2001] A text emphasizing robust computation, including interval
arithmetic.

Rutishauser [1990] An annotated translation from the German of an older text
based on posthumous notes by one of the pioneers of numerical analysis;
although the subject matter reflects the state of the art in the early 1970s, the
treatment is highly original and is supplemented by translator’s notes to each
chapter pointing to more recent developments.

Schwarz [1989] A mathematically oriented treatment of all major areas of numer-
ical analysis, including ordinary and partial differential equations.

Stoer and Bulirsch [2002] Fairly comprehensive in coverage; written in a style
appealing more to mathematicians than engineers and computer scientists; has
many exercises and bibliographic references; serves not only as a textbook but
also as a reference work.

Todd [1979, 1977] Rather unique books, emphasizing problem-solving in areas
often not covered in other books on numerical analysis.

**P3.2 Monographs and Books on Specialized Topics**

A collection of outstanding survey papers on specialized topics in numerical
analysis is being assembled by Ciarlet and Lions [1990–2003] in handbooks of
numerical analysis; nine volumes have appeared so far. Another source of surveys
on a variety of topics is Acta numerica, an annual series of books edited by Iserles
[1992–2010], of which 19 volumes have been published so far. For an authoritative
account of the history of numerical analysis from the 16th through the 19th century,
the reader is referred to the book by Goldstine [1977]. For more recent history, see
Bultheel and Cools, eds. [2010].

The related areas of Scientific Computing and Parallel Computing are rather
more recent fields of study. Basic introductory texts are Scott et al. [2005]
and Tveito and Winter [2009]. Texts relevant to linear algebra and differential
equations are Schendel [1984], Ortega and Voigt [1985], Ortega [1989], Golub
and Ortega [1992], [1993], Van de Velde [1994], Burrage [1995], Heath [1997],
Deuflhard and Bornemann [2002], O’Leary [2009], and Quarteroni et al. [2010].
Other texts address topics in optimization, Pardalos et al. [1992] and Gonnet
and Scholl [2009]; computational geometry, Akl and Lyons [1993]; and other
miscellaneous areas, Crandall [1994], [1996], K¨ockler [1994], Bellomo and Preziosi
[1995], Danaila et al. [2007], and Farin and Hansford [2008]. Interesting historical
essays are contained in Nash, ed. [1990]. Matters regarding the Complexity of
numerical algorithms are discussed in an abstract framework in books by Traub and
Wo´zniakowski [1980] and Traub, Wasilkowski, and Wo´zniakowski [1983], [1988],
with applications to the numerical integration of functions and nonlinear equations,
and similarly, applied to elliptic partial differential equations and integral equations,
in the book by Werschulz [1991]. Other treatments are those by Kronsj¨o [1987], Ko
[1991], Bini and Pan [1994], Wang et al. [1994], Traub and Werschulz [1998], Ritter
[2000], and Novak et al. [2009]. For an in-depth complexity analysis of Newton’s
method, the reader is encouraged to study Smale’s [1987] lecture.

Material on Computational Number Theory can be found, at the undergraduate
level, in the book by Rosen [2000], which also contains applications to cryptography
and computer science, and in Allenby and Redfern [1989], and at a more advanced
level in the books by Niven et al. [1991], Cohen [1993], and Bach and Shallit
[1996]. Computational methods of factorization are dealt with in the book by
Riesel [1994]. Other useful sources are the set of lecture notes by Pohst [1993]
on algebraic number theory algorithms, and the proceedings volumes edited by
Pomerance [1990] and Gautschi [1994a, Part II]. For algorithms in Combinatorics,
see the books by Nijenhuis and Wilf [1978], Hu and Shing [2002], and Cormen et
al. [2009]. Various aspects of Computer Algebra are treated in the books by Geddes
et al. [1992], Mignotte [1992], Davenport et al. [1993], Mishra [1993], Heck [2003],
and Cox et al. [2007].

Other relatively new disciplines are Computational Geometry and Geometric
Modeling, Computer-Aided Design, and Computational Topology, for which rel-
evant texts are, respectively, Preparata and Shamos [1985], Edelsbrunner [1987],
M¨antyl¨a [1988], Taylor [1992], McLeod and Baart [1998], Gallier [2000], Cohen et
al. [2001], and Salomon [2006]; Hoschek and Lasser [1993], Farin [1997], [1999],
and Prautsch et al. [2002]; Edelsbrunner [2006], and Edelsbrunner and Harer [2010].
Statistical Computing is covered in general textbooks such as Kennedy and Gentle
[1980], Anscombe [1981], Maindonald [1984], Thisted [1988], Monahan [2001],
Gentle [2009], and Lange [2010]. More specialized texts are Devroye [1986] and
H¨ormann et al. [2004] on the generation of nonuniform random variables, Sp¨ath
[1992] on regression analysis, Heiberger [1989] on the design of experiments,
Stewart [1994] on Markov chains, Xiu [2010] on stochastic computing and uncer-
tainty quantification, and Fang and Wang [1994], Manno [1999], Gentle [2003],
Liu [2008], Shonkwiler and Mendivil [2009], and Lemieux [2009] on Monte Carlo
and number-theoretic methods. Numerical techniques in Optimization (including
optimal control problems) are discussed in Evtushenko [1985]. An introductory
book on unconstrained optimization is Wolfe [1978]; among more advanced and
broader texts on optimization techniques we mention Gill et al. [1981], Ciarlet
[1989], and Fletcher [2001]. Linear programming is treated in Nazareth [1987] and
Panik [1996], linear and quadratic problems in Sima [1996], and the application of
conjugate direction methods to problems in optimization in Hestenes [1980]. The
most comprehensive text on (numerical and applied) Complex Analysis is the three-
volume treatise by Henrici [1988, 1991, 1986]. Numerical methods for conformal
mapping are also treated in Kythe [1998], Schinzinger and Laura [2003], and
Papamichael and Stylianopoulos [2010]. For approximation in the complex domain,
the standard text is Gaier [1987]; Stenger [1993] deals with approximation by
sinc functions, Stenger [2011] providing some 450 Matlab programs. The book by
Iserles and Nørsett [1991] contains interesting discussions on the interface between
complex rational approximation and the stability theory of discretized differential
equations. The impact of high-precision computation on problems and conjectures
involving complex approximation is beautifully illustrated in the set of lectures by
Varga [1990].

For an in-depth treatment of many of the preceding topics, also see the four-
volume work of Knuth [1975, 1981, 1973, 2005–2006].
Perhaps the most significant topic omitted in our book is numerical linear algebra
and its application to solving partial differential equations by finite difference or
finite element methods. Fortunately, there are many treatises available that address
these areas. For Numerical Linear Algebra, we refer to the classic work of Wilkinson
[1988] and the book by Golub and Van Loan [1996]. Links and applications
of matrix computation to orthogonal polynomials and quadrature are the subject
of Golub and Meurant [2010]. Other general texts are Jennings and McKeown
[1992], Watkins [2002], [2007], Demmel [1997], Trefethen and Bau [1997], Stewart
[1973], [1998], Meurant [1999], White [2007], Allaire and Kaber [2008], and
Datta [2010]; Higham [2002], [2008] has a comprehensive treatment of error and
stability analyses and the first, equally extensive, treatment of the numerics of matrix
functions. Solving linear systems on vector and shared memory parallel computers
and the use of linear algebra packages on high-performance computers are discussed
in Dongarra et al. [1991], [1998]. The solution of sparse linear systems and the
special data structures and pivoting strategies required in direct methods are treated
in Østerby and Zlatev [1983], Duff et al. [1989], Zlatev [1991], and Davis [2006],
whereas iterative techniques are discussed in the classic texts by Young [2003]
and Varga [2000], and in Il’in [1992], Hackbusch [1994], Weiss [1996], Fischer
[1996], Brezinski [1997], Greenbaum [1997], Saad [2003], Broyden and Vespucci
[2004], Hageman and Young [2004], Meurant [2006], Chan and Jin [2007], Byrne
[2008], and Wo´znicki [2009]. The books by Branham [1990] and Bj¨orck [1996]
are devoted especially to least squares problems. For eigenvalues, see Chatelin
[1983], [1993], and for a good introduction to the numerical analysis of symmetric
eigenvalue problems, see Parlett [1998]. The currently very active investigation of
large sparse symmetric and nonsymmetric eigenvalue problems and their solution
by Lanczos-type methods has given rise to many books, for example, Cullum and
Willoughby [1985], [2002], Meyer [1987], Sehmi [1989], and Saad [1992]. For
structured and symplectic eigenvalue problems, see Fassbender [2000] and Kressner
[2005], and for inverse eigenvalue problems, Xu [1998] and Chu and Golub [2005].
For readers wishing to test their algorithms on specific matrices, the collection of
test matrices in Gregory and Karney [1978] and the “matrix market” on the Web
(http://math.nist.gov./MatrixMarket) are useful sources.

Even more extensive is the textbook literature on the numerical solution of Par-
tial Differential Equations. The field has grown so much that there are currently only
a few books that attempt to cover the subject more or less as a whole. Among these
are Birkhoff and Lynch [1984] (for elliptic problems), Hall and Porsching [1990],
Ames [1992], Celia and Gray [1992], Larsson and Thom´ee [2003], Quarteroni and
Valli [1994], Morton and Mayers [2005], Sewell [2005], Quarteroni [2009], and
Tveito and Winter [2009]. Variational and finite element methods seem to have
attracted the most attention. An early and still frequently cited reference is the
book by Ciarlet [2002] (a reprint of the 1978 original); among more recent texts
we mention Beltzer [1990] (using symbolic computation), K˘r´ı˘zek and Neittaanm¨aki
[1990], Brezzi and Fortin [1991], Schwab [1998], Kwon and Bang [2000] (using
Matlab), Zienkiewicz and Taylor [2000], Axelsson and Barker [2001], Babuˇska
and Strouboulis [2001], H¨ollig [2003], Monk [2003] (for Maxwell’s equation),
Ern and Guermonde [2004], Kythe and Wei [2004], Reddy [2004], Chen [2005],
Elman et al. [2005], Thom´ee [2006] (for parabolic equations), Braess [2007],
Demkowicz [2007], Brenner and Scott [2008], Bochev and Gunzburger [2009],
Efendiev and Hou [2009], and Johnson [2009]. Finite difference methods are treated
in Ashyralyev and Sobolevski˘ı [1994], Gustafsson et al. [1995], Thomas [1995],
[1999], Samarskii [2001], Strikwerda [2004], LeVeque [2007], and Gustafsson
[2008]; the method of lines in Schiesser [1991]; and the more refined techniques
of multigrids and domain decomposition in McCormick [1989], [1992], Bramble
[1993], Sha˘ıdurov [1995], Smith et al. [1996], Quarteroni and Valli [1999], Briggs
et al. [2000], Toselli and Widlund [2005], and Mathew [2008]. Problems in potential
theory and elasticity are often approached via boundary element methods, for which
representative texts are Brebbia and Dominguez [1992], Chen and Zhou [1992],
Hall [1994], and Steinbach [2008]. A discussion of conservation laws is given in the
classic monograph by Lax [1973] and more recently in LeVeque [1992], Godlewski
and Raviart [1996], Kr¨oner [1997], and LeVeque [2002]. Spectral methods, i.e.,
expansions in (typically) orthogonal polynomials, applied to a variety of problems,
were pioneered in the monograph by Gottlieb and Orszag [1977] and have received
extensive treatments in more recent texts by Canuto et al. [1988], [2006], [2007],
Fornberg [1996], Guo [1998], Trefethen [2000] (in Matlab), Boyd [2001], Peyret
[2002], Hesthaven et al. [2007], and Kopriva [2009].

Early, but still relevant, texts on the numerical solution of Integral Equations are
Atkinson [1976] and Baker [1977]. More recent treatises are Atkinson [1997] and
Kythe and Puri [2002]. Volterra integral equations are dealt with by Brunner and van
der Houwen [1986] and Brunner [2004], whereas singular integral equations are the
subject of Pr¨ossdorf and Silbermann [1991].

**P4 Journals**

Here we list the major journals (in alphabetical order) covering the areas of
numerical analysis and mathematical software.

* ACM Transactions on Mathematical Software
* Applied Numerical Mathematics
* BIT Numerical Mathematics
* Calcolo
* Chinese Journal of Numerical Mathematics and Applications
* Computational Mathematics and Mathematical Physics
* Computing
* IMA Journal on Numerical Analysis
* Journal of Computational and Applied Mathematics
* Mathematical Modelling and Numerical Analysis
* Mathematics of Computation
* Numerical Algorithms
* Numerische Mathematik
* SIAM Journal on Numerical Analysis
* SIAM Journal on Scientific Computing

					
Chapter 1  Machine Arithmetic and Related Matters
--------------------------------------------------				
			
			
				
					
The questions addressed in this first chapter are fundamental in the sense that they are relevant in any situation that involves numerical machine computation, regardless of the kind of problem that gave rise to these computations. In the first place, one has to be aware of the rather primitive type of number system available on computers. It is basically a finite system of numbers of finite length, thus a far cry from the idealistic number system familiar to us from mathematical analysis. The passage from a real number to a machine number entails rounding, and thus small errors, called roundoff errors. Additional errors are introduced when the individual arithmetic operations are carried out on the computer. In themselves, these errors are harmless, but acting in concert and propagating through a lengthy computation, they can have significant – even disastrous – effects.
					
Most problems involve input data not representable exactly on the computer. Therefore, even before the solution process starts, simply by storing the input in computer memory, the problem is already slightly perturbed, owing to the necessity of rounding the input. It is important, then, to estimate how such small perturbations in the input affect the output, the solution of the problem. This is the question of the (numerical) condition of a problem: the problem is called well conditioned if the changes in the solution of the problem are of the same order of magnitude as the perturbations in the input that caused those changes. If, on the other hand, they are much larger, the problem is called ill conditioned. It is desirable to measure by a single number – the condition number of the problem – the extent to which the solution is sensitive to perturbations in the input. The larger this number, the more ill conditioned the problem.
					
Once the solution process starts, additional rounding errors will be committed, which also contaminate the solution. The resulting errors, in contrast to those caused by input errors, depend on the particular solution algorithm. It makes sense, therefore, to also talk about the condition of an algorithm, although its analysis is usually quite a bit harder. The quality of the computed solution is then determined by both (essentially the product of) the condition of the problem and the condition of the algorithm.
					
1.1 Real Numbers, Machine Numbers, and Rounding
-----------------------------------------------
					
We begin with the number system commonly used in mathematical analysis and confront it with the more primitive number system available to us on any particular computer. We identify the basic constant (the machine precision) that determines the level of precision attainable on such a computer.
					
1.1.1 Real Numbers
					
One can introduce real numbers in many different ways. Mathematicians favor the axiomatic approach, which leads them to define the set of real numbers as a “complete Archimedean ordered field.” Here we adopt a more pedestrian attitude and consider the set of real numbers R to consist of positive and negative numbers represented in some appropriate number system and manipulated in the usual manner known from elementary arithmetic. We adopt here the binary number system, since it is the one most commonly used on computers. Thus,

.. math::
			
   x \in R \text{ iff } x = \pm (b_n2^n + b_{n-1}2^{n-1}+ ... + b_0 + b_{-1}2^{-1} +  b_{-2}2^{-2} + ...) (1.1) 

Here :math:`n \geq 0` is some integer, and the “binary digits” bi are either 0 or 1,

.. math::	
				
   b_i = 0 \text{ or } b_i = 1 \text{ for all i}. (1.2)
					
It is important to note that in general we need infinitely many binary digits to represent a real number. We conveniently write such a number in the abbreviated form (familiar from the decimal number system)
	
.. math::
				
   x = \pm (b_nb:{n-1} ... b_0.b_{-1}b_{-2}b_{-3}...)_ 2; (1.3)
					
where the subscript 2 at the end is to remind us that we are dealing with a binary number. (Without this subscript, the number could also be read as a decimal number, which would be a source of ambiguity.) The dot in (1.3) – appropriately called the binary point – separates the integer part on the left from the fractional part on the right. Note that representation (1.3) is not unique, for example, :math:`(.0.011\bar{1}...)_2=(0.1)_2`. We regain uniqueness if we always insist on a finite representation, if one exists.
					
Examples.1. :math:`(10011.01)_2=2^4+2^1+2^0+2^{-2}=16+2+1+\frac{1}{4}=(19.25)_{10}`
				
			
2. :math:`(.0101\bar{01}...)_2 = \sum_{k=2 \ (k even)}^{\infty} 2^{-k} = \sum_{m=1}^{\infty} 2^{-2m} = \frac{1}{4} \sum_{m=0}^{\infty} (\frac{1}{4})^m`
				
:math:`\frac{1}{4} \frac{1}{1-\frac{1}{4}}=\frac{1}{3} = (0.33\bar{3}...)_{10}`
				
3. :math:`\frac{1}{5}=(0.2)_{10} = (0.0011\bar{0011}...)_2


To determine the binary digits on the right, one keeps multiplying by 2 and observing the integer part in the result; if it is zero, the binary digit in question is 0, otherwise 1. In the latter case, the integral part is removed and the process repeated.
				
			
The last example is of interest insofar as it shows that to a finite decimal number there may correspond a (nontrivial) infinite binary representation. One cannot assume, therefore, that a finite decimal number is exactly representable on a binary computer. Conversely, however, to a finite binary number there always corresponds a finite decimal representation. (Why?)
					
**1.1.2 Machine Numbers**
					
There are two kinds of machine numbers: floating point and fixed point. The first corresponds to the “scientific notation” in the decimal system, whereby a number is written as a decimal fraction times an integral power of 10. The second allows only for fractions. On a binary computer, one consistently uses powers of 2 instead of 10. More important, the number of binary digits, both in the fraction and in the exponent of 2 (if any), is finite and cannot exceed certain limits that are characteristics of the particular computer at hand.
					
**1.1.2.1 Floating-Point Numbers**
					
We denote by t the number of binary digits allowed by the computer in the fractional part and by s the number of binary digits in the exponent. Then the set of (real) floating-point numbers on that computer will be denoted by R.t; s/. Thus,

.. math::

   x \in R(t,s) \text{ iff }  x=f \cdot 2^3,

where, in the notation of (1.3),

.. math::
					
   f= \pm (.b_{-1}b_{-2} ... b_{-t})_2,  e=\pm (c_{s-1}c_{s-2} ... c_0)_2: (1.5)
					
Here all :math:`b_i` and :math:`c_j` are binary digits, that is, either zero or one. The binary fraction f is usually referred to as the mantissa of x and the integer e as the exponent of x. The number x in (1.4) is said to be normalized if in its fraction f we have :math:`b_{-1}=1`. We assume that all numbers in R(t,s) are normalized (with the exception of x =0, which is treated as a special number). If :math:`x \neq 0` were not normalized, we could
				
			
		
		
			
 Fig. 1.1 Packing of a floating-point number in a machine register
					
multiply f by an appropriate power of 2, to normalize it, and adjust the exponent accordingly. This is always possible as long as the adjusted exponent is still in the admissible range.
					
We can think of a floating-point number (1.4) as being accommodated in a machine register as shown in Fig. 1.1. The figure does not quite correspond to reality, but is close enough to it for our purposes.
					
Note that the set (1.4) of normalized floating-point numbers is finite and is thus represented by a finite set of points on the real line. What is worse, these points are not uniformly distributed (cf. Ex. 1). This, then, is all we have to work with!
					
It is immediately clear from (1.4) and (1.5) that the largest and smallest magnitude of a (normalized) floating-point number is given, respectively, by

.. math::
					
   max_{x \in R(t,s)} |x| = (1-2^{-t})2^{2^s}-1}, min_{x \in R(t,s)} |x| = 2^{-2^s}

On a Sun Sparc workstation, for example, one has t = 23, s = 7, so that the maximum and minimum in (1.6) are :math:`1.70 \times 10^{38}` and :math:`2.94 \times 10^{-39}`, respectively. (Because of an asymmetric internal hardware representation of the exponent on these computers, the true range of floating-point numbers is slightly shifted, more like from :math:`1.18 \times 10^{38}` to :math:`3.40 \times 10^{38}`.) Matlab arithmetic, essentially double precision, uses t D 53 and s D 10, which greatly expands the number range from something like :math:`10^{-308}` to :math:`10^{+308}`.
					
A real nonzero number whose modulus is not in the range determined by (1.6) cannot be represented on this particular computer. If such a number is produced during the course of a computation, one says that overflow has occurred if its modulus is larger than the maximum in (1.6) and underflow if it is smaller than the minimum in (1.6). The occurrence of overflow is fatal, and the machine (or its operating system) usually prompts the computation to be interrupted. Underflow is less serious, and one may get away with replacing the delinquent number by zero. However, this is not foolproof. Imagine that at the next step the number that underflowed is to be multiplied by a huge number. If the replacement by zero has been made, the result will always be zero.
					
To increase the precision, one can use two machine registers to represent a machine number. In effect, one then embeds :math:`\mathbb{R}(t,s) \subset \mathbb{R}(2t,s)`, and calls :math:`x \in \mathbb{R}(2t,s)` a double-precision number.
				
					
Fig. 1.2 Packing of a fixed-point number in a machine register
					
**1.1.2.2 Fixed-Point Numbers**
					
This is the case (1.4) where e = 0. That is, fixed-point numbers are binary fractions, x = f , hence |f| < 1. We can therefore only deal with numbers that are in the interval (–1,1). This, in particular, requires extensive scaling and rescaling to make sure that all initial data, as well as all intermediate and final results, lie in that interval. Such a complication can only be justified in special circumstances where machine time and/or precision is at a premium. Note that on the same computer as considered before, we do not need to allocate space for the exponent in the machine register, and thus have in effect s C t binary digits available for the fraction f , hence more precision; cf. Fig. 1.2.
					
**1.1.2.3 Other Data Structures for Numbers**
					
Complex floating-point numbers consist of pairs of real floating-point numbers, the first of the pair representing the real part and the second the imaginary part. To avoid rounding errors in arithmetic operations altogether, one can employ rational arithmetic, in which each (rational) number is represented by a pair of extended-precision integers – the numerator and denominator of the rational number. The Euclidean algorithm is used to remove common factors. A device that allows keeping track of error propagation and the influence of data errors is interval arithmetic involving intervals guaranteed to contain the desired numbers. In complex arithmetic, one employs rectangular or circular domains.
					
**1.1.3 Rounding**
					
A machine register acts much like the infamous Procrustes bed in Greek mythology. Procrustes was the innkeeper whose inn had only beds of one size. If a fellow came along who was too tall to fit into his beds, he cut off his feet. If the fellow was too short, he stretched him. In the same way, if a real number comes along that is too long, its tail end (not the head) is cutoff; if it is too short, it is padded by zeros at the end.
				
					
More specifically, let
				
.. math::

   x \in \mathbb{R}, x=\pm (\sum_{k=1}^{\infty} b_{-k}2^{-k})2^e			
			
 be the “exact” real number (in normalized floating-point form) and

.. math::

   x* \in \mathbb{R}, x*=\pm (\sum_{k=1}^{t} b*_{-k}2^{-k})2^{e*} 					
					
the rounded number. One then distinguishes between two methods of rounding, the first being Procrustes’ method.

(a) Chopping.Onetakes

.. math::

   x* = chop(x), e*= e, b*_{-k} =  b_{-k} \text{ for } k = 1, 2, ..., t

(b) Symmetric rounding. This corresponds to the familiar rounding up or rounding down in decimal arithmetic, based on the first discarded decimal digit: if it is larger than or equal to 5, one rounds up; if it is less than 5, one rounds down. In binary arithmetic, the procedure is somewhat simpler, since there are only two possibilities: either the first discarded binary digit is 1, in which case one rounds up, or it is 0, in which case one rounds down. We can write the procedure very simply in terms of the chop operation in (1.9):
					
.. math::

   x*= rd(x), rd(x) := chop(x + \frac{1}{2} \dot 2^{-t} \dot 2^e).

					
There is a small error incurred in rounding, which is most easily estimated in the case of chopping. Here the absolute error |x- x*| is
				
.. math::

   |x-chop(x)| = |\pm \sum_{k=t+1}^{\infty} b_{-k} 2^{-k}|2^e

   \leq \sum_{k=t+1}^{\infty} 2^{-k} \dot 2^e = 2^{-t} \dot 2^e
			

It depends on e (i.e., the magnitude of x), which is the reason why one prefers the relative error |(x x*)/x| (if :math:`x \neq 0`), which, for normalized x, can be estimated as
					
.. math::

9999

    ˇx chop.x/ˇ 2t 2e 2t 2e t
				
			
			
				
					
ˇ ˇD22:(1.11) ˇxˇˇX1 ˇ122e
				
			
			
				
					
!
				
			
			
				
					
2e
				
				
					
(1.8)
				
			
			
				
					
(1.7)
				
			
			 			 			 			
				
					
ˇ ̇
				
				
					
bk 2k ˇ 2e
				
			
			
				
					
kD1
				
			
		
		
			
				
					
1.2 Machine Arithmetic 7 Similarly, in the case of symmetric rounding, one finds (cf. Ex. 6)
					
ˇˇ
 ˇ x rd.x/ ˇ 2t : (1.12)
					
The number on the right is an important, machine-dependent quantity, called the machine precision (or unit roundoff),
					
eps D 2t I (1.13)
					
it determines the level of precision of any large-scale floating-point computation. In Matlab double-precision arithmetic, one has t = 53, so that eps 1:11 1016 (cf. Ex. 5), corresponding to a precision of 15–16 significant decimal digits.
					
Since it is awkward to work with inequalities, one prefers writing (1.12) equivalently as an equality,
					
rd.x/Dx.1C"/; j"jeps; (1.14) and defers dealing with the inequality (for ") to the very end.
					
1.2 Machine Arithmetic
					
The arithmetic used on computers unfortunately does not respect the laws of ordinary arithmetic. Each elementary floating-point operation, in general, generates a small error that may then propagate through subsequent machine operations. As a rule, this error propagation is harmless, except in the case of subtraction, where cancellation effects may seriously compromise the accuracy of the results.
					
1.2.1 A Model of Machine Arithmetic
					
Any of the four basic arithmetic operations, when applied to two machine numbers, may produce a result no longer representable on the computer. We have therefore errors also associated with arithmetic operations. Barring the occurrence of overflow or underflow, we may assume as a model of machine arithmetic that each arithmetic operation ı .D C; ; ; =/ produces a correctly rounded result. Thus, if x; y 2 R.t;s/ are floating-point machine numbers, and fl.xıy/ denotes the machine- produced result of the arithmetic operation xıy, then
					
fl.xıy/Dxıy.1C"/; j"jeps: (1.15)
				
			
			
				
					
ˇˇ x
				
			
			 		
		
			
				
					
8 1 Machine Arithmetic and Related Matters
				
			
			
				
					
This can be interpreted in a number of ways, for example, in the case of multiplication,
					
pp fl.xy/DŒx.1C"/yDxŒy.1C"/D.x 1C"/.y 1C"/D:
				
			
			 			 			
				
					
In each equation we identify the computed result as the exact result on data that are slightly perturbed, whereby the respective relative perturbations can be estimated,
				
			
			
				
					
pˇˇ forexample,byj"jepsinthefirsttwoequations,and 1C1C12",ˇ12"ˇ
				
			
			 			
				
					
12 eps in the third. These are elementary examples of backward error analysis, a powerful tool for estimating errors in machine computation (cf. also Sect. 1.3).
					
Even though a single arithmetic operation causes a small error that can be neglected, a succession of arithmetic operations can well result in a significant error, owing to error propagation. It is like the small microorganisms that we all carry in our bodies: if our defense mechanism is in good order, the microorganisms cause no harm, in spite of their large presence. If for some reason our defenses are weakened, then all of a sudden they can play havoc with our health. The same is true in machine computation: the rounding errors, although widespread, will cause little harm unless our computations contain some weak spots that allow rounding errors to take over to the point of completely invalidating the results. We learn about one such weak spot (indeed the only one) in the next section.1
					
1.2.2 Error Propagation in Arithmetic Operations: Cancellation Error
					
We now study the extent to which the basic arithmetic operations propagate errors already present in their operands. Previously, in Sect. 1.2.1, we assumed the
					
1Rounding errors can also have significant implications in real life. One example, taken from politics, concerns the problem of apportionment: how should the representatives in an assembly, such as the US House of Representatives or the Electoral College, be constituted to fairly reflect the size of population in the various states? If the total number of representatives in the assembly is given, say, A, the total population of the US is P , and the population of State i is pi , then State i should be allocated
					
ri D pi A P
				
			
			 			
				
					
representatives. The problem is that ri is not an integer, in general. How then should ri be rounded
				
			
			
				
					
to an integer ri ? One can think of three natural criteria to be imposed: (1) ri should be one of the two integers closest to ri (“quota condition”). (2) If A is increased, all other things being
				
			
			
				
					
				
			
			
				
					
the same, then ri should not decrease (“house monotonicity”). (3) If pi is increased, the other pj
				
			
			
				
					
remaining constant, then ri should not decrease (“population monotonicity”). Unfortunately, there is no apportionment method that satisfies all three criteria. There is indeed a case in US history when Samuel J. Tilden lost his bid for the presidency in 1876 in favor of Rutherford B. Hayes, purely on the basis of the apportionment method adopted on that occasion (which, incidentally, was not the one prescribed by law at the time).
				
			
		
		
			
				
					
1.2 Machine Arithmetic 9
				
			
			
				
					
operands to be exact machine-representable numbers and discussed the errors due to imperfect execution of the arithmetic operations by the computer. We now change our viewpoint and assume that the operands themselves are contaminated by errors, but the arithmetic operations are carried out exactly. (We already know what to do, cf. (1.15), when we are dealing with machine operations.) Our interest is in the errors in the results caused by errors in the data.
					
(a) Multiplication. We consider values x.1 C "x/ and y.1 C "y/ of x and y contaminated by relative errors "x and "y , respectively. What is the relative error in the product? We assume "x , "y sufficiently small so that quantities of second order, "2x , "x "y , "2y – and even more so, quantities of still higher order – can be neglected against the epsilons themselves. Then
					
x.1C"x/y.1C"y/Dxy.1C"x C"y C"x"y/xy.1C"x C"y/: Thus, the relative error "xy in the product is given (at least approximately) by
					
"xy D"x C"y; (1.16)
					
that is, the (relative) errors in the data are being added to produce the (relative) error in the result. We consider this to be acceptable error propagation, and in this sense, multiplication is a benign operation.
				
			
			
				
					
(b) Division. Here we have similarly (if y ¤ 0)
 x.1C"x/ D x.1C"x/.1"y C"2y C /
				
			
			 			
				
					
that is,
				
				
					
y.1C"y/ y
 yx . 1 C " x " y / ;
					
"x=y D"x "y:
				
			
			
				
					
Also division is a benign operation.
 (c) Addition and subtraction. Since x and y can be numbers of arbitrary signs, it
				
			
			
				
					
suffices to look at addition. We have
					
x.1C"x/Cy.1C"y/DxCyCx"x Cy"y
					
D.xCy/ 1Cx"xCy"y ; xCy
					
assuming x C y ¤ 0. Therefore,
					
"xCyD x "xC y "y: xCy xCy
				
				
					
(1.18)
				
			
			
				
					
(1.17)
				
			
			 			 			 		
		
			
				
					
10 1
				
				
					
Machine Arithmetic and Related Matters
				
			
			 			 			 			 			 			 			
				
					
x=
					
y= x−y= =
				
			
			
				
					
101100101bbgggg
				
			
			 			 			 			 			 			 			 			
				
					
101100101bbgggg
				
			
			 			 			 			 			 			 			 			
				
					
000000000bbgggg
				
			
			
				
					
↑
					
Fig. 1.3
				
				
					
The cancellation phenomenon
				
			
			
				
					
As before, the error in the result is a linear combination of the errors in the data, but now the coefficients are no longer ̇1 but can assume values that are arbitrarily large. Note first, however, that when x and y have the same sign, then both coefficients are positive and bounded by 1, so that
					
j"xCyj  j"xj C j"yj .x y > 0/I (1.19)
					
addition, in this case, is again a benign operation. It is only when x and y have opposite signs that the coefficients in (1.18) can be arbitrarily large, namely, when jx C yj is arbitrarily small compared to jxj and jyj. This happens when x and y are almost equal in absolute value, but opposite in sign. The large magnification of error then occurring in (1.18) is referred to as cancellation error. It is the only serious weakness – the Achilles heel, as it were – of numerical computation, and it should be avoided whenever possible. In particular, one should be prepared to encounter cancellation effects not only in single devastating amounts, but also repeatedly over a long period of time involving “small doses” of cancellation. Either way, the end result can be disastrous.
					
We illustrate the cancellation phenomenon schematically in Fig. 1.3, where b, b0, b00 stand for binary digits that are reliable, and the g represent binary digits contaminated by error; these are often called “garbage” digits. Note in Fig. 1.3 that “garbage – garbage D garbage,” but, more importantly, that the final normalization of the result moves the first garbage digit from the 12th position to the 3rd.
					
Cancellation is such a serious matter that we wish to give a number of elementary examples, not only of its occurrence, but also of how it might be avoided.
					
Examples. 1. An algebraic identity: .a b/2 D a2 2ab C b2. Although this is a valid identity in algebra, it is no longer valid in machine arithmetic. Thus, on a 2-decimal-digit computer, with a D 1.8, b D 1.7, we get, using symmetric rounding,
					
fl.a2 2abCb2/D3:26:2C2:9D0:10
					
instead of the true result 0.010, which we obtain also on our 2-digit computer if we use the left-hand side of the identity. The expanded form of the square thus produces a result which is off by one order of magnitude and on top has the wrong sign.
				
			
			
				
					
↓
				
			
			
				
					
e
				
			
			 			
				
					
e
				
			
			 			
				
					
e
				
			
			 			 			 			 			 			 			 			 			
				
					
bbgggg?????????
				
			
			
				
					
e−9
				
			
			 			 		
		
			
				
					
1.3 The Condition of a Problem 11
				
			
			
				
					
2. Quadraticequation:x256xC1D0.Theusualformulaforaquadraticgives, in 5-decimal arithmetic,
					
p
 x1 D28 783D2827:982D0:018000;
					
p
 x2 D28C 783D28C27:982D55:982:
				
			
			 			 			
				
					
This should be contrasted with the exact roots 0.0178628. . . and 55.982137. . . . As can be seen, the smaller of the two is obtained to only two correct decimal digits, owing to cancellation. An easy way out, of course, is to compute x2 first, which involves a benign addition, and then to compute x1 D 1=x2 by Vieta’s formula, which again involves a benign operation – division. In this way we obtain both roots to full machine accuracy.
				
			
			
				
					
pp
 3. ComputeyD xCı– x,wherex>0andjıjisverysmall.Clearly,the
				
			
			 			
				
					
formula as written causes severe cancellation errors, since each square root has to be rounded. Writing instead
					
yDpıp xCıC x
					
completely removes the problem.
					
    4. 							
Compute y D cos.x C ı/ cos x, where jıj is very small. Here cancellation
 							
can be avoided by writing y in the equivalent form
 							
yD2sin2ısin xC2ı :
 						
    5. 							
Computey Df.xCı/f.x/,wherejıjisverysmallandf agivenfunction. Special tricks, such as those used in the two preceding examples, can no longer be played, but if f is sufficiently smooth in the neighborhood of x, we can use Taylor expansion:
 							
y D f 0 . x / ı C 12 f 0 0 . x / ı 2 C    :
 The terms in this series decrease rapidly when jıj is small so that cancellation
 							
is no longer a problem.
 							
Addition is an example of a potentially ill-conditioned function (of two vari-
 						
					
ables). It naturally leads us to study the condition of more general functions.
					
1.3 The Condition of a Problem
					
A problem typically has an input and an output. The input consists of a set of data, say, the coefficients of some equation, and the output of another set of numbers uniquely determined by the input, say, all the roots of the equation in some prescribed order. If we collect the input in a vector x 2 Rm (assuming the data
				
			
			 			 		
		
			
				
					
12 1 Machine Arithmetic and Related Matters
				
			
			 			
				
					
xy
					
Fig. 1.4 Black box representation of a problem
					
consist of real numbers), and the output in the vector y 2 Rn (also assumed real), we have the black box situation shown in Fig. 1.4, where the box P accepts some input x and then solves the problem for this input to produce the output y.
					
We may thus think of a problem as a map f , given by
 f W Rm ! Rn; y D f .x/: (1.20)
					
(One or both of the spaces Rm, Rn could be complex spaces without changing in any essential way the discussion that follows.) What we are interested in is the sensitivity of the map f at some given point x to a small perturbation of x, that is, how much bigger (or smaller) the perturbation in y is compared to the perturbation in x. In particular, we wish to measure the degree of sensitivity by a single number – the condition number of the map f at the point x. We emphasize that, as we perturb x, the function f is always assumed to be evaluated exactly, with infinite precision. The condition of f , therefore, is an inherent property of the map f and does not depend on any algorithmic considerations concerning its implementation.
					
This is not to say that knowledge of the condition of a problem is irrelevant to any algorithmic solution of the problem. On the contrary, the reason is that quite often the computed solution y of (1.20) (computed in floating-point machine arithmetic, using a specific algorithm) can be demonstrated to be the exact solution to a “nearby” problem, that is,
					
y D f .x/; (1.21) where x is a vector close to the given data x,
					
x DxCı; (1.22)
					
and moreover, the distance kık of x to x can be estimated in terms of the machine precision. Therefore, if we know how strongly (or weakly) the map f reacts to a small perturbation, such as ı in (1.22), we can say something about the error y y in the solution caused by this perturbation. This, indeed, is an important technique of error analysis – known as backward error analysis – which was pioneered in the 1950s by J. W. Givens, C. Lanczos, and, above all, J. H. Wilkinson.
					
Maps f between more general spaces (in particular, function spaces) have also been considered from the point of view of conditioning, but eventually, these spaces have to be reduced to finite-dimensional spaces for practical implementation of the maps in question.
				
			
			
				
					
P
				
			
			 			 		
		
			
				
					
1.3 The Condition of a Problem 13
				
			
			
				
					
1.3.1 Condition Numbers
					
We start with the simplest case of a single function of one variable.
 The case m D n D 1: y D f.x/. Assuming first x ¤ 0, y ¤ 0, and denoting by x a small perturbation of x, we have for the corresponding perturbation y by
					
Taylor’s formula
					
y D f .x C x/ f .x/ f 0.x/x; (1.23) assuming that f is differentiable at x. Since our interest is in relative errors, we
					
write this in the form
					
y xf0.x/ x : (1.24) y f.x/ x
					
The approximate equality becomes a true equality in the limit as x ! 0. This suggests that the condition of f at x be defined by the quantity
					
ˇˇ
					
ˇxf 0.x/ˇ
 .condf /.x/ WD ˇ f.x/ ˇ: (1.25)
					
This number tells us how much larger the relative perturbation in y is compared to the relative perturbation in x.
					
If x D 0 and y ¤ 0, it is more meaningful to consider the absolute error measure for x and for y still the relative error. This leads to the condition number jf 0.x/=f.x/j. Similarly for y D 0, x ¤ 0. If x D y D 0, the condition number by (1.23) would then simply be jf 0.x/j.
					
The case of arbitrary m; n: here we write
 x D Œx1;x2;:::;xmT 2 Rm; y D Œy1;y2;:::;ynT 2 Rn
					
and exhibit the map f in component form
 y D f.x1;x2;:::;xm/;  D 1;2;:::;n: (1.26)
					
We assume again that each function f has partial derivatives with respect to all m variables at the point x. Then the most detailed analysis departs from considering each component y as a function of one single variable, x. In other words, we subject only one variable, x, to a small change and observe the resulting change in just one component, y . Then we can apply (1.25) and obtain
					
ˇˇ ˇx@f ˇ
					
.x/WD.cond f/.x/WDˇ @x ˇ : (1.27)  ˇf.x/ˇ
				
			
			 			 			 			 			 		
		
			
				
					
14 1 Machine Arithmetic and Related Matters This gives us a whole matrix .x/ D Œ.x/ 2 Rnm of condition numbers.
					
To obtain a single condition number, we can take any convenient measure of the “magnitude” of the matrix .x/ such as one of the matrix norms defined in (1.30),
					
.condf /.x/ D k.x/k; .x/ D Œ.x/: (1.28)
					
The condition so defined, of course, depends on the choice of norm, but the order of magnitude (and that is all that counts) should be more or less the same for any reasonable norm.
					
If a component of x, or of y, vanishes, one modifies (1.27) as discussed earlier.
					
A less-refined analysis can be modeled after the one-dimensional case by defining the relative perturbation of x 2 Rm to mean
					
kxkRm; xDŒx1;x2;:::;xmT; (1.29) kxkRm
					
where x is a perturbation vector whose components x are small compared to x,andwherekkRm issomevectornorminRm.Fortheperturbationycausedby x, one defines similarly the relative perturbation kykRn =kykRn , with a suitable vector norm k  kRn in Rn. One then tries to relate the relative perturbation in y to the one in x.
					
To carry this out, one needs to define a matrix norm for matrices A 2 Rnm. We choose the so-called “operator norm,”
					
kAxkRn
 kAkRnm WD max : (1.30)
					
In the following we take for the vector norms the “uniform” (or infinity) norm,
				
			
			
				
					
kxkRm D max jxj DW kxk1; kykRn D max jyj DW kyk1 : 1m 1 n
					
It is then easy to show that (cf. Ex. 32)
					
Xm
					
jaj; A D Œa 2 Rnm: D1
				
				
					
(1.31)
					
(1.32)
				
			
			
				
					
kAkRnm D kAk1 WD max 1 n
					
Now in analogy to (1.23), we have
				
			
			
				
					
x2Rm kxkRm x¤0
				
			
			
				
					
Xm @f
 y Df.xCx/f.x/ @x x
					
D1
				
			
			
				
					
C
				
			
			 			 			 		
		
			
				
					
1.3 The Condition of a Problem 15
				
			
			
				
					
with the partial derivatives evaluated at x. Therefore, at least approximately, ˇˇ ˇˇ
					
D1 @x
					
Since this holds for each D 1;2;:::;n, it also holds for maxjyj, giving, in
				
			
			
				
					
Xm ˇ @ f ˇ
 ˇ ˇjxjmaxjxj
				
				
					
Xm ˇ @ f ˇ ˇ ˇ
				
			
			
				
					
jyj
 maxjxjmax ˇ ˇ:
				
			
			 			 			
				
					
D1 @x ˇˇ
				
			
			
				
					
Xm ˇ @ f ˇ  D1 @x
				
			
			 			
				
					
view of (1.31) and (1.32),
					
Here,
				
				
					
					
@f kyk1 kxk1 @x :
					
1
					
23 6@f1 @f1 @f1 7
					
6@x@x @x7 612m7
					
67 6 @f2 @f2 @f2 7
				
				
					
(1.33)
					
(1.34)
				
			
			 			 			 			 			
				
					
@f D 6 @x1 @x2 @xm 7 2 Rnm @x6 7
				
			
			 			 			 			 			
				
					
6    7 67 4@f@f @f5
				
			
			
				
					
nnn @x1 @x2 @xm
				
			
			 			 			 			
				
					
is the Jacobian matrix of f . (This is the analogue of the first derivative for systems of functions of several variables.) From (1.33) one now immediately obtains for the relative perturbations
					
kyk1 kxk1 k@f =@xk1 kxk1 : kyk1 kf .x/k1 kxk1
					
Although this is an inequality, it is sharp in the sense that equality can be achieved for a suitable perturbation x. We are justified, therefore, in defining a global condition number by
					
.condf/.x/WDkxk1k@f=@xk1 : (1.35) kf .x/k1
					
Clearly, in the case m D n D 1, definition (1.35) reduces precisely to definition (1.25) (as well as (1.28)) given earlier. In higher dimensions (m and/or n larger than 1), however, the condition number in (1.35) is much cruder than the one in (1.28). This is because norms tend to destroy detail: if x, for example, has components
				
			
			 			 			 			 		
		
			
				
					
16 1 Machine Arithmetic and Related Matters
				
			
			
				
					
of vastly different magnitudes, then kxk1 is simply equal to the largest of these components, and all the others are ignored. For this reason, some caution is required when using (1.35).
				
			
			
				
					
To give an example, consider
					
23
				
				
					
23
				
			
			
				
					
6 6 x1 C x1 7 7 6 x 1 7 f.x/D6 1 27; xD6 7:
				
			
			
				
					
411545 x x x2
					
12
 The components of the condition matrix .x/ in (1.27) are then
				
			
			
				
					
ˇˇˇˇˇˇˇˇ ˇxˇ ˇxˇ ˇxˇ ˇxˇ
				
			
			
				
					
11 D ˇ 2 ˇ ; 12 D ˇ 1 ˇ ; 21 D ˇ 2 ˇ ; 22 D ˇ 1 ˇ ; x1 Cx2 x1 Cx2 x2 x1 x2 x1
				
			
			 			 			 			 			
				
					
indicating ill-conditioning if either x1 x2 or x1 x2 and jx1j (hence also jx2j) is not small. The global condition number (1.35), on the other hand, since
					
23
				
			
			
				
					
@f.x/D 1 6x2
				
				
					
x12 7; 5
				
			
			
				
					
@x x12x2 4 x2
				
			
			 			 			
				
					
x12
 becomes, when L1 vector and matrix norms are used (cf. Ex. 33),
				
			
			
				
					
kxk1 2
				
			
			
				
					
max.x12; x2/ jx1x2j.jx1 C x2j C jx1 x2j/
				
			
			 			
				
					
x12x2
 Here x1 x2 or x1 x2 yields .cond f /.x/ 2, which is obviously misleading.
				
			
			
				
					
.condf/.x/D 1
				
				
					
jx1j C jx2j max.x12; x2/
 D2 jx1x2j jx1 Cx2jCjx1 x2j:
				
			
			 			 			 			 			
				
					
1.3.2 Examples
					
We illustrate the idea of numerical condition in a number of examples, some of which are of considerable interest in applications.
					
Z
				
			
			
				
					
1 tn
 t C 5dt for some fixed integer n 1. As it stands, the
				
			
			
				
					
1. Compute In D
 example here deals with a map from the integers to reals and therefore does
				
			
			 			
				
					
0
				
			
		
		
			
				
					
1.3
				
				
					
The Condition of a Problem 17
				
			
			 			
				
					
yy
					
0
				
			
			
				
					
f
				
				
					
n
				
			
			
				
					
n
					
not fit our concept of “problem” in (1.20). However, we propose to compute In recursively by relating Ik to Ik1 and noting that
					
(1.36)
				
			
			 			 			
				
					
I0 D
 To find the recursion, observe that
				
			
			
				
					
Fig. 1.5 Black box for recursion (1.38)
				
			
			
				
					
Z ˇ1
 1dt ˇ6
				
			
			
				
					
t C 5 D ln.t C 5/ˇ D ln 5 : 00
				
			
			 			
				
					
tD15: tC5 tC5
					
Thus, multiplying both sides by tk1 and integrating from 0 to 1 yields Ik D 5Ik1 C k1; k D 1;2;:::;n:
				
				
					
(1.37)
				
			
			 			 			
				
					
We see that Ik is a solution of the (linear, inhomogeneous, first-order) difference equation
					
yk D 5yk1 C k1; k D 1;2;3;::: : (1.38)
					
We now have what appears to be a practical scheme to compute In: start with y0 D I0 given by (1.36) and then apply in succession (1.38) for k D 1;2;:::;n; then yn D In. Recursion (1.38), for any starting value y0, defines a function,
					
yn D fn.y0/: (1.39)
					
WehavetheblackboxinFig.1.5andthusaproblemfn W R!R.(Heren is a parameter.) We are interested in the condition of fn at the point y0 D I0 given by (1.36). Indeed, I0 in (1.36) is not machine representable and must be rounded to I0 before recursion (1.38) can be employed. Even if no further errors are introduced during the recursion, the final result will not be exactly In, but some approximation In D fn.I0/, and we have, at least approximately (actually exactly; see the remark after (1.46)),
					
ˇˇ ˇˇ
 ˇI I ˇ ˇI I ˇ
 ˇ n n ˇ D .condfn/.I0/ˇ 0 0 ˇ : (1.40)
				
			
			 			 			
				
					
In I0
				
			
		
		
			
				
					
18
				
				
					
1 Machine Arithmetic and Related Matters To compute the condition number, note that fn is a linear function of y0.
				
			
			
				
					
Indeed, if n D 1, then If n D 2, then
				
				
					
y1 D f1.y0/ D 5y0 C 1:
				
			
			
				
					
y 2 D f 2 . y 0 / D  5 y 1 C 12 D . 5 / 2 y 0 5 C 21 ; and so on. In general,
					
yn D fn.y0/ D .5/ny0 C pn; where pn is some number (independent of y0). There follows
					
ˇˇˇˇ
				
			
			
				
					
ˇy0f 0.y0/ˇ ˇy0.5/n ˇ
				
			
			
				
					
.cond f /.y / D ˇ n ˇ D ˇ ˇ : n0ˇyˇˇyˇ
				
				
					
(1.41)
				
			
			 			 			
				
					
Now, if y0 D I0, then yn D In, and from the definition of In as an integral it is clear that In decreases monotonically in n (and indeed converges monotonically to zero as n ! 1). Therefore,
					
I0 5n I0 5n
 .cond fn/.I0/ D I > I D 5n: (1.42)
					
n0
					
We see that fn.y0/ is severely ill-conditioned at y0 D I0, the more so the larger n.
					
We could have anticipated this result by just looking at the recursion (1.38): we keep multiplying by (–5), which tends to make things bigger, whereas they should get smaller. Thus, there will be continuous cancellation occurring throughout the recursion.
					
How can we avoid this ill-conditioning? The clue comes from the remark just made: instead of multiplying by a large number, we would prefer dividing by a large number, especially if the results get bigger at the same time. This is accomplished by reversing recurrence (1.38), that is, by choosing an > n and computing
					
					
yk1D15 k1yk ; kD;1;:::;nC1: (1.43)
					
The problem then, of course, is how to compute the starting value y . Before we deal with this, let us observe that we now have a new black box, as shown in Fig. 1.6.
					
As before, the function involved, gn, is a linear function of y, and an argument similar to the one leading to (1.41) then gives
				
			
			
				
					
nn
				
			
			 			 		
		
			
				
					
1.3
				
				
					
The Condition of a Problem
				
				
					
19
				
			
			 			
				
					
yv yn (v > n) Fig. 1.6 Black box for the recursion (1.43)
					
ˇˇ ˇy 1 nˇ
					
.condgn/.y/ D ˇ 						5 ˇ;  > n: ˇ yn ˇ
				
			
			 			 			
				
					
(1.44)
					
(1.45)
					
(1.46)
					
where I is some approximation of I. Actually, I does not even have to be close to I for (1.46) to hold, since the function gn is linear. Thus, we may take I D 0, committing a 100% error in the starting value, yet obtaining In with a relative error
				
			
			
				
					
For y D I, we get, again by the monotonicity of In,
				
			
			
				
					
1 n .condgn/.I/ < 5 ;  > n:
				
			
			
				
					
In analogy to (1.40), we now have
 ˇˇ ˇˇˇˇ
				
			
			
				
					
ˇIIˇ ˇIIˇ 1 nˇIIˇ ˇ n nˇD.condgn/.I/ˇ ˇ< ˇ ˇ; In I 5 I
				
			
			 			 			 			
				
					
ˇˇ ˇIIˇ 1 n ˇ n nˇ<
				
			
			
				
					
; >n: (1.47) The bound on the right can be made arbitrarily small, say, ", if we choose
					
large enough, for example,
					
nCln1" : (1.48) ln5
					
The final procedure, therefore, is: given the desired relative accuracy ", choose to be the smallest integer satisfying (1.48) and then compute
				
			
			 			
				
					
In 5
				
			
			 			
				
					
I D 0 ;
 I D1 1I ; kD;1;:::;nC1:
					
This will produce a sufficiently accurate In In, even in the presence of rounding errors committed in (1.49): they, too, will be consistently attenuated.
					
Similar ideas can be applied to the more important problem of computing solutions to second-order linear recurrence relations such as those satisfied by Bessel functions and many other special functions of mathematical physics.
				
			
			
				
					
k1 5 k k
				
			
			
				
					
				
				
					
(1.49)
				
			
			
				
					
gn
				
			
		
		
			
				
					
20 1 Machine Arithmetic and Related Matters
				
			
			
				
					
The procedure of backward recurrence is then closely tied up with the theory
					
of continued fractions.
 2. Algebraic equations: these are equations involving a polynomial of given
					
degree n,
 p.x/D0; p.x/Dxn Can1xn1 CCa1xCa0; a0 ¤0: (1.50)
					
Let be some fixed root of the equation, which we assume to be simple,
					
p./D0; p0./¤0: (1.51)
					
The problem then is to find , given p. The data vector a D Œa0; a1; : : : ; an1T 2 Rn consists of the coefficients of the polynomial p, and the result is , a real or complex number. Thus, we have
					
W Rn ! C;  D .a0;a1;:::;an1/: (1.52) What is the condition of ? We adopt the detailed approach of (1.27) and first
					
define
				
			
			
				
					
.cond /.a/ D
				
				
					
(1.54)
				
			
			
				
					
ˇˇ ˇa @ ˇ ˇ @a ˇ
				
			
			
				
					
D.cond/.a/Dˇ 						ˇ; D0;1;:::;n1: ˇˇ
				
			
			
				
					
Then we take a convenient norm, say, the L1 norm kk1 vector DŒ0;:::;n1T,todefine
					
n1 X
				
				
					
WD
				
				
					
D0
				
			
			
				
					
.cond /.a/:
 To determine the partial derivative of with respect to a , observe that we have
					
the identity
					
Œ.a0;a1;:::;an/n Can1Œ./n1 CCaŒ./ CCa0 0: Differentiating this with respect to a , we get
					
nŒ.a0;a1;:::;an/n1 @ Can1.n1/Œ./n2 @ C @a @a
					
Ca Œ./1 @ CCa @ CŒ./ 0; @a 1@a
				
			
			
				
					
D0
				
			
			
				
					
P
				
				
					
(1.53) n1 jj of the
				
			
			 			 			 			 			
				
					
				
			
			
				
					
where the last term comes from differentiating the first factor in the product a . The last identity can be written as
				
			
		
		
			
				
					
1.3
				
				
					
The Condition of a Problem
				
				
					
21
				
			
			
				
					
p0./@ C D0: @a
					
Since p0./ ¤ 0, we can solve for @=@a and insert the result in (1.53) and (1.54) to obtain
					
n1 1X
					
.cond/.a/ D jp0./j
 We illustrate (1.55) by considering the polynomial p of degree n that has the
					
zeros 1;2;:::;n,
 p.x/D .x/Dxn Can1xn1 CCa0: (1.56)
				
			
			 			
				
					
Yn D1
				
			
			
				
					
This is a famous example due to J.H. Wilkinson, who discovered the ill- conditioning of some of the zeros almost by accident. If we let D , D 1;2;:::;n, it can be shown that
					
mincond Dcond1 n2 as n!1;
				
			
			
				
					
p !n 1 2C1
				
			
			
				
					
max cond p p as n ! 1: 22n21
				
			
			
				
					
jaj jj: (1.55)
				
			
			 			
				
					
D0
				
			
			 			 			
				
					
p
					
The worst-conditioned root is 0 with 0 the integer closest to n= 2, when n is large. Its condition number grows like .5:828 : : : /n , thus exponentially fast in n. For example, when n D 20, then cond 0 D 0:540 1014.
					
The example teaches us that the roots of an algebraic equation written in the form (1.50) can be extremely sensitive to small changes in the coefficients a . It would, therefore, be ill-advised to express every polynomial in terms of powers, as in (1.56) and (1.50). This is particularly true for characteristic polynomials of matrices. It is much better here to work with the matrices themselves and try to reduce them (by similarity transformations) to a form that allows the eigenvalues – the roots of the characteristic equation – to be read off relatively easily.
					
3. Systems of linear algebraic equations: given a nonsingular square matrix A 2 Rnn, and a vector b 2 Rn, the problem now discussed is solving the system
					
Ax D b: (1.57)
					
Here the data are the elements of A and b, and the result the vector x. The map in question is thus Rn2Cn ! Rn. To simplify matters, let us assume that A is a fixed matrix not subject to change, and only the vector b is undergoing perturbations. Wethenhaveamapf W Rn !Rn givenby
					
x D f .b/ WD A1b:
				
			
		
		
			
				
					
22
				
				
					
1 Machine Arithmetic and Related Matters It is in fact a linear map. Therefore, @f =@b D A1, and we get, using (1.35),
					
.cond f /.b/ D kbk kA1k ; (1.58) kA1bk
					
where we may take any vector norm in Rn and associated matrix norm (cf. (1.30)). We can write (1.58) alternatively in the form
					
.cond f /.b/ D kAxk kA1k .where Ax D b/; kxk
					
and since there is a one-to-one correspondence between x and b, we find for the worst condition number
					
max .cond f /.b/ D max kAxk kA1k D kAk  kA1k ; b2Rn x2Rn kxk
					
b¤0 x¤0
					
by definition of the norm of A. The number on the far right no longer depends on the particular system (i.e., on b) and is called the condition number of the matrix A. We denote it by
					
cond A WD kAk  kA1k : (1.59)
					
It should be clearly understood, though, that it measures the condition of a linear system with coefficient matrix A, and not the condition of other quantities that may depend on A, such as eigenvalues.
					
Although we have considered only perturbations in the right-hand vector b, it turns out that the condition number in (1.59) is also relevant when perturbations in the matrix A are allowed, provided they are sufficiently small (so small, for example, that kAk  kA1k < 1).
					
We illustrate (1.59) by several examples. (a) Hilbert2 matrix:
				
			
			 			 			 			 			
				
					
2David Hilbert (1862–1943) was the most prominent member of the Go ̈ttingen school of mathe- matics. Hilbert’s fundamental contributions to almost all parts of mathematics – algebra, number theory, geometry, integral equations, calculus of variations, and foundations – and in particular the 23 now famous problems he proposed in 1900 at the International Congress of Mathematicians in Paris gave a new impetus, and new directions, to 20th-century mathematics. Hilbert is also known for his work in mathematical physics, where among other things he formulated a variationl principle for Einstein’s equations in the theory of relativity.
				
			
		
		
			
				
					
1.3
				
				
					
The Condition of a Problem
				
				
					
23
				
			
			
				
					
23 61117
				
			
			
				
					
6 2 n7 61 1 1 7
				
			
			 			
				
					
62 3 nC17 nn
 HnD6 72R : (1.60)
				
			
			
				
					
67 67
				
			
			
				
					
6    7 67 45
				
			
			
				
					
111
 n nC1 2n1
					
This is clearly a symmetric matrix, and it is also positive definite. Some numerical values for the condition number of Hn, computed with the Euclidean norm,3 are shown in Table 1.1. Their rapid growth is devastating.
					
Table 1.1 The condition of Hilbert matrices
					
n cond2Hn 10 1:60 1013 20 2:45 1028 40 7:65 1058
					
A system of order n D 10, for example, cannot be solved with any reliability in single precision on a 14-decimal computer. Double precision will be “exhausted” by the time we reach nD 20. The Hilbert matrix thus is a prototype of an ill-conditioned matrix. From a result of G. Szego ̋ it can be seen that
					
p 4nC4 2C1
					
cond2Hn 215=4p n as n!1: (b) Vandermonde4 matrices: these are matrices of the form
					
3We have cond H D .H / .H 1/, where .A/ denotes the largest eigenvalue of 2 n max n max n max
					
the (symmetric, positive definite) matrix A. The eigenvalues of H and H 1 are easily computed nn
					
by the Matlab routine eig, provided that the inverse of H n is computed directly from well-known formulae (not by inversion); see MA 9.
					
4Alexandre The ́ophile Vandermonde (1735–1796), a musician by training, but through acquain- tance with Fontaine turned mathematician (temporarily), and even elected to the French Academy of Sciences, produced a total of four mathematical papers within 3 years (1770–1772). Though written by a novice to mathematics, they are not without interest. The first, e.g., made notable contributions to the then emerging theory of equations. By virtue of his fourth paper, he is regarded as the founder of the theory of determinants. What today is referred to as “Vandermonde determinant,” however, does not appear anywhere in his writings. As a member of the Academy, he sat in a committee (together with Lagrange, among others) that was to define the unit of length – the meter. Later in his life, he became an ardent supporter of the French revolution.
				
			
			 			 			 			 			 			 			 		
		
			
				
					
24
				
				
					
1 Machine Arithmetic and Related Matters
				
			
			
				
					
23
				
			
			
				
					
111 67
				
			
			
				
					
6 t1 t2 tn 7
				
			
			
				
					
6 7nn VnD6 72R ;
				
				
					
(1.61)
				
			
			
				
					
6 7 45
				
			
			
				
					
tn1 tn1 tn1 12n
				
			
			
				
					
where t1, t2; : : : ; tn are parameters, here assumed real. The condition number of these matrices, in the 1-norm, has been studied at length. Here are some sample results: if the parameters are equally spaced in [–1,1], that is,
				
			
			 			
				
					
then
				
				
					
t D12.1/; D1;2;:::;n; n1
					
cond V 1e =4en.4C12 ln2/; n!1: 1n
				
			
			
				
					
Numerical values are shown in Table 1.2. They are not growing quite as fast as those for the Hilbert matrix, but still exponentially fast. Worse than exponential growth is observed if one takes harmonic numbers as parameters,
				
			
			 			 			 			
				
					
1.4
				
				
					
Fortunately, there are not many matrices occurring naturally in applications that are that ill-conditioned, but moderately to severely ill-conditioned matrices are no rarity in real-life applications.
					
The Condition of an Algorithm
				
			
			
				
					
Then indeed
				
				
					
Table 1.2 The condition of Vandermonde matrices
					
n cond1 V n 10 1:36 104 20 1:05 109 40 6:93 1018 80 3:15 1038
					
tD1; D1;2;:::;n: cond1V n > nnC1:
				
			
			
				
					
We again assume that we are dealing with a problem f given by
 f W Rm ! Rn; y D f .x/: (1.62)
				
			
		
		
			
				
					
1.4 The Condition of an Algorithm 25
				
			
			
				
					
Along with the problem f , we are also given an algorithm A that “solves” the problem. That is, given a machine vector x 2 Rm.t;s/, the algorithm A produces a vector yA (in machine arithmetic) that is supposed to approximate y D f .x/. Thus, we have another map fA describing how the problem f is solved by the algorithm A,
					
fA W Rm.t; s/ ! Rn.t; s/; yA D fA.x/: (1.63) In order to be able to analyze fA in these general terms, we must make a basic
				
			
			
				
					
assumption, namely, that
					
for every x 2 Rm.t; s/; there holds
					
fA.x/Df.xA/ forsome xA 2Rm:
				
				
					
(1.64)
				
			
			
				
					
That is, the computed solution corresponding to some input x is the exact solution for some different input xA (not necessarily a machine vector and not necessarily uniquely determined) that we hope is close to x. The closer we can find an xA to x, the more confidence we should place in the algorithm A. We therefore define the condition of A in terms of the xA closest to x (if there is more than one), by comparing its relative error with the machine precision eps:
					
.cond A/.x/ D inf kxA xk =eps: (1.65) xA kxk
					
Here the infimum is over all xA satisfying yA D f .xA/. In practice, one can take any such xA and then obtain an upper bound for the condition number:
					
.cond A/.x/ kxA xk =eps: (1.66) kxk
					
The vector norm in (1.65), respectively, (1.66), can be chosen as seems convenient. Here are some very elementary examples.
					
1. Suppose a library routine for the logarithm function y D ln x, for any positive machine number x, produces a yA satisfying yA D Œln x.1 C "/, j"j  5 eps. What can we say about the condition of the underlying algorithm A? We clearly have
				
			
			 			 			
				
					
Consequently,
				
				
					
yA D ln xA; where xA D x1C" .uniquely/: ˇˇ
					
ˇx1C" xˇ ˇ ˇ
				
			
			
				
					
ˇxA xˇ
				
			
			
				
					
ˇ ˇDˇ ˇDjx" 1jDˇe"lnx 1ˇj"lnxj5jlnxjeps; ˇˇ
				
			
			 			 			
				
					
xx
				
			
		
		
			
				
					
26 1 Machine Arithmetic and Related Matters
				
			
			
				
					
and, therefore, .condA/.x/ 5jlnxj. The algorithm A is well conditioned, except in the immediate right-hand vicinity of x D 0 and for x very large. (In the latter case, however, x is likely to overflow before A becomes seriously ill- conditioned.)
					
2. Consider the problem
					
fW Rn!R; yDx1x2xn: We solve the problem by the obvious algorithm
					
p1 Dx1;
 A W pk D fl.xkpk1/; k D 2;3;:::;n;
					
yA D pn:
					
Note that x1 is machine representable, since for the algorithm A we assume x 2 Rn.t;s/.
					
Now using the basic law of machine arithmetic (cf. (1.15)), we get p1 D x1;
					
pk D xkpk1.1 C "k/; k D 2;3;:::;n; j"kj  eps;
					
from which
					
pn Dx1x2xn.1C"2/.1C"3/.1C"n/: Therefore, we can take for example (there is no uniqueness),
					
xA DŒx1;x2.1C"2/;:::;xn.1C"n/T: This gives, using the 1-norm,
					
kxA xk1 D kŒ0;x2"2;:::;xn"nTk1 kxk1eps D 1; kxk1eps kxk1eps kxk1eps
					
and so, by (1.66), .cond A/.x/ 1 for any x 2 Rn.t; s/. Our algorithm, to nobody’s surprise, is perfectly well conditioned.
				
			
			 			 			 		
		
			
				
					
1.5 Computer Solution of a Problem; Overall Error 27
				
			
			
				
					
1.5 Computer Solution of a Problem; Overall Error
					
The problem to be solved is again
 f W Rm ! Rn; y D f .x/: (1.67)
					
This is the mathematical (idealized) problem, where the data are exact real numbers, and the solution is the mathematically exact solution.
					
When solving such a problem on a computer, in floating-point arithmetic with precision eps, and using some algorithm A, one first of all rounds the data, and then applies to these rounded data not f , but fA:
				
			
			
				
					
x D rounded data; y DfA.x/:
				
				
					
kx xk D "; kxk
				
				
					
(1.68)
				
			
			 			
				
					
A
				
			
			
				
					
Here " represents the rounding error in the data. (The error " could also be due to sources other than rounding, e.g., measurement.) The total error that we wish to
				
			
			
				
					
estimate is then
				
			
			
				
					
ky yk A
					
kyk
					
optimally, we have
 f A . x / D f . x A / ; A D . c o n d A / . x / e p s :
				
			
			
				
					
: (1.69) By the basic assumption (1.64) made on the algorithm A, and choosing xA
				
			
			 			
				
					
kx xk kx k
				
				
					
( 1 . 7 0 )
				
			
			 			
				
					
Let y D f .x/. Then, using the triangle inequality, we have
					
ky yk ky yk ky yk ky yk ky yk AACAC;
				
			
			 			 			 			 			 			
				
					
kyk kyk kyk kyk kyk
 where we have used the (harmless) approximation ky k  ky k. By virtue of (1.70),
				
			
			
				
					
we now have for the first term on the right,
					
kyk kf .x/k .condf/.x/ A
				
			
			
				
					
ky yk kfA.x/ f .x/k kf .x/ f .x/k ADDA
				
			
			 			 			 			
				
					
kx xk kx k
				
			
			
				
					
kf .x/k
				
			
			 			
				
					
D .cond f /.x/ .cond A/.x/ eps:
				
			
		
		
			
				
					
28 1 Machine Arithmetic and Related Matters For the second term we have
					
ky yk D kf .x/ f .x/k .cond f /.x/ kx xk D .cond f /.x/ ": kyk kf .x/k kxk
					
Assuming finally that .cond f /.x/ .cond f /.x/, we get
					
ky yk
 A .cond f /.x/f" C .cond A/.x/ epsg: (1.71)
					
kyk
					
This shows how the data error and machine precision contribute toward the total error: both are amplified by the condition of the problem, but the latter is further amplified by the condition of the algorithm.
					
1.6 Notes to Chapter 1
					
In addition to rounding errors in the data and those committed during the execution of arithmetic operations, there may be other sources of errors not considered in this introductory chapter. One such source of error, which is not entirely dismissible, is a faulty design of the computer chip that executes arithmetic operations. This was brought home in an incident several years ago, when it was discovered (by Thomas Nicely in the course of number-theoretic computations involving reciprocals of twin primes) that the Pentium floating-point divide chip manufactured by Intel can produce erroneous results for certain (extremely rare) bit patterns in the divisor. The incident – rightly so – has stirred up considerable concern and prompted not only remedial actions but also careful analysis of the phenomenon; some relevant articles are those by Coe et al. [1995] and Edelman [1997].
					
Neither should the occurrence of overflow and proper handling thereof be taken lightly, especially not in real-time applications. Again, a case in point is the failure of the French rocket Ariane 5, which on June 4, 1996, less than a minute into its flight, self-destructed. The failure was eventually traced to an overflow in a floating-point to integer conversion and lack of protection against this occurrence in the rocket’s on-board software (cf. Anonymous [1996]).
					
Many of the topics covered in this chapter, but also the effect of finite precision computation on convergence and stability of mathematical processes, and issues of error analyses are dealt with in Chaitin-Chatelin and Fraysse ́ [1996].
					
Section 1.1.1. The abstract notion of the real number system is discussed in most texts on real analysis, for example, Hewitt and Stromberg [1975, Chap. 1, Sect. 1.5] or Rudin [1976, Chap. 1]. The development of the concept of real (and complex) numbers has had a long and lively history, extending from pre-Hellenic times to the recent past. Many of the leading thinkers over time contributed to this development. A reader interested in a detailed historical account (and who knows German) is referred to the monograph by Gericke [1970].
				
			
			 			 			 			 		
		
			
				
					
1.6 Notes to Chapter 1 29
				
			
			
				
					
Section1.1.2.1. The notion of the floating-point number system and associated arithmetic, including interval arithmetic, can also be phrased in abstract algebraic terms; see, for example, Kulisch and Miranker [1981]. For a comprehensive treat- ment of computer arithmetic, including questions of validation, see Kulisch [2008]. A more elementary, but detailed, discussion of floating-point numbers and arith- metic is given in Sterbenz [1974]. There the reader will learn, for example, that computing the average of two floating-point numbers, or solving a quadratic equation, can be fairly intricate tasks if they are to be made foolproof. The quadratic equation problem is also considered at some length in Young and Gregory [1988,Sect.3.4], where further references are given to earlier work of W. Kahan and G. E. Forsythe.
					
The basic standard for binary floating-point arithmetic, used on all contemporary computers, is the ANSI/IEEE Standard 754 established in IEEE [1985]. It provides for t D 23 bits in the mantissa and s D 7 bits in the exponent, in single- precision arithmetic, and has t D 52, s D 11 in double precision. There is also an “extended precision” for which t D 63, s D 14, allowing for a number range of approx. 104964 to 10C4964. A good source for IEEE floating-point arithmetic is Overton [2001].
					
Section1.1.2.3. Rationalarithmeticisavailableinallmajorsymboliccomputation packages such as Mathematica and Macsyma.
					
Interval arithmetic has evolved to become an important tool in computations that strive at obtaining guaranteed and sharp inclusion regions for the results of mathe- matical problems. Basic texts on (real) interval analysis are Moore [1966], [1979], Alefeld and Herzberger [1983], and Moore et al. [2009], whereas complex interval arithmetic is treated in Petkovic ́ and Petkovic ́ [1998]. For the newly evolving field of validated numerics we refer to Tucker [2011]. Specific applications such as computing inclusions of the range of functions, of global extrema of functions of one and several variables, and of solutions to systems of linear and nonlinear equations are studied, respectively, in Ratschek and Rokne [1984], [1988], Hansen and Walster [2004], and Neumaier [1990]. Other applications, e.g., to parameter estimation, robust control, and robotics can be found in Jaulin et al. [2001]. Concrete algorithms and codes (in Pascal and CCC) for “verified computing” are contained in Hammer et al. [1993], [1995]. Interval arithmetic has been most widely used in processes involving finite-dimensional spaces; for applications to infinite- dimensional problems, notably differential equations, see, however, Eijgenraam [1981] and Kaucher and Miranker [1984]. For a recent expository account, see also Rump [2010].
					
Section1.2. Forfloating-pointarithmetic,seethehandbookbyMulleretal.[2010]. The fact that thoughtless use of mathematical formulae and numerical methods, or inherent sensitivities in a problem, can lead to disastrous results has been known since the early days of computers; see, for example, the old but still relevant
				
			
		
		
			
				
					
30 1 Machine Arithmetic and Related Matters
				
			
			
				
					
papers by Stegun and Abramowitz [1956] and Forsythe [1970]. Nearby singularities can also cause the accuracy to deteriorate unless corrective measures are taken; Forsythe [1958] has an interesting discussion of this.
					
Section1.2.1. For the implications of rounding in the problem of apportion- ment, mentioned in footnote 1, a good reference is Garfunkel and Steen, eds. [1988, Chap. 12, pp.230–249].
					
Section1.3.1. Anearlybutbasicreferenceforideasofconditioninganderroranal- ysis in algebraic processes is Wilkinson [1994]. An impressive continuation of this work, containing copious references to the literature, is Higham [2002]. It analyzes the behavior in floating-point arithmetic of virtually all the algebraic processes in current use. Problems of conditioning specifically involving polynomials are discussed in Gautschi [1984]. The condition of general (differentiable) maps has been studied as early as 1966 in Rice [1966].
					
Section1.3.2. 1. For a treatment of stability aspects of more general difference equations, and systems thereof, including nonlinear ones, the reader is referred to the monograph by Wimp [1984]. This also contains many applications to special functions. Other relevant texts are Lakshmikantham and Trigiante [2002] and Elaydi [2005].
					
    2. 							
The condition of algebraic equations, although considered already in 1963 by Wilkinson, has been further analyzed by Gautschi [1973]. The circumstances that led to Wilkinson’s example (1.56), which he himself describes as “the most traumatic experience in [his] career as a numerical analyst,” are related in the essay Wilkinson [1984,Sect.2]. This reference also deals with errors committed in the evaluation and deflation of polynomials. For the latter, also see Cohen [1994]. The asymptotic estimates for the best- and worst-conditioned roots in Wilkinson’s example are from Gautschi [1973]. For the computation of eigenvalues of matrices, the classic treatment is Wilkinson [1988]; more recent accounts are Parlett [1998] for symmetric matrices and Golub and Van Loan [1996, Chap. 7–9] for general matrices.
 						
    3. 							
A more complete analysis of the condition of linear systems that also allows for perturbations of the matrix can be found, for example, in the very readable books by Forsythe and Moler [1967, Chap. 8] and Stewart [1973, Chap. 4, Sect. 3]. The asymptotic result of Szego ̋ cited in connection with the Euclidean condition number of the Hilbert matrix is taken from Szego ̋ [1936]. For the explicit inverse of the Hilbert matrix, referred to in footnote 3, see Todd [1954]. The condition of Vandermonde and Vandermonde-like matrices has been studied in a series of papers by the author; for a summary, see Gautschi [1990], and Gautschi [2011b] for optimally scaled and optimally conditioned Vandermonde and Vandermonde- like matrices.
 						
					
Sections1.4and1.5. Thetreatmentoftheconditionofalgorithmsandoftheoverall error in computer solutions of problems, as given in these sections, seems to be more or less original. Similar ideas, however, can be found in the book by Dahlquist and Bjo ̈ rck [2008, Sect. 2.4].
				
			
		
		
			
				
					
Exercises 31
				
			
			
				
					
Exercises and Machine Assignments to Chapter 1 Exercises
					
    1. 							
Represent all elements of RC.3; 2/ D fx 2 R.3; 2/ W x > 0; x normalizedg as dots on the real axis. For clarity, draw two axes, one from 0 to 8, the other from 0 t o 12 .
 						
    2. 							
(a) Whatisthedistanced.x/ofapositivenormalizedfloating-pointnumber x 2 R.t; s/ to its next larger floating-point number:
 							
d.x/D min.yx/‹ y2R.t;s/
 y>x
 							
(b) Determinetherelativedistancer.x/Dd.x/=x,withxasin(a),andgive upper and lower bounds for it.
 						
    3. 							
Theidentityfl.1Cx/D1,x0,istrueforxD0andforxsufficientlysmall. What is the largest machine number x for which the identity still holds?
 						
    4. 							
Consider a miniature binary computer whose floating-point words consist of four binary digits for the mantissa and three binary digits for the exponent (plus sign bits). Let
 							
x D .0:1011/2 20; y D .0:1100/2 20:
 							
Mark in the following table whether the machine operation indicated (with the result z assumed normalized) is exact, rounded (i.e., subject to a nonzero rounding error), overflows, or underflows.
 						
				
			
			
				
					
Operation
					
z D fl.x y/
 z D fl..y x/10/ z D fl.x C y/
 z D fl.y C .x=4// z D fl.x C .y=4//
				
				
					
Exact Rounded Overflow Underflow
				
			
			
				
					
5. The Matlab “machine precision” eps is twice the unit roundoff (2 2t , t D 53; cf. Sect. 1.1.3). It can be computed by the following Matlab program (attributed to CLEVE MOLER):
				
			
		
		
			
				
					
32
				
				
					
1 Machine Arithmetic and Related Matters
				
			
			
				
					
6. 7.
				
				
					
%EI_5 Matlab machine precision %
 a=4/3;
 b=a-1;
					
               c=b+b+b;
                eps0=abs(c-1)

					
Run the program and prove its validity.
 Prove(1.12).
 A set S of real numbers is said to possess a metric if there is defined a distance function d.x; y/ for any two elements x; y 2 S that has the following properties:
					
(i) d.x; y/ 0 and d.x; y/ D 0 if and only if x D y (positive definiteness); (ii) d.x;y/Dd.y;x/(symmetry);
					
(iii) d.x;y/d.x;z/Cd.z;y/(triangleinequality).
 Discuss which of the following error measures is, or is not, a distance function
				
			
			
				
					
on what set S of real numbers:
 (a) absolute error: ae.x; y/ D jx yj;
				
			
			
				
					
ˇˇ (b) relative error: re.x; y/ D ˇ xy ˇ;
				
			
			 			
				
					
x
 (c) relative precision (F.W.J. Olver, 1978): rp.x; y/ D j ln jxj  ln jyj j.
				
			
			
				
					
If y D x.1 C "/, show that rp.x; y/ D O."/ as " ! 0.
 8. Assume that x1, x2 are approximations to x1, x2 with relative errors E1 and
					
E2, respectively, and that jEi j  E, i D 1; 2. Assume further that x1 ¤ x2.
					
    • 							
(a)  How small must E (in dependence of x1 and x2) be to ensure t h a t x 1 ¤ x 2 ?
 						
    • 							
(b)  Taking 1 to approximate 1 , obtain a bound on the relative error x1 x2 x1x2
 							
committed, assuming (1) exact arithmetic; (2) machine arithmetic with machine precision eps. (In both cases, neglect higher-order terms in E1, E2, eps.)
 						
					
9. Considerthequadraticequationx2CpxCqD0withrootsx1,x2.Asseenin the second Example of Sect. 1.2.2, the absolutely larger root must be computed first, whereupon the other can be accurately obtained from x1x2 D q. Suppose one incorporates this idea in a program such as
					
                 x1=abs(p/2)+sqrt(p*p/4-q);
                  if p>0, x1=-x1; end
                  x2=q/x1;

					
Find two serious flaws with this program as a “general-purpose quadratic equation solver.” Take into consideration that the program will be executed in floating-point machine arithmetic. Be specific and support your arguments by examples, if necessary.
				
			
			 			 		
		
			
				
					
Exercises 33
				
			
			
				
					
10. Suppose,forjxjsmall,onehasanaccuratevalueofyDex1(obtained,e.g.,
					
by Taylor expansion). Use this value to compute accurately sinh x D 12 .ex
					
ex / for small jxj. p
					
11.Letf.x/D 1Cx21.
					
    • 							
(a)  Explainthedifficultyofcomputingf.x/forasmallvalueofjxjandshow how it can be circumvented.
 						
    • 							
(b)  Compute.condf/.x/anddiscusstheconditioningoff.x/forsmalljxj.
 						
    • 							
(c)  Howcantheanswersto(a)and(b)bereconciled?
 						
					
12. Thenthpowerofsomepositive(machine)numberxcanbecomputed (i) eitherbyrepeatedmultiplicationbyx,or
					
(ii) asxn Denlnx.
					
In each case, derive bounds for the relative error due to machine arithmetic, neglecting higher powers of the machine precision against the first power. (Assume that exponentiation and taking logarithms both involve a relative error " with j"j  eps.) Based on these bounds, state a criterion (involving x and n) for (i) to be more accurate than (ii).
					
13. Letf.x/D.1cosx/=x,x¤0.
					
    • 							
(a)  Show that direct evaluation of f is inaccurate if jxj is small; assume fl.f .x// D fl..1 fl.cos x//=x/, where fl.cos x/ D .1 C "c / cos x, and estimate the relative error "f of fl.f .x// as x ! 0.
 						
    • 							
(b)  A mathematically equivalent form of f is f .x/ D sin2 x=.x.1 C cos x//. Carry out a similar analysis as in (a), based on fl.f.x// D fl.Œfl.sinx/2= fl.x.1 C fl.cosx////, assuming fl.cosx/ D .1 C "c/cosx, fl.sinx/ D .1 C "s / sin x and retaining only first-order terms in "s and "c . Discuss the result.
 						
    • 							
(c)  Determine the condition of f.x/. Indicate for what values of x (if any) f .x/ is ill-conditioned. (jxj is no longer small, necessarily.)
 						
				
			
			 			
				
					
p 1=2 1=2
 14. IfzDxCiy,then zD rCx Ci rx ,wherer D .x2 Cy2/1=2.
				
			
			 			 			
				
					
p 2 2 1=2
 Alternatively, z D u C iv, u D rCx , v D y=2u. Discuss the
				
			
			 			
				
					
2
					
computational merits of these two (mathematically equivalent) expressions. Illustrate with z D 4:5 C 0:025i, using eight significant decimal places. fHint: you may assume x > 0 without restriction of generality. Why?g
					
15. Considerthenumericalevaluationof
				
			
			
				
					
X1 1
					
1 C n4 .t n/2 .t n 1/2 ;
					
say, for t D 20, and 7-digit accuracy. Discuss the danger involved.
 16. Let XC be the largest positive machine representable number, and X the absolute value of the smallest negative one (so that X x XC for any machine number x). Determine, approximately, all intervals on R on which the
					
tangent function overflows.
				
			
			
				
					
f .t / D
				
			
			 			
				
					
nD0
				
			
		
		
			
				
					
34 1 Machine Arithmetic and Related Matters
				
			
			
				
					
17. (a)
					
(b) (c)
				
				
					
Use Matlab to determine the first value of the integer n for which nŠ overflows. fHint: use Stirling’s formula for nŠ.g
 Do the same as (a), but for xn, x D 10;20;:::;100.
 Discuss how xnex=nŠ can be computed for large x and n without unnecessarily incurring overflow. fHint: use logarithms and an asymptotic formula for ln nŠ.g
				
			
			
				
					
    18. 							
Consider a decimal computer with three (decimal) digits in the floating-point mantissa.
 							
(a) Estimatetherelativeerrorcommittedinsymmetricrounding.
 (b) Let x1 D 0:982, x2 D 0:984 be two machine numbers. Calculate in machine arithmetic the mean m D 12.x1 C x2/. Is the computed number
 							
between x1 and x2?
 (c) Derive sufficient conditions for x1 < fl.m/ < x2 to hold, where x1, x2 are
 							
two machine numbers with 0 < x1 < x2.
 						
    19. 							
For this problem, assume a binary computer with 12 bits in the floating-point
 							
mantissa.
 							
        ◦ 									
(a)  Whatisthemachineprecisioneps?
 								
        ◦ 									
(b)  Let x D 6=7 and x be the correctly rounded machine approximation to x
 									
(symmetric rounding). Exhibit x and x as binary numbers.
 								
        ◦ 									
(c)  Determine (exactly) the relative error " of x as an approximation to x, and
 									
calculate the ratio j"j=eps.
 								
    20. 						
    21. 							
Thedistributivelawofalgebrastatesthat
 							
.a C b/c D ac C bc:
 							
Discuss to what extent this is violated in machine arithmetic. Assume a computer with machine precision eps and assume that a, b, c are machine- representable numbers.
 							
        ◦ 									
(a)  Let y1 be the floating-point number obtained by evaluating .a C b/c (as written) in floating-point arithmetic, and let y1 D .aCb/c.1Ce1/. Estimate je1j in terms of eps (neglecting second-order terms in eps).
 								
        ◦ 									
(b)  Let y2 be the floating-point number obtained by evaluating ac C bc (as written) in floating-point arithmetic, and let y2 D .aCb/c.1Ce2/. Estimate je2j (neglecting second-order terms in eps) in terms of eps (and a, b, and c).
 								
        ◦ 									
(c)  Identify conditions (if any) under which one of the two yi is significantly less accurate than the other.
 								
    22. 						
					
21. Letx1,x2;:::;xn,n>1,bemachinenumbers.Theirproductcanbecomputed by the algorithm
					
p1 D x1;
 pk D fl.xkpk1/; k D 2;3;:::;n:
				
			
		
		
			
				
					
Exercises 35
				
			
			
				
					
(a) Find an upper bound for the relative error .pn x1 x2   xn /= .x1 x2   xn / in terms of the machine precision eps and n.
				
			
			
				
					
(b)
				
				
					
Foranyintegerr 1nottoolargesoastosatisfyreps< 1 ,showthat 10
					
.1Ceps/r 1<1:06reps:
 Hence, for n not too large, simplify the answer given in (a). fHint: use the
				
			
			
				
					
binomial theorem.g
					
    22. 							
Analyze the error propagation in exponentiation, x ̨ .x > 0/:
 							
(a) assumingxexactand ̨subjecttoasmallrelativeerror" ̨; (b) assuming ̨exactandxsubjecttoasmallrelativeerror"x.
 							
Discuss the possibility of any serious loss of accuracy.
 						
    23. 							
Indicatehowyouwouldaccuratelycompute
 						
				
			
			
				
					
24. (a)
				
				
					
.xCy/1=4y1=4; x>0; y>0:
					
LetaD0:23371258104,bD0:33678429102,cD0:33677811 102. Assuming an 8-decimal-digit computer, determine the sum s D a C bCc either as (1) fl.s/ D fl.fl.aCb/Cc/ or as (2) fl.s/ D fl.aCfl.bCc/). Explain the discrepancy between the two answers.
				
			
			
				
					
(b) For arbitrary machine numbers a, b, c on a computer with machine precision eps, find a criterion on a, b, c for the result of (2) in (a) to be more accurate than the result of (1). fHint: compare bounds on the relative errors,neglectinghigher-ordertermsinepsandassumingaCbCc ¤ 0; see also MA 7.g
					
    25. 							
Write the expression a2 2ab cos C b2 (a > 0; b > 0) as the sum of two positive terms to avoid cancellation errors. Illustrate the advantage gained in the case a D 16:5, b D 15:7, D 5ı, using 3-decimal-digit arithmetic. Is the method foolproof?
 						
    26. 							
Determinetheconditionnumberforthefollowingfunctions:
 							
(a) f.x/Dlnx; x>0;
 							
(b)f.x/Dcosx; jxj<12 ;
 							
(c) f.x/ D sin1 x; jxj < 1;
 							
(d) f.x/Dsin1 p x . 1Cx2
 							
Indicate the possibility of ill-conditioning.
 						
    27. 							
Compute the condition number of the following functions, and discuss any
 							
possible ill-conditioning:
 (a) f.x/ D x1=np.x > 0; n > 0 an integer);
 							
(b)f.x/Dx x21 .x>1/; q
 							
(c)f.x1;x2/D x12Cx2; (d) f.x1;x2/Dx1Cx2.
 						
				
			
			 			 			 			 		
		
			
				
					
36 1 Machine Arithmetic and Related Matters
				
			
			
				
					
Considerthecompositefunctionh.t/Dg.f.t//.Expresstheconditionof h in terms of the condition of g and f . Be careful to state at which points the various condition numbers are to be evaluated.
 Illustrate (a) with h.t/ D 1Csin t ; t D 1 .
					
about .cond f =g/.x/?
 30.Letf WR2 !RbegivenbyyDx1Cx2.Define(condf)(x)=
					
(cond11f )(x)+ (cond12f )(x), where x D Œx1; x2T (cf. (1.27)).
					
    • 							
(a)  Derive a formula for .x1; x2/ D .cond f /.x/.
 						
    • 							
(b)  Show that .x1;x2/ as a function of x1;x2 is symmetric with respect to
 							
both bisectors b1 and b2 (see figure).
 x
 							
2
 						
				
			
			
				
					
28. (a) (b)
				
			
			 			
				
					
1sin t 4
 29. Show that .cond f g/.x/ .cond f /.x/ C .cond g/.x/. What can be said
				
			
			
				
					
33.LettheL1normofavectoryDŒybedefinedbykyk1 D matrix A 2 Rnm, show that
				
				
					
P
					
P
				
			
			
				
					
kAk1 WD max x2Rm x¤0
				
				
					
kxk1
				
				
					
1 D max
				
				
					
jaj;
				
			
			
				
					
kAxk X
				
			
			
				
					
b
					
1
					
x
					
1
					
b
					
2
				
			
			 			
				
					
(c) Determine the lines in R2 on which .x1;x2/ D c, c 1 a constant. (Simplify the analysis by using symmetry; cf. part (b).)
					
31. Let k  k be a vector norm in Rn and denote by the same symbol the associated matrix norm. Show for arbitrary matrices A, B 2 Rnn that
					
(a) kABkkAkkBk;
 (b) cond.AB/condAcondB.
					
P
					
32. Prove (1.32). fHint: let m1 D max jaj. Show that kAk1 m1 as well as kAk1 m1, the latter by taking a special vector x in (1.30).g
				
			
			
				
					
jyj.Fora
				
			
			 			
				
					
that is, kAk1 is the “maximum column sum.” fHint: let m1 D max
 Show that kAk1 m1 as well as kAk1 m1, the latter by taking for x in (1.30) an appropriate coordinate vector.g
					
34. Let a, q be linearly independent vectors in Rn of (Euclidean) length 1. Define b. / 2 Rn as follows:
					
b./Daq; 2R:
				
			
			
				
					
				
			
			
				
					
jaj.
				
			
		
		
			
				
					
Exercises 37 Compute the condition number of the angle ̨. / between b. / and q at the
					
value D 0 D qTa. (Then b. 0/ ? q; see figure.) Discuss the answer. b(ρ )
					
q
				
			
			
				
					
ndn ex (a) Show that ffng satisfies the recursion
				
				
					
; nD0;1;2;::: :
				
			
			
				
					
0a
				
			
			 			
				
					
35. The area of a triangle ABC is given by D 12 ab sin (see figure). Discuss the numerical condition of .
				
			
			 			
				
					
36. Define, for x ¤ 0,
 fn Dfn.x/D.1/ dxn x
				
			
			
				
					
				
			
			
				
					
γ
				
			
			 			 			
				
					
ex ykD xyk1 C x ; kD1;2;3;:::I y0D x :
					
fHint: differentiate k times the identity ex D x .ex =x/.g
					
    • 							
(b)  Why do you expect the recursion in (a), without doing any analysis, to be
 							
numerically stable if x > 0 ? How about x < 0 ?
 						
    • 							
(c)  Support and discuss your answer to (b) by considering yn as a function of
 							
y0 (which for y0 D f0.x/ yields fn D fn.x/) and by showing that the condition number of this function at f0 is
 							
.condyn/.f0/ D 1 ; jen.x/j
 							
where en.x/ D 1 C x C x2=2Š C    C xn=nŠ is the nth partial sum of the exponential series. fHint: use Leibniz’s formula to evaluate fn.x/.g
 						
					
37. Considerthealgebraicequation
					
xn Cax1D0; a>0; n2:
				
			
			
				
					
k ex
				
			
			 			 			 		
		
			
				
					
38 1 Machine Arithmetic and Related Matters
				
			
			
				
					
(a) Showthattheequationhasexactlyonepositiveroot.a/. (b) Obtainaformulafor(cond)(a).
 (c) Obtain(good)upperandlowerboundsfor(cond)(a).
					
38. Considerthealgebraicequation
					
xn Cxn1 aD0; a>0; n2: (a) Showthatthereisexactlyonepositiveroot.a/.
					
(b) Showthat.a/iswellconditionedasafunctionofa.Indeed,prove .cond/.a/< 1 :
				
			
			 			
				
					
39. ConsiderLambert’sequation for real values of x and a.
				
				
					
n1 xex D a
				
			
			
				
					
    • 							
(a)  Showgraphicallythattheequationhasexactlyoneroot.a/0ifa0, exactly two roots 2.a/ < 1.a/ < 0 if 1=e < a < 0, a double root 1 if a D 1=e, and no root if a < 1=e.
 						
    • 							
(b)  Discuss the condition of .a/, 1.a/, 2.a/ as a varies in the respective intervals.
 						
					
    40. 							
Given the natural number n, let D .a/ be the unique positive root of the equation xn D aex .a > 0/. Determine the condition of as a function of a; simplify the answer as much as possible. In particular, show that (cond /.a/ < 1=n.
 						
    41. 							
Let f .x1 ; x2 / D x1 C x2 and consider the algorithm A given as follows: fAWR2.t;s/!R.t;s/ yADfl.x1Cx2/:
 							
Estimate .x1; x2/ D .cond A/.x/, using any of the norms q
 						
				
			
			 			
				
					
kxk1 D jx1j C jx2j; kxk2 D
 Discuss the answer in the light of the conditioning of f .
				
			
			
				
					
x12 C x2; kxk1 D max .jx1j; jx2j/: p
				
			
			 			
				
					
42. Thisproblemdealswiththefunctionf.x/D 1x1,1<x<1.
					
    • 							
(a)  Computetheconditionnumber.condf/.x/.
 						
    • 							
(b)  Let A be the algorithm that evaluates f .x/ in floating-point arithmetic on
 							
a computer with machine precision eps, given an (error-free) floating-point number x. Let "1, "2, "3 be the relative errors due, respectively, to the subtraction in 1x, to taking the square root, and to the final subtraction of 1. Assume j"ij  eps (i D 1;2;3). Letting fA.x/ be the value of f.x/ so computed,writefA.x/Df.xA/andxA Dx.1C"A/.Express"A interms
 						
				
			
		
		
			
				
					
Machine Assignments 39
				
			
			
				
					
of x, "1, "2, "3 (neglecting terms of higher order in the "i ). Then determine an upper bound for j"Aj in terms of x and eps and finally an estimate of .cond A/.x/.
					
(c) Sketch a graph of .cond f /.x/ (found in (a)) and a graph of the estimate of .cond A/.x/ (found in (b)) as functions of x on .1; 1/. Discuss your results.
					
43. Consider the function f.x/ D 1 ex on the interval 0 x 1.
				
			
			
				
					
Showthat(condf).x/1on[0,1].
 Let A be the algorithm that evaluates f.x/ for the machine number x in floating-point arithmetic (with machine precision eps). Assume that the ex- ponential routine returns a correctly rounded answer. Estimate .cond A/.x/ for 0 x 1, neglecting terms of O.eps2/. fPoint of information: ln.1 C "/ D " C O."2/, " ! 0.g
 Plot .cond f /.x/ and your estimate of .cond A/.x/ as functions of x on [0,1]. Comment on the results.
					
SupposeAisanalgorithmthatcomputesthe(smooth)functionf.x/fora given machine number x, producing fA.x/ D f .x/.1 C "f /, where j"f j  '.x/eps (eps D machine precision). If 0 < .cond f /.x/ < 1, show that
					
.cond A/.x/ '.x/ .cond f /.x/
					
if second-order terms in eps are neglected. fHint: set fA.x/ D f.xA/,
					
xA D x.1 C "A/, and expand in powers of "A, keeping only the first.g
					
Apply the result of (a) to f.x/ D 1cosx; 0 < x < 1 , when evaluated sinx 2
					
as shown. (You may assume that cos x and sin x are computed within a relative error of eps.) Discuss the answer.
 Do the same as (b), but for the (mathematically equivalent) function f.x/D sinx ;0<x<1 .
					
Machine Assignments
					
1. LetxD1C =106.ComputethenthpowerofxfornD100;000;200;000;:::; 1;000;000 once in single and once in double Matlab precision. Let the two results be pn and dpn. Use the latter to determine the relative errors rn of the former. Print n; pn; dpn; rn; rn=.n eps0/, where eps0 is the single-precision eps. What should xn be, approximately, when n D 1;000;000? Comment on the results.
					
2. Compute the derivative dy=dx of the exponential function y D ex at x D 0 from the difference quotients d.h/ D .eh 1/=h with decreasing h. Use
					
(a) hDh1WD2i,i D5W5W50;
 (b) hDh2WD.2:2/i,i D5W5W50.
				
			
			
				
					
(a) (b)
					
(c) 44. (a)
					
(b) (c)
				
			
			 			 			 			
				
					
1Ccos x 2
				
			
		
		
			
				
					
40 1 Machine Arithmetic and Related Matters
				
			
			
				
					
Print the quantities i; h1; h2; d1 WD d.h1/; d 2 WD d.h2/, the first and two last
					
ones in f-format, the others in e-format. Explain what you observe.
 3. Considerthefollowingprocedurefordeterminingthelimitlim.eh1/=hona
				
			
			
				
					
computer. Let
				
				
					
h!0
					
n
 dn Dfl e2 1 fornD0;1;2;:::
				
			
			 			
				
					
2n
 and accept as the machine limit the first value satisfying dn D dn1
				
			
			
				
					
.n 1/.
					
    • 							
(a)  WriteandrunaMatlabroutineimplementingtheprocedure.
 						
    • 							
(b)  In R.t;s/-floating-point arithmetic, with rounding by chopping, for what value of n will the correct limit be reached, assuming no underflow (of 2n) occurs? fHint: use eh D 1 C h C 12h2 C  .g Compare with the
 							
experiment made in (a).
 						
    • 							
(c)  On what kind of computer (i.e., under what conditions on s and t) will
 							
underflow occur before the limit is reached?
 						
					
    4. 							
Euler’sconstantD0:57721566490153286::: isdefinedasthelimit
 							
D limn; wherenD1C1C1CC1lnn: n!1 23n
 							
Assumingthatn cnd,n!1,forsomeconstantscandd >0,tryto
 							
determine c and d experimentally on the computer.
 						
    5. 							
Letting un D unC1 un, one has the easy formula
 							
XN
 un D uNC1 u1:
 							
nD1
 							
With un D ln.1Cn/, compute each side (as it stands) for N D 1;000 W 1;000 W
 							
10;000, the left-hand side in Matlab single precision and the right-hand side in
 							
double precision. Print the relative discrepancy of the two results. Repeat with
 							
NnD1 un: compute the sum in single and double precision and compare the results. Try to explain what you observe.
 						
				
			
			
				
					
P
					
6. (a)
				
				
					
Writeaprogramtocompute
					
XN 1 1 XN 1 SND nnC1 D n.nC1/;
					
once using the first summation and once using the (mathematically equiv- alent) second summation. For N D 10k, k D 1W7, print the respective absolute errors. Comment on the results.
				
			
			 			 			
				
					
nD1 nD1
				
			
		
		
			
				
					
Machine Assignments 41
				
			
			
				
					
(b)
					
7. (a)
					
(b)
				
				
					
Writeaprogramtocompute
					
pN D
					
For the same values of N as in part (a), print the relative errors. Comment on the results.
 Prove: based on best possible relative error bounds, the floating-point addition fl.fl.x C y/ C z/ is more accurate than fl.x C fl.y C z// if and only if jx C yj < jy C zj. As applications, formulate addition rules in the cases
					
(a1) 0<x<y<z;
 (a2) x>0,y<0,z>0; (a3) x<0,y>0,z<0.
					
Consider the nth partial sums of the series defining the zeta function .s/, resp., eta function .s/,
				
			
			
				
					
8. LetnD106 and
				
			
			
				
					
zn D
 kD1
				
				
					
ks
				
				
					
;
				
				
					
en D
				
				
					
.1/k1
				
				
					
ks
				
				
					
:
				
			
			
				
					
YN n
					
nC1:
				
			
			 			
				
					
nD1
				
			
			
				
					
Xn 1 Xn 1
				
			
			
				
					
For s D 2; 11=3; 5; 7:2; 10 and n D 50; 100; 200; 500; 1000, compute these sums in Matlab single precision, once in forward direction and once in backward direction, and compare the results with Matlab double-precision evaluations. Interpret the results in the light of your answers to part (a), especially (a2) and (a3).
				
			
			
				
					
s D 1011n C
				
				
					
Xn kD1
				
				
					
ln k:
				
			
			
				
					
    • 							
(a)  Determinesanalyticallyandevaluateto16decimaldigits.
 						
							
(b)  The following Matlab program computes s in three different (but mathe-
 							
matically equivalent) ways:
 							
                %MAI_8B
                %
                n=10ˆ6; s0=10ˆ11*n;
                s1=s0;
                for k=1:n
 							
                  s1=s1+log(k);
                end
 							
                s2=0;
                for k=1:n
 							
                   s2=s2+log(k);
    •  						
				
			
			
				
					
kD1
				
			
		
		
			
				
					
42
				
				
					
1 Machine Arithmetic and Related Matters
				
			
			
				
					
                  end
                   s2=s2+s0;
                   i=1:n;
                   s3=s0+sum(log(i));
                   [s1 s2 s3]’

					
Run the program and discuss the results.
 9. Write a Matlab program that computes the Euclidean condition number of the
					
Hilbert matrix H n following the prescription given in footnote 3 of the text. (a) The inverse of the Hilbert matrix H n has elements
					
nj ni i1
					
(cf. Note 3 to Sect. 1.3.2). Simplify the expression to avoid factorials of large numbers. fHint: express all binomial coefficients in terms of factorials and simplify.g
					
(b) Implement in Matlab the formula obtained in (a) and reproduce Table 1.1 of the text.
					
10. The (symmetrically truncated) cardinal series of a function f is defined by
				
			
			
				
					
!!!  nCi1 nCj1 iCj2 2
				
			
			
				
					
H 1 D .1/i Cj .i C j 1/ n ij
				
			
			
				
					
XN x k h
				
			
			
				
					
CN.f;h/.x/ D
 where h > 0 is the spacing of the data and the sinc function is defined by
				
			
			
				
					
f.kh/sinc h ;
				
			
			 			
				
					
sinc.u/ D
				
				
					
ˆ:
				
			
			
				
					
kDN
				
			
			
				
					
8
 ˆ ˆ< s i n .
					
ˆ u
					
1
 Under appropriate conditions, CN .f; h/.x/ approximates f .x/ on ŒN h; N h.
					
(a) Showthat
					
h xXN .1/k CN.f;h/.x/D sin h kDN xkhf.kh/:
					
Since this requires the evaluation of only one value of the sine function, it provides a more efficient way to evaluate the cardinal series than the original definition.
				
			
			
				
					
u /
 if u D 0:
				
			
			
				
					
if u ¤ 0;
				
			
			 			 		
		
			
				
					
Machine Assignments 43
				
			
			
				
					
    • 							
(b)  While the form of CN given in (a) may be more efficient, it is numerically unstable when x is near one of the abscissae kh. Why?
 						
    • 							
(c)  Find a way to stabilize the formula in (a). fHint: introduce the integer k0 a n d t h e r e a l n u m b e r t s u c h t h a t x D . k 0 C t / h , j t j  12 . g
 						
    • 							
(d)  Write a program to compute CN .f; h/.x/ according to the formula in (a) and the one developed in (c) for N D 100, h D 0:1, f.x/ D x exp.x2/, and x D 0:55, x D 0:5C108, x D 0:5C1015. Print CN .f;h/.x/, f.x/, and the error jCN .f; h/.x/ f .x/j in either case. Compare the results.
 						
				
			
			
				
					
11. In the theory of Fourier series, the numbers
 n D 1 C 2 Xn 1 t a n k
				
			
			
				
					
; n D 1 ; 2 ; 3 ; : : : ; known as Lebesgue constants, are of some importance.
				
			
			 			 			
				
					
2nC1 kD1 k 2nC1
				
			
			
				
					
    • 							
(a)  Showthatthetermsinthesumincreasemonotonicallywithk.Howdothe terms for k near n behave when n is large?
 						
    • 							
(b)  Compute n for n D 1; 10; 102; : : : ; 105 in Matlab single and double precision and compare the results. Do the same with n replaced by dn=2e. Explain what you observe.
 						
				
			
			
				
					
12. Sum the series
				
				
					
X1
 (a) .1/n=nŠ2;
					
nD0
				
				
					
X1 1=nŠ2
					
nD0
				
			
			
				
					
until there is no more change in the partial sums to within the machine precision. Generate the terms recursively. Print the number of terms required and the value of the sum. (Answers in terms of Bessel functions: (a) J0.2/; cf. Abramowitz and Stegun [1964, (9.1.18)] or Olver et al. [2010, (10.9.1)] and (b) I0.2/; cf.Abramowitz and Stegun [1964, (9.6.16)] or Olver et al. [2010, (10.32.1)].)
				
			
			
				
					
    13. 							
(P.J. Davis, 1993) Consider the series to three correct decimal digits.
 						
    14. 							
Weknowfromcalculusthat
 							
n!1 What is the “machine limit”? Explain.
 						
				
				
					
. Try to compute the sum
				
			
			
				
					
P
				
				
					
1 1 kD1 k3=2Ck1=2
				
			
			
				
					
(b)
				
			
			 			
				
					
lim
				
				
					
1n
					
1 C D e: n
				
			
			
				
					
				
			
			
				
					
15. Let f.x/ D .n C 1/x 1. The iteration
 xk D f.xk1/; k D 1;2;:::;KI x0 D 1=n;
					
in exact arithmetic converges to the fixed point 1=n in one step (Why?). What happens in machine arithmetic? Run a program with n D 1 W 5 and K D 10 W 10 W 50 and explain quantitatively what you observe.
				
			
		
		
			
				
					
44 1 Machine Arithmetic and Related Matters
				
			
			
				
					
16.
					
17.
				
				
					
Compute the integral 01exdx from Riemann sums with n equal subintervals, evaluating the integrand at the midpoint of each. Print the Riemann sums for n D 5;000 W 5;000 W 100;000 (to 15 decimal digits after the decimal point), together with absolute errors. Comment on the results.
				
			
			
				
					
R
					
Letyn D 01tnetdt,nD0;1;2;::: .
					
    • 							
(a)  Use integration by parts to obtain a recurrence formula relating yk to yk1 for k D 1; 2; 3; : : : ; and determine the starting value y0.
 						
    • 							
(b)  Write and run a Matlab program that generates y0;y1;:::;y20, using the recurrence of (a), and print the results to 15 decimal digits after the decimal point. Explain in detail (quantitatively, using mathematical analysis) what is happening.
 						
    • 							
(c)  Use the recursion of (a) in reverse order, starting (arbitrarily) with yN D
 							
0. Place into five consecutive columns of a (21 5) matrix Y the values
 							
y.N/;y.N/;:::;y.N/ thus obtained for N D 22;24;26;28;30. Determine 0 1 20
 							
how much consecutive columns of Y differ from one another by printing ei Dmaxj.Y.W;iC1/Y.W;i//:=Y.W;iC1/j; iD1;2;3;4:
 							
PrintthelastcolumnY.W;5/ofY andexplainwhythisrepresentsaccurately the column vector of the desired quantities y0 ; y1 ; : : : ; y20 .
 						
				
			
			
				
					
R
				
			
			
				
					
Selected Solutions to Exercises
					
14. We may assume x > 0, since otherwise we could multiply z by 1 and the result by i. p
					
In the first expression for z there will be a large cancellation error in the imaginary part when jyj is very small, whereas in the second expression all arithmetic operations are benign. Illustration: z D 4:5 C 0:025i (in eight significant digits)
					
r D 4:5000694;
					
;
					
vD y1=2 D5:8925338103: 2 rCx
					
2
					
The last five digits in the first evaluation of v are in error! 21. (a) We have
					
p1 D x1;
 pk Dxkpk1.1C"k/; j"kjeps; kD2;3;:::;n:
				
			
			
				
					
rx 1=2 3 v D 2 D 5:8906706 10
				
			
			 			 			 		
		
			
				
					
Selected Solutions to Exercises 45 Therefore,
				
			
			
				
					
p2 D x1x2.1 C "2/;
 p3 D x1x2x3.1 C "2/.1 C "3/;
					

 pn D x1x2 xn.1C"2/.1C"3/.1C"n/;
				
			
			
				
					
so that
					
If E 0, then jEj  .1 C eps/n1 1; otherwise, jEj  1 .1 eps/n1. Since the first bound is larger than the second, we get
					
jEj  .1 C eps/n1 1: (b) Usingthebinomialtheorem,onehas
					
					
2 3Š
					
C.r1/.r2/1epsr1 : rŠ
					
Sincereps< 1 ,onehasalso 10
					
.rk/eps< 1; kD1;2;:::;r1; 10
					
and so
 .1Ceps/r 1<reps 1C 1101C 1102CC 110.r1/
					
<reps10 1101C 1102C 1Š 2Š
					
Dreps10fe101 1gD1:051709:::reps < 1:06r eps:
				
			
			
				
					
pnx1x2xn D.1C"2/.1C"3/.1C"n/1DWE: x1x2 xn
				
			
			 			
				
					
.1Ceps/r 1 D 1C r1 epsC r2 eps2 CCepsr 1
 D r eps 1C r 1 epsC .r 1/.r 2/ eps2 C
				
			
			 			 			 			
				
					
2Š 3Š rŠ
				
			
		
		
			
				
					
46 1 Machine Arithmetic and Related Matters Hence, if .n 1/eps < 1=10, the result in (a) can be simplified to
				
			
			
				
					
34. We have cos ̨./D
				
				
					
qTb./ D kqk  kb. /k
				
				
					
qT.a q/
 Œ.a q/T.a q/1=2
				
			
			
				
					
jEj  1:06.n 1/eps:
				
			
			 			 			
				
					
0 .120 C2/1=2
				
			
			
				
					
D
 ̨. /Dcos1R. /; R. 0/D0 if j 0j<1;
				
			
			
				
					
DW R. /;
				
			
			 			
				
					
̨0./Dp 1 R0./ 1R2. /
					
Dp 1 1R2. /
					
.12 0 C 2/1=2 . 0 /Œ.12 0 C 2/1=20 .120 C2/ :
				
			
			 			 			 			 			 			
				
					
For
				
				
					
D
				
				
					
0, therefore, assuming j 0j < 1, we get
 0 .1 02/1=2 1
				
			
			
				
					
̨.0/D102 D.102/1=2; jj1
				
			
			 			 			
				
					
0 . 1 02 / 1 = 2 2 j 0 j .cond ̨/. 0/D 1 D .1 2/1=2:
				
			
			 			 			 			
				
					
20
				
			
			
				
					
0 D 0, i.e., a is already orthogonal to q, hence b D a, then .cond ̨/. 0/ D
				
			
			
				
					
If
 0, as expected. If j 0j " 1, then .cond ̨/. 0/ " 1, since in the limit, a is parallel to q and cannot be orthogonalized. In practice, if j 0j is close to 1, the problem of ill-conditioning can be overcome by a single, or possibly repeated, reorthogonalization.
					
44. (a) Following the Hint, we have
					
fA.x/ D f.x/.1 C "f / D f.xA/
 D f .x.1 C "A// D f .x C x"A/ D f .x/ C x"Af 0.x/ C O."2A/:
				
			
		
		
			
				
					
Selected Solutions to Exercises 47 Neglecting the O."2A/ term, one gets
				
			
			
				
					
hence
				
				
					
x"Af 0.x/ D f.x/"f ; ˇˇˇˇ
				
			
			
				
					
ˇxA xˇ ˇ f.x/ ˇ
				
				
					
'.x/ .condf/.x/
				
			
			
				
					
ˇ
				
				
					
ˇ D j"Aj D ˇ 0 ˇ j"f j  xf .x/
				
				
					
eps;
				
			
			 			 			 			
				
					
which proves the assertion. (b) One easily computes
				
			
			
				
					
x
				
			
			
				
					
.condf/.x/D x ; 0<x< : sinx 2
				
			
			 			
				
					
Furthermore,
 fA.x/D .1.cosx/.1C"1//.1C"2/ .1C"4/; j"ijeps;
					
.sin x/.1 C "3/
					
where "1, "2, "3, "4 are the relative errors committed, respectively, in evaluating the cosine function, the difference in the numerator, the sine function, and the quotient. Neglecting terms of O."2i /, one obtains by a simple computation that
					
that is,
				
			
			 			
				
					
no
				
			
			
				
					
f .x/D 1cosx 1C" C" " " cosx ; A sinx 2 4 3 11cosx
				
			
			 			 			
				
					
ˇˇ
				
			
			
				
					
cosx
 1 cos x
					
and one gets
 .condA/.x/sinx 3C cosx ; 0<x< :
					
Obviously, .condA/.x/ ! 1 as x ! 0, whereas .condA/.x/ ! 6= as x ! =2. The algorithm is ill-conditioned near x D 0 (cancellation error), but well conditioned near =2. The function itself is quite well conditioned,
					
1.condf/.x/ 2:
				
			
			
				
					
ˇ cosx ˇ
				
			
			
				
					
j"fjDˇ"2 C"4 "3 "1 Therefore,
				
				
					
1 cos x
				
				
					
ˇ 3C
				
				
					
eps:
				
			
			 			 			
				
					
'.x/D3C cosx ; 1cosx
				
			
			 			
				
					
				
			
			 			 			
				
					
x 1cosx 2
				
			
		
		
			
				
					
48
				
				
					
1 Machine Arithmetic and Related Matters (c) In this case (the condition of f being of course the same),
					
fA.x/D .sinx/.1C"1/ .1C"4/; j"ij  eps; .1 C .cos x/.1 C "2//.1 C "3/
					
giving
				
			
			 			
				
					
f .x/D sinx 1C" " C" " cosx ;
				
			
			
				
					
A
				
				
					
1Ccosx 1 3 4 2 1Ccosx
				
			
			 			 			
				
					
that is,
 j"fjDˇ"1"3C"4"21Ccosxˇ 3C1Ccosx eps;
				
			
			
				
					
ˇˇ ˇ cosx ˇ cosx
				
			
			 			 			
				
					
and
				
				
					
					
.condA/.x/ sinx 3C cosx : x 1Ccosx
				
			
			 			 			
				
					
Now, A is entirely well conditioned, 6.condA/.x/72; 0<x<2:
				
			
			
				
					
Selected Solutions to Machine Assignments
					
7. (a) Forarbitraryrealx,y,z,thefirstadditioncanbewrittenas fl.fl.x C y/ C z/ D ..x C y/.1 C "1/ C z/.1 C "2/
					
xCyCzC.xCy/"1 C.xCyCz/"2
					
D.xCyCz/ 1C xCy "1C"2 ; xCyCz
					
where the "i are bounded in absolute value by eps. The best bound for the relative error is
					
					
jrel:err:j  jx C yj C 1 eps: jx C y C zj
				
			
			 			 		
		
			
				
					
Selected Solutions to Machine Assignments 49 Likewise, for the second addition, there holds (interchange x and z)
				
			
			
				
					
jrel:err:j  jy C zj C 1 eps:
				
			
			 			
				
					
jx C y C zj
 Based on these two error bounds, the first addition is more accurate than
				
			
			
				
					
the second if and only if jx C yj < jy C zj, as claimed. Examples
 (a1) 0<x<y<z.Here,
					
jx C yj D x C y < y C z D jy C zj: Thus, addition in increasing order is more accurate.
					
(a2) x>0,y<0,z>0.Here,
 jxCyjDjxjyjj; jyCzjDjzjyjj;
					
and adding to the negative number y the positive number closer to jyj
					
first is more accurate.
 (a3) x<0,y>0,z<0.Here,
				
			
			
				
					
(b)
				
				
					
jx C yj D jjxj C yj D jjxj  yj ; jy C zj D jy jzjj D jjzj  yj ;
					
and adding to the positive number y the negative number first whose modulus is closer to y is more accurate.
					
PROGRAM
					
%MAI_7B
 %
 f0=’%6.4f %8.1e %9.2e %9.2e %9.2e %9.2e\n’;
 disp(’ zeta eta’) disp(’ s n forw backw forw backw’) for s=[2 11/3 5 7.2 10]
					
for n=[50 100 200 500 1000] k=1:n;
					
z=sum(1./k.ˆs); e=sum((-1).ˆ(k-1)./k.ˆs); zf=single(0); ef=single(0); for kf=1:n
					
zf=zf+single(1/kfˆs);
				
			
		
		
			
				
					
50
				
				
					
1 Machine Arithmetic and Related Matters
				
			
			
				
					
ef=ef+single((-1)ˆ(kf-1)/kfˆs); end
					
zf0=zf; ef0=ef; zb=single(0); eb=single(0); for kb=n:-1:1
					
zb=zb+single(1/kbˆs);
					
eb=eb+single((-1)ˆ(kb-1)/kbˆs); end
					
zb0=zb; eb0=eb;
 errzf=abs((zf0-z)/z); errzb=abs((zb0-z)/z); erref=abs((ef0-e)/e); erreb=abs((eb0-e)/e); fprintf(f0,s,n,errzf,errzb,erref,erreb)
				
			
			
				
					
end
					
    fprintf(’\n’)
   end

					
   OUTPUT
>> MAI_7B

				
			
			
				
					
zeta
				
				
					
eta
				
			
			
				
					
s n
 2.0000 5.0e+01 1.14e-07 3.30e-08 5.16e-08 2.09e-08 2.0000 1.0e+02 7.11e-08 1.82e-09 4.35e-08 4.35e-08 2.0000 2.0e+02 9.34e-08 5.20e-08 1.16e-07 2.94e-08 2.0000 5.0e+02 4.52e-08 4.52e-08 3.92e-07 3.01e-08 2.0000 1.0e+03 1.70e-07 4.77e-08 3.85e-07 2.23e-08
					
3.6667 5.0e+01 2.48e-07 3.30e-08 2.84e-08 3.54e-08 3.6667 1.0e+02 1.26e-07 1.82e-08 5.97e-08 4.07e-09 3.6667 2.0e+02 1.43e-06 3.15e-08 8.21e-08 1.84e-08 3.6667 5.0e+02 1.65e-06 4.06e-08 8.40e-08 2.02e-08 3.6667 1.0e+03 1.67e-06 4.88e-08 8.41e-08 2.03e-08
					
5.0000 5.0e+01 2.46e-07 1.61e-08 4.04e-08 2.09e-08 5.0000 1.0e+02 2.81e-07 5.08e-08 3.89e-08 2.24e-08 5.0000 2.0e+02 2.83e-07 5.30e-08 3.88e-08 2.25e-08 5.0000 5.0e+02 2.83e-07 5.31e-08 3.88e-08 2.25e-08 5.0000 1.0e+03 2.83e-07 5.31e-08 3.88e-08 2.25e-08
					
7.2000 5.0e+01 7.20e-09 7.20e-09 5.45e-08 5.52e-09 7.2000 1.0e+02 7.20e-09 7.20e-09 5.45e-08 5.52e-09 7.2000 2.0e+02 7.20e-09 7.20e-09 5.45e-08 5.52e-09 7.2000 5.0e+02 7.20e-09 7.20e-09 5.45e-08 5.52e-09 7.2000 1.0e+03 7.20e-09 7.20e-09 5.45e-08 5.52e-09
					
10.0000 5.0e+01 1.20e-08 1.20e-08 2.32e-08 2.32e-08 10.0000 1.0e+02 1.20e-08 1.20e-08 2.32e-08 2.32e-08
				
			
			
				
					
forw
				
				
					
backw forw
				
				
					
backw
				
			
		
		
			
				
					
Selected Solutions to Machine Assignments 51
				
			
			
				
					
10.0000 2.0e+02 1.20e-08 1.20e-08 2.32e-08 2.32e-08 10.0000 5.0e+02 1.20e-08 1.20e-08 2.32e-08 2.32e-08 10.0000 1.0e+03 1.20e-08 1.20e-08 2.32e-08 2.32e-08 >>
					
Interpretation
					
Rather consistently, backward summation gives more accurate results than forward summation, by as much as two decimal orders (for s D 11=3 and n D 200 in the case of .s/). For large s (for example s D 10) there is no noticeable difference in accuracy. All this (and more) is consistent with the answers given in part (a). Indeed, the series for the zeta function has terms that are all positive and strictly decreasing, so that by (a1) summation in increasing order of the terms, i.e., backward summation, is more accurate. In the case of the eta series, consider
				
			
			
				
					
xD1;yD 1 ;zD 1 : ks .k C 1/s .k C 2/s
					
					
					
Since the function x=.x C 1/ for x > 0 increases monotonically, it follows that jx C yj > jy C zj for all k > 0, and backward summation is more accurate than forward summation. Moreover,
					
					
					
sothattheimprovementjyCzj ofbackwardoverforwardsummationdisappears jxCyj
					
asymptotically as k ! 1. Also, for large s, the improvement is relatively small, even for only moderately large k.
					
The same discussion holds for
					
xD1;yD 1 ;zD 1 : ks .k C 1/s .k C 2/s
				
			
			 			 			
				
					
Then
				
			
			
				
					
111ks jxCyjDks .kC1/s Dks 1 kC1 ;
				
			
			 			 			
				
					
111kC1s jyCzjD.kC1/s .kC2/s D.kC1/s 1 kC2 :
				
			
			 			 			 			 			
				
					
jxCyjD1 11C1s s;k!1; ks k ksC1
				
			
			 			
				
					
1 1s 1s 2s s jyCzjDks 1Ck 1 1Ck 1Ck ksC1; k!1;
				
			
			 			 			 			 		
		
			
				
					
52 1 Machine Arithmetic and Related Matters 11. (a) LetxD k ,sothat0<x< if1kn.Then,uptoapositive
					
f . x / D x1 t a n x :
 We show that f increases monotonically: we have
				
			
			 			
				
					
2nC1 2
 constant factor, the general term of the sum is
				
			
			
				
					
Œxf.x/0 D 1 ; cos2 x
				
			
			 			
				
					
hence
				
			
			
				
					
xf0.x/D 1 f.x/D 1 sinx
				
			
			 			 			 			
				
					
cos2 x D 1
				
				
					
cos2 x x cos x 1 1 sinx cosx
				
			
			 			
				
					
cos2 x
 D 1 1sin2x >0:
				
			
			
				
					
x cos2 x 2x
				
			
			 			 			
				
					
Thus, the terms in the sum increase monotonically. For n very large, say n D 105, most terms of the sum are negligibly small except for a few very near n, where they sharply increase to the maximum value 4 . This can be seen by letting k D n r for some fixed (small) integer r and large n. Then
				
			
			
				
					
nr D1 2rC1 ; 2nC1 2 2.2nC1/
				
			
			 			 			
				
					
and, as n ! 1,
				
			
			
				
					
.n r/ 2nC1
					
PROGRAM
				
				
					
2r C 1 2 2nC1
				
				
					
cos sin
					
1 2r C 1
				
				
					
4
				
				
					
n 2rC1
				
			
			
				
					
				
				
					
					
2rC1 2 2nC1
					
2rC1 2 2nC1
					
as n!1:
				
			
			 			
				
					
tan Therefore,
				
				
					
D tan
				
				
					
2
				
				
					
				
				
					
D
				
				
					
:
				
			
			 			 			 			 			 			
				
					
1 n r
				
				
					
tan.nr/ 2n C 1
				
				
					
4
				
			
			 			 			 			
				
					
(b)
				
			
			
				
					
%MAI_11B
 %
 f0=’%10.0f %12.8f %19.16f %12.4e\n’; disp(’ n Lebesgue Lebesgue double
				
			
			
				
					
diff’)
 % disp(’ n truncated single and double Lebesgue’)
				
			
			
				
					
for n=[1 10 100 1000 10000 100000] den0=single(1/(2*n+1));
				
			
		
		
			
				
					
Selected Solutions to Machine Assignments
				
				
					
53
				
			
			
				
					
>>
					
Comments
				
			
			
				
					
 den=1/(2*n+1);

					
 k=1:n;
 % k=1:ceil(n/2);

					
 s0=sum(single(tan(k*pi*den0)./k));
  s=sum(tan(k*pi*den)./k);
  s0=den0+single(2*s0/pi);
  s=den+2*s/pi;

					
 diff=abs(s-s0);

					
 fprintf(f0,n,subs(s0),s,diff)
end

				
			
			
				
					
OUTPUT
					
>> MAI_11B n
				
				
					
Lebesgue Lebesgue double
 1.43599117 1.4359911241769170 4.3845e-08 2.22335672 2.2233569241536819 2.0037e-07 3.13877344 3.1387800926548395 6.6513e-06 4.07023430 4.0701636043524356 7.0694e-05 5.00332785 5.0031838616314577 1.4398e-04 5.92677021 5.9363682125234796 9.5980e-03
				
			
			
				
					
    1
    10
   100
  1000
 10000
100000

				
			
			
				
					
Because of the behavior of the terms in the sum, when n is large, the accuracy of the sum is largely determined by the accuracy of the terms very near to n. But there, the argument of the tangent is very close to =2. Since
					
.condtan/.x/Dx.1Ctan2x/; 0<x< =2; tan x
					
the tangent is very ill-conditioned for x near =2. In fact, for " > 0 very small,
				
			
			
				
					
diff
				
			
			 			
				
					
					
Since k D n corresponds to " D n , that is, " D 2 2nC1
				
			
			
				
					
one has
				
			
			
				
					
.cond tan/ " tan " D cos " : 2 22 2sin"2"
				
			
			 			 			 			
				
					
				
			
			
				
					
.condtan/ 2" 2 =.4n/D2n; n!1:
				
			
			
				
					
2.2nC1/
				
				
					
4n
				
				
					
,
				
			
			 			
				
					
So, for n D 105, for example, we must expect a loss of about five decimal digits. This is confirmed by the numerical results shown above.
					
The inaccuracy observed cannot be ascribed merely to the large volume of computation. In fact, if we extended the sum only to, say, k D n=2, we would escape the ill-conditioning of the tangent and, even for n D 105, would get more accurate answers. This is shown by the numerical results below.
				
			
		
		
			
				
					
54
				
				
					
1 Machine Arithmetic and Related Matters
				
			
			
				
					
>> MAI_11B n
				
				
					
truncated single and double Lebesgue 1.43599117 1.4359911241769170 4.3845e-08 0.57060230 0.5706023117647347 1.3982e-08 0.54363489 0.5436349730685069 8.1558e-08 0.54078776 0.5407873971420362 3.5930e-07 0.54050153 0.5405010907553436 4.4418e-07 0.54047358 0.5404724445910691 1.1358e-06
				
			
			
				
					
>>
				
			
			
				
					
    1
    10
   100
  1000
 10000
100000

				
			
		
		
			
				
					
Chapter 2
 Approximation and Interpolation
				
			
			
				
					
The present chapter is basically concerned with the approximation of functions. The functions in question may be functions defined on a continuum – typically a finite interval – or functions defined only on a finite set of points. The first instance arises, for example, in the context of special functions (elementary or transcendental) that one wishes to evaluate as a part of a subroutine. Since any such evaluation must be reduced to a finite number of arithmetic operations, we must ultimately approximate the function by means of a polynomial or a rational function. The second instance is frequently encountered in the physical sciences when measurements are taken of a certain physical quantity as a function of some other physical quantity (such as time). In either case one wants to approximate the given function “as well as possible” in terms of other simpler functions.
					
The general scheme of approximation can be described as follows. We are given the function f to be approximated, along with a class ˆ of “approximating functions” ' and a “norm” k  k measuring the overall magnitude of functions. We are looking for an approximation 'O 2 ˆ of f such that
					
kf 'Okkf 'k forall '2ˆ: (2.1)
					
The function 'O is called the best approximation to f from the class ˆ, relative to the norm k  k.
					
The class ˆ is called a (real) linear space if with any two functions '1, '2 2 ˆ it also contains '1 C '2 and c'1 for any c 2 R, hence also any (finite) linear combination of functions 'i 2 ˆ. Given n “basis functions” j 2 ˆ, j D 1;2;:::;n, we can define a linear space of finite dimension n by
					
89 < Xn =
					
ˆDˆnD 'W'.t/D cj j.t/;cj2R : (2.2) :;
					
jD1
					
Examplesoflinearspaces ̊. 1.ˆDPm:polynomialsofdegreem.Abasisfor Pm is,forexample, j.t/Dtj1,j D1;2;:::;mC1,sothatnDm C 1. Polynomials are the most frequently used “general-purpose” approximants for
					
W.Gautschi,NumericalAnalysis,DOI10.1007/978-0-8176-8259-0 2, 55 © Springer Science+Business Media, LLC 1997, 2012
				
			
		
		
			
				
					
56 2 Approximation and Interpolation
				
			
			
				
					
dealing with functions on bounded domains (finite intervals or finite sets of points). One reason is Weierstrass’s theorem, which states that any continuous function can be approximated on a finite interval as closely as one wishes by a polynomial of sufficiently high degree.
					
2. ˆ D Skm./: (polynomial) spline functions of degree m and smoothness class k on the subdivision
					
W aDt1 <t2 <t3 <<tN1 <tN Db
					
of the interval [a;b]. These are piecewise polynomials of degree m pieced together at the “joints” t2 ; : : : ; tN 1 in such a way that all derivatives up to and including the kth are continuous on the whole interval [a; b], including the joints:
				
			
			
				
					
ˇ
 Sk./Dfs2CkŒa;bW sˇ 2P ; iD1;2;:::;N1g:
				
			
			
				
					
m Œti;tiC1 m
				
			
			
				
					
We assume here 0 k < m; otherwise, we are back to polynomials Pm (see Ex. 68). We set k D 1 if we allow discontinuities at the joints. The dimension ofSkm./isnD.mk/.N 2/CmC1(seeEx.71),buttofindabasisisa nontrivial task; for m D 1, see Sect. 2.3.2.
					
3. ˆ D Tm Œ0; 2 : trigonometric polynomials of degree m on [0, 2 ]. These are linear combinations of the basic harmonics up to and including the mth one, that is,
					
k.t/Dcos .k1/t; kD1;2;:::;mC1I mC1Ck.t/ D sinkt; k D 1;2;:::;m;
					
where now n D 2m C 1. Such approximants are a natural choice when the function f to be approximated is periodic with period 2 . (If f has period p, one makes a preliminary change of variables t 7! t p=2 .)
					
4. ˆ D En: exponential sums. For given distinct ̨j > 0, one takes j .t/ D e ̨j t , j D 1; 2; : : : ; n. Exponential sums are often employed on the half-infinite interval RC: 0 t < 1, especially if one knows that f decays exponentially as t ! 1.
					
Note that the important class of rational functions,
					
ˆDRr;s Df'W 'Dp=q; p2Pr; q2Psg;
					
is not a linear space. (Why not?)
 Possible choices of norm – both for continuous and discrete functions –
					
and the type of approximation they generate are summarized in Table 2.1. The continuous case involves an interval [a;b] and a “weight function” w.t/ (possibly w.t/ 1) defined on [a; b] and positive except for isolated zeros. The discrete case involves a set of N distinct points t1 , t2 ; : : : ; tN along with positive weight factors
				
			
		
		
			
				
					
2 Approximation and Interpolation
 Table 2.1 Types of approximation and associated norms
				
				
					
57
				
			
			 			
				
					
Continuous norm
					
kuk1 D max ju.t/j at b
				
				
					
Approximation
					
L1 Uniform
					
Chebyshev
				
				
					
Discrete norm
					
kuk1 D max 1i N
				
				
					
ju.ti /j
				
			
			 			
				
					
kuk1 D kuk1;w D
					
kuk2;w D
				
				
					
ju.t/jdt Zb
				
				
					
L1
 Weighted L1
				
				
					
kuk1 D kuk1;w D
				
				
					
ju.ti/j XN
				
			
			
				
					
Zb a
				
				
					
XN iD1
				
			
			
				
					
ju.t/jw.t/dt ZN2
				
			
			
				
					
wi ju.ti /j
 !1 !1
				
			
			
				
					
a
 b2X
					
ju.t/j2w.t/dt WeightedL2 kuk2;w D Least squares
				
			
			
				
					
a
				
			
			
				
					
w1; w2; : : : ; wN
 the weight function w is such that the integral extended over [a; b], which defines the norm, makes sense.
					
Hence, we may take any one of the norms in Table 2.1 and combine it with any of the preceding linear spaces ˆ to arrive at a meaningful best approximation problem (2.1). In the continuous case, the given function f , and the functions ' of the class ˆ, of course, must be defined on [a; b] and such that the norm kf 'k makes sense. Likewise, f and ' must be defined at the p
				
			
		
	 
