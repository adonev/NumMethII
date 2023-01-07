---
title: Numerical Methods II at NYU
layout: default
---
## Numerical Methods II (MATH-GA.2020-001 / CSCI-GA.2421-001)

his course (3pts) will cover fundamental methods that are essential for the numerical solution of differential equations. It is intended for students familiar with ODE and PDE and interested in numerical computing; computer programming assignments in MATLAB/Python will form an essential part of the course. The course will introduce students to numerical methods for (approximately in this order): 
1. The Fast Fourier Transform and spectral methods for elliptic PDEs
2. Finite difference and finite element and integral equation methods for elliptic partial differential equations (Poisson eq.) 
3. Ordinary differential equations, explicit and implicit Runge-Kutta and multistep methods, convergence and stability
4. Finite difference, finite element, and (pseudo)spectral methods for parabolic (diffusion/heat eq.) partial differential equations 
5. Finite volume methods for hyperbolic (advection and wave eqs.) partial differential equations. 
For more information consult the webpage for previous iterations of [this class taught by A. Donev](https://cims.nyu.edu/~donev/Teaching/NMII). Communication/grading will be handled via NYU Brightspace.

### Instructor

**[Aleksandar Donev](http://cims.nyu.edu/%7Edonev)**, 1016 Warren Weaver Hall, (Email)[mailto:donev@courant.nyu.edu]. 
Office hours: **3 to 5 pm Wednesdays** or by [appointment](mailto:donev@cims.nyu.edu) 
 
**Grader/TA**: Mariya Savinov (mas10009@nyu).
Office hours TBD.

### Reading Materials

The primary required textbook for this class is: 

1. "[Finite Difference Methods for Ordinary and Partial Differential Equations](https://epubs.siam.org/doi/book/10.1137/1.9780898717839)" by Randy **LeVeque**. This textbook is now available freely to you in [PDF format](https://epubs.siam.org/doi/book/10.1137/1.9780898717839), and [Matlab and latex files](https://staff.washington.edu/rjl/fdmbook/) are available from the author's webpage. Everyone ready to take this course should be able to follow this textbook without a problem. 

However, this does not cover spectral methods/representation. There is no great book on this that I know of, but the closest is:

2. "[Spectral Methods in Matlab](https://epubs.siam.org/doi/book/10.1137/1.9780898719598)" by Nick **Trefethen**, which includes lots of [MATLAB codes](https://people.maths.ox.ac.uk/trefethen/spectral.html), and focuses on Fourier and Chebyshev representations for elliptic PDEs.

Advanced students can use as a very good resource this book available to you in PDF format:

3. Hundsdorfer, W., & Verwer, J.G. (2003). Springer Series in Computational Mathematics \[Series, Vol. 33\], [Numerical Solution of Time-Dependent Advection-Diffusion-Reaction Equations](http://link.springer.com/book/10.1007/978-3-662-09017-6), New York, NY: Springer-Verlag.

### Prerequisites

This course **requires Numerical Methods I** or equivalent graduate course in numerical analysis (as approved by instructor). In particular I will assume you are comfortable with the [topics in the NM-I as class taught by Michael Overton](NM-I-Syllabus-Overton.pdf). If you did not get at least B in NM-I you will have a rather hard time with this course! Things I will expect you to be **very familiar / comfortable** with include: 
- numerical linear algebra (dense factorization, sparse systems, eigenvalue methods)
- iterative solvers for linear systems
- nonlinear systems (Newton' method in many dimensions)
- interpolation, including splines and orthogonal polynomials
- integration / quadrature including Gauss quadrature
- undergraduate or graduate course in ODEs
- undergraduate or graduate course covering basic hyperbolic (advection, wave), parabolic (heat/diffusion), and elliptic (Laplace/Poisson) PDEs, including Fourier series/transform methods (separation of variables)

### Assignments and grading

There will be several computational assignments / exercises during the semester, each of which will involve coding, analyzing/plotting results, and preparing a typeset report (preferably in LaTex). [Academic integrity policies](http://www.nyu.edu/about/policies-guidelines-compliance/policies-and-guidelines/academic-integrity-for-students-at-nyu.html) will be strictly enforced for homework assignments and exams. In particular, **group work is not allowed** and will be treated as a violation of academic integrity. You may discuss strategies to solve the problems with peers, but every line of code and everything in the solution (including figures) for each homework must be 100% yours. Allowing others to copy code or solutions from you is considered cheating. 
 
Each student will be required to do either a _take home final_ similar to the homeworks, **or** a _computational project_ on a subject of choice, due the day the final exam is scheduled for. Only students with instructor approval will be allowed to do a project, and this approval will be based on your proposal for the project and your performance in the homeworks. The grade will be based on the homeworks (50%) and the project (50%). Assuming the total possible number of points (excluding extra credit) is 100, the grade scale will be based on the weights used in computing your GPA: 

- \>92.5    = A
- 87.5-92.5 = A-
- 80.0-87.5 = B+
- 72.5-80.0 = B
- 65.0-72.5 = B-
- 57.5-65.0 = C+
- 50.0-57.5 = C
- 42.5-50.0 = C- 
- \<42.5       = F

As a first assignment, please submit the answers to this questionnaire [via email](mailto:donev@courant.nyu.edu) as soon as possible: 

1. Your name (if you have a pseudonym, send me that and your official name), degree you are working on (if any) and class/year, and thesis advisor and topic if any.
2. List your previous academic degrees or relevant educational experience.
3. Explain in words (e.g., relevant courses, prior research) your background in numerical analysis. 
4. Why did you choose this course, and which of the topics listed in the course description interest you most (in particular, do you know what subject you would like to present on in class)?
5. What is your programming experience (list programming languages with proficiency level)?

