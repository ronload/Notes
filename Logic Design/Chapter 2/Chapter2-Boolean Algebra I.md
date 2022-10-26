# Chapter 2-Boolean Algebra

## Basic Operation

1. the prime (') denotes the *complementation*.
2. The AND operation can be defined (.).
3. The OR operation can be define (+).

### Inverse

If x = 0, x' = 1

If x = 1, x' = 0

<img src="figure 2.1.png" width="30%">

### AND gate (.)

00 = 0

01 or 10 = 0

11 = 1

<img src="figure 2.2.png" width="35%">

### OR gate(+)

0 + 0 = 0

0 + 1 or 1 + 0 = 1

1 + 1 = 1

<img src="figure 2.3.png" width="35%">

### Switches

If switch *X* is open, then we will define the value of *X* to be 0;

if switch *X* is closed, then we will define the value of *X* to be 1.

<img src="figure 2.4.png" width="35%">              

Switches with gates: 

 <img src="figure 2.5.png" width="40%">      <img src="figure 2.6.png" width="40%">

## Boolean Expressions and Truth Table

<img src="figure 2.7.png" width="100%">

## Basic Theorems

1. Operations with 0 and 1:

   $X + 0 = X$

   $X + 1 = 1$

   $X\cdot1 = X$

   $X \cdot 0 = 0$

2. Idenpotemt Laws:

   $X + X = X$

   $X \cdot X = X$

3. Laws of complementarity:

   $X + X' = 1$

   $X \cdot X' = 0$

### Commutative and Associative Laws

1. Commutative Laws:

   $XY = YX$

   $X + Y = Y + X$

2. Associative Laws:

   $(XY)Z = X(YZ) = XYZ$

   $(X + Y) + Z = X + (Y + Z) = X + Y + Z$

### Distributave Laws

1. $X(Y + Z) = XY + XZ$
2. $X + YZ = (X + Y)(X + Z)$

### Simplification Theorems

1. $XY + XY' = X$
2. $(X + Y)(X + Y') = X$
3. $X + XY = X$
4. $X(X + Y) = X$
5. $(X + Y')Y = XY$
6. $XY' + Y = X + Y$

### Examples

1. Simplify $Z = A'BC + A'$:

   Let $X = A',\space Y = BC \implies Z = XY + X = X = A'$

   $\implies Z = A'$

2. Simplify $Z = (A + B'C + D + EF)[A + B'C + (D + EF)']$

   Let $X = A + B'C,\space Y = D + EF$

   $\implies Z = (X + Y)(X + Y') = X$

   $\implies Z = X = A + B'C$

3. Simplify $Z = (AB + C)(B'D + C'E') + (AB + C)'$

   Let $X = B'D + C'E', \space Y = (AB + C)'$

   $\implies Z = XY' + Y =X + Y$

   $\implies Z = B'D + C'E' + (AB + C)'$

   

## Multiplying Out and Factoring

### Sum-Of-Product (SOP)

> Definition: All products are the product of single variables

For example:

$AB' + CD'E + AC'E'$

$ABC' + DEFG + H$

$A + B' + C + D' + E$

are all sum-of-products.

But

$(A + B)CD + EF$

 is not SOP form.

#### Multiplying out

For example, to multiply out $(A + BC)(A + D + E)$

$(A + BC)(A + D + E)$

$ = A + BC(D + E) \implies$(By Distributive Law)

$ = A + BCD + BCE$

then we get its' SOP form.

### Product-Of-Sums (POS)

> Definition: All sums are the sums of single variables

For example:

$(A + B')(C + D' + E)(A + C' + E')$

$(A + B)(C + D + E)F$

$AB'C(D' + E)$

are all product of sums.

But

$(A + B)(C + D) = EF$

is not a POS form.

#### Factoring out

For example, to factoring out $A + B'CD$

$A + B'CD$

$ = (A + B')(A + CD)$

$ = (A + B')(A + C)(A + D)$

then we get the POS form.



Example 1. $AB' + C'D$

$AB' + C'D = (AB' + C')(AB' + D)$

$ = (A + C')(B' + C')(A + D)(B' + D)$



Example 2. $C'D + C'E' + G'H$

$C'D + C'E' + G'H$

$ = C'(D + E') + G'H$

$ = (C' + G'H)(D + E' + G'H)$

$ = (C' + G')(C' + H)(D + E' + G')(D + E' + H)$

### Demorgan's Laws

Definition: $(X + Y)' = X'Y',\space (XY)' = X' + Y'$

if we generalized to *n* variables:

$(X_1 + X_2 + X_3 + ... + X_n)' = X_1'X_2'X_3'...X_n'$

$(X_1X_2X_3...X_n)' = X_1' + X_2' + X_3' + ... + X_n'$



Example 1.

To find the complement of $(A' + B)C'$.

$(A' + B)C' = (A' + B)' + C = AB' + C$



Example 2.

To find the complement of $[(AB' + C)D' + E]'$

$[(AB' + C)D' + E]' = [(AB' + C)D']'E'$

$ = [(AB' + C)' + D]E' = [(AB')'C' + D]E'$

$ = [(A' + B)C' + D]E'$

**Note that in the single expression, the complement operation is applied only to single variables.**



