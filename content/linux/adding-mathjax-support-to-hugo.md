+++
date = '2025-04-02T13:04:54+07:00'
draft = true
title = 'MathJax Support for Hugo '
+++

### Adding MathJax Support for Hugo 

If CDNs are blocked in your region, self-host MathJax: (Best way!)


1. Download from mathjax.org
2. Place in static/js/mathjax/
3. Update the script tag:

{{< code lang="bash" file="layouts/_defaults/baseof.html" >}}
<script src="{{ "js/mathjax/es5/tex-mml-chtml.js" | relURL }}"></script>
{{< /code >}}


Create a new partial (layouts/partials/mathjax.html):

{{< code lang="bash" file="layouts/partials/mathjax.html" >}}
{{ if or .Params.math .Site.Params.math }}
<div class="mathjax-warning" hidden>
  <p>Math rendering may take a moment. If equations don't appear, refresh the page.</p>
</div>

<script>
document.addEventListener('DOMContentLoaded', function() {
  if (typeof MathJax === 'undefined') {
    document.querySelector('.mathjax-warning').hidden = false;
    console.warn('MathJax failed to load. Using fallback...');
    
    // Optional: Load from alternative CDN if primary fails
    const fallbackScript = document.createElement('script');
    fallbackScript.src = 'https://cdnjs.cloudflare.com/ajax/libs/mathjax/3.2.2/tex-mml-chtml.js';
    fallbackScript.id = 'MathJax-fallback';
    document.head.appendChild(fallbackScript);
  }
});
</script>
{{ end }}
{{< /code >}}


Add this to your CSS (assets/css/mathjax.css):

{{< code lang="bash" file="assets/css/mathjax.css" >}}
/* MathJax container scaling */
.MathJax {
  font-size: 1.3em !important; /* Base size increase */
}

/* Inline math */
mjx-container[jax="CHTML"][display="false"] {
  font-size: 120% !important;
  vertical-align: middle;
}

/* Block math */
mjx-container[jax="CHTML"][display="true"] {
  font-size: 140% !important;
  margin: 1em 0 !important;
}

/* Mobile responsiveness */
@media (max-width: 768px) {
  .MathJax {
    font-size: 1.1em !important; /* Slightly smaller on mobile */
  }
}
{{< /code >}}


Create a new content/post.md to test everything.
For example:

{{< code lang="bash" file="content/post.md" >}}
---
title: "Calculus Fundamentals"
date: 2024-03-15
math: true
---

## Differentiation

### Power Rule
The derivative of $x^n$ is:
$$ \frac{d}{dx} x^n = nx^{n-1} $$

**Example:**
$$ \frac{d}{dx} x^3 = 3x^2 $$

### Chain Rule
For composite functions:
$$ \frac{d}{dx} f(g(x)) = f'(g(x)) \cdot g'(x) $$

---

## Integration

### Basic Integral
The antiderivative of $x^n$ (for $n \neq -1$):
$$ \int x^n \, dx = \frac{x^{n+1}}{n+1} + C $$

**Example:**
$$ \int x^2 \, dx = \frac{x^3}{3} + C $$

### Definite Integral
Area under curve from $a$ to $b$:
$$ \int_a^b f(x) \, dx = F(b) - F(a) $$
where $F'(x) = f(x)$.

---

## Common Formulas

### Fundamental Theorem
$$ \frac{d}{dx} \int_a^x f(t) \, dt = f(x) $$

### Integration by Parts
$$ \int u \, dv = uv - \int v \, du $$
{{< /code >}}



_*Voila!*_

$\begin{eqnarray}
\mathrm{ det }A
 = | A |
 = \begin{vmatrix} a & b \\\ c & d \end{vmatrix}
 = ad - bc
\end{eqnarray}$

$$ \frac{x}{x-1} $$

\begin{eqnarray}
A = \left(
  \begin{array}{cccc}
    a_{ 11 } & a_{ 12 } & \ldots & a_{ 1n } \\\
    a_{ 21 } & a_{ 22 } & \ldots & a_{ 2n } \\\
    \vdots & \vdots & \ddots & \vdots \\\
    a_{ m1 } & a_{ m2 } & \ldots & a_{ mn }
  \end{array}
\right)
\end{eqnarray}

\begin{eqnarray}
{}_n \mathrm{ C }_k
 = \binom{ n }{ k }
 = \frac{ n! }{ k! ( n - k )! }
\end{eqnarray}

\begin{array}{c|ccccc}
  x     & \cdots & -1 & \cdots & 1 & \cdots \\\ 
  \hline
  f’(x) & + & 0 & – & 0 & + \\\
  \hline
  f(x)  & \nearrow & e & \searrow & -e & \nearrow
\end{array}

\begin{array}{|c|c|c|}
  \hline
  xxx & yyy & zzz \\\
  \hline
  1   & 2   & 3 \\\
  \hline
\end{array}

## Differentiation

### Power Rule
The derivative of $x^n$ is:
$$ \frac{d}{dx} x^n = nx^{n-1} $$

**Example:**
$$ \frac{d}{dx} x^3 = 3x^2 $$

### Chain Rule
For composite functions:
$$ \frac{d}{dx} f(g(x)) = f'(g(x)) \cdot g'(x) $$

---

## Integration

### Basic Integral
The antiderivative of $x^n$ (for $n \neq -1$):
$$ \int x^n \, dx = \frac{x^{n+1}}{n+1} + C $$

**Example:**
$$ \int x^2 \, dx = \frac{x^3}{3} + C $$

### Definite Integral
Area under curve from $a$ to $b$:
$$ \int_a^b f(x) \, dx = F(b) - F(a) $$
where $F'(x) = f(x)$.

---

## Common Formulas

### Fundamental Theorem
$$ \frac{d}{dx} \int_a^x f(t) \, dt = f(x) $$

### Integration by Parts
$$ \int u \, dv = uv - \int v \, du $$


