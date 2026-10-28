# Index of entries

Each row is one entry of the atlas, with its four facets and the status of the map between the logic and its algebras. The entries are listed from the smallest systems upwards, intuitionistic first and linear second.

| Entry | Logic | Type theory | Algebra | Category | Logic–algebra |
|---|---|---|---|---|---|
| [IPL(→)](entries/ipl-imp.md) | implicational IPL | λ-calculus with → | Hilbert algebras | Jacobs' models | algebraizable |
| [IPL(→,∧)](entries/ipl-imp-conj.md) | →, ∧, ⊤ fragment of IPL | λ-calculus with →, × | Brouwerian semilattices | cartesian closed categories | algebraizable |
| [IPL](entries/ipl.md) | intuitionistic propositional logic | λ-calculus with →, ×, + | Heyting algebras | bicartesian closed categories | algebraizable |
| [IMLL(⊸)](entries/imll-imp.md) | BCI logic | linear λ-calculus with ⊸ | BCI-algebras | models of linear explicit substitutions | partial |
| [LP](entries/lp.md) | Lambek calculus with permutation | linear λ-calculus with ⊸, ⊗ | commutative residuated semigroups | symmetric closed multicategories | open |
| [IMLL](entries/imll.md) | ⊸, ⊗, I fragment of ILL | linear λ-calculus with ⊸, ⊗, I | lineales | symmetric monoidal closed categories | open |

## Relations between entries

- IPL(→) is a fragment of IPL(→,∧), which is a fragment of IPL.
- IMLL(⊸) is a fragment of LP, which is IMLL without the unit I.
- Adding weakening and contraction to IMLL gives IPL(→,∧), with ⊗ becoming ∧ and ⊸ becoming →.
