---
Name: Shicheng Wang
Topic: [26]
Title: Basis function options/choices, pros and cons of each. Include examples. Include orthogonal polynomials of multiple flavors.
----
## Table of Contents
- [Overview](#Overview)
- [Background](#Background)
- [Polynomial Basis](#polynomial-basis)
- [Orthogonal Polynomials](#orthogonal-polynomials)
- [Trigonometric Basis](#trigonometric-basis)
- [References](#references)

## Overview
Basis functions are essential tools in mathematics, numerical analysis, and data approximation, serving as the foundation for representing complex functions in simpler, more manageable forms. Different basis functions are used depending on the nature of the problem and the data involved. 

Polynomial basis functions are simple to implement but may suffer from numerical instability, especially with high degrees. Orthogonal polynomials, like Legendre, Chebyshev, Hermite, and Laguerre polynomials, provide improved stability and error minimization but are often confined to specific domains or weight functions. 

Trigonometric basis functions, such as sine and cosine, excel at representing periodic functions but may encounter issues like the Gibbs phenomenon near discontinuities. Radial basis functions, like Gaussian kernels, are flexible and particularly well-suited for scattered or high-dimensional data, though they can become computationally expensive with large datasets. 

Selecting the appropriate basis function involves balancing the function’s properties, numerical stability, and computational efficiency to best meet the problem’s requirements. Basis functions are essential tools in mathematics, numerical analysis, and data approximation. They serve as the foundation for representing complex functions in simpler, more manageable forms. The choice of basis function depends on the specific nature of the problem and the data involved.

## Background
The basis functions comes from the concept of linear combinations in linear algebra, where any vector can be expressed as a sum of basis vectors. In function spaces, we use basis functions to break down a complicated function into smaller, more manageable parts. By combining these basis functions with coefficients, we can approximate curves, solve equations, and analyze data. This method is widely applied in areas like interpolation, machine learning, signal processing, and solving differential equations.

The simplest and most common basis functions are **polynomials**, which are easy to calculate, integrate, and differentiate. For smooth and well-behaved functions, polynomial basis functions provide an effective approximation. However, when using higher-degree polynomials, they can become unstable and produce large oscillations, particularly near the edges of an interval. This issue is known as **Runge's phenomenon**, and it highlights the need for better basis function choices when working with complex data or functions.

To address these challenges, more advanced basis functions have been developed over time. **Orthogonal polynomials**, such as Legendre, Chebyshev, and Hermite polynomials, minimize errors and improve stability by satisfying specific mathematical properties. For periodic functions, trigonometric basis functions, like sine and cosine, are highly effective, as seen in Fourier series. Modern techniques, such as radial basis functions for scattered data and wavelets for localized signals, allow for more flexibility and accuracy when approximating functions in different applications. These advancements make basis functions essential tools for solving a wide range of problems in science, engineering, and data analysis.



## Polynomial Basis
Polynomial basis functions are one of the simplest and most widely used types of basis functions. They take the form $\( 1, x, x^2, x^3, \dots \)$, where each term is a power of $\ x\$. These basis functions are commonly used because they are easy to calculate, integrate, and differentiate, making them useful in a variety of applications such as curve fitting, interpolation, and Taylor series expansions. By combining these functions with coefficients, we can approximate smooth functions or model data. For example, a quadratic polynomial basis would include the terms $\ 1 \,\ x\, and  \ x^2\ $, which can approximate a parabolic curve.

However, polynomial basis functions have limitations. When high-degree polynomials are used to approximate a function, they can become unstable, leading to large oscillations, especially near the edges of the interval. This problem is known as **Runge's phenomenon**. For this reason, simpler or lower-degree polynomials are often preferred, or special techniques like orthogonal polynomials (e.g., Legendre or Chebyshev polynomials) are used to minimize errors. Despite these challenges, polynomial basis functions remain fundamental in mathematics due to their simplicity and flexibility in solving many problems.

### Example

Suppose we want to approximate a simple function $$\ f(x) = 3x^2 + 2x + 5 \ $$ using a polynomial basis. 

The polynomial basis functions are:

$$\
\phi_0(x) = 1, \quad \phi_1(x) = x, \quad \phi_2(x) = x^2.
\$$

The function $$\ f(x) \$$ can then be written as a linear combination of these basis functions with coefficients $$\ c_0 = 5 \, \ c_1 = 2 \, and \ c_2 = 3 \$$:

$$\
f(x) = c_0 \cdot \phi_0(x) + c_1 \cdot \phi_1(x) + c_2 \cdot \phi_2(x) = 5 \cdot 1 + 2 \cdot x + 3 \cdot x^2.
\$$

This example demonstrates how polynomials of increasing degree can be combined to approximate or represent functions. The coefficients $$\ c_0, \ c_1\,  and \ c_2 \$$ determine the contribution of each basis function.

## Orthogonal Polynomials
Orthogonal polynomials are a special class of polynomials that are mutually orthogonal with respect to a given weight function over a specific interval. Two polynomials $$\ P_m(x) \ and \ P_n(x) \$$ are considered orthogonal if their weighted inner product equals zero, that is:

$$\
\int_a^b P_m(x) P_n(x) w(x) \, dx = 0 \quad \text{for} \ m \neq n,
\$$

where $$\ w(x) \$$ is a weight function defined on the interval $$\[a, b]\$$. This orthogonality property makes these polynomials highly useful in numerical methods, such as approximation theory, solving differential equations, and performing Gaussian quadrature. Each type of orthogonal polynomial is associated with a specific weight function and domain.

Some of the most well-known families of orthogonal polynomials include **Legendre polynomials**, **Chebyshev polynomials**, and **Hermite polynomials**. Legendre polynomials are defined on the interval $$\[-1, 1]\$$ with a uniform weight function $$\ w(x) = 1 \$$. They are widely used in solving boundary value problems and approximating smooth functions. Chebyshev polynomials, on the other hand, are defined with a weight function $$\ w(x) = (1 - x^2)^{-1/2} \$$ and are effective in minimizing errors in polynomial approximations, particularly for interpolation. Hermite polynomials are suited for problems involving Gaussian distributions, while Laguerre polynomials are used on semi-infinite intervals $$\[0, \infty)\$$ in applications like quantum mechanics.

The orthogonality property of these polynomials provides several advantages. For example, orthogonal polynomials simplify function approximation by ensuring minimal error with respect to the weight function. In numerical integration, Gaussian quadrature methods leverage orthogonal polynomials to achieve highly accurate approximations with fewer points. Additionally, they reduce numerical instability compared to standard polynomials, which is particularly important when approximating functions with higher degrees. Overall, orthogonal polynomials are powerful tools for solving complex mathematical problems efficiently and accurately.

### Legendre polynomials

Legendre polynomials are a family of orthogonal polynomials defined on the interval $$\ [-1, 1]\$$ with a weight function $$\ w(x) = 1 \$$. They are widely used in mathematics and physics, particularly for solving boundary value problems, approximating smooth functions, and employing spectral methods to find numerical solutions for differential equations. Legendre polynomials are denoted as $$\ P_n(x)\$$, where $$\ n\$$ represents the degree of the polynomial. These polynomials satisfy the **orthogonality condition**:

$$\
\int_{-1}^1 P_m(x) P_n(x) \, dx = 0 \quad \text{for} \ m \neq n.
\$$

The first few Legendre polynomials are: $$\ P_0(x) = 1 \, \ P_1(x) = x \, and \ P_2(x) = \frac{1}{2}(3x^2 - 1) \$$. They are generated using **Rodrigues' formula**:

$$\
P_n(x) = \frac{1}{2^n n!} \frac{d^n}{dx^n} \left[ (x^2 - 1)^n \right].
\$$

### Example

Consider approximating a function $$\ f(x) = x^2 \$$ on the interval $$\[-1, 1]\$$ using Legendre polynomials. We can express $$\ f(x) \$$ as a linear combination of Legendre polynomials $$\ P_0(x) \, \ P_1(x) \, and \ P_2(x) \$$. Since $$\ P_2(x) = \frac{1}{2}(3x^2 - 1) \$$, we observe that $$\ f(x) = x^2 \$$ can be written as:

$$\
f(x) = \frac{2}{3} P_2(x) + \frac{1}{3} P_0(x).
\$$


This example demonstrates how Legendre polynomials can efficiently approximate functions. The orthogonality property makes it easy to compute the expansion coefficients, and the resulting approximation minimizes errors across the given interval.

### Pros:

Legendre polynomials are orthogonal over the interval $$\[-1, 1]\$$ with a constant weight function $$\ w(x) = 1 \$$, which simplifies computations for function approximations. Their orthogonality reduces numerical errors compared to using standard polynomial bases, particularly for higher-degree approximations. Additionally, these polynomials are well-suited for approximating smooth functions over finite intervals, as they minimize the approximation error in a least-squares sense.

### Cons:

Legendre polynomials are defined specifically on the interval $$\[-1, 1]\$$, which necessitates transformations to apply them to other intervals. They have difficulty approximating functions that exhibit sharp discontinuities or rapid oscillations. Additionally, high-degree interpolations using equally spaced points can still experience oscillations, although these are generally less severe than those encountered with standard polynomials.

## Chebyshev polynomials
Chebyshev polynomials, denoted as $$\ T_n(x) \$$, are a family of orthogonal polynomials defined on the interval $$\[-1, 1]\$$ with the weight function $$\ w(x) = \frac{1}{\sqrt{1 - x^2}} \$$. These polynomials are significant in numerical analysis and approximation theory due to their unique properties. Chebyshev polynomials can be generated using a recurrence relation:

$$\
T_0(x) = 1, \quad T_1(x) = x, \quad T_{n+1}(x) = 2xT_n(x) - T_{n-1}(x).
\$$

Alternatively, they can be expressed in trigonometric form as:

$$\
T_n(x) = \cos\left( n \cdot \arccos(x) \right),
\$$

which reveals their oscillatory nature. The first few Chebyshev polynomials are $$\ T_0(x) = 1 \, \ T_1(x) = x \, \ T_2(x) = 2x^2 - 1 \, \ T_3(x) = 4x^3 - 3x \, and \ T_4(x) = 8x^4 - 8x^2 + 1 \.$$ The roots of $$\ T_n(x) \$$, which are symmetrically distributed in the interval $$\ [-1, 1]\$$, are given by:

$$\
x_k = \cos\left( \frac{2k - 1}{2n} \pi \right), \quad k = 1, 2, \dots, n.
\$$

Chebyshev polynomials have several key properties that make them particularly suitable for numerical methods. They are orthogonal to the weight function $$\ w(x) = \frac{1}{\sqrt{1 - x^2}} \$$, which ensures stability and minimizes errors when approximating functions. Additionally, Chebyshev polynomials have the **minimax property**, meaning they minimize the maximum error in approximating a function compared to other polynomials of the same degree.

Chebyshev polynomials are widely used in polynomial interpolation, spectral methods, and numerical integration. For interpolation, the roots of Chebyshev polynomials, known as **Chebyshev nodes**, are often utilized to decrease interpolation errors and enhance accuracy. In numerical integration, Chebyshev polynomials serve as the basis for **Gauss-Chebyshev quadrature**, which approximates integrals that involve the weight function $$\ w(x) = \frac{1}{\sqrt{1 - x^2}} \$$. Their trigonometric form also links them to the Fourier series, allowing for efficient approximations of smooth functions through Chebyshev expansions.

### Example  

Suppose we want to approximate the function $$\ f(x) = \frac{1}{1 + 25x^2} \$$ on the interval $$\[-1, 1]\$$. Using Chebyshev polynomials as the basis functions reduces the large oscillations that occur with standard polynomial interpolation. The Chebyshev nodes, defined as:

$$\
x_k = \cos\left( \frac{(2k + 1)\pi}{2n + 2} \right), \quad k = 0, 1, \dots, n,
\$$

are chosen to ensure the error is minimized. By constructing an interpolation polynomial using these nodes and Chebyshev polynomials $$\ T_n(x) \$$, the resulting approximation is stable and accurate, even for higher degrees. This property makes Chebyshev polynomials a powerful tool for approximating functions with complex behaviors.

### Pros:

Chebyshev polynomials effectively minimize oscillations near the edges of the interval $$\[-1, 1]\$$, a common issue in polynomial interpolation with equally spaced nodes. These polynomials are designed to minimize the maximum error in polynomial approximations, making them the best choice for approximating a function in the uniform norm. They are orthogonal with respect to the weight function $$\ w(x) = \frac{1}{\sqrt{1 - x^2}} \$$ on the interval $$\[-1, 1]\$$, which contributes to the numerical stability of these approximations and helps to reduce computational errors. When combined with Chebyshev nodes, Chebyshev polynomials enable highly accurate polynomial interpolation and spectral methods using fewer points.


### Cons:

Like other orthogonal polynomials, Chebyshev polynomials are not very effective at approximating functions that have discontinuities or sharp jumps. The trigonometric form $$\ T_n(x) = \cos(n \cdot \arccos(x)) \$$ can present computational challenges when evaluating Chebyshev polynomials for very large values of $$\ n \$$. Additionally, when applied to non-standard domains or with non-uniform weights, extra preprocessing steps may be required to appropriately adapt the Chebyshev polynomials.

## Hermite Polynomials
Hermite polynomials, denoted as $$\ H_n(x) \$$, are a family of orthogonal polynomials defined on the infinite interval $$\ (-\infty, \infty) \$$ with the weight function $$\ w(x) = e^{-x^2} \$$. They are widely used in physics, particularly in quantum mechanics for solving the Schrödinger equation for the quantum harmonic oscillator, and in statistics for applications involving Gaussian distributions. Hermite polynomials satisfy the orthogonality condition:

$$\
\int_{-\infty}^\infty H_m(x) H_n(x) e^{-x^2} \, dx = 0 \quad \text{for} \, m \neq n,
\$$

ensuring their usefulness in approximating functions weighted by Gaussian distributions. Hermite polynomials can be generated using the **recurrence relation**:

$$\
H_0(x) = 1, \quad H_1(x) = 2x, \quad H_{n+1}(x) = 2xH_n(x) - 2nH_{n-1}(x).
\$$

Alternatively, they can be derived using the **Rodrigues' formula**:

$$\
H_n(x) = (-1)^n e^{x^2} \frac{d^n}{dx^n} \left( e^{-x^2} \right).
\$$

The first few Hermite polynomials are:

$$\
H_0(x) = 1, \quad H_1(x) = 2x, \quad H_2(x) = 4x^2 - 2, \quad H_3(x) = 8x^3 - 12x, \quad H_4(x) = 16x^4 - 48x^2 + 12.
\$$

These polynomials exhibit symmetry properties:

$$\
H_n(-x) = (-1)^n H_n(x),
\$$

which means they are symmetric when $$\ n \$$ is even and antisymmetric when $$\ n \$$ is odd.  

Hermite polynomials have several important applications due to their properties. In physics, they form the solutions to the quantum harmonic oscillator problem, where their orthogonality with the Gaussian weight $$\ e^{-x^2} \$$ simplifies calculations. In numerical methods, they are used in **Gauss-Hermite quadrature**, a technique for integrating functions involving the weight $$\ e^{-x^2} \$$ efficiently. Hermite polynomials are also used to approximate Gaussian-like functions, as their orthogonal nature ensures minimal error in weighted approximations. Their recurrence relations and symmetry properties make them computationally efficient and easy to implement in theoretical and applied problems.

### Example  

Consider approximating the function $$\ f(x) = x^2 \$$ over the interval $$\(-\infty, \infty)\$$ using Hermite polynomials. The first few Hermite polynomials are $$\ H_0(x) = 1 \, \ H_1(x) = 2x \, and \ H_2(x) = 4x^2 - 2 \$$. By projecting $$\ f(x) = x^2 \$$ onto these polynomials, we observe that $$\ x^2 \$$ can be expressed as:

$$\
f(x) = \frac{1}{4} H_2(x) + \frac{1}{2} H_0(x).
\$$

This demonstrates how Hermite polynomials can efficiently approximate functions that are symmetric or Gaussian-like. Their orthogonality with respect to $$\ e^{-x^2} \$$ makes them particularly useful in problems involving probability distributions and physics.
### Pros:
Due to their orthogonality, Hermite polynomials are particularly effective for approximating functions that resemble Gaussian functions or exhibit exponential decay. They play a key role in Gauss-Hermite quadrature, a numerical integration technique that efficiently evaluates integrals with the weight $$\ e^{-x^2} \$$. Hermite polynomials also exhibit a property of symmetry: $$\ H_n(-x) = (-1)^n H_n(x) \$$. Specifically, even-degree polynomials are symmetric, while odd-degree polynomials are antisymmetric, which can simplify certain calculations.

### Cons:

Hermite polynomials are orthogonal only for the weight $$\ e^{-x^2} \$$. For other weight functions, they are not as effective. These polynomials are defined over the infinite domain $$\ (-\infty, \infty) \$$, which makes them less useful for problems restricted to finite intervals. As the degree $$\ n \$$ increases, Hermite polynomials involve increasingly complex terms, leading to higher computational costs, especially for very large $$\ n \$$. While Hermite polynomials excel for Gaussian-like functions, they are not optimal for approximating functions with non-Gaussian behavior or sharp discontinuities.

## Trigonometric Basis  
Trigonometric basis functions form the foundation for representing periodic functions, making them essential in applications such as Fourier analysis, signal processing, and solving partial differential equations. These functions are built using sine and cosine terms, which exhibit periodic behavior over a defined interval. For a given interval $$\ [-L, L]\$$, the trigonometric basis functions are defined as:

$$\
\phi_n(x) = \cos\left( \frac{n\pi x}{L} \right) \quad \text{and} \quad \psi_n(x) = \sin\left( \frac{n\pi x}{L} \right), \quad n = 0, 1, 2, \dots
\$$

These functions are orthogonal over the interval $$\ [-L, L]\$$ with respect to the standard inner product. The orthogonality property is expressed as follows:

$$\
\int_{-L}^L \cos\left( \frac{m\pi x}{L} \right) \cos\left( \frac{n\pi x}{L} \right) \, dx = 0 \quad \text{for } m \neq n,
\$$

and similarly for the sine terms. This orthogonality ensures that the basis functions provide a unique and stable decomposition of periodic functions into a linear combination of sine and cosine terms, known as the **Fourier series**.

A Fourier series represents a periodic function $$\ f(x) \$$ with period $$\ 2L \$$ as:

$$\
f(x) = a_0 + \sum_{n=1}^\infty \left[ a_n \cos\left( \frac{n\pi x}{L} \right) + b_n \sin\left( \frac{n\pi x}{L} \right) \right],
\$$

where the coefficients $$\ a_n \$$ and $$\ b_n \$$ are determined by projecting $$\ f(x) \$$ onto the trigonometric basis functions. The coefficients are calculated as:

$$\
a_n = \frac{1}{L} \int_{-L}^L f(x) \cos\left( \frac{n\pi x}{L} \right) \, dx, \quad b_n = \frac{1}{L} \int_{-L}^L f(x) \sin\left( \frac{n\pi x}{L} \right) \ dx.
\$$

Trigonometric basis functions have several important properties. They are **orthogonal** on their interval, which ensures a stable and unique decomposition of periodic signals. Additionally, the smooth and periodic nature of sine and cosine functions makes them particularly effective for representing smooth, continuous, and periodic functions. The **Parseval's theorem** further highlights that the total energy of a function in the time domain equals the energy in its Fourier coefficients, which is useful for analyzing signal strength and error.

Trigonometric basis functions are widely applied in solving periodic problems, such as analyzing waveforms in signal processing, solving the heat and wave equations, and decomposing functions in Fourier analysis.

### Example   

Consider the periodic function $$\ f(x) = x \$$ defined on the interval $$\ [-1, 1]\$$. We aim to approximate this function using the **trigonometric basis functions** in its Fourier series form:

$$\
f(x) \approx a_0 + \sum_{n=1}^N \left[ a_n \cos(n\pi x) + b_n \sin(n\pi x) \right].
\$$

The Fourier coefficients $$\( a_n \)$$ and $$\( b_n \)$$ are calculated as:

$$\
a_n = \int_{-1}^1 f(x) \cos(n\pi x) \, dx, \quad b_n = \int_{-1}^1 f(x) \sin(n\pi x) \, dx.
\$$

For $$\ f(x) = x \$$:  

- The coefficient $$\ a_0 \$$, which corresponds to the constant term, is $$\ 0 \$$ because the function $$\ f(x) = x \$$ is odd.  
- All the $$\ a_n \$$ coefficients are also $$\ 0 \$$ due to the symmetry of the function.

The sine coefficients $$\ b_n \$$ can be calculated as:

$$\
b_n = \int_{-1}^1 x \sin(n\pi x) \, dx.
\$$

After solving, the coefficients $$\ b_n \$$ are:

$$\
b_n = \frac{2(-1)^{n+1}}{n\pi}.
\$$

Thus, the Fourier series representation of $$\ f(x) = x \$$ becomes:

$$\
f(x) \approx \sum_{n=1}^N \frac{2(-1)^{n+1}}{n\pi} \sin(n\pi x).
\$$

This example demonstrates how a periodic function like $$\ f(x) = x \$$ can be represented as a sum of sine functions in the trigonometric basis. By increasing $$\ N \$$, the approximation becomes more accurate.

### Pros:

Trigonometric basis functions, such as sine and cosine, are well-suited for representing periodic functions due to their inherent periodic nature. These functions are orthogonal over a specific interval $$\ [-L, L]\$$, which guarantees a stable and unique decomposition of functions in the Fourier series. Periodic signals can be efficiently represented using a finite number of sine and cosine terms, allowing for compact approximations in various applications. Trigonometric basis functions form the foundation of Fourier series in fields like signal processing, image compression, and solving partial differential equations. Additionally, these functions are smooth and differentiable, making them ideal for approximating smooth and continuous functions.

### Cons:

Trigonometric basis functions are designed for periodic functions. When applied to non-periodic problems, they require modifications like extending the function periodically, which can introduce errors. When approximating functions with sharp discontinuities, the Fourier series exhibits overshoots near the discontinuities. This effect known as the Gibbs phenomenon causes reduced accuracy. Trigonometric basis functions work best on uniform intervals. Adapting them for non-uniform or irregular domains can add computational complexity.

## References

1. Boyd, J. P. (2001). *Chebyshev and Fourier Spectral Methods* (2nd ed.). Dover Publications.  
2. Szegő, G. (1975). *Orthogonal Polynomials* (4th ed.). American Mathematical Society.  
3. Mason, J. C., & Handscomb, D. C. (2002). *Chebyshev Polynomials*. Chapman & Hall/CRC.  
4. Shen, J., Tang, T., & Wang, L. L. (2011). *Spectral Methods: Algorithms, Analysis and Applications*. Springer.    
5. Boyd, J. P. (2014). Orthogonal Polynomials on the Unit Circle and Applications in Approximation Theory. *Journal of Computational Physics*, 250, 356–374.  
6. Weisstein, E. W. (n.d.). Legendre Polynomials. *MathWorld–A Wolfram Web Resource*.(https://mathworld.wolfram.com/LegendrePolynomial.html).   
7. Olver, F. W. J., Lozier, D. W., Boisvert, R. F., & Clark, C. W. (2010). *NIST Handbook of Mathematical Functions*. Cambridge University Press.  
8. Press, W. H., Teukolsky, S. A., Vetterling, W. T., & Flannery, B. P. (2007). *Numerical Recipes: The Art of Scientific Computing* (3rd ed.). Cambridge University Press.  
9. Haberman, R. (2013). *Applied Partial Differential Equations with Fourier Series and Boundary Value Problems* (4th ed.). Pearson Education.
