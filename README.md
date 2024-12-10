---
Name: Shicheng Wang
Topic: [26.md]
Title: Basis function options/choices, pros and cons of each. Include examples. Include orthogonal polynomials of multiple flavors.
----
## Table of Contents
- [Overview](#Overview)
- [Background](#Background)
- [Polynomial Basis](#polynomial-basis)
- [Orthogonal Polynomials](#orthogonal-polynomials)
- [Trigonometric Basis](#trigonometric-basis)
- [Radial Basis Functions](#radial-basis-functions)
- [Wavelets](#wavelets)
- [Comparison Table](#comparison-table)
- [References](#references)

## Overview
Basis functions are essential tools in mathematics, numerical analysis, and data approximation, serving as the foundation for representing complex functions in simpler, more manageable forms. Different types of basis functions are used depending on the nature of the problem and the data involved. Polynomial basis functions, such as **$( 1, x, x^2, \dots \)$**, are simple to implement but may suffer from numerical instability, especially with high degrees. Orthogonal polynomials, like Legendre, Chebyshev, Hermite, and Laguerre polynomials, provide improved stability and error minimization but are often confined to specific domains or weight functions. Trigonometric basis functions, such as sine and cosine, excel in representing periodic functions but encounter issues like Gibbs phenomenon near discontinuities. Radial basis functions, such as Gaussian kernels, are flexible and well-suited for scattered or high-dimensional data but can become computationally expensive for large datasets. Wavelets are ideal for localized and multi-resolution analysis, effectively capturing both time and frequency information, though their implementation can be complex. Selecting the appropriate basis function involves balancing the function’s properties, numerical stability, and computational efficiency to best meet the problem’s requirements.


## Background
Basis functions are simple building blocks used to represent more complex functions. The idea comes from linear algebra, where any vector can be written as a combination of basis vectors. Similarly, in function spaces, we can approximate a complicated function using a combination of simpler basis functions. This is very useful in many fields, such as solving equations, approximating curves, and analyzing data. By choosing the right set of basis functions, difficult problems become easier to solve.

Polynomials were one of the first types of basis functions because they are easy to work with for calculations like addition, integration, and differentiation. However, when using high-degree polynomials, the results can become unstable. For example, Runge's phenomenon. To fix this, special types of polynomials called **orthogonal polynomials** (e.g., Legendre and Chebyshev) were developed to minimize errors. For periodic functions, trigonometric functions like sine and cosine work very well. Over time, more advanced basis functions, such as radial basis functions for scattered data and wavelets for localized signals, were created to handle a wider range of problems.




