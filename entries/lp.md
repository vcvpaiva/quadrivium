---
id: lp
name: Lambek calculus with permutation
short: LP
status: full correspondence on three sides; algebraizability open
bibliography: ../references.bib
logic:
  name: Lambek calculus with permutation (Lambek–van Benthem calculus)
  EPS: TODO
  presentations: [sequent calculus, natural deduction]
  connectives: [⊸, ⊗]
  structural_rules: [exchange]
  cut_elimination: yes
type_theory:
  name: Linear λ-calculus with tensor and no unit
  type_formers: [⊸, ⊗]
  equations: [β, η, commuting conversions]
  normalization: strong
  equality_decidable: TODO
algebra:
  name: Commutative residuated partially ordered semigroups
  CAL: TODO
  kind: TODO
  algebraizable: open
category:
  name: Symmetric closed multicategories
  free_object: syntactic multicategory of the linear λ-calculus modulo βη and commuting conversions
correspondence:
  logic-type_theory:    { status: isomorphism }
  type_theory-category: { status: equivalence }
  category-algebra:     { status: posetal-reflection }
  logic-algebra:        { status: open }
---

# Lambek calculus with permutation

Lambek introduced his calculus to describe the syntax of natural language, with two implications, one looking left and one looking right, because word order matters in a sentence [@lambek1958]. Adding the structural rule of permutation makes the two implications coincide, and the resulting calculus LP was proposed by van Benthem as the logic of semantic types for categorial grammar, where proofs give the meanings of sentences as linear λ-terms [@vanbenthem1991]. As a logic, LP is [IMLL](imll.md) without the unit I, and its Curry–Howard partner and categorical models follow from those of IMLL by leaving out the unit.

## Logic

Formulas are built from atoms with linear implication ⊸ and tensor ⊗, and there is no unit. The sequent calculus has the rules of IMLL for ⊸ and ⊗, together with exchange; weakening and contraction are absent, and cut elimination holds. Lambek's original calculus requires every sequent to have at least one formula on the left, and LP is usually presented with the same restriction, so that A ⊸ A is not a theorem on its own but A ⊢ A is.

## Type theory

The Curry–Howard partner of LP is the linear λ-calculus of IMLL without the unit type ∗ and its let-construct:

$$
M ::= x \mid \lambda x{:}A.\ M \mid M\ N \mid M \otimes N \mid \mathsf{let}\ M\ \mathsf{be}\ x \otimes y\ \mathsf{in}\ N
$$

with every variable occurring exactly once and the β, η and commuting conversions of IMLL restricted to these terms. Van Benthem used exactly these linear terms as the meanings delivered by derivations in categorial grammar. With the restriction to non-empty antecedents every typed term has at least one free variable.

## Algebra

The ordered models of LP are commutative residuated partially ordered semigroups: partially ordered sets with an associative, commutative, monotone product ⊗ and an operation ⊸ such that a ⊗ b ≤ c holds exactly when a ≤ b ⊸ c. They are lineales without the unit. As for IMLL, the natural semantics is a class of ordered structures rather than a quasivariety, so algebraizability in the sense of Blok and Pigozzi is recorded as open.

## Category

Without a unit, and with non-empty antecedents, the natural categorical models are multicategories rather than monoidal categories. Lambek introduced multicategories precisely to model deductive systems of this kind, with a morphism from a non-empty list of objects to a single object [@lambek1969]. The models of LP are the symmetric multicategories that are closed, for ⊸, and representable, for ⊗, with non-empty sources, and the term calculus modulo βη and commuting conversions gives the free one.

## Correspondence

The maps of the square are those of IMLL with the unit left out. Between logic and type theory the Curry–Howard isomorphism is a bijection between LP proofs and linear terms. Between type theory and category the term model is the free symmetric closed representable multicategory. Between category and algebra the map is the posetal reflection, since a commutative residuated partially ordered semigroup is a symmetric closed representable multicategory that is a preorder. Between logic and algebra, LP is sound and complete for commutative residuated partially ordered semigroups, and algebraizability is open, as for IMLL.

## References

::: {#refs}
:::
