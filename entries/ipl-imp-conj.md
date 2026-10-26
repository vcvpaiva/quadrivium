---
id: ipl-imp-conj
name: Implication–conjunction fragment of intuitionistic propositional logic
short: IPL(→,∧)
status: full correspondence
bibliography: ../references.bib
logic:
  name: Implication–conjunction fragment of IPL
  EPS: TODO            # EPS entry for NJ / LJ restricted to →, ∧, ⊤
  presentations: [natural deduction NJ, sequent calculus LJ]
  connectives: [→, ∧, ⊤]
  structural_rules: [weakening, contraction, exchange]
  cut_elimination: yes
type_theory:
  name: Simply typed λ-calculus with products
  type_formers: [→, ×, 1]
  equations: [β, η]
  normalization: strong
  equality_decidable: yes
algebra:
  name: Brouwerian semilattices (implicative semilattices)
  CAL: TODO            # CAL entry for Brouwerian semilattices
  kind: variety
  algebraizable: yes
category:
  name: Cartesian closed categories
  free_object: syntactic category of the λ-calculus modulo βη
correspondence:
  logic-type_theory:    { status: isomorphism }
  type_theory-category: { status: equivalence }
  category-algebra:     { status: posetal-reflection }
  logic-algebra:        { status: algebraizable }
---

# Implication–conjunction fragment of intuitionistic propositional logic

The fragment of intuitionistic propositional logic with only implication, conjunction and truth is the starting point of the atlas, because it is the case in which all four facets match with no extra machinery. Its proofs are the terms of the simply typed λ-calculus with products, its algebras are the Brouwerian semilattices, and its categories are the cartesian closed categories. Adding disjunction and falsity, as in the entry for full IPL, already requires commuting conversions and makes equality of proofs hard to decide; nothing of the kind happens here.

## Logic

Formulas are built from propositional atoms with the connectives → and ∧ and the constant ⊤. In natural deduction [@prawitz1965] each connective has introduction and elimination rules:

$$
\begin{prooftree}
\AxiomC{$[A]$}
\noLine
\UnaryInfC{$\vdots$}
\noLine
\UnaryInfC{$B$}
\RightLabel{$\to\mathrm{I}$}
\UnaryInfC{$A \to B$}
\end{prooftree}
\qquad
\begin{prooftree}
\AxiomC{$A \to B$}
\AxiomC{$A$}
\RightLabel{$\to\mathrm{E}$}
\BinaryInfC{$B$}
\end{prooftree}
\qquad
\begin{prooftree}
\AxiomC{$A$}
\AxiomC{$B$}
\RightLabel{$\land\mathrm{I}$}
\BinaryInfC{$A \land B$}
\end{prooftree}
\qquad
\begin{prooftree}
\AxiomC{$A_1 \land A_2$}
\RightLabel{$\land\mathrm{E}_i$}
\UnaryInfC{$A_i$}
\end{prooftree}
\qquad
\begin{prooftree}
\AxiomC{}
\RightLabel{$\top\mathrm{I}$}
\UnaryInfC{$\top$}
\end{prooftree}
$$

where ∧E has two versions, one for each conjunct. The sequent calculus LJ restricted to these connectives has cut elimination [@gentzen1935], and full IPL is conservative over the fragment, so a formula in →, ∧ and ⊤ is provable here exactly when it is provable in full IPL. All three structural rules are present.

## Type theory

The Curry–Howard partner of this fragment [@howard1980] is the simply typed λ-calculus with function types, binary products and a unit type. Application is written by juxtaposition, and the dot in an abstraction only separates the bound variable from the body. Terms are

$$
M ::= x \mid \lambda x{:}A.\ M \mid M\ N \mid \langle M, N\rangle \mid \pi_1 M \mid \pi_2 M \mid \langle\rangle
$$

and each typing rule is the corresponding natural-deduction rule with terms attached, so a derivation of x₁:A₁, …, xₙ:Aₙ ⊢ M : B is exactly a proof of B from A₁, …, Aₙ. The equations are β and η for each type former:

$$
(\lambda x.\ M)\ N = M[N/x] \qquad \pi_i\langle M_1, M_2\rangle = M_i \qquad \lambda x.\ (M\ x) = M \quad (x \notin \mathrm{FV}(M)) \qquad \langle \pi_1 M, \pi_2 M\rangle = M \qquad M = \langle\rangle \quad (M : 1)
$$

Reading β from left to right gives a reduction that is strongly normalizing, by Tait's reducibility method [@tait1967], and confluent. A β-redex is a detour in a proof, an introduction immediately followed by an elimination, and β-reduction is Prawitz's proof normalization. Normal forms have the subformula property without any further conversions. Equality modulo βη is decided by computing β-normal η-long forms [@girardlafonttaylor1989].

## Algebra

A Brouwerian semilattice, also called an implicative semilattice [@nemitz1965], is a meet-semilattice with a top element 1 and a binary operation → such that a ∧ b ≤ c holds exactly when a ≤ b → c. Brouwerian semilattices form a variety. Every Heyting algebra is a Brouwerian semilattice by forgetting joins and the bottom element, and every finite Brouwerian semilattice is the →,∧ reduct of a Heyting algebra.

The fragment is algebraizable in the sense of Blok and Pigozzi [@blokpigozzi1989], with the variety of Brouwerian semilattices as its equivalent algebraic semantics: a formula is provable iff it evaluates to 1 under every valuation in every Brouwerian semilattice. The Lindenbaum–Tarski algebra of the fragment on a set of atoms is the free Brouwerian semilattice on those atoms.

## Category

A cartesian closed category has finite products and exponentials. Interpreting atoms as objects, ∧ as binary product, ⊤ as the terminal object 1 and → as exponential, a proof of B from A₁, …, Aₙ becomes a morphism A₁ × ⋯ × Aₙ → B, and the β and η equations are exactly the equations of the adjunction between − × A and the exponential (−)^A, together with the universal properties of products and the terminal object. Lambek and Scott [@lambekscott1986] proved that the syntactic category of the λ-calculus modulo βη, with types as objects and terms in one free variable as morphisms, is the free cartesian closed category on the atoms. They also showed the converse direction: every cartesian closed category has an internal language which is a typed λ-calculus of this kind, so the two notions are equivalent.

## Correspondence

All four maps of the square are present and as strong as one could ask. Between logic and type theory the Curry–Howard isomorphism is a bijection between natural-deduction proofs and typed terms, under which proof normalization is β-reduction. Between type theory and category the Curry–Howard–Lambek correspondence is an equivalence, since the term model modulo βη is the free cartesian closed category and every cartesian closed category is the model of its internal language. Between category and algebra the map is the posetal reflection: a Brouwerian semilattice is exactly a cartesian closed preorder, and identifying all parallel morphisms of the free cartesian closed category gives the free Brouwerian semilattice. Between logic and algebra the map is provability, recorded by algebraizability.

The categorical and type-theoretic facets distinguish proofs, while the algebraic facet keeps only provability. The two proofs λx.λy.x and λx.λy.y of A → A → A, for instance, are different morphisms in the free cartesian closed category and the same element 1 in the free Brouwerian semilattice. This fragment is the reference case of the atlas, where every facet exists, the equational theory of proofs is decidable, and no conversions beyond β and η are needed.

## References

::: {#refs}
:::

