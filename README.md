# The ODE Template and Its Domain Equivalents

Mechanical and electrical forms of one second-order equation

## The template and its equivalents

A common quantity, three linear relations and a signed balance give one
second-order ODE template. The article derives the MCK, KCM, LRC and CRL
forms, provides a coefficient and quantity table, and proves the
mechanical-electrical scaling and reciprocal dual substitution. It also
sets the forced-template and phasor conventions used by the companions.

The article focuses on this mathematics and is limited to four pages.

## Four related articles

| Article | Main role |
| --- | --- |
| [Template](ode-template.pdf) | Common equation, domain dictionary, duality and harmonic convention. |
| [Coefficient synthesis](https://github.com/hobnilre/physics-ode-coefficient-synthesis) | Coefficient family, LRC table, stairs and phasor factors. |
| [Interconnection](https://github.com/hobnilre/physics-ode-interconnect-ser-par) | Series/parallel constraints, initial coordinates, elimination and phasor solutions. |
| [Energy](https://github.com/hobnilre/physics-ode-energy) | Signed power and work of the added term, with fixed-motion coefficient scaling. |

Each article states its local assumptions. Shared derivations are linked
where they are used. The energy article uses the coefficient-synthesis
article for $A_{-1,3}=LRC$.

## Article and build

[Read the article (PDF)](ode-template.pdf) · [Manuscript source](ode-template.md)

Install GNU Make, GNU Coreutils, Pandoc, XeLaTeX and the TeX Gyre fonts, including the LaTeX
packages used by `preamble.tex` and `preamble-local.tex` and the TikZ/PGFPlots standalone figures.
Run `make pdf` from this repository. It regenerates changed figures and builds
the article without any sibling repository or private working files.

The title date is the first version's creation date, pinned in `ARTICLE_DATE`
in the Makefile and retained in the manuscript's `date`. Keep both unchanged
when revising the article. The first page also gives the PDF creation time in UTC, followed by the
[GitHub repository](https://github.com/hobnilre/physics-ode-template). An up-to-date PDF keeps its timestamp;
`make -B pdf` forces a rebuild. Intermediates go to ignored `build/` by default;
`BUILD_DIR=/absolute/path` selects another location. `make clean` removes that
build directory and keeps the published PDF and figure assets.

Shared typography is installed locally in `article-style.yaml`, `preamble.tex`
and `figures/figure-style.tex`. Article-specific definitions are in
`preamble-local.tex`. These files are complete build inputs; no tools checkout
is required.
