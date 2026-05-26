TI-84 CALCULUS TOOLKIT  ---  SOURCE FILES
==========================================

These are plain-text TI-BASIC source files for the modular calculus
toolkit described in the accompanying paper. Each file maps to one
program on the calculator. Together they cover limits, continuity,
single- and multi-variable derivatives, integrals, Maclaurin
polynomials, gradients, directional derivatives, tangent planes, and
critical-point classification.

MODULE INDEX
------------
LIMT.txt   Numeric limit estimation (two-sided table + DNE check)
CONT.txt   Continuity classifier (jump / removable / continuous)
DER1.txt   First derivative at a point + tangent line
DER2.txt   Second derivative + concavity / inflection
IMPL.txt   Implicit differentiation: dy/dx = -Fx/Fy
INT1.txt   Definite integral + average value
MACL.txt   Maclaurin polynomial coefficients (degree 4)
GRAD.txt   Gradient vector at a point + magnitude
DDER.txt   Directional derivative (auto-normalizes direction)
TANP.txt   Tangent plane to z = f(x,y)
CRIT.txt   2-variable critical point test (D = Fxx Fyy - Fxy^2)

CONVENTIONS USED IN THE SOURCE
------------------------------
- Lines begin with ':' (TI-BASIC line marker).
- '->' represents the STO> arrow (on the calculator: STO> key).
- 'Y1' represents the function variable Y1 (enter via
  VARS > Y-VARS > Function > 1:Y1). Single-variable modules expect
  the user to define their function in the Y= editor first.
- Multivariable modules read the function as a string via Input
  and evaluate it with expr( ). Use the variables X and Y in the
  string, for example:  X^2 + 3*X*Y - Y^2
- 'sqrt(' should be entered as the square-root token (2nd > x^2).
- 'abs(' is from MATH > NUM > 1:abs(.
- '1E-5' is entered as 1, then 2nd > , (EE), then 5.

HOW TO LOAD ONTO THE CALCULATOR
-------------------------------
Option A. Type directly into the calculator:
  1. PRGM > NEW > Create New.
  2. Name it as in the file header (e.g. LIMT).
  3. Enter each line. Use the menus, not letter-by-letter typing,
     for tokens like Disp, Prompt, nDeriv(, fnInt(, expr(, Y1, ->.

Option B. TI Connect CE (recommended for transferring all at once):
  1. Open each .txt file in TI Connect CE's Program Editor, or
     paste the source into a new program.
  2. Save as .8xp.
  3. Connect calculator via USB and send the .8xp file.

Option C. TokenIDE or SourceCoder (cross-platform):
  1. Open the .txt file.
  2. Export / compile to .8xp.
  3. Transfer with TI Connect CE.

USAGE
-----
On the calculator, run any module with:
  PRGM > EXEC > [select program] > ENTER > ENTER

Single-variable workflow:
  1. Define f(x) in Y1 (Y= editor).
  2. Run LIMT / DER1 / DER2 / INT1 / MACL.

Multivariable workflow:
  1. Run GRAD / DDER / TANP / CRIT.
  2. When prompted, type the formula as a string using X and Y.
     Use a 7 sign for multiplication when needed (e.g. 3*X*Y).
  3. Enter the point (X, Y).

NUMERICAL NOTES
---------------
- Single-variable derivatives use the calculator's built-in
  nDeriv( (symmetric difference, h = 1E-3 by default).
- Single-variable integrals use fnInt( (adaptive Gauss-Kronrod).
- Multivariable partial derivatives use a symmetric central
  difference with h = 0.001.
- Second derivatives use the 3-point stencil
  (f(a+h) - 2 f(a) + f(a-h)) / h^2.
- The mixed partial Fxy in CRIT uses the 4-point cross stencil
  (f(p+h,q+h) - f(p+h,q-h) - f(p-h,q+h) + f(p-h,q-h)) / (4 h^2).
- LIMT flags a removable / jump discontinuity when the one-sided
  evaluations differ by more than 1E-4. Adjust if your problems
  involve sharper transitions.

KNOWN LIMITATIONS
-----------------
- expr( cannot reference Y1 reliably inside multivariable programs
  on all OS versions, which is why GRAD/DDER/TANP/CRIT take a
  string instead of a Y-var. This is intentional.
- All output is numeric. Symbolic simplification is out of scope
  for the TI-84 platform without a CAS.
- Memory footprint of the full toolkit is well within standard
  TI-84 Plus CE RAM; no archived applications need to be removed.
