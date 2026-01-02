---
title: "Linear Independence and Uniqueness of Representation"
date: 2026-01-02
categories: proof-diary
tags: [linear-algebra]
---

### Statement

Let \( \vec v_1, \ldots, \vec v_m \in \mathbb{K}^n \).  
The following are equivalent:

1. \( \{\vec v_1, \ldots, \vec v_m\} \) is linearly independent.
2. The equation  
   \[
   \vec 0 = c_1 \vec v_1 + \cdots + c_m \vec v_m
   \]
   has a unique solution \( c_1 = \cdots = c_m = 0 \).
3. Every vector \( \vec b \in \mathrm{span}(\vec v_1, \ldots, \vec v_m) \) has a unique representation as a linear combination of the vectors.

---

### Idea / Strategy

Linear independence can be understood as the absence of ambiguity in linear combinations.
If the zero vector has only the trivial representation, then no vector in the span can have two different representations.
The proof proceeds by comparing two representations and subtracting them.

---

### Proof

(1) ⇒ (2):  
If the vectors are linearly independent, then by definition the only linear combination equal to \( \vec 0 \) is the trivial one. Hence the solution is unique.

(2) ⇒ (3):  
Suppose  
\[
\vec b = c_1 \vec v_1 + \cdots + c_m \vec v_m
= d_1 \vec v_1 + \cdots + d_m \vec v_m.
\]
Subtracting gives
\[
\vec 0 = (c_1 - d_1)\vec v_1 + \cdots + (c_m - d_m)\vec v_m.
\]
By uniqueness in (2), all coefficients must be zero, so \( c_i = d_i \) for all \( i \).

(3) ⇒ (2):  
Apply (3) to \( \vec b = \vec 0 \). Since the trivial combination always works, uniqueness implies it is the only one.

Thus all three statements are equivalent.

---

### Remarks

This result explains why linearly independent sets provide coordinate systems for their span.
It also motivates the definition of a basis as a set with both spanning and uniqueness properties.
