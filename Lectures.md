---
title: Lectures for Numerical Methods II by Aleks Donev (Spring 2023)
layout: default
---

## Lectures 

I will post here lecture notes for each class in the form of slides (typed or hand-written). While these contain all of the information you need to know, reading going beyond this is essential to the class and will be indicated here. I will refer mostly to the textbook of LeVeque, but there will also be links to papers or notes by other people. 

For more advanced material consult my [Computational Methods for PDEs class](https://adonev.github.io/CompPDEs).

For the PDE review by Prof. Jonathan Goodman, see these notes on [Fourier series](Lectures/PDE_Review_Fourier.pdf) and these notes on [Modes and the heat equation](Lectures/PDE_Review_ModesAndHeat.pdf) and these notes on [physical PDEs](Lectures/PDE_Review_Physical.pdf).
 
**These pages are constantly updated up to but sometimes also after the lecture. *Please refer to them regularly especially when doing homework.*** 

### 1. (1/24) [The Fast Fourier Transform (FFT)](Lectures/Lecture-FFT.handout.pdf) and 2. (1/31 and 2/7) [Pseudospectral Methods](Lectures/Lecture-Spectral.handout.pdf)

The use of Fourier techniques in PDEs, both their analysis and numerical solution, will come up many times in this class. There are three separate but related topics to consider here. The first is the [FFT as a discrete unitary transform](Lectures/Lecture-FFT.handout.pdf) (linear algebra), and using the Fourier series as an [approximation to periodic functions](https://epubs.siam.org/doi/pdf/10.1137/141001007) (approximation theory, see sections 2,3 and 4 in the paper ["Extension of Chebfun to periodic functions"](https://epubs.siam.org/doi/pdf/10.1137/141001007) 2015), and [FFTs as as a tool to solve PDEs](Lectures/Lecture-Spectral.handout.pdf). The use of FFTs to do Chebyshev series is described in chapter 7 of Trefethen.

By far the most popular/efficient library for FFTs is [FFTW](https://www.fftw.org/), see [documentation for what normalization it uses](https://www.fftw.org/fftw3_doc/What-FFTW-Really-Computes.html). FFTW is used under the hood in Matlab/numpy, but they may use differet normalization, see for example the [Matlab's fft/ifft convention](https://www.mathworks.com/help/matlab/ref/fft.html#buuutyt-6).

**Appendix A.5 in Leveque** reviews measuring errors. **Appendix B.3 in LeVeque** reviews orthogonal polynomials. **Appendix E.3 in LeVeque** reviews using Fourier transforms to solve PDEs with pen and paper and you should read this if it is not already comfortably familiar. I recommend reading Appendices A, B, and E in their entirety asap.
 
A complete source on trigonometric and Chebyshev polynomials and more is the book "[Spectral Methods in Matlab](https://epubs.siam.org/doi/book/10.1137/1.9780898719598)" (available electronically at Courant) by Nick Trefethen, which includes lots of [MATLAB codes](https://people.maths.ox.ac.uk/trefethen/spectral.html).
 
See also these [short notes on handling the unmatched mode](Lectures/SolutionPseudoKdV.pdf) for even-sized grids. There are some subtle issues with spectral differentiation, as discused in detail in these [technical notes by Steven G. Johnson](Lectures/SpectralDerivatives_FFT.pdf), as well as with aliasing, as discussed in these [selected pages on aliasing](Lectures/Aliasing.pdf) from the detailed [notes on pseudospectral methods by Denys Dutykh](https://arxiv.org/abs/1606.05432v1). For the approximation theory behind using Fourier series as an approximation to periodic functions, see sections 2,3 and 4 in the paper ["Extension of Chebfun to periodic functions" by Nick Trefethen](https://epubs.siam.org/doi/pdf/10.1137/141001007). 

### 3. (2/7 and 2/14) [One-step methods for ODEs](Lectures/Lecture-ODE.handout.pdf)

We begin our study of differential equations with some [basic methods and theory for solving systems of ODEs](Lectures/Lecture-ODE.handout.pdf), namely, concepts of consistency, zero-stability and convergence for one-step methods. 
 
Read chapter 5 except 5.9 and chapter 6 except 6.4 in LeVeque -- we will come back to multistep methods shortly.
 
A paper by Shampine and Reichelt describes [The MATLAB ODE suite](https://epubs.siam.org/doi/10.1137/S1064827594276424) and is important reading for anyone using the MATLAB solvers. 

### 4. (2/21) [Runge-Kutta methods and adaptivity](Lectures/RungeKuttaNumMethII.pdf)

We will give some more details about [Runge-Kutta methods](Lectures/RungeKuttaNumMethII.pdf) and also adaptive time stepping (needed for Homework 3).

We will not cover in class the last aside in the lecture notes, which describes how to derive the fully [implicit Gauss RK2 scheme](https://en.wikipedia.org/wiki/Gauss%E2%80%93Legendre_method) of 4th order, the maximum possible for two stages. Some of the calculations and the proof that this method is of 4th order for linear ODEs are done in a [Maple worksheet](Lectures/GaussRK2.pdf) ([Maple _mws_ file](Lectures/GaussRK2.mws)). To understand the theory behind these methods, look at chapter 17 (Collocation methods) in these [lecture notes by Michael Lindsey](https://quantumtative.github.io/math228a_lecture_notes.pdf).

### 5. (3/7)  [Absolute Stability and Stiffness](Lectures/Lecture-Stability.handout.pdf) and [Linear Multistep Methods](Lectures/LinearMultistepMethods.pdf)

The lecture on 2/28 will be given by Mariya Savinov, see these [additional notes on HW2](Lectures/LectureStability_ExtraNotes.pdf). They will introduce regions of [absolute stability](Lectures/Lecture-Stability.handout.pdf) for various one-step methods and discuss the concept of stiffness, which will be crucial for PDEs. Read chapters 7 and 8 in LeVeque, except 7.3, 7.6.1 and 8.4.

### 6. (3/7) [Linear Multistep Methods](Lectures/LinearMultistepMethods.pdf) and [IMEX RK schemes](Lectures/IMEX.pdf)

We will cover [linear multistep methods](Lectures/LinearMultistepMethods.pdf), including convergence, zero and absolute stability. Read sections 5.9, 6.4, 7.3, 7.6.1, and 8.4 in LeVeque. 

In the time remaining, we will discuss [IMEX temporal integrators](Lectures/IMEX.pdf). The IMEX RK schemes in these notes are based on the article by [Pareschi and Russo on "Implicit-explicit Runge-Kutta schemes and applications to hyperbolic systems with relaxation"](https://link.springer.com/article/10.1007/s10915-004-4636-4), which derives a (recommended!) scheme that combines (Strong Stability Preserving or SSP) RK3 for advection with an L-stable (Diagonally Implicit RK or DIRK) RK2 scheme for diffusion.

(3/14) No class, **spring break**!

### 7. (3/21) [Exponential Time Integrators](Lectures/ExponentialIntegrators.pdf) and (more advanced topic) [Spectral Deferred Correction](Lectures/SpectralDeferredCorrection.pdf)

[Exponential integrators](Lectures/ExponentialIntegrators.pdf) are covered briefly in section 11.6 of LeVeque. The original source of ETDRK schemes is the paper ["Exponential time differencing for stiff systems"](https://www.math.fsu.edu/%7Eokhanmoh/media/Cox,%20Matthews,%20JCP,%202002,%20Exponential%20Time%20Differencing%20for%20Stiff%20Systems.pdf) by Cox and Matthews. Another more recent article from the group of Nick Trefethen discusses a [4th order exponential integrator method](https://people.maths.ox.ac.uk/trefethen/fourth-order.pdf) (ETDRK4) for time stepping a system of ODEs in time. Here is a [pseudospectral code](https://cims.nyu.edu/%7Edonev/Teaching/PDE/Matlab/KdV.m) to solve the [KdV equation](https://en.wikipedia.org/wiki/Korteweg%E2%80%93de_Vries_equation) (u_t+u\*u_x+u_xxx=0) using ETDRK4 written by A. K. Kassam and L. N. Trefethen with some small changes by me. This code does something smart to avoid roundoff problems (catastrophic cancellation).

Spectral accuracy in time can be achieved by using the [Spectral Deferred Correction (SDC) Method](Lectures/SpectralDeferredCorrection.pdf); here is more information about [Gauss-Radau quadrature](https://mathworld.wolfram.com/RadauQuadrature.html). We will only cover this briefly to give the main idea, and those interested in the topic can use it for a final project. A review article that gives the complicated history of this class of methods is ["Deferred Correction Methods for Ordinary Differential Equations" by Ong & Spiteri](https://link.springer.com/article/10.1007/s10915-020-01235-8). Michael Minion and collaborators have used SDC for PDEs in a series of works. For example, for SDC with a pseudo-spectral discretization of (17) and discussion see this [paper by Layton and Minion](https://msp.org/camcos/2007/2-1/p01.xhtml), or for advection-diffusion see Section 5.4 in this [early paper by Minion](https://projecteuclid.org/journals/communications-in-mathematical-sciences/volume-1/issue-3/Semi-implicit-spectral-deferred-correction-methods-for-ordinary-differential-equations/cms/1250880097.pdf). Many pieces are required to make SDC efficient and effective for PDEs, for example, handling of stiff terms robustly benefits from the LU trick developed in the paper ["Faster SDC convergence on non-equidistant grids by DIRK sweeps" by M. Weiser](https://link.springer.com/article/10.1007/s10543-014-0540-y).

A recent paper ["On the Stability of Exponential Integrators for Non-Diffusive Equations" by Buvoli and Minion](https://arxiv.org/abs/2108.00185) has lots of possible topics for a final project. For applications of exponential integrators to more challenging PDEs more broadly (not just periodic and pseudospectral), see the article ["Implementation of parallel adaptive-Krylov exponential solvers for large scale stiff problems" by J. Loffeld and M. Tokman](http://dx.doi.org/10.1137/13094462X).

Another possible topic for a final project are pseudospectral methods for (nonlinear) wave equations, see for example the article ["A pseudospectral procedure for the solution of nonlinear wave equations with examples from free-surface flows"](https://epubs.siam.org/doi/abs/10.1137/S1064827597321532) by Milewski and Tabak (see also the paper ["The fidelity of exponential and IMEX integrators for wave turbulence" by Yang et al](https://doi.org/10.1016/j.jcp.2020.109992)).

### 8. (3/28, 4/4, 4/11) [Finite Difference Discretizations for Elliptic Equations](Lectures/FiniteDifference_Elliptic.pdf)

I will follow relatively closely the book of LeVeque but not necessarily in the same order and with some additional comments. Read Chapters 1 and 2 in LeVeque.

### 9. (4/18) [Finite Difference Methods for Parabolic Equations](Lectures/FiniteDifference_Parabolic.pdf)

I will follow relatively closely chapter 9 in the book of LeVeque.

### 10. (4/25, 5/2) [Finite Difference Methods for Hyperbolic Equations](Lectures/FiniteDifference_Hyperbolic.pdf) 

I will follow relatively closely chapter 10 in the book of LeVeque. Here is a [Maple script for the third-order upwind biased FD for advection](Lectures/ThirdOrderUpwind.pdf) ([Maple source](Lectures/ThirdOrderUpwind.mw)).

### 11. (5/9, optional) [Finite Element Method](Lectures/FEM.pdf)

I will discuss classical Finite Element Methods (FEM) for parabolic and elliptic problems, based on notes by Georg Stadler, themselves based on these [notes by Patrick E. Farell](https://people.maths.ox.ac.uk/farrellp/femvideos/notes.pdf). I will skip much of the theory and focus on some more practical aspects. As a brief background look first at these short [notes on interpolation in 2D/3D](Lectures/Interp2D.pdf).

If there is time, I will also briefly discuss the basic idea behind the [Discontinuous Galerkin (DEG) method for hyperbolic problems](Lectures/DG_Advection.pdf) based on lecture notes by Sandra May. This method is a combination of FV and FE methods and still under active development, so we will not go into any detail. While DEG also works for parabolic problems, whether there is any advantage to that is still an open area of research and I will not cover that.

An important aspect that we will not have time to cover are efficient linear solvers for the linear systems that arise in various grid-based FD/FV/FE methods, in particular for elliptic problems. While in 2D it is possible to use multifrontal direct solvers due to the abundance of memory on modern computers, for 3D iterative solvers based on algebraic or geometric **multigrid methods** are required; see these [lecture notes on geometric multigrid by William L. Briggs](http://www.math.ust.hk/%7Emawang/teaching/math532/mgtut.pdf). There are many existing libraries implementing such solvers.


## Self-study materials

These are topics that we will not cover in class but I have some lecture materials for already. Some of these are suited for a final project. Students interested in going into more depth can take the [Computational Methods for PDEs class](https://adonev.github.io/CompPDEs), taught by Aleks Donev and/or Georg Stadler.

### 1. [Spectral methods for elliptic PDEs in bounded domains](Lectures/SpectralBVPs.pdf)

We will briefly discuss (pseudo-spectral) methods for solving elliptic and by extension parabolic PDEs in non-periodic domains in one dimension. The basic idea is to use orthogonal polynomials (Chebyshev or Legendre) but the dilemma is in how to impose the PDE (weakly using Galerkin or strongly using collocation, or some other approach) and how to impose boundary conditions. What I will present is based on recent work by my PhD student Ondrej Maxian on [electrostatics](https://arxiv.org/abs/2101.07088).

You will also need background material from Numerical Methods I on orthogonal polynomials (Chebyshev or Legendre), including both interpolation and quadrature. A nice summary of the difference between type-1 and type-2 grids, which is a muddled topic in the literature, can be found in the paper ["The Chebyshev points of the first kind" by Kuan Xu](https://doi.org/10.1016/j.apnum.2015.12.002). Lots of numerical analysis tools built around Chebyshev polynomials are in the [Matlab chebfun library](https://www.chebfun.org/).

The standard collocation method using type-2 Chebyshev grid is described in the book ["Spectral Methods in Matlab" by Nick Trefethen](https://epubs.siam.org/doi/book/10.1137/1.9780898719598), which includes lots of [MATLAB codes](https://people.maths.ox.ac.uk/trefethen/spectral.html).

I will discuss both weak imposition in Galerkin methods and strong imposition using a spectral equivalent of the "ghost cell" technique. This is based (but slightly modified) from the approach described pedagogically in the paper ["Block Operators and Spectral Discretizations" by Aurentz and Trefethen](https://people.maths.ox.ac.uk/trefethen/blocks_final.pdf) based on the method proposed in the paper ["Rectangular spectral collocation" by Driscoll and N. Hale](https://doi.org/10.1093/imanum/dru062).

A state-of-the-art spectral solver for one dimensional BVPs with non-constant coefficients is described in the paper ["A fast and well-conditioned spectral method" by S. Olver and A. Townsend](https://epubs.siam.org/doi/abs/10.1137/120865458) and can form the basis of a final project. Note that this solver, like most non-Galerkin spectral methods, does not preserve the structure of Sturm-Louiville problems (e.g., the definiteness of the 2nd order operator).

For software/methods for solving evolution PDEs in bounded (but logically rectangular) 2D and 3D domains using orthogonal polynomial basis see the [Dedalus](https://dedalus-project.org/) package.

Note that FFT-based methods can be used to solve elliptic PDEs in irregular domains by using extention into a rectangular periodic domain. This can also be a topic of a final project. I suggest looking at the paper [The smooth forcing extension method by Qadeer and Griffith](https://doi.org/10.1016/j.jcp.2021.110390) for a simple yet accurate approach.

### 2. [Boundary Integral Methods](Lectures/BoundaryIntegralMethods.pdf)

In this brief lecture I will cover some basic ideas behind boundary integral methods; my lecture notes are pretty elementary and based primarily on two sources. These [notes by Alex Barnett](Lectures/BoundaryIntegral_Barnett.pdf) give the basic discretizations with some code snippets. These incomplete [notes by Mike O'Neil](https://cims.nyu.edu/%7Eoneil/courses/fa17-math2011/int_eq_notes_2017.pdf) give an introduction to single and double layer operators. If you have never studied electrostatics or forgot all about it, it would be very useful to quickly review these [notes on electrostatics](https://cims.nyu.edu/%7Eoneil/courses/sp19-math2840/electrostatics.pdf).

Note that efficiently computing quadratures with Green's function kernels in (log)linear time in the number of points requires using [fast multipole methods](https://math.nyu.edu/faculty/greengar/shortcourse_fmm.pdf) (in unbounded domains) or using the FFT (in periodic domains, in spectral Ewald splitting methods). More recently, methods based on low-rank compression are emerging as (algebraic) alternatives; see special topics course on randomized methods for linear algebra taught by Mike O'Neil and/or Jonathan Weare.

### 3. [Basic Finite Volume Methods](Lectures/BasicFVM.pdf)

We will discuss finite volume methods for advection-diffusion equations in one dimension, focusing on advection. Much of this material is in the books of LeVeque, but for a more self-contained reading see these [lecture notes from V. Springel and C.P. Dullemond](Lectures/SlopeLimiters_Notes.pdf) (you can also access freely their [full set of lectures](http://www.ita.uni-heidelberg.de/%7Edullemond/lectures/num_fluid_2012/)), which also contain material for subsequent lectures. 

This [Maple worksheet](Lectures/ThirdOrderUpwind.pdf) ([as Maple file](Lectures/ThirdOrderUpwind.mw)) shows that the 3rd-order upwind biased spatial discretization of advection is 3rd order only as a FV scheme for non-constant advection, but not when viewed as an FD scheme.

