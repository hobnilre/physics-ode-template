# The ODE Template and Its Domain Equivalents

[Read the article (PDF)](ode-template.pdf) · [Manuscript](ode-template.md)

Three linear relations and a balance produce one second-order ODE.
The article derives its mechanical and electrical forms, maps their
coordinates and units, and shows how reciprocal coefficients give the dual.

For higher derivative orders, [coefficient synthesis](https://github.com/hobnilre/physics-ode-coefficient-synthesis)
extends the dimension rule. [Interconnection](https://github.com/hobnilre/physics-ode-interconnect-ser-par)
joins the resulting blocks through their common and summed quantities.
The forced LRC form starts the [signed-power calculation](https://github.com/hobnilre/physics-ode-energy).

## Build

Install GNU Make, GNU Coreutils, Pandoc, XeLaTeX, the TeX Gyre fonts and the
LaTeX packages used by the included preambles and figures. Run `make pdf`;
all build inputs are in this repository.

The title date stays fixed; the PDF creation timestamp advances on rebuild.
Use `make -B pdf` to force a rebuild. Intermediates go to ignored `build/`,
or to the path set by `BUILD_DIR`. `make clean` removes that directory and
keeps the article PDF and figure assets.
