# 9-2 Generating Functions(生成函數)

$f(x) = a_0x^0 + a_1x^1 + a_2x^2 + ...$ $\implies$ Function like this is called **Generating Function**.



Eg.  $(1-x^{n+1}) = (1 - x)(1 + x + x ^2 + x^3 + ...... + x^n)$

$\implies (1 - x^{n+1})/(1 - x) = (1 + x + x ^2 + x^3 + ...... + x^n) \implies $ Seq: $\underbrace{1,1,1,1,1,1,......}_{n個1},0,0,0,0,......$

Eg. $1 = (1 - x)(1 + x + x ^1 + x^2 + x ^3 + ...)$

$\implies 1/(1 - x) = (1 + x + x^2 + x^3 + ...) \implies$ Seq: $1, 1, 1, 1, 1, 1, ......$



Eg. $(1 + x)^n = \begin{pmatrix} n \\ 0\end{pmatrix}x^0 + \begin{pmatrix} n \\ 1\end{pmatrix}x^1 + \begin{pmatrix} n \\ 2\end{pmatrix}x^2 + \begin{pmatrix} n \\ 3\end{pmatrix}x^3 + ...... + \begin{pmatrix} n \\ n\end{pmatrix}x^n$ (二像是後面接0)

