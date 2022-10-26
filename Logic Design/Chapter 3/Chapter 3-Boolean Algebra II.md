# Chapter 3-Boolean Algebra II

## Multiplying Out Factoring Expressions Distributive Laws

Given an expression in POS form, the corresponding SOP expression can be obtained by multiplying out, using the two distributive laws:

$X(Y+Z) = XY + YZ$

$(X + Y)(Y + Z) = X + YZ$

In addition, the following theoreom is also very useful for factoring and multiplying out:

$(X + Y)(X' + Z) = XZ + X'Y$

> Note that the variable that is paired of **X** on the one side of the equation is paired with **X'** on the othrer side, and vice verca.

### Example

1. $(A + B + C')(A + B + D)(A + B + E)(A + D' + E)(A' + C)$

   When you see an expression like this, don't try to multipy out.

   $= (A + B + C'D)(A + B + E)[AC + A'(D' + E)]$

   $ = (A + B + C'DE)(AC + A'D' + A'E)$

   $ = AAC + AA'D + AA'E + ABC + A'BD' + A'BE + ACC'DE + A'C'DD'E + A'C'DEE$

   $ = AC + ABC + A'BD + A'BE + A'C'DE$

   $ = AC(1 + B) + A'BD + A'BE + A'C'DE $

   $ = AC + A'BD + A'BE + A'C'DE$

2. $AC + A'BD' + A'BE + A'C'DE$

   $ = AC + A'(BD' + BE + C'DE)$

   $ = (A + BD' + BE + C'DE)(A' + C)$

   $ = [A + B(D' + E) + C'DE](A' + C)$

   $ = (A + B + C'DE)(A + C'DE + D' + E)(A' + C)$

   $ = (A + B + C')(A + B + D)(A + B + E)(A + D' + E)(A' + C)$

## Exclusive-OR and Equivalence Operations

### Definition:

1. Exclusive-OR ($\bigoplus$):

   <img src="figure 3.1.png" width="40%">
   > $X \bigoplus Y = X'Y + XY'$

   $0 \bigoplus 0 = 0$

   $0 \bigoplus 1 = 1$

   $ 1 \bigoplus 0 = 1$

   $1 \bigoplus 1 = 0$

2. Equivalence Ooperation ($\equiv$):

   <img src ="figure 3.2.png" width="40%">

   > $X \equiv Y = XY + X'Y'$

   $(0 \equiv 0) = 1$

   $(0 \equiv 1) = 0$

   $(1 \equiv 0) = 0$

   $(1 \equiv 1) = 1$

3. $(X\bigoplus Y)' = (X\equiv Y)$

   > equivalence is the complement of exclusive-OR
   >
   > equivalence is also called **exclusive-NOR**

### Simplifying an Expression

Example 1: 

$F = (A'B\equiv C) + (B\bigoplus AC')$

$ = (A'BC + (A'B)'C') + [B'(AC') + B(AC')']$

$ = A'BC + (A+B')C' + AB'C' + (A' + C)B$

$ = B(A'C + A' + C) + C'(A + B' + AB')$

$ = B(A' + C) + C'(A + B')$

## Consensus Theorem

### Definition: 

$XY + X'Z + YZ \lArr$ the term **YZ**

> The key to recognizing the consensus term is to first find a pair of terms, one of which contains a variable and the other its complement.

### Example:

1. $(a + b + c')\enclose{downdiagonalstrike}{(a + b + d')}(b + c +d')\rArr$ took $c$ and $c'$

2. $a'c'd + a'bd + bcd + abc + acd'$

   In this case, we can:

   1. $a'c'd + a'bd + \enclose{downdiagonalstrike}{bcd} + abc + acd'\rArr$ took $a$ and $a'$
   2. $a'c'd + \enclose{downdiagonalstrike}{a'bd} + bcd + \enclose{downdiagonalstrike}{abc} + acd'\rArr$ took $c$ and $c'$, $d$ and $d'$

3. $F = abcd + b'cde + a'b' + bce'$

   In this case, it is imposible to eliminate any pairs, but we can try this:

   $F = abcd + b'cde + a'b' + bce' + (acde)\rArr$ adding $acde$ from $abcd$ and $b'cde$ 

   then we find that $\rArr F = \enclose{downdiagonalstrike}{abcd} + \enclose{downdiagonalstrike}{b'cde} + a'b' + bce' + acde$

   Finally, we get $F = a'b' + bce' + acde$

## Algebraic Simplification of Switching Expressions

### Basic methods for simplifying functions

1. Combining terms:

   Definition: Use the theorem $XY + XY' = X$ to combine two terms.

   For example:

   1. $abc'd' + abcd' =abd\implies[X = abd',\space Y =c]$

   2. $(a + bc)(d + e') + a'(b' + c')(d + e') = d + e'\implies [X = d + e',\space Y = a + bc]$

2. Eliminating terms:

   Definition: Use the theorem $X + XY = X$ to eliminate redundunt terms, 

   ​					then try to apply the consensus theorem$(XY + X'Z + YZ = XY + X'Z)$.

   For example:

   1. $a'b + a'bc = a'b\implies [X = a'b]$
   2. $a'bc' + bcd + a'bd = abc' + bcd\implies [X = c,\space Y = bd,\space Z = a'b]$

3. Eliminating literals:

   Definition: Use the theorem $X + X'Y = X + Y$ to eliminate.

   For example:

   $a'b + a'b'c'd' + abcd' = a'(b + b'c'd') + abcd'$

   $ = a'(b + c'd') + abcd' = a'b + a'c'd' + abcd'$

   $ = b(a' + acd') + a'c'd' = b(a'+ cd') + a'c'd'$

   $ = a'b + bcd' + a'c'd'$

4. Adding redendant terms:

   Definition: several ways, such as:

   1. adding $xx'$
   2. multiplying by $(x + x')$
   3. adding $yz$ to $xy + x'z$
   4. adding $xy$ to $x$

   For example:

   $wx + xy + x'z' + xy'z'$

   $ = wx + xy + x'z' + wy'z' + wz'$

   $ = wx + xy + x'z' + wz'$

   $ = wx + xy + x'z'$

## Proving Validity of an Equation

> Often we will need to determine **if an equation is valid** for all combinations of values of the variables. Several methods can be used to determine if an equation is valid,

1. Construct a truth table. (too tedious)
2. Manipulate one side of the equation by applying various theorems.
3. Reduce both side to the same expression.

**Multiplying and adding both side of the equation is not permissible because division and subtraction is not difined for Boolean algebra.**

1. First reduce both sides to SOP or POS.
2. Compare.
3. Try to add terms to one side.
4. Eliminate.

> Frequently compare both sides of the equation and let the difference between them serve as a guide for what steps to take next.

Example 1.

$a'bd' + bcd + abc' + ab'd = bc'd' + ad + a'bc$

$\implies a'bd' + bcd + abc' + ab'd + bc'd' + a'bc + abd$ (starting from the left side)

$\implies ad + bc'd + a'bc$