---
id: imll
name: Intuitionistic multiplicative linear logic
short: IMLL
status: full correspondence on three sides; algebraizability open
bibliography: ../references.bib
logic:
  name: Intuitionistic multiplicative linear logic
  EPS: TODO            # EPS entry for ILL / IMLL
  presentations: [natural deduction, sequent calculus]
  connectives: [⊸, ⊗, I]
  structural_rules: [exchange]
  cut_elimination: yes
type_theory:
  name: Simply typed linear λ-calculus with tensor and unit
  type_formers: [⊸, ⊗, I]
  equations: [β, η, commuting conversions]
  normalization: strong
  equality_decidable: TODO
algebra:
  name: Lineales (commutative residuated partially ordered monoids)
  CAL: TODO            # CAL entry for commutative residuated pomonoids
  kind: TODO           # ordered structures; not obviously a variety without meets
  algebraizable: open
category:
  name: Symmetric monoidal closed categories
  free_object: syntactic category of the linear λ-calculus modulo βη and commuting conversions
correspondence:
  logic-type_theory:    { status: isomorphism }
  type_theory-category: { status: equivalence }
  category-algebra:     { status: posetal-reflection }
  logic-algebra:        { status: sound-and-complete }
---

# Intuitionistic multiplicative linear logic

This entry removes the structural rules of weakening and contraction from the [implication–conjunction fragment](ipl-imp-conj.md) and keeps only exchange, which is the first substructural step in the atlas. Without weakening and contraction each hypothesis is used exactly once, so conjunction splits into a multiplicative conjunction ⊗ and implication becomes linear implication ⊸. The four facets are natural deduction for the ⊗, ⊸, I fragment of intuitionistic linear logic, the linear λ-calculus, lineales and symmetric monoidal closed categories. Adding weakening and contraction back collapses ⊗ to ∧ and ⊸ to →, and on the algebraic facet a lineale whose tensor is the meet is exactly a Brouwerian semilattice.

## Logic

Formulas are built from propositional atoms with linear implication ⊸, tensor ⊗ and the unit I. Linear logic is due to Girard [@girard1987], and its intuitionistic fragment has a natural-deduction presentation in which contexts are multisets of hypotheses that are split, never shared, between premises:

$$
\begin{prooftree}
\AxiomC{$\Gamma, A \vdash B$}
\RightLabel{$\multimap\mathrm{I}$}
\UnaryInfC{$\Gamma \vdash A \multimap B$}
\end{prooftree}
\qquad
\begin{prooftree}
\AxiomC{$\Gamma \vdash A \multimap B$}
\AxiomC{$\Delta \vdash A$}
\RightLabel{$\multimap\mathrm{E}$}
\BinaryInfC{$\Gamma, \Delta \vdash B$}
\end{prooftree}
\qquad
\begin{prooftree}
\AxiomC{$\Gamma \vdash A$}
\AxiomC{$\Delta \vdash B$}
\RightLabel{$\otimes\mathrm{I}$}
\BinaryInfC{$\Gamma, \Delta \vdash A \otimes B$}
\end{prooftree}
\qquad
\begin{prooftree}
\AxiomC{$\Gamma \vdash A \otimes B$}
\AxiomC{$\Delta, A, B \vdash C$}
\RightLabel{$\otimes\mathrm{E}$}
\BinaryInfC{$\Gamma, \Delta \vdash C$}
\end{prooftree}
$$

together with the axiom A ⊢ A, the rule ⊢ I and an elimination rule for I with the same shape as ⊗E. Exchange is built into the use of multisets, while weakening (adding an unused hypothesis) and contraction (using a hypothesis twice) are absent. The sequent calculus for this fragment has cut elimination [@girard1987].

## Type theory

The Curry–Howard partner of IMLL is the linear λ-calculus, in which every variable in a term occurs exactly once [@bentonetal1993; @abramsky1993]. Terms are

$$
M ::= x \mid \lambda x{:}A.\ M \mid M\ N \mid M \otimes N \mid \mathsf{let}\ M\ \mathsf{be}\ x \otimes y\ \mathsf{in}\ N \mid \ast \mid \mathsf{let}\ M\ \mathsf{be}\ \ast\ \mathsf{in}\ N
$$

