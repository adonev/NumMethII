---
title: Assignments for Numerical Methods II by Aleks Donev (Spring 2023)
layout: default
---

## Homework instructions

Please submit solutions via NYU's class management system Brightspace as a self-contained PDF report that is organized with a discussion, figures, and results/answers, along with source codes (plain text please) as attachments. Please do not include codes in the PDF, attach them separately as a zip file or plain text .m or .py files. Jupiter notebooks with code will **not** be accepted (unless you hide all the code in the PDF and export it as a standalone text file); the intention is for you to practice scientific writing which does not usually involve codes (just code snippets when required).

### Logistics

1. Submit a stand-alone **self-contained** PDF file and your codes as plain text files or a **zip** archive.
2. Do not include top-level folders/subfolders, that is, when we unpack the archive it should give runnable code sources, not a complex directory hierarchy.
3. Submit the archive file as a solution via NYU Brightspace. Make sure to complete the submission as otherwise we cannot access the file. 
4. Late submissions will only be accepted if you send a request/justification to the instructor **at least two days** before the due date, except for medical reasons. Most requests will be granted unless there is a repeating pattern of late submissions.
5. If you use any external source, even Wikipedia, make sure you acknowledge it by citing it. Recall that you may discuss the problems with your colleagues but each student must do the actual programming and writeup independently.

### Organize your files 

1. Name files sensibly (e.g., not "A.m" or "script.m" but also not "Solution of Problem 1 by Me.m"). Include your name in the filename in the text of the PDF writeup.
2. In general, one should be able to grade without looking at all the codes. The reports should be mostly self-contained, e.g., the figures should be included in the writeup along with legends, explanations, calculations, etc. Do not include MATLAB codes in the writeup, only the results.
3. Package the files so that the codes can be run by us -- do not put all the sources in one long text file, for example. Also, we do not need your tex, lyx, Word, svn files etc., only a PDF of the final product. Please make it easy for us to find and examine the files quickly.

### Present your information effectively

1. Plot figures with thought and care! For example, errors should typically be plotted on a logarithmic scale, not linear, so you can see it going down instead of flat lines. The plots should have axes labels and be easy to understand at a glance.
2. A picture is worth a thousand words! Instead of large tables, or printouts of matrices, make a plot. Do not submit pages of numbers unless there is a really good reason -- it is not an effective way to present the information.
3. However, a picture by itself is not enough! You must write a concise explanation of the figure, especially what you learn from the figure (think of in scientific papers). 
4. If you do print things, to format the output nicely instead of printing large matrices. Also use format compact and other format commands to control how MATLAB prints things. 

## Homework assignments

Homeworks will often contain two parts, one that is required to submit and will be graded for points, and **optional** more advanced questions that only those students interested in going more in depth should do. There will be no extra points for the advanced parts, in order not to put any pressure on you to do them; do the extra stuff only if you have time and interest. They will usually be due on Tuesdays by class time since I will sometimes discuss solutions in class.

The assignments below will be edited as we go along the semester; the version attached below may be from previous iterations of this course.

### 1. (Due 5pm on 2/7) [Accuracy of Fourier Interpolation](Assignments/AssignmentFFT.pdf)

### 2. (Due 5pm on 2/21) [Pseudospectral spatial discretizations](Assignments/AssignmentPseudospectral.pdf)

==================NOT UPDATED FROM HERE============================

### 3. (Due ?) [ODEs for planetary motion](Assignments/AssignmentODE.pdf)

### 4. (Due ?) [Pseudospectral method for KdV](Assignments/AssignmentKdV.pdf)

### 5. (Due ?) [Elliptic and Parabolic PDEs](Assignments/AssignmentDiffusion.pdf)

## Final Project Ideas

Due ???

For the final projects, you have some freedom in selecting what you want to do. This would preferably be related to the subject of your Ph.D./masters research and be something you are interested in. The goal is to do something more "real-world" than the homeworks, or to learn a method we did not cover in class. If you are also taking the High Performance Computing (HPC) class, it is OK to use the same project for this class, but note that the goal is difference and for this class the focus is on the numerical analysis (testing convergence, order of accuracy, stability, robustness, etc.) and not just on efficiency. 
 
Most important is that you must carefully analyze and test the numerical accuracy of the codes using methods discussed in class. In particular, **projects without validations of the code and determination of order of accuracy and discussion of sources of error will be heavily penalized**. To be more specific, here are the things that you are expected to do in your final project and report: 

1. The project is **not about results** (it is a numerical analysis project, not a science project). It is of course great to get some results, especially for the presentation, but this is not the goal and even if you don't finish or manage to get final results that is fine.
2. The report should explain the numerical method you used in **sufficient detail** for someone else to be able to reproduce your results -- this is the standard for all scientific writing/papers.
3. You must **validate your code** (consistency). Remember that this cannot be validating against the code itself, i.e., it cannot be empirical convergence testing. Validation must be done against solutions obtained by analytical methods, manufactured solutions, or results obtained by another method (perhaps slower but should be more accurate).
4. You must **study the stability** (if appropriate for your code) of your method. If there is a time step size, what sets the limit. Does the problem behave well as you refine the grid or are you seeing some instabilities. Etc. Stability here is both a property of spatial and temporal discretizations. Empirical stability is OK but of course analytical explanations are best.
5. You must confirm an **order of convergence** and study the accuracy of the method (consistency+stability=convergence so you cannot do this until steps 3 and 4 are complete!).
6. You must discuss the **computational complexity** of the algorithm/code etc. What limits the scalability/efficiency of the code. How could you improve it if you had more time. What other methods could you have used and how would they compare.

