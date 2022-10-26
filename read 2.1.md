## read 2.1

### Theorem 1

**Let A, B, C be the matrices of the same size, and let r and s be scalars.**

1.   $A + B = B + A$
2.   $(A + B) + C = A + (B + C)$
3.   $A + 0 = A$
4.   $r(A + B) = rA + rB$
5.   $(r + s)A = rA + sA$
6.   $r(sA) = (rs)A$

### Theorem 2

**Let A be an m x n matrix, and let B and C have sizes for which the indicated sums and products are defined.**

1.   $A(BC) = (AB)C$ (Associative law of multiplication)
2.   $A(B + C) = AB + AC$ (Left distributive law)
3.   $(B + C)A = BA + CA$ (Right distributive law)
4.   $r(AB) = (rA)B = A(rB)$ (for any scalar $r$)
5.   $I_mA = A = AI_n$ (Identity for matrix multiplication)

### Theorem 3

**Let A and B denote matrices whose sizes are appropriate for the following sums and products.**

1.   $(A^T)^T = A$
2.   $(A + B)^T = A^T + B^T$

3.   For any scalar $r$, $(rA)^T = rA^T$
4.   $(AB)^T = B^TA^T$, $(ABC)^T = C^TB^TA^T......$



### Square matrix

**DEF: A matrix with n rows and n columns is called a square matrix of order n.**

#### Some types of square matrix

1.   Zero matrix: all entries are zero.

2.   Diagonal matrix: $\langle A_{ij}\rangle = 0$ if $i\ne j$

3.   Unit(identity) matrix: $diag(1,1,1,1,...,1)$

     $IA = A = AI$

4.   Triangular matrix:

     (i)  upper triangular: all entries below the main diagonal are zero.

     (ii) lower triangular: all entries above the main diagonal are zero.

     (a) $u^T = L$

     (b) $u\times u = u$

     (c) $L^T = u$

     (d) $L\times L = L$

5.   Symmetric matrix: A square matrix for which $A^T = A$

     $\implies\langle A\rangle_{ij} = \langle A\rangle_{ji}$