and the typing rules are the natural-deduction rules with terms attached, so the linearity condition on variables is exactly the splitting of contexts. The β-equations are

$$
(\lambda x.\ M)\ N = M[N/x] \qquad \mathsf{let}\ M \otimes N\ \mathsf{be}\ x \otimes y\ \mathsf{in}\ P = P[M/x, N/y] \qquad \mathsf{let}\ \ast\ \mathsf{be}\ \ast\ \mathsf{in}\ P = P
$$

and the η-equations say that λx.(M x) = M, that let M be x ⊗ y in x ⊗ y = M, and that let M be ∗ in ∗ = M. The elimination rules for ⊗ and I have the shape of disjunction elimination in IPL, so the calculus also needs commuting conversions that move a let past another elimination, for instance

$$
(\mathsf{let}\ M\ \mathsf{be}\ x \otimes y\ \mathsf{in}\ N)\ P = \mathsf{let}\ M\ \mathsf{be}\ x \otimes y\ \mathsf{in}\ (N\ P)
$$

Since no variable is ever duplicated, each β-step strictly decreases the size of a term, so for the fragment with linear implication alone normalization terminates in a number of steps bounded by the size of the term. This simple bound does not survive the addition of tensors: the commuting conversions for ⊗ and I do not decrease size, and Maria Emilia Maietti, Eike Ritter and de Paiva showed that bounding normalization becomes much harder once tensors are present [@maiettietal2002].

## Algebra

The posetal models of IMLL are the lineales of Hyland and de Paiva [@hylanddepaiva1991]. A lineale is a partially ordered set with a commutative monoid structure (⊗, I) that is monotone, and a binary operation ⊸ such that a ⊗ b ≤ c holds exactly when a ≤ b ⊸ c. Lineales are the same thing as the commutative residuated partially ordered monoids used by Troelstra as algebraic models of intuitionistic linear logic [@troelstra1992]. A lineale whose tensor is the meet and whose unit is the top element is a Brouwerian semilattice, which is how this entry sits under the first one.

A formula A is provable in IMLL iff I ≤ A under every valuation in every lineale, and the Lindenbaum–Tarski construction, ordering formulas by provable linear implication, gives the free lineale on the atoms. 

Under the original definition of Blok and Pigozzi [@blokpigozzi1989] the fragment is not algebraizable: without meets the order of a lineale is not definable by equations in the signature ⊗, ⊸, I, so the natural semantics is a class of ordered structures rather than a quasivariety. Algebraic logicians regard this as a limitation of the definition rather than of the logic, and which notion of algebraizability is the right one for linear logic is open.

## Category

A symmetric monoidal closed category has a tensor product ⊗ with unit I, symmetric and associative up to coherent isomorphism, and for each object A a right adjoint A ⊸ − to the functor − ⊗ A. Interpreting the connectives as these structures, a proof of B from hypotheses A₁, …, Aₙ becomes a morphism A₁ ⊗ ⋯ ⊗ Aₙ → B. The term model of the linear λ-calculus, modulo the β, η and commuting conversions, is the free symmetric monoidal closed category on the atoms [@bentonetal1993]. The coherence theorem of Kelly and Mac Lane [@kellymaclane1971] describes which diagrams commute in every symmetric monoidal closed category, and so which pairs of proofs are identified.

## Correspondence

Three maps of the square are as strong as for IPL, and the fourth depends on the choice of consequence relation. Between logic and type theory the Curry–Howard isomorphism is a bijection between linear natural-deduction proofs and linear terms, with normalization, including commuting conversions, as reduction. Between type theory and category the correspondence is an equivalence, since the term model is the free symmetric monoidal closed category. Between category and algebra the map is the posetal reflection, because a lineale is exactly a symmetric monoidal closed partial order. Between logic and algebra the logic is sound and complete for lineales, with the free lineale as Lindenbaum–Tarski algebra, while algebraizability in the Blok–Pigozzi sense is recorded as open.

Removing weakening and contraction changes the categorical facet from cartesian to monoidal closure. The tensor of a symmetric monoidal closed category has no projections A ⊗ B → A or diagonals A → A ⊗ A in general, and those are exactly the categorical forms of the two missing structural rules.

## References

::: {#refs}
:::
