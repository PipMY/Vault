### **General Method to Solve Least Squares Solutions for $Ax=b$

If $Ax=b$ has **no exact solution**, we find a **least squares solution** by solving:

$A^TAx=A^Tb$

This is called the **normal equation** and ensures that $Ax$ is as close as possible to $b$.

---

## **Step-by-Step Solution**

### **1. Compute $A^TA$**

Find the **Gram matrix**:

$A^TA$

This matrix is always **square** and **symmetric**.

---

### **2. Compute $A^Tb$

Find the **right-hand side** of the normal equation:

$A^Tb$

---

### **3. Solve $A^TAc=A^Tb$**

This is now a **square system** that can be solved using:

- **Gaussian elimination**
- **Matrix inversion** (if $A^TA$ is invertible)
- **LU or Cholesky decomposition** (if $A^T A$ is positive definite)

---

### **4. Express the General Solution**

If $A^T A$ is **singular** (not full rank), then:

- There are **infinitely many solutions**.
- The solution includes a **particular solution $x_{p}$​** plus a **null space component**.
$$
x=x_{p}+tv
$$
where $v$ is a **basis vector of the null space of $A$.