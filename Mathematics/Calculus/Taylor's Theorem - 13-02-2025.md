## **1. Introduction to Taylor’s Theorem**

Taylor’s Theorem is a fundamental result in calculus that allows us to approximate functions using polynomials. It provides a way to express a function as an infinite series (Taylor series) or a finite-degree polynomial with a remainder term.

### **Key Ideas:**

- Approximation of functions using polynomials.
- Deriving Taylor series as an **infinite** sum that exactly equals $f(x)$.
- Using Taylor’s theorem to cap the series at $n$ terms while still keeping it accurate.
- Applications in approximations, physics, and numerical analysis.

---

## **2. Quadratic Approximation**

### **Definition**

A quadratic approximation of a function $f(x)$ near $x_{0}$​ is given by:
$$
f(x)\approx a_{0}+a_{1}(x-x_{0})+a_{2}(x-x_{0})^2
$$
To ensure accuracy, we require that:

1. $f(x)$ and the approximation have the **same function value** at $x_{0}$​.
2. $f(x)$ and the approximation have the **same first derivative** at $x_0$​.
3. $f(x)$ and the approximation have the **same second derivative** at $x_0$.

By setting these conditions, we derive:
$$
f(x)\approx f(x_{0})+f^{'}(x_{0})(x-x_{0})+\frac{f^{''}(x_{0})}{2}(x-x_{0})^2
$$
---
## **3. Taylor Series Expansion**

A **Taylor series** expresses a function as an **infinite power series** centered at $x_{0}$​:
$$
f(x)=\sum_{{n=0}}^{\infty}{\frac{f^{(n)}(x_{0})}{n!}}(x-x_{0})^n
$$
This series represents the function exactly **if the function is infinitely differentiable** and the series converges.

**Maclaurin Series** is a special case where $x_{0}=0$:

---
## **4. Taylor’s Theorem**

Taylor’s Theorem provides a **precise bound** for truncating the Taylor series at $n$ terms.

For a function $f(x)$ that is $n$-times differentiable on $[a,x]$, there exists some $\xi \in (a,x)$ such that:
$$
f(x)=f(a)+f^{'}(a)(x-a)+\frac{f^{''}(a)}{2!}(x-a)^2 + \dots + \frac{f^{(n-1)}(a)}{(n-1)!}(x-a)^{n-1} + \frac{f^{(n)}(\xi)}{n!}(x-a)^n $$
The last term is called the **remainder term** $R_n(x)$:
$$
R_{n}(x)=\frac{f^{(n)}(\xi)}{n!}(x-a)^n
$$
For the Taylor series to converge to $f(x)$, we require:
$$
\lim_{ n \to \infty } R_{n}(x)=0
$$
---
## **5. Proof of Taylor’s Theorem**

To prove Taylor’s Theorem, we use **Rolle’s Theorem**:

1. Define a function $F(y)$ such that:
$$
F(y)=f(x)-f(y)-f^{'}(y)(x-y)-\dots-\frac{f^{(n-1)}(y)}{(n-1)!}(x-y)^{n-1} -\frac{k}{n!}(x-y)^n
$$

1. Since $F(a) = F(x)=0$, we apply Rolle’s Theorem to find $\xi$ such that:

$$
F^{'}(\xi)=0
$$
1. This leads to:
$$
f^{(n)}(\xi)=k
$$
Thus, proving:
$$
R_{n}(x)=\frac{f^{(n)}(\xi)}{n!}(x-a)^n
$$
---
## **6. Important Taylor Series Expansions**

### **Maclaurin Series Expansions**

1. **Exponential function:**
$$e^x=\sum_{n=0}^\infty \frac{x^n}{n!}$$
1. **Sine function:**
    $$\sin x=\sum_{k=0}^\infty(-1)^k\frac{x^{2k+1}}{(2k+1)!}$$
3. **Cosine function:**
    $$
\cos x=\sum_{k=0}^\infty(-1)^k \frac{x^{2k}}{(2k)!} 
$$
1. **Natural logarithm $|x| < 1$:**
    $$
\ln(1+x)=\sum_{n=1}^\infty (-1)^{n+1}\frac{x^n}{n}
$$
1. **Binomial series $|x| < 1$:**
    $$
(1+x)^r=\sum_{n=0}^\infty {r\choose n}x^n
$$
---
## **7. Applications of Taylor’s Theorem**

### **a. L’Hôpital’s Rule (Extended)**

If $f$ and $g$ are $n$-times differentiable and satisfy:

- $f(a)=g(a)=0$,
- $f^{(r)}(a)=g^{(r)}(a)=0$ for $1 \leq r \leq n-1$,
- $f^{(n)}(a) \neq 0, g^{(n)}(a) \neq 0$,

then:
$$
\lim_{ x \to a } \frac{f(x)}{g(x)}=\lim_{ x \to a } {\frac{f^{(n)}(x)}{g^{(n)}(x)}}
$$
### **b. Classifying Extrema Using Taylor’s Theorem**

- A local maximum at $x=a$ occurs if the first nonzero derivative $f^{(n)}(a)$ is of **even order** and $f^{(n)}(a) <0$.
- A local minimum at $x=a$ occurs if the first nonzero derivative $f^{(n)}(a)$ is of **even order** and $f^{(n)}(a) >0$.
- If the first nonzero derivative is of **odd order**, then $f(x)$ has a **stationary point of inflection** at $x=a$.