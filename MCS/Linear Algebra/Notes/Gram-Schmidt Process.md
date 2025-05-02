For a matrix $M$:
$$
M=\begin{bmatrix}
v_{1}  & v_{2} & v_{3} & \dots & v_k
\end{bmatrix}
$$
Where $v$ is a vector apply the following steps to attain the matrix $G$:
$$
G=\begin{bmatrix}
q_{1} & q_{2} & q_{3} & \dots & q_{k}
\end{bmatrix}
$$
Follow the steps below:

1. Start with the first vector:
$$
q_{1}=\frac{v_{1}}{||v_{1}||}, \space where \space ||v_{1}|| = \sqrt{ ⟨v_{1}​,v_{1}​⟩ }
$$
2. Subtract the projection of $v_2$ onto $q_1$ to make it orthogonal:
$$
u_{2}=v_{2}-proj_{q_{1}}v_{2}
$$
where:
$$
proj_{q_{1}}v_{2}=\frac{⟨v_{2}​,q_{1}​⟩}{⟨q_{1}​,q_{1}​⟩}q_{1}
$$
Then normalise:
$$
q_{2}=\frac{u_{2}}{||u_{2}||}
$$
3. Repeat this process for $v_{3}, v_{4}, etc$:
$$
u_{k}=v_{k}-\sum_{j=1}^{k-1}proj_{q_{j}}v_{k}
$$
Then normalise:
$$
q_{k}=\frac{u_{k}}{||u_{k}||}
$$
At the end, $q_{1},q_{2},\dots,q_{n}$ form an orthonormal basis.

Note: If the inner space is is $C[a,b]$ Then the inner product space is as follows:
$$
⟨f,g​⟩ = \int^b_{a}f(x)g(x) dx
$$
