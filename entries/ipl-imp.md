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
category_theory:
  name: TODO           # Jacobs' models for the →-only calculus
  free_object: syntactic model of the λ-calculus modulo βη
correspondence:
  logic-type_theory:    { status: isomorphism }
  type_theory-category: { status: equivalence }
  category-algebra:     { status: TODO }
  logic-algebra:        { status: algebraizable }
---

# Implicational fragment of intuitionistic propositional logic

The implicational fragment of intuitionistic propositional logic has a full Curry–Howard correspondence with implication as its only connective. It sits underneath [the implication–conjunction fragment](ipl-imp-conj.md), and removing conjunction changes the categorical facet more than the others: without product types, contexts can no longer be internalized as a single type, so the models are not simply cartesian closed categories.

## Logic

The implicational fragment of intuitionistic propositional logic has implication as its only connective, and its logical rules are those of natural deduction for implication. Formulas are given by

$$
A, B ::= p \mid A \to B
$$

where p ranges over propositional atoms. Sequents have the form Γ ⊢ A, with Γ a finite list of formulas, and the rules of natural deduction in sequent form are given in @fig-ipl-imp-nd.

::: {#fig-ipl-imp-typing .rules}

$$
\dfrac{}{\Gamma, A \vdash  A}\ (\mathrm{Var})
$$

$$
\dfrac{\Gamma, A \vdash B}{\Gamma \vdash  A \to B}\ (\to\mathrm{I})
\qquad
\dfrac{\Gamma \vdash A \to B \qquad \Gamma \vdash A}{\Gamma \vdash  B}\ (\to\mathrm{E})
$$

ND rules for the implicational fragment of intuitionistic propositional logic.

:::

All three [structural rules](https://github.com/vcvpaiva/quadrivium/blob/main/INTRODUCTION.md#structural-rules), exchange, weakening and contraction, hold. An equivalent Hilbert-style presentation, in @fig-ipl-imp-hilbert, has modus ponens as its only rule and two axiom schemes.

::: {#fig-ipl-imp-hilbert .rules}

$$
\mathrm{K}\colon\ A \to (B \to A) \qquad \mathrm{S}\colon\ (A \to (B \to C)) \to ((A \to B) \to (A \to C))
$$

$$
\begin{prooftree}
\AxiomC{$A \to B$}
\AxiomC{$A$}
\RightLabel{$\mathrm{MP}$}
\BinaryInfC{$B$}
\end{prooftree}
$$

Hilbert-style presentation of the implicational fragment of intuitionistic propositional logic.

:::

The sequent calculus for the fragment has cut elimination. Full [intuitionistic propositional logic](ipl.md) is conservative over the fragment: a formula built from atoms with → alone is provable in IPL exactly when it is provable here.

## Type theory

The Curry–Howard partner of the fragment is the simply typed λ-calculus with function types only [@howard1980; @girardlafonttaylor1989, ch. 3]. Types and terms are given by

$$
A, B ::= p \mid A \to B \qquad M, N ::= x \mid \lambda x{:}A.\ M \mid M\ N
$$

so types are exactly the formulas of the logic. Typing judgements have the form Γ ⊢ M : A, where Γ is a list of typed variables x₁:A₁, …, xₙ:Aₙ with distinct variables, and the typing rules are in @fig-ipl-imp-typing. In these rules the context is shared between premises rather than split; because weakening and contraction hold, this presentation and the one in @fig-ipl-imp-nd prove the same sequents.

::: {#fig-ipl-imp-typing .rules}

$$
\dfrac{}{\Gamma, x{:}A \vdash x : A}\ (\mathrm{Var})
$$

$$
\dfrac{\Gamma, x{:}A \vdash M : B}{\Gamma \vdash \lambda x{:}A.\ M : A \to B}\ (\to\mathrm{I})
\qquad
\dfrac{\Gamma \vdash M : A \to B \qquad \Gamma \vdash N : A}{\Gamma \vdash M\ N : B}\ (\to\mathrm{E})
$$

Typing rules for the simply typed λ-calculus with function types.

:::

The equations between terms are β and η, in @fig-ipl-imp-equations. Read from left to right, β is a reduction step, and a β-redex corresponds to a detour in a proof, an introduction of → immediately followed by its elimination.

::: {#fig-ipl-imp-equations .rules}

$$
(\lambda x{:}A.\ M)\ N = M[N/x] \qquad (\beta)
$$

$$
\lambda x{:}A.\ (M\ x) = M \quad \text{if } x \text{ is not free in } M \qquad (\eta)
$$

Equations for the simply typed λ-calculus with function types.

:::

Reduction is strongly normalizing and confluent, and βη-equality is decided by computing β-normal η-long forms. The axioms K and S of the Hilbert system are the types of the combinators K = λx.λy.x and S = λx.λy.λz.(x z)(y z), so the Hilbert system corresponds to combinatory logic.

## Algebra

A Hilbert algebra is an algebra (A, →, 1) satisfying the equations that make x → (y → x) and the S-axiom equal to 1, with x → y = 1 = y → x implying x = y. Hilbert algebras form a variety, and they are exactly the →,1 subreducts of Heyting algebras. Diego proved that the variety is locally finite [@diego1966]. The implicational fragment of IPL is algebraizable, with Hilbert algebras as its equivalent algebraic semantics.

## Category

Since the calculus has no product types, a context x₁:A₁, …, xₙ:Aₙ cannot be interpreted as a single type. Jacobs gives categorical models for the calculus with function types only, in which contexts carry the finite products that the types lack, and proves that they correspond to the calculus [@jacobs1992]. Every cartesian closed category gives such a model, but the free model is not a cartesian closed category.

## Correspondence

All four facets exist and match. Between logic and type theory the Curry–Howard isomorphism is a bijection between natural-deduction proofs and terms, with normalization as β-reduction. Between type theory and category, Jacobs' models are sound and complete for βη-equality, with the term model as the free model. Between logic and algebra the map is algebraizability, with Hilbert algebras. The map between category and algebra should be the posetal reflection, taking a model to the Hilbert algebra of its types ordered by provability.

## References

::: {#refs}
:::
