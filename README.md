# Quadrivium: a Curry–Howard Atlas

![cartoon 4 qudrivium](https://github.com/vcvpaiva/quadrivium/blob/main/The%20Curry%E2%80%93Howard%20correspondence.png)


The Curry–Howard correspondence says that proofs are programs and propositions are types, and the Lawvere/Lambek part of the story adds that both are morphisms and objects of a suitable category. 

For intuitionistic logic this picture is complete and traditional, and for linear logic it is well developed, but for most of the logics people actually study nobody has written down which parts of it hold. Quadrivium is an atlas of such cases. Each entry takes one logic and records its four facets, the logic, the type theory, the algebra and the category, together with how strong the connection between each pair of facets is.

The atlas builds on two existing open resources. Logics and their proof systems are linked to the [Encyclopedia of Proof Systems](https://proofsystem.github.io/Encyclopedia/) (EPS) started by Bruno Woltzenlogel Paleo, and algebras to Peter Jipsen's [Categories, Algebras and Logics](https://github.com/jipsen/Algebras-and-Logics) database (CAL). Quadrivium adds the type-theoretic and categorical facets and the maps between all four.

## Entries

Every entry is a Markdown file in `entries/`. It starts with a YAML header holding the structured data, followed by prose sections with the same names as the facets: Logic, Type theory, Algebra, Category and Correspondence. The header is the part that becomes the dataset, so it should say briefly what the prose says in full. The `EPS` and `CAL` fields hold the identifiers of the corresponding entries in those databases.

The `correspondence` block in the header records the four maps of the square, between logic and type theory, type theory and category, category and algebra, and logic and algebra. Each map gets a status, such as `isomorphism`, `equivalence`, `posetal-reflection`, `algebraizable`, `partial`, `open` or `none`. An entry may leave facets or maps as `open`; an honest gap is data, and it is exactly what the atlas exists to find.

The paradigmatic case is [the implication–conjunction fragment of intuitionistic propositional logic](entries/ipl-imp-conj.md), whose four facets are natural deduction, the simply typed λ-calculus with products, Brouwerian semilattices and cartesian closed categories, and where every map between them is as strong as one could ask. Entries are compared with each other in many directions, by taking fragments or extensions, by adding or dropping structural rules, and by adding or removing units, and the [index](INDEX.md) lists the entries together with these relations.

## Mathematics and references

Mathematics is written in LaTeX between dollar signs and rendered with MathJax, with proof trees in `bussproofs` syntax. Markdown treats a backslash followed by punctuation as an escape, so `\,`, `\;`, `\{` and `\}` do not survive; use `\ `, `\quad`, `\lbrace` and `\rbrace` instead.

References live in a single shared file, `references.bib`. An entry cites a work as `[@gentzen1935]` and ends with a References section containing `::: {#refs}` and `:::`, which is filled in when the site is built. Before adding a BibTeX entry, check whether the work is already in the file.

## Contributing

Contributions are welcome from students and anyone else interested in logic. The simplest way to start is to open an issue proposing a logic, then copy an existing entry, fill in what you know and mark the rest as `open`. Pull requests are reviewed for both the format and the mathematics.

## License

The content of the atlas is licensed under [Creative Commons Attribution 4.0 International](LICENSE).


