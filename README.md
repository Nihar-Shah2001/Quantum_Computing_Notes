# Foundations of Quantum Computing: Theory and Implementation

A book that builds quantum computing up from first principles, from qubits and gates through
Deutsch–Jozsa, Simon, the Quantum Fourier Transform, phase estimation, Shor's algorithm and
Grover's search / amplitude amplification. Every chapter favours intuition and complete
derivations over compressed formalism, and is paired with runnable Qiskit code.

It grew out of my own attempt to learn the subject from *Nielsen & Chuang*. These are the notes
I wish I had while reading it.

**Prerequisites:** basic linear algebra and probability. Appendix A covers the linear algebra you need.

## Read the book

**[Download the latest PDF](https://github.com/Nihar-Shah2001/Quantum_Computing_Notes/releases/latest)** (from GitHub Releases).

The book is a working draft. Corrections and suggestions are very welcome via
[issues](https://github.com/Nihar-Shah2001/Quantum_Computing_Notes/issues).

## Chapters and companion notebooks

| # | Chapter | Notebook |
|---|---------|----------|
| 1 | Introduction | |
| 2 | Axioms of Quantum Mechanics | |
| 3 | Qubits and Quantum Gates | [ch03_qubits_and_quantum_gates](notebooks/ch03_qubits_and_quantum_gates.ipynb) |
| 4 | Quantum Circuits | |
| 5 | Entanglement | [ch05_entanglement](notebooks/ch05_entanglement.ipynb) |
| 6 | Elitzur–Vaidman Bomb Detection | |
| 7–8 | Deutsch's Algorithm, Deutsch–Jozsa Algorithm | [ch07-08_deutsch_and_deutsch_jozsa](notebooks/ch07-08_deutsch_and_deutsch_jozsa.ipynb) |
| 9 | Bernstein–Vazirani Algorithm | [ch09_bernstein_vazirani](notebooks/ch09_bernstein_vazirani.ipynb) |
| 10 | Simon's Algorithm | [ch10_simon](notebooks/ch10_simon.ipynb) |
| 11 | Discrete Log Problem | |
| 12 | Quantum Fourier Transform | [ch12_quantum_fourier_transform](notebooks/ch12_quantum_fourier_transform.ipynb) |
| 13 | Phase Estimation | [ch13_phase_estimation](notebooks/ch13_phase_estimation.ipynb) |
| 14 | Order Finding | [ch14_order_finding](notebooks/ch14_order_finding.ipynb) |
| 15 | Shor's Algorithm | [ch15_shor](notebooks/ch15_shor.ipynb) |
| 16 | Grover's Search Algorithm | [ch16_grover](notebooks/ch16_grover.ipynb) |
| A | Linear Algebra and Calculus Prerequisites | |
| B | Classical Computations | |
| C | Qiskit | [appC_qiskit_introduction](notebooks/appC_qiskit_introduction.ipynb) |

### Running the notebooks

The notebooks target **Qiskit 1.x**. Qiskit 2.0 removed some APIs they use.

```sh
python -m venv .venv && source .venv/bin/activate
pip install -r notebooks/requirements.txt
jupyter lab notebooks/
```

`ch15_shor.ipynb` imports helper functions from `ch14_order_finding.ipynb`, so run it from inside `notebooks/`.

## Building the PDF yourself

You need a TeX distribution (TeX Live or MacTeX) with `latexmk`:

```sh
cd book
latexmk -pdf main.tex
```

In VS Code, install the LaTeX Workshop extension, open `book/main.tex` and press ⌘⌥B (Ctrl+Alt+B on Windows and Linux).

## Repository layout

```
book/
  main.tex            root file: parts, chapter order, appendices
  preamble.tex        packages, colours, theorem environments
  frontmatter/        title page, acknowledgements, preface
  chapters/           one file per chapter
  appendices/         A: linear algebra, B: classical computation, C: Qiskit
  Images/             figures
  references.bib
notebooks/            companion Qiskit notebooks, numbered by chapter
  extras/             alternate versions and helper notebooks
```

## License

- **Book text and figures** (`book/`): [CC BY-NC-SA 4.0](LICENSE-TEXT). Commercial use requires the author's
  prior permission; please get in touch to request it.
- **Code** (`notebooks/`): [MIT](LICENSE-CODE)

© 2024–2026 Nihar Shah
