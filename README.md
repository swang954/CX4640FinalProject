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
Basis functions are fundamental tools in mathematics and engineering, used to approximate complex functions with simpler components. The idea comes from the concept of **linear combinations** in linear algebra, where any vector can be expressed as a sum of basis vectors. In function spaces, we use basis functions to break down a complicated function into smaller, more manageable parts. By combining these basis functions with coefficients, we can approximate curves, solve equations, and analyze data. This method is widely applied in areas like interpolation, machine learning, signal processing, and solving differential equations.

The simplest and most common basis functions are **polynomials**, such as $\( 1, x, x^2, \dots \)$, which are easy to calculate, integrate, and differentiate. For smooth and well-behaved functions, polynomial basis functions provide an effective approximation. However, when using higher-degree polynomials, they can become unstable and produce large oscillations, particularly near the edges of an interval. This issue is known as **Runge's phenomenon**, and it highlights the need for better basis function choices when working with complex data or functions.

To address these challenges, more advanced basis functions have been developed over time. **Orthogonal polynomials**, such as Legendre, Chebyshev, and Hermite polynomials, minimize errors and improve stability by satisfying specific mathematical properties. For periodic functions, **trigonometric basis functions**, like sine and cosine, are highly effective, as seen in Fourier series. Modern techniques, such as **radial basis functions** for scattered data and **wavelets** for localized signals, allow for more flexibility and accuracy when approximating functions in different applications. These advancements make basis functions essential tools for solving a wide range of problems in science, engineering, and data analysis.



## Polynomial Basis
Polynomial basis functions are one of the simplest and most widely used types of basis functions. They take the form $\( 1, x, x^2, x^3, \dots \)$, where each term is a power of $\ x\$. These basis functions are commonly used because they are easy to calculate, integrate, and differentiate, making them useful in a variety of applications such as curve fitting, interpolation, and Taylor series expansions. By combining these functions with coefficients, we can approximate smooth functions or model data. For example, a quadratic polynomial basis would include the terms $\ 1 \,\ x\, and  \ x^2\ $, which can approximate a parabolic curve.

However, polynomial basis functions have limitations. When high-degree polynomials are used to approximate a function, they can become unstable, leading to large oscillations, especially near the edges of the interval. This problem is known as **Runge's phenomenon**. For this reason, simpler or lower-degree polynomials are often preferred, or special techniques like orthogonal polynomials (e.g., Legendre or Chebyshev polynomials) are used to minimize errors. Despite these challenges, polynomial basis functions remain fundamental in mathematics due to their simplicity and flexibility in solving many problems.

Suppose we want to approximate a simple function $\ f(x) = 3x^2 + 2x + 5 \$ using a polynomial basis. Here, the polynomial basis functions are:

$\[
\phi_0(x) = 1, \quad \phi_1(x) = x, \quad \phi_2(x) = x^2.
\]$

The function $\( f(x) \)$ can then be written as a **linear combination** of these basis functions with coefficients $\( c_0 = 5 \), \( c_1 = 2 \), and \( c_2 = 3 \)$:

$\[
f(x) = c_0 \cdot \phi_0(x) + c_1 \cdot \phi_1(x) + c_2 \cdot \phi_2(x) = 5 \cdot 1 + 2 \cdot x + 3 \cdot x^2.
\]$

This example demonstrates how polynomials of increasing degree can be combined to approximate or represent functions. The coefficients $\ c_0, c_1, \$ and $\ c_2 \$ determine the contribution of each basis function.


