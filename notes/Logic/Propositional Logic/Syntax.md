# Alphabet

## Logical Symbols

- Logical Connectives
	- Unary connective
		- **negation**, (or **logical not**, **logical complement**) $\lnot$
	- Binary connectives (notation: we use in $@$ for any binary connective)
		- **Logical disjunction** $\lor$
		- **Logical conjunction** $\land$
		- **Material conditional** (or **material implication**) $\rightarrow$
		- **logical biconditional** (or **material biconditional**) $\leftrightarrow$ 
	- $n$-ary connective
- Punctuation: '$($' and '$)$'

## Non-Logical Symbols

- (Proposition Variables) $\mathcal{P}= \{ P_{1},P_{2},\dots ,P_{n},\dots  \}$ 

> also called: sentence symbols, elementary proposition (פסוק אלמנטרי)

# Propositions

## Definition

We define the set ${\mathcal{L}}$ of all propositions generated by the set $\mathcal{P}$ of a proposition variables
### Recursive Definition

- Any string with one proposition variable is a **proposition**
- Any proposition preceded by $¬$ is a **proposition**
- Any two propositions can be made into another **proposition** by writing one of these symbols between them, $∧, ∨, →, ↔$ and enclosing the result in parentheses
### Induction Defintion

- $E_{0}$ is the set of of **elementary propositions** with one symbol
- Given $E_{n-1}$ is defined: $E_{n}$ is the set of all strings in $E_{n-1}$ in additional all strings $(\varphi\land\psi)$, $(\varphi\lor\psi)$, $(\varphi\rightarrow\psi)$, and $(\varphi\leftrightarrow\psi)$ for which $\psi$ and $\varphi$ are in $E_{n-1}$
- A string is called a **proposition** if and only if, it is in one of the sets $E_{n}$ 
- Depth:
	- The **depth** of a proposition $\varphi$, denoted by $d(\varphi)$, is the smallest number $n$ such that $\varphi\in E_{n}$ 
	- A proposition $\varphi$ is an elementary proposition, if and only if, $d(\varphi)=0$
	- Given a proposition φ, we define its depth to be 1 + the length of the longest path of its parse tree
	- $d(P)=0$ for each elementary proposition $P$, and $d(\lnot\varphi)=d(\varphi)+1$, and $d((\varphi @ \psi))=\max(d(\varphi),d(\psi))+1$ for each binary connective @ and propositions $\varphi$ and $\psi$.


> [!NOTE] Necessary and sufficient conditions for a string to be a proposition
> - It is a proposition
> - It is construct from elementary proposition and connectives according to the allowed construction rules
> - it is in one of the sets $E_{n}$
> - It has a structure tree
> - It has a formation sequence


## Unique Readability

The propositions are naturally divided into three types:

- Elementary propositions
- Negation propositions, of the form $\lnot\alpha$, where $\alpha$ is a proposition. In other words, a string whose first symbol is the negation connective, and the rest of the string is also a proposition.
- Compound propositions, which are of the form $(\alpha{@}\beta)$, where $\alpha$ and $\beta$ are propositions.

- The Unique Readability Theorem (2.2)
	- Every proposition belongs to one of the three types we described, and to only one.
	- Every compound proposition is of the form $(\alpha{@}\beta)$ for some connective $@$ and for a pair of single propositions, $\alpha$ and $\beta$. 
		- The position of this connective in the string $(\alpha{@}\beta)$ is characterized by the following: after removing the outer parentheses, it is the unique binary connective in the string $\alpha{@}\beta$ such that the segment to its left has an equal number of left and right parentheses (any other binary connective before or after it has an excess of left parentheses to its left.)

- In a negation proposition $\lnot{\alpha}$, the connective $\lnot$ is called the **main connective** of the proposition and $\alpha$ is called the **main component** of the proposition
- In a compound proposition, $(\alpha{@}\beta)$, the connective $@$ is called the **main connective** of the proposition and $\alpha$ and $\beta$ are called the **main components** of the proposition

- (q2.6) A proper prefix of a proposition is not a proposition


## Structure Tree 

The unique readability theorem provides us with an algorithm that, given a string of propositional keyboard symbols, does the following:

1. Determines whether the string is a proposition.
2. If the string is a non-elementary proposition, the algorithm finds the main connective and main components.
3. As long as the components are not elementary propositions, the algorithm continues to analyze them in the same way.
4. The algorithm presents the analysis result as a tree where the given proposition's root appears, all the sub-propositions of the given proposition are written in nodes, and the branches of each node are the main components of the proposition at that node.


## Structural Induction

### Proving Properties on Propositions 

- (Theorem 2.1)
	- Let $R$ be a property of some (or all) the strings. Given:
		- Every elementary proposition has the property $R$
		- If a proposition $\varphi$ has the property $R$ then $\lnot\varphi$ has the property $R$ as well
		- For each binary connective @, if $\varphi$ and $\psi$ has the property $R$, then $(\varphi{@}\psi)$ has the property $R$ as well
	- Then, every proposition has the property $R$

### Defining 

