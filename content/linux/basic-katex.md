---
title: "Basic KaTeX Math Guide"
date: 2026-03-26
math: true
---

# Basic KaTeX Math Guide

Add `math: true` to your front matter to enable math.

## Inline Math

Wrap with `$`:
- $E = mc^2$
- $a^2 + b^2 = c^2$
- $\frac{1}{2}$

## Display Math

Wrap with `$$`:
$$
\frac{-b \pm \sqrt{b^2 - 4ac}}{2a}
$$

## Fractions

$\frac{1}{2}$ inline

$$
\frac{n!}{k!(n-k)!}
$$

## Exponents

$x^2$ and $x^{2n}$

$$
e^{i\pi} + 1 = 0
$$

## Subscripts

$x_1$ and $x_{ij}$

$$
\sum_{i=1}^{n} i = \frac{n(n+1)}{2}
$$

## Roots

$\sqrt{x}$ and $\sqrt[3]{x}$

$$
\sqrt{\frac{a}{b}}
$$

## Greek Letters

$\alpha, \beta, \gamma, \pi, \theta, \mu, \sigma$

$$
\Gamma, \Delta, \Theta, \Pi, \Sigma, \Omega
$$

## Integrals

$\int_a^b f(x) dx$

$$
\int_{-\infty}^{\infty} e^{-x^2} dx = \sqrt{\pi}
$$

## Derivatives

$f'(x)$ and $\frac{dy}{dx}$

$$
\frac{\partial f}{\partial x}
$$

## Limits

$\lim_{x \to \infty} f(x)$

$$
\lim_{x \to 0} \frac{\sin x}{x} = 1
$$

## Matrices

$$
\begin{pmatrix}
a & b \\
c & d
\end{pmatrix}
$$

$$
\begin{bmatrix}
1 & 2 & 3 \\
4 & 5 & 6 \\
7 & 8 & 9
\end{bmatrix}
$$

## Vectors

$\vec{v}$ and $\mathbf{v}$

$$
\vec{F} = m\vec{a}
$$

## Summations

$\sum_{i=1}^{n} i$

$$
\sum_{i=1}^{\infty} \frac{1}{i^2} = \frac{\pi^2}{6}
$$

## Products

$\prod_{i=1}^{n} i = n!$

$$
\prod_{i=1}^{n} x_i
$$

## Brackets

$(a+b)$, $[a+b]$, $\{a+b\}$, $|a+b|$

$$
\left( \frac{1}{x} \right) \quad \left[ \frac{1}{x} \right] \quad \left\{ \frac{1}{x} \right\}
$$

## Text in Math

$x = 1 \text{ if } x > 0$

## Color

$\color{red}{red}$, $\color{blue}{blue}$, $\color{green}{green}$

## Common Symbols

$\infty$ infinity  
$\pm$ plus/minus  
$\times$ times  
$\div$ divide  
$\le$ less than or equal  
$\ge$ greater than or equal  
$\neq$ not equal  
$\approx$ approximately  
$\forall$ for all  
$\exists$ there exists  
$\implies$ implies  
$\iff$ if and only if  

## Quick Reference

| Type | Syntax | Example |
|------|--------|---------|
| Inline | `$...$` | $x^2$ |
| Display | `$$...$$` | $$x^2$$ |
| Fraction | `\frac{a}{b}` | $\frac{a}{b}$ |
| Exponent | `x^2` | $x^2$ |
| Subscript | `x_2` | $x_2$ |
| Square Root | `\sqrt{x}` | $\sqrt{x}$ |
| Sum | `\sum` | $\sum$ |
| Integral | `\int` | $\int$ |

## Need More?

- [KaTeX Docs](https://katex.org/docs/supported.html)
- [LaTeX Guide](https://en.wikibooks.org/wiki/LaTeX/Mathematics)