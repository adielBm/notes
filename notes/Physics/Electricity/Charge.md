# Electric charge

- Electric charge is **quantized**, that is, exists in discrete quantities which are integer multiples of the **elementary charge** $e=1.6022\times 10 ^{-19}\,\mathsf{C}\approx 1.6\times 10^{-19}\,\mathsf{C}$
	- The charge of an electron is $-e$ and the charge of a proton is $+e$
	- The SI unit of charge is the **coulomb** (C)
- **Conservation of charge**: the total charge in an isolated system remains constant
- An object can become charged by:
	- rubbing (friction)
	- conduction (transfer of charge from one charged object to another by touching)
	- induction


## Coulomb's Law

```tex
\documentclass[varwidth]{standalone}
\usepackage{xcolor,tikz,amsmath}
\newcommand*\circled[2]{\tikz[baseline=(char.base)]{\node[shape=circle,draw,fill=#1,inner sep=2pt] (char) {#2};}}
\begin{document}
$\underset{q_1}{\circled{red!40}{$\pm$}}$ 
$\underset{\vec{\mathbf{F}}_{12}}{\longrightarrow}$ 
$\underset{\vec{\mathbf{F}}_{21}}{\longleftarrow}$ 
$\underset{q_2}{\circled{blue!40}{$\mp$}}$
\\
$\underset{\vec{\mathbf{F}}_{12}}{\longleftarrow}$
$\underset{q_1}{\circled{red!40}{$\pm$}}$
$\underset{q_2}{\circled{red!40}{$\pm$}}$ 
$\underset{\vec{\mathbf{F}}_{21}}{\longrightarrow}$
\end{document}
```

- $\displaystyle F=k\frac{q_1q_2}{r^2}$ is the **electrostatic force** (or **Coulomb force**) between two charges (in $\mathsf{N}$)
	- $q_1$ and $q_2$ are the magnitudes of the charges (in $\mathsf{C}$)
	- $r$ is the distance between the charges (in $\mathsf{m}$)
	- $\displaystyle k=\frac{1}{4\pi\epsilon_{0}}=8.99\times 10^9\ \mathsf{N\cdot m^2/C^2}$ is **Coulomb's constant**
	- $\epsilon_{0}=\frac{1}{4\pi k}=8.85\times 10^{-12}\ \mathsf{C^2/N\cdot m^2}$ is the **permittivity of free space**

- limitations and assumptions of Coulomb's Law #todo
	- point charges
	- objects are at rest (electrostatics force)
	- electric force




## Electric field

- The **electric field** of is defined as a vector field that associates to each point in space the force per unit of charge exerted on an infinitesimal test charge at rest at that point
- SI unit of electric field is $\mathsf{N/C}=\mathsf{V/m}$
- $k$ is Coulomb's constant
- $\displaystyle E=\frac{F}{q}$ (vector form: $\displaystyle \vec{\mathbf{E}}=\frac{\vec{\mathbf{F}}}{q}$)
	- $E$ is the electric field that a charge $q$ experiences (in $\mathsf{N/C}$)
	- $F$ is the force on a charge (in $\mathsf{N}$)
	- $q$ is the test charge (in $\mathsf{C}$)
- $E=-\frac{V_{ba}}{d}$ is the electric field (uniform $\vec{\mathbf{E}}$)
	- $V_{ba}$ is the potential difference between points $a$ and $b$ (in $\mathsf{V}$)
	- $d$ is the distance between the points (in $\mathsf{m}$)

### Electric field of a single point charge

- $\displaystyle E =k\frac{Q}{r^2}$ (vector form: $\displaystyle \vec{\mathbf{E}}=k\frac{Q}{r^2}\hat{\mathbf{r}}$)
	- $P$ is the point in space where the electric field is being calculated
	- $Q$ is the point charge creating the electric field (in $\mathsf{C}$)
	- $E$ is the electric field created by a point charge $Q$ (in $\mathsf{N/C}$)
	- $r$ is the distance between the charge and the point in space (in $\mathsf{m}$)
	- $\hat{\mathbf{r}}$ is the unit vector pointing from the charge to the point in space



```tex
\usepackage{tikz}
\usetikzlibrary{arrows.meta}
\definecolor{_red}{HTML}{D63146}
\definecolor{_pink}{HTML}{ef3875}
\definecolor{_green}{HTML}{5dc3ad}
\newcommand{\customarrow}[5]{
	\draw[ultra thick, arrows = {-Stealth[reversed, reversed]}, color=#4] (#1,#2) -- (#3,#2) node[midway, below] {#5};
}
\begin{document}
\begin{tikzpicture}
\customarrow{0}{0}{1}{_red}{$\vec{\mathbf{E}}$}
\draw[fill] (0,0) circle [radius=0.08] node[above] {$P$};
\draw[fill=_green, draw=none] (2,0) circle [radius=0.2] node[right, xshift=0.2cm] {$Q$};
\node at (2, 0) {$-$};
\node at (4, 0) {$\mathsf{negative\ charge}$};
\draw[|-|] (0,0.7) -- (2,0.7) node[midway, below] {$r$};
\customarrow{0}{-1}{-1}{_red}{$\vec{\mathbf{E}}$}
\draw[fill] (0,-1) circle [radius=0.08] node[above] {$P$};
\draw[fill=_pink, draw=none] (2,-1) circle [radius=0.2] node[right, xshift=0.2cm] {$Q$};
\node at (2, -1) {$+$};
\node at (4, -1) {$\mathsf{positive\ charge}$};
\end{tikzpicture}
\end{document}
```

> There is no electric charge at point $P$. But there is an electric field there. The only real charge is $Q$.

### Superposition principle

- the total force on a charge is the vector sum of the forces exerted by the other charges

### todo

- electric field lines
- electric dipole
- static electric field
- equipotential surfaces, equipotential lines