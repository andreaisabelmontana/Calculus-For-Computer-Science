# Calculus for Computer Science — TI-84 Programming Toolkit

A modular TI-BASIC toolkit that turns a TI-84 Plus CE into a lightweight
computational calculus assistant, plus the accompanying research paper.

**Author:** Andrea Montana — IE University, BSc Computer Science & AI (2026)
**Supervisor:** Carlos Gordon

## Contents

- **[`paper.pdf`](./paper.pdf)** — Canonical research paper (PDF export of the original).
- **[`paper.md`](./paper.md)** — Same paper as Markdown, rendered inline on GitHub.
- **[`TI84_Calculus_Toolkit/`](./TI84_Calculus_Toolkit/)** — TI-BASIC source files (`.txt`)
  for each module, plus a per-folder README describing transfer and usage.

## The Toolkit at a glance

| Module | File | Topic |
|---|---|---|
| `LIMT` | [`LIMT.txt`](./TI84_Calculus_Toolkit/LIMT.txt) | Numeric limit estimation, two-sided table, DNE check |
| `CONT` | [`CONT.txt`](./TI84_Calculus_Toolkit/CONT.txt) | Continuity classifier (jump / removable / continuous) |
| `DER1` | [`DER1.txt`](./TI84_Calculus_Toolkit/DER1.txt) | First derivative at a point + tangent line |
| `DER2` | [`DER2.txt`](./TI84_Calculus_Toolkit/DER2.txt) | Second derivative + concavity / inflection |
| `IMPL` | [`IMPL.txt`](./TI84_Calculus_Toolkit/IMPL.txt) | Implicit differentiation `dy/dx = −Fx/Fy` |
| `INT1` | [`INT1.txt`](./TI84_Calculus_Toolkit/INT1.txt) | Definite integral + average value |
| `MACL` | [`MACL.txt`](./TI84_Calculus_Toolkit/MACL.txt) | Maclaurin polynomial coefficients (degree 4) |
| `GRAD` | [`GRAD.txt`](./TI84_Calculus_Toolkit/GRAD.txt) | Gradient vector at a point + magnitude |
| `DDER` | [`DDER.txt`](./TI84_Calculus_Toolkit/DDER.txt) | Directional derivative (auto-normalized) |
| `TANP` | [`TANP.txt`](./TI84_Calculus_Toolkit/TANP.txt) | Tangent plane to `z = f(x, y)` |
| `CRIT` | [`CRIT.txt`](./TI84_Calculus_Toolkit/CRIT.txt) | 2-variable critical point test (`D = Fxx Fyy − Fxy²`) |

## Quick start

1. Open any `.txt` source in **TI Connect CE**, **TokenIDE**, or **SourceCoder**.
2. Compile / save it as an `.8xp` program file.
3. Send the resulting `.8xp` to your TI-84 Plus CE over USB.
4. On the calculator: `PRGM` → `EXEC` → select the module → `ENTER`.

For single-variable modules, first define `f(x)` in `Y1` via the `Y=` editor.
Multivariable modules read the function as a string at runtime — type it using
the variables `X` and `Y` (e.g. `X^2 + 3*X*Y - Y^2`).

See [`TI84_Calculus_Toolkit/README.txt`](./TI84_Calculus_Toolkit/README.txt) for
the full source conventions (`->` for STO, `Y1` token entry, stencil sizes, etc.).

## Numerical conventions

- Single-variable derivatives use the calculator's built-in `nDeriv(`
  (symmetric difference).
- Single-variable definite integrals use `fnInt(` (adaptive Gauss–Kronrod).
- Multivariable partials use a symmetric central difference with `h = 0.001`.
- Second derivatives use the 3-point stencil
  `(f(a+h) − 2 f(a) + f(a−h)) / h²`.
- Mixed partials use the 4-point cross stencil
  `(f(p+h, q+h) − f(p+h, q−h) − f(p−h, q+h) + f(p−h, q−h)) / (4 h²)`.

## License & academic use

This repository accompanies an IE University research project. The toolkit is
provided for educational use; please cite the paper if reusing material.
