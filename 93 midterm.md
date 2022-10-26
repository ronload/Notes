# 93 midterm

1.   (a) If square matrix $A$ has an inverse, prove that the inverse is unique.

    Pf: 

    Let $A$ be a square matrix. If possible let $B$ and $C$ are its two inverses. 

    As $B$ is the inverse of $A$ 

    $AB = BA = I$ …(1) 

    As $C$ is the inverse of $A$ 

    $AC = CA = I$ …(2) 

    $B = BI = B(AC) = (BA)C = IC = C B = C $

    Hence the inverse of $A$ is unique.

    

    (b) If square matrix $A$ is nonsingular, prove that the solution of matrix equation $Ax = b$ is unique.

    Pf:

    If $A$ is nonsingular, $A^{−1}$ exists and $A^{−1}A = I$. Then, $x = A^{−1}b$.

    

2. Let $A$ be an invertible matrix. Prove:

    (a) $(A^T)^{-1} = (A^{-1})^T$

    Pf: 

    $AA^{−1} = I,\space A^{−1}A = I$

    $(AA^{−1})^T = (A^{−1})^T A^T = I^T = I$

    $(A^{−1}A)^T = A^T (A^{−1})^T = I^T = I$

    $\implies(A^T )^{−1} = (A^{−1})^T$

    

    (b) $(A^T)^n = (A^n)^T, \space n > 1$

    Pf: 

    $(AB)^T = B^TA^T$

    $(A^n)^T = {\underbrace{(A\cdots A)}_{n\text{ times}}}^T = \underbrace{A^T\cdots A^T}_{n\text{ times}}= (A^T)^n$

    

3. Let $v_1,v_2,v_3,...,v_n$ be vectors in a vector space $V$, and let $S$ be the span of $v_1,v_2,v_3,...,v_n$. Prove that $S$ is the subspace of $V$.

4. Let 

    $$A = \begin{bmatrix}1 & 0 & 0 & 0 & 0\\2 & 2 & 0 & 0 & 0\\3 & 1 & 3 & 0 & 0\\1 & 2 & 1 & 4 & 0\\ 2 & 1 & 1 & 1 & 1\end{bmatrix},\space B = \begin{bmatrix}1 & 2 & 1 & 2 & 1\\0 & 2 & 3 & 3 & 2\\0 & 0 & 3 & 1 & 2\\0 & 0 & 0 & 1 & 3\\ 0 & 0 & 0 & 0 & 4\end{bmatrix}$$

     Compute $det(AB).$

5.   (a) Let $v_1 = (1, 3, -1), v_2 = (-5, -8, 2)$ and $U = (3, -5, h)$, Determine the value of $h$ such that $u$ is in the span of $v_1$ and $v_2$.

    (b) Let $W$ be the set of all vectors of the form $(a-b, b-c, c-a, b)$, where $a, b, c \in R$. Find vector $v_1, v_2, v_3$ such that $W$ is the span of $v_1, v_2, v_3$.

6.   Let 

    $A = \begin{bmatrix}1 & 0 & 5\\1 & 0 & 0\\3 & 2 & 6\end{bmatrix}$

    Find the inverse of $A$ by elementary row operations.

7. Solve the following system by Gauss method method.

    $x_1 - 2x_2 - x_3 + 3x_4 = 0$

    $-2x_1 + 4x_2 + 5x_3 - 5x_4 = 3$

    $3x_1 - 6x_2 - 6x_3 + 8x_4 = 2$

8. For the following definition of a set $S$ and a vector space $V$, determine whether $S$ is a subsapce of $V$. If your answer is "No", you must explain why.

    (a) $S = \{(x,y)|xy|\geq 0\}$

    ​     $V = R^2$

    (b) $S$ is all polynomials of the form $p(t) = at^2$ where $a \in R$.

    ​     $V = P_n$

    (c) $S = \{\begin{bmatrix}a & b \\ c & d\end{bmatrix}|det\begin{bmatrix}a & b \\ c & d\end{bmatrix} = 0\}$

    ​	 $V = M_{22}$

    (d) $S = \{(x, y, z)|y = x + z\}$

    ​	 $V = R^3$

    (e) $S = \{(3s, 2 + 5s)|s \in R\}$

    ​	 $V = R^2$

9. Determine each of the following statements is true or false.

    (a) Let $A, B$ be matrices. Then $(A + B)(A - B) = A^2 - B^2$.

    (b) If matrix $A$ is invertible and scalar $r \neq 0$, then $(rA)^{-1} = rA^{-1}$.

    (c) Let $A, B, C$ be matrices. If $AB = AC$, then $B = C$.

    (d) Let $A, B$ be matrices. If $AB = O$, then either $A = O$ or $B = O$.

    (e) If $A$ is a $3 \times 3$ matrix, then $det(5A) = 5det(A)$.

    (f) The transpose of an elemantory matrix is an elemantary matrix.

    (g) The row echelon form of a matrix is unique.

    (h) If $A$ is an $n \times n$ matrix, then $det(AA^T) \geq 0$.

    (i) If matrix $A$ is invertible, then $Ax = O$ has only solution $x = O$.

    (j) A matrix $A$ is invertible if and only if $det(A) \neq 0$.

    