---
id: ipl-imp
name: Implicational fragment of intuitionistic propositional logic
short: IPL(→)
status: full correspondence
bibliography: ../references.bib
logic:
  name: Implicational fragment of IPL
  EPS: TODO
  presentations: [natural deduction, sequent calculus, Hilbert system with axioms K and S]
  connectives: [→]
  structural_rules: [weakening, contraction, exchange]
  cut_elimination: yes
type_theory:
  name: Simply typed λ-calculus with function types only
  type_formers: [→]
  equations: [β, η]
  normalization: strong
  equality_decidable: yes
algebra:
  name: Hilbert algebras
  CAL: TODO
  kind: variety
  algebraizable: yes
category:
  name: TODO           # Jacobs' models for the →-only calculus
  free_object: syntactic model of the λ-calculus modulo βη
correspondence:
  logic-type_theory:    { status: isomorphism }
  type_theory-category: { status: equivalence }
  category-algebra:     { status: TODO }
  logic-algebra:        { status: algebraizable }
---

# Implicational fragment of intuitionistic propositional logic

The smallest fragment of IPL with a full Curry–Howard correspondence has implication as its only connective. It sits underneath [the implication–conjunction fragment](ipl-imp-conj.md), and removing conjunction changes the categorical facet more than the others: without product types, contexts can no longer be internalized as a single type, so the models are not simply cartesian closed categories.

## Logic

The implicational fragment of intuitionistic propositional logic has implication as its only connective, and its logical rules are those of natural deduction for implication. Formulas are given by

$$
A, B ::= p \mid A \to B
$$

where p ranges over propositional atoms. Sequents have the form Γ ⊢ A, with Γ a finite list of formulas, and the logical rules are

$$
\begin{prooftree}
\AxiomC{}
\RightLabel{$\mathrm{Ax}$}
\UnaryInfC{$A \vdash A$}
\end{prooftree}
\qquad
\begin{prooftree}
\AxiomC{$\Gamma, A \vdash B$}
\RightLabel{$\to\mathrm{I}$}
\UnaryInfC{$\Gamma \vdash A \to B$}
\end{prooftree}
\qquad
\begin{prooftree}
\AxiomC{$\Gamma \vdash A \to B$}
\AxiomC{$\Delta \vdash A$}
\RightLabel{$\to\mathrm{E}$}
\BinaryInfC{$\Gamma, \Delta \vdash B$}
\end{prooftree}
$$

The [structural rules]() of exchange, weakening, and contraction are all present.

An equivalent Hilbert-style presentation has modus ponens as its only rule and two axiom schemes,

$$
\mathrm{K}\colon\ A \to (B \to A) \qquad \mathrm{S}\colon\ (A \to (B \to C)) \to ((A \to B) \to (A \to C))
$$

and the sequent calculus for the fragment has cut elimination. Full [intuitionistic propositional logic](ipl.md) is conservative over the fragment: a formula built from atoms with → alone is provable in IPL exactly when it is provable here.

## Type theory

The Curry–Howard partner is the simply typed λ-calculus with function types only [@howard1980; @girardlafonttaylor1989, ch. 3], with terms

$$
M ::= x \mid \lambda x{:}A.\ M \mid M\ N
$$

and the equations β, (λx. M) N = M[N/x], and η, λx. (M x) = M when x is not free in M. The axioms K and S are the types of the combinators K and S, so the Hilbert system corresponds to combinatory logic. Reduction is strongly normalizing and confluent, and βη-equality is decided by β-normal η-long forms.

## Algebra

A Hilbert algebra is an algebra (A, →, 1) satisfying the equations that make x → (y → x) and the S-axiom equal to 1, with x → y = 1 = y → x implying x = y. Hilbert algebras form a variety, and they are exactly the →,1 subreducts of Heyting algebras. Diego proved that the variety is locally finite [@diego1966]. The implicational fragment of IPL is algebraizable, with Hilbert algebras as its equivalent algebraic semantics.

## Category

Since the calculus has no product types, a context x₁:A₁, …, xₙ:Aₙ cannot be interpreted as a single type. Jacobs gives categorical models for the calculus with function types only, in which contexts carry the finite products that the types lack, and proves that they correspond to the calculus [@jacobs1992]. Every cartesian closed category gives such a model, but the free model is not a cartesian closed category.

## Correspondence

All four facets exist and match. Between logic and type theory the Curry–Howard isomorphism is a bijection between natural-deduction proofs and terms, with normalization as β-reduction. Between type theory and category, Jacobs' models are sound and complete for βη-equality, with the term model as the free model. Between logic and algebra the map is algebraizability, with Hilbert algebras. The map between category and algebra should be the posetal reflection, taking a model to the Hilbert algebra of its types ordered by provability.

## References

::: {#refs}
:::
