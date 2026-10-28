---
id: imll-imp
name: Implicational fragment of intuitionistic multiplicative linear logic
short: IMLL(⊸)
status: full correspondence
bibliography: ../references.bib
logic:
  name: Implicational fragment of IMLL (BCI logic)
  EPS: TODO
  presentations: [natural deduction, sequent calculus, Hilbert system with axioms B, C and I]
  connectives: [⊸]
  structural_rules: [exchange]
  cut_elimination: yes
type_theory:
  name: Linear λ-calculus with linear function types only
  type_formers: [⊸]
  equations: [β, η]
  normalization: strong
  equality_decidable: yes
algebra:
  name: BCI-algebras
  CAL: TODO
  kind: quasivariety
  algebraizable: TODO
category:
  name: TODO           # models of linear explicit substitutions
  free_object: syntactic model of the linear λ-calculus modulo βη
correspondence:
  logic-type_theory:    { status: isomorphism }
  type_theory-category: { status: equivalence }
  category-algebra:     { status: TODO }
  logic-algebra:        { status: TODO }
---

# Implicational fragment of intuitionistic multiplicative linear logic

This entry stands to [IMLL](imll.md) as the implicational fragment of IPL stands to the implication–conjunction fragment. Keeping only linear implication removes the tensor, and with it the commuting conversions, so this is the simplest linear system in the atlas and the one where normalization is easiest. As in the intuitionistic case, the absence of a type former for contexts means the categorical models are not simply symmetric monoidal closed categories.

## Logic

Formulas are built from propositional atoms with ⊸ alone. Natural deduction has the rules ⊸I and ⊸E of the IMLL entry, with contexts split between premises. The Hilbert-style presentation has modus ponens with the axioms B, (B ⊸ C) ⊸ ((A ⊸ B) ⊸ (A ⊸ C)), C, (A ⊸ (B ⊸ C)) ⊸ (B ⊸ (A ⊸ C)), and I, A ⊸ A, which is why this logic is also known as BCI logic. Exchange is present, and weakening and contraction are absent.

## Type theory

The Curry–Howard partner is the linear λ-calculus with linear function types only, with terms

$$
M ::= x \mid \lambda x{:}A.\ M \mid M\ N
$$

in which every variable occurs exactly once, and the equations β and η as in the intuitionistic case. The axioms B, C and I are the types of the corresponding linear combinators. Since no variable is duplicated, each β-step strictly decreases the size of a term, so normalization terminates in a number of steps bounded by the size of the term; this bound is the one that adding tensors destroys [@maiettietal2002].

## Algebra

A BCI-algebra is an algebra (A, →, 1) whose axioms are the algebraic forms of B, C and I together with the rule that x → y = 1 = y → x implies x = y [@iseki1966]. BCI-algebras form a quasivariety that is not a variety. Lineales are the ordered models of the full multiplicative fragment, and the ⊸,I parts of lineales give BCI-algebras.

## Category

Without a tensor, a context of linear hypotheses cannot be interpreted as a single type. Ghani, de Paiva and Ritter give categorical models for linear calculi of explicit substitutions, replacing the indexed categories used for cartesian calculi with presheaves, and prove soundness and completeness for them [@ghanietal1999; @ghanietal2000]. These models cover the linear λ-calculus with ⊸ alone, with the term model as the free model.

## Correspondence

All four facets exist. Between logic and type theory the Curry–Howard isomorphism is a bijection between linear natural-deduction proofs and linear terms. Between type theory and category, the models of Ghani, de Paiva and Ritter are sound and complete. Between logic and algebra the logic is sound and complete for BCI-algebras, and the map between category and algebra should be the posetal reflection, as in the intuitionistic case.

## References

::: {#refs}
:::