Here are some possible projects that I am familiar with and could help you with. But please feel free to suggest your own:

### Chaotic PDEs in 1D and 2D

Use pseudospectral methods to solve the [Kuramoto–Sivashinsky equation](https://en.wikipedia.org/wiki/Kuramoto%E2%80%93Sivashinsky_equation) in one and higher dimensions. If time permits, use Krylov methods to implement the exponential integrators for non-periodic domains.

### Finite-Element Methods in 1D or 2D

Learn about the finite element method and solve an elliptic PDE with it, either writing your own code for a one-dimensional Sturm-Louville problem (in which case it would be great to compare to finite difference and maybe also spectral methods, see below), or using a package to solve a two-dimensional non-constant coefficient elliptic problem.

### Spectral Methods for BVPs in 1D

Learn about solving boundary value problems (ODEs) in 1D using orthogonal polynomials such as Chebyhev polynomials. Start with the book of Trefethen on Spectral Methods, but then switch to one (or try both if you can!) of the two improved methods described in this article by Leslie Greengard on an [integral equation reformulation](https://epubs.siam.org/doi/abs/10.1137/0728057) (this article has an important typo so talk to me if you are trying to implement this), or this article by Nick Trefethen's group on [rectangular matrix discretizations](https://epubs.siam.org/doi/abs/10.1137/16M1065975).

### Space-Time Methods for Advection-Diffusion Equations

Learn how to efficiently combine space-time methods like Lax-Wendroff or Fromm's method for the advection equation with implicit diffusion to second-order accuracy. You can refer to [Lecture 7 from my CFD class](https://cims.nyu.edu/%7Edonev/Teaching/CFD/Lectures.html) for help. More advanced students can also add a limiter in 1D or try to implement a 2D solver.

### Finite-Volume Methods for the KdV Equation

In Homework 4 we solved the KdV equation, a prime example of a nonlinear hyperbolic PDE, using pseudospectral methods. Develop now a finite-volume method to solve this conservation law in periodic BCs, and compare to the pseudo-spectral method in terms of accuracy and robustness.

### Finite Volume Methods for Nonlinear Hyperbolic Equations

Learn about finite volume Godunov-type methods for nonlinear hyperbolic systems with shock (discontinous) solutions and solve some nontrivial equation such as the shallow water equations. A good but perhaps overly detailed source is the book "[Finite Volume Methods for Hyperbolic Problems](http://depts.washington.edu/clawpack/book.html)" by Randall J. Leveque.

### Integral Equations for Conformal Maps

Implement a solver for the Kerzman-Stein integral equation used to compute conformal maps based on this [article Rokhlin and O'Donnell](https://epubs.siam.org/doi/pdf/10.1137/0910031).  Another (concise) description is in Section 4 of [paper by Prof. Mike O'Neil (Courant)](https://www.sciencedirect.com/science/article/pii/S0021999113001721), whom you can ask for assistance if needed.

### Integral Equations for Poisson in 2D

You can also implement an integral equation method for solving the Poisson equation in 2d in some nontrivial domain or with obstacles (e.g. put many disjoint circles as holes in a domain), and compare first and second kind discretizations. These [notes by Alex Barnett](Lectures/BoundaryIntegral_Barnett.pdf) give the basic discretizations with some code snippets.

A more advanced step would to learn how to efficiently compute the trapezoidal quadrature in (log)linear time in the number of points using [fast multipole methods](https://math.nyu.edu/faculty/greengar/shortcourse_fmm.pdf) (in unbounded domains, using [existing codes](https://cims.nyu.edu/cmcl/fmm2dlib/fmm2dlib.html)) or using the FFT in periodic domains (with Ewald splitting).

### Reduced-Order Modeling

Learn about POD methods for constructing reduced-order models of advection-diffusion-type equations (1D is OK) from the notes "[An introduction to the POD Galerkin method for fluid flows with analytical examples and MATLAB source codes](http://berndnoack.com/publications/Luchtenburg2009romfc.PDF)". Take a diffusive equation (heat, or advection-diffusion solved with your favorite discretization either in 1 or 2D) and construct a low rank basis using the SVD to construct the POD basis. Compare how many basis modes you need to capture 99.9% of the energy for different parameters in the equation. You can talk to Profs. Georg Stadler or Benjamin Peherstorfer for guidance.

### Libraries

Using high-performance libraries developed by experts is welcome and in fact encouraged, as long as you understand and document what the library did for you (e.g., what algorithm was used, what linear solver was used, etc.). Here are some examples of libraries/tools that you may consider learning and using:
* [Dedalus](https://dedalus-project.org/) is a library of pseudo-spectral solvers.
* [FEniCSx](https://fenicsproject.org/) is an easy-to-use yet powerful framework for finite-element based PDE solvers. The book "Introduction to Automated Modeling with FEniCs" by Ridgway Scott gives a lot of examples you can build on.
* [OpenFOAM](https://www.openfoam.com/) is a commercial but free library/package for finite-volume based PDE solvers
* [chebfun](https://www.chebfun.org/) is a library of numerical analysis tools built around Chebyshev polynomials.
* [EPIC](https://faculty.ucmerced.edu/mtokman/#software) is a library of exponential time integrators.
* [fiNUFFT](https://finufft.readthedocs.io/en/latest/) is a library for non-uniform FFTs if you need that as part of your project.
* [FMM3D](https://fmm3d.readthedocs.io/en/latest/) is a 3D Fast Multipole Method library for Poisson and Helmholtz kernels, which can be useful if you want to do boundary integral methods.

