---
id: ipl
name: Intuitionistic propositional logic
short: IPL
status: full correspondence
bibliography: ../references.bib
logic:
  name: Intuitionistic propositional logic
  EPS: TODO            # EPS entry for NJ / LJ
  presentations: [natural deduction NJ, sequent calculus LJ]
  connectives: [→, ∧, ∨, ⊤, ⊥]
  structural_rules: [weakening, contraction, exchange]
  cut_elimination: yes
type_theory:
  name: Simply typed λ-calculus with products and sums
  type_formers: [→, ×, +, 1, 0]
  equations: [β, η, commuting conversions]
  normalization: strong
  equality_decidable: yes
algebra:
  name: Heyting algebras
  CAL: TODO            # CAL entry for Heyting algebras
  kind: variety
  algebraizable: yes
category:
  name: Bicartesian closed categories
  free_object: syntactic category of the λ-calculus with sums modulo βη
correspondence:
  logic-type_theory:    { status: isomorphism }
  type_theory-category: { status: equivalence }
  category-algebra:     { status: posetal-reflection }
  logic-algebra:        { status: algebraizable }
---

# Intuitionistic propositional logic

This entry extends [the implication–conjunction fragment](ipl-imp-conj.md) with disjunction and falsity, and it is the first case in the atlas where the four facets still match but the type-theoretic facet needs more than β and η. Disjunction corresponds to sum types, falsity to the empty type, and on the other two facets the Brouwerian semilattices become Heyting algebras and the cartesian closed categories become bicartesian closed. The new connectives bring commuting conversions into proof normalization, and they make equality of proofs much harder to decide.

## Logic

Formulas are built from propositional atoms with the connectives →, ∧ and ∨ and the constants ⊤ and ⊥, and negation is defined as ¬A = A → ⊥. Natural deduction for full IPL [@prawitz1965; @eps2017] adds to the rules of the fragment the introduction and elimination rules for disjunction and the elimination rule for falsity:

$$
\begin{prooftree}
\AxiomC{$A_i$}
\RightLabel{$\lor\mathrm{I}_i$}
\UnaryInfC{$A_1 \lor A_2$}
\end{prooftree}
\qquad
\begin{prooftree}
\AxiomC{$A \lor B$}
\AxiomC{$[A]$}
\noLine
\UnaryInfC{$\vdots$}
\noLine
\UnaryInfC{$C$}
\AxiomC{$[B]$}
\noLine
\UnaryInfC{$\vdots$}
\noLine
\UnaryInfC{$C$}
\RightLabel{$\lor\mathrm{E}$}
\TrinaryInfC{$C$}
\end{prooftree}
\qquad
\begin{prooftree}
\AxiomC{$\bot$}
\RightLabel{$\bot\mathrm{E}$}
\UnaryInfC{$C$}
\end{prooftree}
$$

There is no introduction rule for ⊥. The sequent calculus LJ has cut elimination [@gentzen1935], and all three structural rules are present.

## Type theory

The Curry–Howard partner of IPL is the simply typed λ-calculus of the fragment extended with binary sums and an empty type [@girardlafonttaylor1989, ch. 10]. The new terms are

$$
M ::= \cdots \mid \mathsf{inl}\ M \mid \mathsf{inr}\ M \mid \mathsf{case}\ M\ \mathsf{of}\ \lbrace \mathsf{inl}\ x \Rightarrow N;\ \mathsf{inr}\ y \Rightarrow P \rbrace \mid \mathsf{abort}_A\ M
$$

and the new β-equations say that a case on an injection picks the corresponding branch:

$$
\mathsf{case}\ (\mathsf{inl}\ M)\ \mathsf{of}\ \lbrace \mathsf{inl}\ x \Rightarrow N;\ \mathsf{inr}\ y \Rightarrow P \rbrace = N[M/x]
$$

and symmetrically for inr. With sums, β-reduction alone no longer gives normal forms with the subformula property, because an elimination can be blocked behind a case. The commuting (permutative) conversions move such an elimination into the branches, for instance

$$
\pi_1 (\mathsf{case}\ M\ \mathsf{of}\ \lbrace \mathsf{inl}\ x \Rightarrow N;\ \mathsf{inr}\ y \Rightarrow P \rbrace) = \mathsf{case}\ M\ \mathsf{of}\ \lbrace \mathsf{inl}\ x \Rightarrow \pi_1 N;\ \mathsf{inr}\ y \Rightarrow \pi_1 P \rbrace
$$

and similarly for abort. Prawitz proved strong normalization for full natural deduction including these conversions [@prawitz1971].

Equality is subtler than reduction. The η-law for sums cannot be oriented as a terminating rewrite rule, and deciding βη-equality with sums took until the 1990s. Neil Ghani gave a decision procedure for binary sums [@ghani1995], Altenkirch, Dybjer, Hofmann and Scott gave another by normalization by evaluation [@altenkirchetal2001], and Gabriel Scherer settled the case with the empty type [@scherer2017].

## Algebra

A Heyting algebra is a bounded lattice with a binary operation → such that a ∧ b ≤ c holds exactly when a ≤ b → c. Equivalently, it is a Brouwerian semilattice that also has binary joins and a bottom element 0. Heyting algebras form a variety and are automatically distributive, and every finite distributive lattice carries a unique Heyting structure. Negation is ¬a = a → 0, and a Heyting algebra is Boolean exactly when ¬¬a = a for all a.

IPL is algebraizable [@blokpigozzi1989], with the variety of Heyting algebras as its equivalent algebraic semantics: a formula is provable iff it evaluates to 1 under every valuation in every Heyting algebra. The Lindenbaum–Tarski algebra of IPL on a set of atoms is the free Heyting algebra on those atoms. The completeness theorem in this algebraic form is due to Helena Rasiowa and Roman Sikorski [@rasiowasikorski1963].

## Category

A bicartesian closed category is a cartesian closed category that also has finite coproducts. Disjunction is interpreted as binary coproduct and ⊥ as the initial object 0, so a proof by cases becomes the copairing map out of a coproduct, and ex falso becomes the unique map out of 0. Since − × A is a left adjoint it preserves coproducts, so products distribute over sums in every bicartesian closed category, which is the categorical form of the distributivity of Heyting algebras. In a cartesian closed category the initial object is strict: any object with a map into 0 is itself initial. The syntactic category of the λ-calculus with sums modulo βη is the free bicartesian closed category on the atoms, extending the result of Lambek and Scott for the cartesian closed case [@lambekscott1986].

## Correspondence

The four maps of the square are the same as in the implication–conjunction fragment, and each one extends to the new connectives. Between logic and type theory the Curry–Howard isomorphism is a bijection between natural-deduction proofs and typed terms, under which proof normalization, now including commuting conversions, is term reduction. Between type theory and category the correspondence is an equivalence, since the term model modulo βη is the free bicartesian closed category. Between category and algebra the map is the posetal reflection: a Heyting algebra is exactly a bicartesian closed preorder. Between logic and algebra the map is provability, recorded by algebraizability.

Compared with the fragment, the cost of the new connectives falls on the type-theoretic facet. Every map of the square survives, but the equational theory of proofs needs the commuting conversions to describe normal forms and serious work to be decided, while on the algebraic facet nothing harder happens than adding joins and a bottom.

## References

::: {#refs}
:::
