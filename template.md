---
id: TODO               # short lowercase name, also the file name: entries/<id>.md
name: TODO             # full name of the logic
short: TODO            # abbreviation used in the index, e.g. IPL(→)
status: TODO           # one line summarising the correspondence
bibliography: ../references.bib
logic:
  name: TODO
  EPS: TODO            # identifier of the EPS entry, if there is one
  presentations: [TODO]
  connectives: [TODO]
  structural_rules: [TODO]   # any of: exchange, weakening, contraction
  cut_elimination: TODO
type_theory:
  name: TODO
  type_formers: [TODO]
  equations: [TODO]          # e.g. β, η, commuting conversions
  normalization: TODO
  equality_decidable: TODO
algebra:
  name: TODO
  CAL: TODO            # identifier of the CAL entry, if there is one
  kind: TODO           # variety, quasivariety, ordered structures, ...
  algebraizable: TODO  # see LabNotes on algebraizability
category:
  name: TODO
  free_object: TODO
correspondence:
  logic-type_theory:    { status: TODO }
  type_theory-category: { status: TODO }
  category-algebra:     { status: TODO }
  logic-algebra:        { status: TODO }
formalizations:
  - system: TODO       # Lean, Agda, Rocq, Isabelle, Dedukti/Logipedia, ...
    facet: TODO        # logic, type_theory, algebra, category or correspondence
    content: TODO      # e.g. cut elimination, strong normalization
    url: TODO
---

# TODO name of the logic

<!-- One paragraph: why this logic is interesting and how it relates to other entries. Do not rely on the order in which entries were written. -->

## Logic

<!-- One connective sentence, then the BNF, then the rules in a box. Give only the rules specific to this logic; structural rules are explained in the introduction. -->

TODO one sentence saying what the logic has. Formulas are given by

$$
A, B ::= p \mid \ldots
$$

where p ranges over propositional atoms, and the rules of natural deduction, in sequent form, are given in @fig-ID-nd.

::: {#fig-ID-nd .rules}
$$
\begin{prooftree}
\AxiomC{}
\RightLabel{$\mathrm{Ax}$}
\UnaryInfC{$A \vdash A$}
\end{prooftree}
\qquad
\text{TODO: introduction and elimination rules}
$$

Natural deduction in sequent form for TODO.
:::

<!-- Choose one of the following two sentences. -->
All three [structural rules](../INTRODUCTION.md#structural-rules), exchange, weakening and contraction, hold.
Exchange is the only [structural rule](../INTRODUCTION.md#structural-rules) that holds; weakening and contraction are absent.

## Type theory

<!-- BNF for types and terms, typing rules in a box, equations in a second box. -->

TODO one sentence naming the calculus. Types and terms are given by

$$
A, B ::= \ldots \qquad M, N ::= x \mid \ldots
$$

with the typing rules in @fig-ID-typing and the equations in @fig-ID-equations.

::: {#fig-ID-typing .rules}
$$
\text{TODO: typing rules}
$$

Typing rules for TODO.
:::

::: {#fig-ID-equations .rules}
$$
\text{TODO: β and η equations}
$$

Equations for TODO.
:::

TODO normalization and decidability of equality.

## Algebra

<!-- The class of algebras, its axioms, whether it is a variety or quasivariety, and the status of algebraizability. -->

TODO

## Category

<!-- The class of categories, how the connectives are interpreted, and what the free model is. -->

TODO

## Correspondence

<!-- The four maps of the square, each with its strength, matching the correspondence block in the header. -->

TODO

## References

::: {#refs}
:::
