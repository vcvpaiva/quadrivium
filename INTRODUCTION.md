# Introduction

The Curry–Howard correspondence is usually stated as a slogan, propositions are types and proofs are programs, but behind the slogan there is a precise mathematical claim. For intuitionistic propositional logic the claim is a theorem: natural-deduction proofs are in bijection with terms of the simply typed λ-calculus, normalization of proofs is reduction of terms, and both present the free cartesian closed category, whose posetal reflection is the free Heyting algebra. Lambek's contribution was the third leg, seeing a deductive system as a category, and the algebraic leg, older than the other three, is the tradition of Lindenbaum–Tarski algebras. The question behind Quadrivium is how much of this picture survives when the logic changes, and the aim of the atlas is to record the answer logic by logic.

## Proofs as objects

The correspondence only makes sense once proofs are mathematical objects with a notion of identity, and the natural-deduction tradition supplies this. Prawitz proved that every natural-deduction derivation reduces to a normal form, one without detours where an introduction rule is immediately followed by the corresponding elimination [@prawitz1965]. He also proposed that two derivations should be identified exactly when they reduce to the same normal form, up to the expansions now called η [@prawitz1971]. Under the Curry–Howard correspondence, normalization becomes evaluation of terms and Prawitz's identity of proofs becomes βη-equality, which is in turn equality of morphisms in the free category.

Martin-Löf took the correspondence as the foundation of a type theory rather than as an observation about one [@martinlof1984]. In his account the meaning of a connective is given by its introduction rules, and the elimination rules are justified because they take back no more than the introductions put in [@martinlof1996]. This is the same balance between introduction and elimination that makes Prawitz's normalization work, and it is a good first test for whether a logic is likely to have a Curry–Howard correspondence at all. Martin-Löf's type theory, with dependent types, is the direction in which the atlas should eventually grow beyond propositional logic.

## Structural rules

Logics differ in their connectives, but many of the differences that matter for the correspondence lie in the structural rules, which say how hypotheses may be handled independently of what they mean. With sequents Γ ⊢ A, where Γ is a list of hypotheses, the three classical structural rules are exchange, weakening and contraction:

$$
\begin{prooftree}
\AxiomC{$\Gamma, A, B, \Delta \vdash C$}
\RightLabel{$\mathrm{Ex}$}
\UnaryInfC{$\Gamma, B, A, \Delta \vdash C$}
\end{prooftree}
\qquad
\begin{prooftree}
\AxiomC{$\Gamma \vdash C$}
\RightLabel{$\mathrm{W}$}
\UnaryInfC{$\Gamma, A \vdash C$}
\end{prooftree}
\qquad
\begin{prooftree}
\AxiomC{$\Gamma, A, A \vdash C$}
\RightLabel{$\mathrm{C}$}
\UnaryInfC{$\Gamma, A \vdash C$}
\end{prooftree}
$$

Exchange says the order of hypotheses is irrelevant, weakening says a hypothesis may go unused, and contraction says a hypothesis may be used more than once. Each rule has a meaning on every facet of the atlas. In the type theory, exchange lets variables in a context be permuted, weakening allows λx.M where x does not occur in M, and contraction allows a variable to occur twice. In the category, exchange is a symmetry A ⊗ B → B ⊗ A, weakening gives projections A ⊗ B → A, which makes the unit a terminal object, and contraction gives diagonals A → A ⊗ A. Fox showed that a symmetric monoidal category in which every object carries a suitably natural commutative comonoid, a diagonal together with a map to the unit, is cartesian [@fox1976], so weakening and contraction together turn the tensor into a product.

On the algebraic facet the same rules become order-theoretic conditions on a residuated structure, where a ⊗ b ≤ c holds exactly when the sequent A, B ⊢ C is provable. Exchange makes ⊗ commutative. Weakening applied to the axiom A ⊢ A gives A, B ⊢ A, so a ⊗ b ≤ a, and with b = 1 this says the unit is the top element. Contraction applied to A, A ⊢ A ⊗ A gives A ⊢ A ⊗ A, so a ≤ a ⊗ a. With both, a ⊗ b is a lower bound of a and b, and if c ≤ a and c ≤ b then c ≤ c ⊗ c ≤ a ⊗ b by monotonicity, so a ⊗ b is the meet: the algebra collapses from a residuated monoid to a Brouwerian semilattice, exactly as the category collapses from monoidal to cartesian.

Dropping structural rules gives the substructural logics [@galatosetal2007]. Without weakening and contraction one gets linear logic, where every hypothesis is used exactly once [@girard1987]; without exchange as well, one gets the Lambek calculus, where implication splits into a left and a right version [@lambek1958]. Relevant logics keep contraction but drop weakening, and affine logics keep weakening but drop contraction. The modalities of linear logic reintroduce weakening and contraction for marked formulas, which is how linear logic recovers intuitionistic logic inside it. The `structural_rules` field of each entry records which of the three rules hold, and the entries themselves give only the rules specific to their logic.

## Aims

The atlas aims to make the landscape of Curry–Howard correspondences visible, including the places where it breaks. For each logic it records whether there is a type theory whose terms are its proofs, a category in which those terms are the morphisms of a free object, and a class of algebras for which the logic is complete, together with how strong each of the four maps between these facets is. Where a facet is missing or a map is only partial, the gap is part of the data: the linear fragments already show that algebraizability in the sense of Blok and Pigozzi can fail while the other three maps hold perfectly.

From the comparisons between entries we hope to extract structural criteria for when a full correspondence exists, in the spirit of Prawitz's normalization and Martin-Löf's balance between introduction and elimination rules. The obvious next steps are classical logic, where the correspondence is known to be delicate, modal logics, and the dependent types of Martin-Löf's type theory. Each entry is meant to be small enough for a student to write and check, and the atlas grows by entries being added, compared and corrected.

## References

::: {#refs}
:::
