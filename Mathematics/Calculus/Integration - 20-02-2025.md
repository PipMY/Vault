## **1. Introduction to Integration**

Integration is a fundamental concept in calculus, used to compute areas under curves, accumulate quantities, and solve differential equations. There are two main types:

1. **Definite Integrals** – Evaluate the accumulation of a function over an interval.
2. **Indefinite Integrals** – Find the general form of antiderivatives.

---

## **2. Definite Integrals**

### **Definition**

A definite integral is the limit of a sum of areas of rectangles approximating the region under a curve. It is given by:

$$
∫_a^bf(x) dx=\lim_{ n \to \infty }\sum_{i=1}^nf(\xi_{i})\Delta_{i}
$$
where:

- $[a,b]$ is the interval of integration.
- $\xi_{i}$ is a sample point in each subinterval.
- $\Delta_{i}=x_{i}-x_{i-1}$ is the subinterval width.
### **Interpretation**

- Represents the signed area between the curve $y=f(x)$ and the x-axis.
- If $f(x)$ is positive, the integral gives the area above the x-axis.
- If $f(x)$ is negative, the integral gives the negative of the area below the x-axis.

### **Properties of Definite Integrals**

1. **Additivity**: The integral over an interval can be split at any point $k$:
$$
\int_{a}^b f(x)dx=\int_{a}^k f(x)dx + \int_{k}^b f(x)dx
$$
2. **Homogeneity**: A constant factor can be pulled out:
$$
\int_{a}^b cf(x)dx=c\int_{a}^b f(x)dx
$$
3. **Linearity**: The sum of two functions integrates separately:
$$
\int_{a}^b (f(x) +g(x))dx=\int_{a}^b f(x)dx + \int_{a}^b g(x)dx
$$
4. **Inequality Property**: $if \space f(x) \leq g(x)$, then:
$$
\int_{a}^b f(x)dx \leq \int_{a}^b g(x)dx
$$
---
## **3. Handling Discontinuities**

### **Case 1: Function is Discontinuous at a Point $c$**

If $f(x)$ is discontinuous at $c$, the integral is defined by:
$$
\int_{a}^b f(x)dx=\lim_{ \epsilon \to 0 } \left[ \int_{a}^{c-\epsilon}f(x)dx+\int_{{c+\epsilon}}^b f(x)dx \right]
$$
Both limits must exist for the integral to be well-defined.

### **Case 2: Piecewise Continuous Functions**

A function is piecewise continuous if it has a countable number of isolated discontinuities. The integral is computed by summing over the continuous pieces.

---

## **4. Mean Value Theorem for Integrals**

If $f$ is continuous on $[a,b]$, there exists some  such that:
$$
\int_{a}^b f(x)dx=(b-a)f(\xi)
$$
---

## **5. The Fundamental Theorem of Calculus**

The Fundamental Theorem of Calculus (FTC) establishes a relationship between differentiation and integration.

### **Part 1: Differentiation of an Integral**

If:

$$
F(x)=\int_{a}^x f(t)dt
$$
then $F(x)$ is differentiable and:

$$F′(x)=f(x)$$
### **Part 2: Evaluating Definite Integrals**

If $F(x)$ is an antiderivative of $f(x)$, then:
$$
\int_{a}^b f(x)dx=F(b)-F(a)
$$
---
## **6. Indefinite Integrals**

An indefinite integral represents a family of functions with an arbitrary constant $C$:

$$
\int f(x)dx=F(x)+C
$$
where $F(x)$ is an antiderivative of $f(x)$.

---
## **7. Evaluating Definite Integrals with Antiderivatives**

Using the Fundamental Theorem:

$$
\int_{a}^b f(x)dx=G(b)-G(a)
$$
where $G(x)$ is any antiderivative of $f(x)$.