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

==================NOT UPDATED FROM HERE============================

### 8. (3/28) [Finite Difference Discretizations](Lectures/FD_Elliptic_1D.pdf) and (3/26 and 4/2) their [Convergence and Stability for Elliptic BVPs](Lectures/FD_Elliptic_Convergence.pdf)

I will follow relatively closely the book of LeVeque but not necessarily in the same order and with some additional comments. Read Chapters 1 and 2 in LeVeque.

### 9. (4/4) [Finite Difference Methods for Parabolic Equations](Lectures/FD_Parabolic.pdf) 

I will follow relatively closely chapter 9 in the book of LeVeque.

### 10. (4/11) [Finite Difference Methods for Hyperbolic Equations](Lectures/FD_Hyperbolic.pdf) 

I will follow relatively closely chapter 10 in the book of LeVeque.

### 11. (4/18) [Finite Volume Methods for Advection-Diffusion Equations](Lectures/FV_Hyperbolic.pdf) 

These lecture notes are an assorted selection from lecture notes in my [class on Computational Fluid Dynamics.](../CFD/Lectures.html) The part about modified equations is common to finite-difference and finite-volume methods and is covered in section 10.8 in the book of LeVeque, but also look at section 10.8 and in particular [Fig. 10.4 in LeVeque](Lectures/Artificial.png). The semi-Lagrangian derivation of Lax-Wendroff is similar to what is done for upwinding in section 10.6 in Leveque.

We will also discuss simple Godunov schemes as a way to obtain finite-volume methods via reconstruction. These ideas are summarized nicely in sections 4.1 to 4.3 these [lecture notes from V. Springel and C.P. Dullemond](../CFD/Lectures/SlopeLimiters_Notes.pdf) (see their [full set of lectures](http://www.ita.uni-heidelberg.de/%7Edullemond/lectures/num_fluid_2012/)), but the most detailed source is chapters 6 and 10 in the book "[Finite Volume Methods for Hyperbolic Problems](http://depts.washington.edu/clawpack/book.html)" by Randall J. Leveque.

These [lecture notes on FV Methods for Conservation Laws](../CFD/Lectures/ConservationLaws.pdf) briefly discuss how to generalize the methods we discussed in detail for advection to more general nonlinear hyperbolic equations coming from conservation laws.

### 12. (4/25 and 5/2) [Finite Element Methods](Lectures/FEM_Elliptic.pdf)

We will cover [FEM methods for elliptic PDEs](Lectures/FEM_Elliptic.pdf) based mostly on chapter 9 in the book of Iserles. I will also use chapter 0 of the [FEM textbook by Susanne Brenner](https://link.springer.com/book/10.1007/978-0-387-75934-0), available freely to you. This book covers also the analysis aspects that are inherent to FEM for elliptic problems, namely Sobolev spaces and variational formulations of elliptic PDEs. Here are some illustrations of [FEM grids/elements in higher dimensions](Lectures/FEM-basis-2D.pdf), including a [quadratic element basis function](Lectures/FEM_quadratic_basis_triangle.png), and [triangulations of an L-shaped region](Lectures/FEM_2D_L_shape_adaptive.png) used to solve Poisson problems.

Here is some brief notes on [FEM methods for the advection equation](Lectures/FEM_Advection.pdf) (same ideas work for the diffusion equation also), taken from my CFD class.

### 13. (5/9) [Multigrid Methods](Lectures/MultigridTutorial_Briggs.pdf)

I will spend a considerable fraction of the first class going through the solution of HW5. You will see in this homework that one can get 2nd order accuracy for parabolic PDEs even when there is an apparent inconsistency (i.e., O(1) error) at the boundary points. This is explained in these lecture notes from my CFD class on [Boundary Conditions](https://cims.nyu.edu/%7Edonev/Teaching/CFD/Lectures/BoundaryConditions.pdf), which are based on section I.5 in the book [Numerical Solution of Time-Dependent Advection-Diffusion-Reaction Equations](http://link.springer.com/book/10.1007/978-3-662-09017-6), available freely to you in PDF format. The elliptic case is discussed in 2.12 in LeVeque.

For multigrid, I will use these excellent [lecture notes by William Briggs](Lectures/MultigridTutorial_Briggs.pdf) (his [textbook on multigrid](http://bookstore.siam.org/ot72/) is a classic) to discuss iterative methods to solve the types of large-scale linear systems that arise from discretizations of parabolic/elliptic PDEs. I will focus on geometric multigrid on regular grids; for unstructred FEM grids one can use [algebraic multigrid techniques](https://www.osti.gov/servlets/purl/897960).

### 14. (Optional, no lecture) [Boundary Integral Methods](Lectures/BoundaryIntegralMethods.pdf)

My lecture notes are pretty elementary and based primarily on two sources. These [notes by Alex Barnett](Lectures/BoundaryIntegral_Barnett.pdf) give the basic discretizations with some code snippets. These incomplete [notes by Mike O'Neil](https://cims.nyu.edu/%7Eoneil/courses/fa17-math2011/int_eq_notes_2017.pdf) give an introduction to single and double layer operators. If you have never studied electrostatics or forgot all about it, it would be very useful to quickly review these [notes on electrostatics](https://cims.nyu.edu/%7Eoneil/courses/sp19-math2840/electrostatics.pdf).

More advanced students can learn how to efficiently compute the trapezoidal quadrature in (log)linear time in the number of points using [fast multipole methods](https://math.nyu.edu/faculty/greengar/shortcourse_fmm.pdf) (in unbounded domains, using [existing Courant codes](https://cims.nyu.edu/cmcl/fmm2dlib/fmm2dlib.html)) or using the FFT in periodic domains (with Ewald splitting).

