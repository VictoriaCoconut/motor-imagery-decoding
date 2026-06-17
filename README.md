# Motor Imagery EEG Decoding — A Build-From-Fundamentals Roadmap

Decoding motor imagery from EEG with classical machine learning. A real
brain–computer interface (BCI) project that reads in two layers:

- **As a project** — a rigorous motor-imagery decoder (CSP+LDA, Riemannian
  pipelines) evaluated per-subject with MOABB.
- **As a learning path** — each step is a self-contained class, from
  "what is learning?" to a multi-pipeline benchmark, so you can see not just
  the result but how it was built.

![Python](https://img.shields.io/badge/Python-3.11-blue) 
![License: MIT](https://img.shields.io/badge/License-MIT-green)
![Status](https://img.shields.io/badge/status-in%20progress-orange)
## Built With

`scikit-learn` · `MNE` · `MOABB` · `pyRiemann` · `braindecode`

Classical ML for neural signal decoding — the standard stack used in BCI
research for motor-imagery classification.
## Roadmap

The repository is built one class at a time. Each class is self-contained and
connects an ML concept to how it is later used on real EEG.

| #  | Topic                                   | Artifact           | Done |
|----|-----------------------------------------|--------------------|------|
| 00 | Repo setup                              | structure + README | ✅   |
| 01 | What is learning? train/test            | notebook           | ⬜   |
| 02 | Cross-validation                        | notebook           | ⬜   |
| 03 | Leakage & group splits                  | notebook           | ⬜   |
| 04 | Features, scaling & Pipeline            | notebook           | ⬜   |
| 05 | Classifiers: LDA & SVM                  | notebook           | ⬜   |
| 06 | Metrics beyond accuracy                 | notebook           | ⬜   |
| 07 | Overfitting & regularization            | notebook           | ⬜   |
| 08 | Real EEG signal (MOABB/MNE)             | notebook           | ⬜   |
| 09 | First decoder: CSP+LDA, one subject     | notebook           | ⬜   |
| 10 | All subjects & between-subject variance | notebook           | ⬜   |
| 11 | Pipeline benchmark (incl. Riemannian)   | notebook           | ⬜   |
| 12 | Final packaging                         | README + figures   | ⬜   |

## Run Locally

```bash
git clone https://github.com//motor-imagery-decoding.git
cd motor-imagery-decoding

python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate

pip install -r requirements.txt
```

The EEG stack (MNE, MOABB, pyRiemann, braindecode) is introduced from Class 08
onward; earlier classes only need the core scientific Python stack.
## Lessons Learned

> Filled in as the project progresses — this section is the payoff of the
> two-layer design.

- _Class 03_ — why group-aware splitting matters: leakage across
  trials/sessions/subjects inflates accuracy and hides it.
- _Class 10_ — reading results at the population level: between-subject
  variance, not a single number.
- _Class 11_ — when Riemannian geometry beats CSP+LDA, and why.

---

_This README is the project's front door. It is intentionally readable both by
a recruiter scanning for a finished BCI project and by someone curious about how
it was built from first principles._