- (2.3) Defintion using Structural Induction
	- (informal version) We can define function from the set of propositions to a set $A$
		- Define $f(e)$ for each elementary proposition $e$
		- Define $f(\lnot{\psi})$ (by the value of $f(\psi)$ given exists)
		- Define $f(\psi @\theta )$ for each binary connective $@$. (by the values of $f(\psi)$ and $f(\theta)$  given exist)
	
	- (formal version) Let $f_{e}$ a function from the set of elementary propositions to the set $A$, and let $C_{\lnot}(x):A\to A$ a function, and for each binary contective $@$ let $C_{@}(x,y):A \times A\to A$, then, there only one function $f$ from the set of elementary propositions to the set $A$, such that:
		- if $\varphi$ is an elementary proposition, then $f(\varphi)=f_e(\varphi)$
		- if $\varphi=\lnot\psi$, then $f(\varphi)=C_{\lnot}(f_{e}(\psi))$
		- if $\varphi=(\psi @ \theta)$ then $f(\varphi)=C_{@}(f(\psi),f(\theta))$
- (2.4) locality of defintion using Structural Induction
	- Let $L_{1}$ and $L_{2}$ be proportional languages (possibly the same), and let $\varphi$ be a proposition in both (and therefore the elementary propositions in $\varphi$ are in both languages). and let $A$ be a set. and let $F_{1}:L_{1}\to A$ and $F_{2}:L_{2}\to A$ functions defiend in structural Induction, such that, 
		- (1.) the functions $C_{\lnot}:A\to A$ and $C_{@}:A \times A\to A$ in the function defintions of $F_{1}$ and $F_{2}$ are the same.
		- (2.) $F_{1}(Q)=F_{2}(Q)$ for each elementary proposition $Q$ in the string $\varphi$.
		- Then: $F_{1}(\varphi)=F_{2}(\varphi)$.

## Substitution

- We say that a string $\varphi'$ is obtained from a string $\varphi$ by **substitution** if $\varphi'$ is obtained from $\varphi$ by replacing all occurrences of a the string $Q$ in $\varphi$ by a string $\psi$. We denote this by $\varphi[\psi/Q]$


## Parentheses

- Every proposition is parentheses **balanced**, that is, the number of left parentheses equals the number of right parentheses.
- Let $S$ be a string representing a proposition. 
	- At any prefix, the number of left parentheses is greater than or equal to the number of right parentheses
	- At any suffix, the number of right parentheses is greater than or equal to the number of left parentheses
- Every binary connective in a proposition sees more left parentheses to its left (and more right parentheses to its right).
## Subproposition

- (2.5) $\psi$ is called a **subproposition** of $\varphi$ if and only if it is substring of $\varphi$ which is also a proposition
- (2.6) If $\alpha\theta\beta$ and $\theta$ and $\psi$ are propositions, then $\alpha\psi\beta$ is also a proposition

## Formation Sequence

- A **formation sequence** (סדרת בנייה) is a finite sequence $\varphi_{1},\dots,\varphi_{n}$ of propositions such that each term is obtained from the previous terms by applying one of the rules of formation of propositions.
- A **formation sequence for $\varphi$** is a formation sequence whose last term is $\varphi$.
- (2.9)
	- (A.) A prefix of a formation sequence is also a formation sequence
	- (B.) For each proposition $\varphi$, there exists a formation sequence that all its strings are subpropositions of $\varphi$.
	- (C.) Every subproposition of a proposition appears in every formation sequence for the proposition.
- A string is a proposition if and only if it has a formation sequence
- A proposition $\psi$ is a subproposition of a proposition $\varphi$ if and only if $\psi$ appears in every formation sequence for $\varphi$.



## BNF Grammar


```xml
<P> ::= <EP> | <Neg> | <BiP>
<EP> ::= P | Q | R | ...
<Neg> ::= ¬<P>
<BiP> ::= (<P>∧<P>) | (<P>∨<P>) | (<P>→<P>) | (<P>↔<P>)
```

# Normal Forms 

## CNF & DNF

| Course Term             |                                                                             | BNF                                                                             |
| ----------------------- | --------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| קוניונקציה מרובה        | $\varphi_{1} \land\dots \land \varphi_{n}$                                  |                                                                                 |
| דיסיונקציה מרובה        | $\varphi_{1} \lor\dots \lor \varphi_{n}$                                    |                                                                                 |
| פסוק בסיסי              | $P$ or $\lnot P$                                                            | **Literal**<br>*Literal→¬Variable*<br>*Literal→Variable*<br>                    |
|                         |                                                                             | **Disjunction**<br>Disjunction→Literal∨Disjunction<br>Disjunction→Literal       |
| קוניונקציה פשוטה        | קוניונקציה מרובה של פסוקים בסיסיים                                          | **Conjunction**<br>Conjunction→Literal∧Conjunction<br>Conjunction→Literal       |
| פסוק דיסיונקטיבי נורמלי | דיסיונקציה של קוניוקציות פשוטות                                             | **Disjunctive normal form (DNF)**<br>DNF→(Conjunction)∨DNF<br>DNF→(Conjunction) |
|                         |                                                                             | **Conjunctive normal form (CNF)**<br>CNF→(Disjunction)∨CNF<br>CNF→(Disjunction) |
| קוניונקציה פשוטה מלאה   | קוניונקציה פשוטה שמופיעה בה כל פסוק אלמנטרי (לחיוב או לשלילה) בדיוק פעם אחת | **Full Conjunction**                                                            |
|                         |                                                                             |                                                                                 |
|                         |                                                                             |                                                                                 |


- Notation of full conjunction: $C=\varepsilon_{1}P_{1}\land\dots \land \varepsilon_nP_{n}$
- In a language $L_{n}$ with the elementary propositions $\{ P_{1},\dots,P_{n} \}$ there are exactly $2^n$ full conjunctions 

- (3.5) Every proposition has an equivalent DNF (see algorithm 3.3.2.1 #todo )

- A CNF is a conjunction of clauses
- A **clause** is a disjunction (or rarely, conjunction) of literals