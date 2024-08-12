- $A\in \mathbb{R}^{m\times n}$
- Solving $y=Ax\in \mathbb{R}^m$ 
- Determined ($m=n$): $A$ is square matrix
- over-determined ($m>n$): $\displaystyle\min_x \| Ax-y \|$
    - $x=(A^TA)^{-1}A^Ty\defeq A^{+}y$
    - $y \approx Ax$
- under-determined ($m<n$): $\displaystyle\min_x \{ \| x \| ; Ax=y \}$
    - $x=A^T(AA^T)^{-1}y\defeq A^{+}y$
    - $y = Ax$
- $A$ ill-posed and/or noise:
    - $\displaystyle\min_x \| Ax-y \| ^2 + \lambda \| x \| ^2$
    - $x=(A^TA+\lambda Id_n )^{-1}A^Ty \rightarrow^{\lambda\rightarrow 0} A^{+}y=A^T(AA^T + \lambda Id_m)^{-1}y$ (Woodbury formula)