# 2. Two-Dimensional Foil Attack (foil.cpp | Foil.java)

## Problem Description

Trisolarans accidentally acquired the technology of two-dimensional foil (二向箔), and intend to attack an unknown planetary system. Due to self-rotation and gravity, a star system's matter collapses, preserving angular momentum and reducing the system to a 2D plane. All planets are given as points on this plane, with coordinates $(x, y)$.

The two-dimensional foil's attack range is represented by an ellipse:

$$Ax^2 + Bxy + Cy^2 + Dx + Ey + F \leq 0$$

The cost of deploying the foil is related to the area it covers. Trisolarans want you to help them minimize the area of the ellipse such that all planets are covered (inside or on the border).

---

## Hint

The familiar ellipse formula from high school $\frac{x^2}{a^2} + \frac{y^2}{b^2} \leq 1$ can be written in matrix form:

$$[x \quad y] \begin{bmatrix} 1/a^2 & 0 \\ 0 & 1/b^2 \end{bmatrix} \begin{bmatrix} x \\ y \end{bmatrix} \leq 1$$

Rotation, scaling, and translation are linear transformations. The area of this ellipse is $\pi ab$.

---

## Key Points

- **Input**: Set of planet coordinates $(x_i, y_i)$
- **Goal**: Find the minimum area ellipse that contains all planets
- **Constraint**: All planets must be inside or on the boundary of the ellipse
- **Optimization objective**: Minimize ellipse area

## Approach

This is a **convex optimization problem**. The general form of an ellipse can be expressed using the quadratic inequality shown above, and the problem involves finding the coefficients $A, B, C, D, E, F$ that:

1. Ensure all points satisfy the inequality (coverage constraint)
2. Minimize the resulting ellipse area

The hint suggests using matrix representations and understanding that transformations preserve the ellipse structure while changing its area by a factor related to the transformation's determinant.