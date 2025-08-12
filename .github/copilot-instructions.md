# Copilot Instructions for Software Foundations (Logical Foundations)

This project contains Coq scripts and supporting files for the "Software Foundations" textbook series, specifically the Logical Foundations volume. It is designed for interactive use with the Coq proof assistant.

## Project Structure
- **.v files**: Coq source files for chapters and exercises (e.g., `Lists.v`, `Basics.v`).
- **Test files**: Files ending with `Test.v` contain exercises and test cases for the main chapters.
- **HTML files**: Generated documentation for each chapter (e.g., `Lists.html`).
- **common/**: Shared JavaScript and CSS for HTML rendering.
- **Makefile / Makefile.coq**: Build automation for compiling Coq files and generating HTML.
- **_CoqProject**: Coq project configuration (load paths, namespaces).
- **README**: High-level project and usage overview.

## Key Workflows
- **Build all Coq files**: Run `make build` (uses `Makefile.coq`, generated from `coq_makefile`).
- **Clean build artifacts**: Run `make clean`.
- **Regenerate Makefile.coq**: Run `coq_makefile -Q . LF -o Makefile.coq *.v` if you add/remove `.v` files.
- **Interactive development**: Open `.v` files in CoqIDE, Proof General, or VS Code with Coq extensions.
- **HTML generation**: Typically handled by the build, but can be customized for documentation.

## Coding and Proof Conventions
- **Module structure**: Each chapter is a self-contained Coq module. Use `From LF Require Export ...` for dependencies.
- **Naming**: Use descriptive names for theorems, lemmas, and definitions. Test cases are named `test_*`.
- **Proof style**: Prefer readable, stepwise proofs. Use comments to clarify non-obvious steps.
- **Exercises**: Marked with star ratings and comments. Leave `Admitted.` for unfinished proofs.
- **Do not modify**: Comments like `(* Do not modify the following line: *)` indicate lines required for grading or automation.

## Integration and Dependencies
- **Coq**: Requires a compatible version of the Coq proof assistant (see Preface.v or project documentation).
- **No external OCaml/ML code**: All logic is in Coq unless otherwise noted (e.g., `impdriver.ml`).
- **No external package manager**: All dependencies are local or standard Coq libraries.

## Examples
- To prove a property about lists, add a theorem to `Lists.v` and test it in `ListsTest.v`.
- To add a new chapter, create a `.v` file, update `_CoqProject`, and regenerate `Makefile.coq`.

## References
- See `Preface.v` and `README` for more context on project goals and setup.
- For build issues, check `Makefile` and `_CoqProject` for correct file lists and flags.

---
If any section is unclear or missing key project-specific details, please provide feedback for further refinement.
