## **1. Introduction to Linear Regression**

Linear regression is a fundamental method in statistics and machine learning that fits a straight line to data points to model the relationship between variables.

### **Key Ideas:**

- Use of **least squares fitting** to find the best-fit line.
- Expressing regression as a **linear system** $Ax=b$.
- **QR decomposition** as an efficient method to solve least squares problems.

---

## **2. Least Squares and Linear Systems**

### **Definition (Least Squares Problem)**

Given an inconsistent system Ax=bAx = bAx=b with mmm equations and nnn variables (m>nm > nm>n), the **least squares solution** minimizes the error:

∥b−Ax∥\| b - Ax \|∥b−Ax∥

where b−Axb - Axb−Ax is the **error vector**, and ∥b−Ax∥\| b - Ax \|∥b−Ax∥ is the **least squares error**.

### **Normal Equations**

To solve for xxx, we use the **normal equation**:

ATAx=ATbA^T A x = A^T bATAx=ATb

where ATAA^T AATA is invertible if and only if AAA has **linearly independent columns**.

---

## **3. Application: Fitting Data with a Straight Line**

We have experimental data points (x1,y1),(x2,y2),...,(xn,yn)(x_1, y_1), (x_2, y_2), ..., (x_n, y_n)(x1​,y1​),(x2​,y2​),...,(xn​,yn​) and seek to fit a **linear function**:

y=a+bxy = a + bxy=a+bx

Rewriting as a system of equations:

{a+bx1=y1a+bx2=y2⋮a+bxn=yn\begin{cases} a + b x_1 = y_1 \\ a + b x_2 = y_2 \\ \vdots \\ a + b x_n = y_n \end{cases}⎩⎨⎧​a+bx1​=y1​a+bx2​=y2​⋮a+bxn​=yn​​

In matrix form:

[1x11x2⋮⋮1xn][ab]=[y1y2⋮yn]\begin{bmatrix} 1 & x_1 \\ 1 & x_2 \\ \vdots & \vdots \\ 1 & x_n \end{bmatrix} \begin{bmatrix} a \\ b \end{bmatrix} = \begin{bmatrix} y_1 \\ y_2 \\ \vdots \\ y_n \end{bmatrix}​11⋮1​x1​x2​⋮xn​​​[ab​]=​y1​y2​⋮yn​​​

This is a least squares problem solved using **normal equations**:

(ATA)v=ATy(A^T A) v = A^T y(ATA)v=ATy

#### **Example**

Given data points:

[10111213][ab]=[1344]\begin{bmatrix} 1 & 0 \\ 1 & 1 \\ 1 & 2 \\ 1 & 3 \end{bmatrix} \begin{bmatrix} a \\ b \end{bmatrix} = \begin{bmatrix} 1 \\ 3 \\ 4 \\ 4 \end{bmatrix}​1111​0123​​[ab​]=​1344​​

Solving for (a,b)(a, b)(a,b):

[1.51]\begin{bmatrix} 1.5 \\ 1 \end{bmatrix}[1.51​]

so the regression line is **y=1.5+xy = 1.5 + xy=1.5+x**.

---

## **4. Uniqueness of Least Squares Solutions**

### **Theorem**

For an m×nm \times nm×n matrix AAA, the least squares solution is **unique** if and only if AAA has linearly independent columns.

#### **Proof Outline:**

- AAA has independent columns ⇔\Leftrightarrow⇔ ATAA^T AATA is **invertible**.
- The system ATAx=ATbA^T A x = A^T bATAx=ATb has a unique solution if ATAA^T AATA is invertible.

Thus, if AAA has full column rank, the least squares solution is unique.

---

## **5. QR Decomposition and Least Squares**

Instead of using the normal equation (ATA)x=ATb(A^T A) x = A^T b(ATA)x=ATb, an alternative is **QR decomposition**.

### **QR Decomposition Definition**

For an m×nm \times nm×n matrix AAA:

A=QRA = QRA=QR

where:

- QQQ is an m×nm \times nm×n **orthonormal** matrix (i.e., QTQ=IQ^T Q = IQTQ=I).
- RRR is an n×nn \times nn×n **upper triangular** matrix.

Using this:

x=R−1QTbx = R^{-1} Q^T bx=R−1QTb

### **Why QR is Better than Normal Equations?**

- **More numerically stable** than computing (ATA)−1(A^T A)^{-1}(ATA)−1.
- **Avoids matrix inversion**, reducing computational errors.
- **Faster** for large-scale problems.

#### **Example**

For A=QRA = QRA=QR, solving Ax=bAx = bAx=b simplifies to:

Rx=QTbRx = Q^T bRx=QTb

which is an **upper triangular system**, easily solved by **back-substitution**.

---

## **6. Projection Matrices**

A **projection matrix** projects a vector bbb onto the **column space of AAA**:

P=A(ATA)−1ATP = A (A^T A)^{-1} A^TP=A(ATA)−1AT

For any vector bbb, the vector PbP bPb is the **orthogonal projection** of bbb onto **Col(A)**.

### **Application**

Used in:

- **Machine learning** (feature selection, dimensionality reduction).
- **Data science** (PCA, regression).
- **Computer graphics** (projecting 3D objects onto 2D planes).

---

## **7. Example: Quadratic Regression**

Instead of fitting a line, we fit a **parabola**:

y=a+bx+cx2y = a + bx + cx^2y=a+bx+cx2

In matrix form:

[1x1x121x2x22⋮⋮⋮1xnxn2][abc]=[y1y2⋮yn]\begin{bmatrix} 1 & x_1 & x_1^2 \\ 1 & x_2 & x_2^2 \\ \vdots & \vdots & \vdots \\ 1 & x_n & x_n^2 \end{bmatrix} \begin{bmatrix} a \\ b \\ c \end{bmatrix} = \begin{bmatrix} y_1 \\ y_2 \\ \vdots \\ y_n \end{bmatrix}​11⋮1​x1​x2​⋮xn​​x12​x22​⋮xn2​​​​abc​​=​y1​y2​⋮yn​​​

Using **QR decomposition**:

x=R−1QTbx = R^{-1} Q^T bx=R−1QTb

Resulting quadratic regression equation:

y=1.97+1.91x−0.2x2y = 1.97 + 1.91x - 0.2x^2y=1.97+1.91x−0.2x2

---

## **8. Summary & Next Class**

- **Linear regression** models a relationship using least squares fitting.
- **Least squares solutions** minimize ∥Ax−b∥\| Ax - b \|∥Ax−b∥.
- **QR decomposition** provides an efficient way to solve least squares problems.
- **Projection matrices** map vectors onto subspaces.
- **Applications**: machine learning, statistics, numerical analysis.

### **Next Class:**

- **Orthogonal matrices**
- **Spectral decomposition**