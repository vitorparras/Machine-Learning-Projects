# Machine Learning Projects

[![Code: AGPL-3.0](https://img.shields.io/badge/Code-AGPL--3.0-blue.svg)](LICENSE)
[![Content: CC BY-SA 4.0](https://img.shields.io/badge/Content-CC%20BY--SA%204.0-blue.svg)](LICENSE-CONTENT)
[![OpenSSF Scorecard](https://api.scorecard.dev/projects/github.com/vitorparras/Machine-Learning-Projects/badge)](https://scorecard.dev/viewer/?uri=github.com/vitorparras/Machine-Learning-Projects)
[![Contributor Covenant](https://img.shields.io/badge/Contributor%20Covenant-2.1-4baaaa.svg)](CODE_OF_CONDUCT.md)
[![PRs welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

Self-contained machine learning projects and experiments, each with its data
source, training scripts and analysis notebooks, built with libraries such as
scikit-learn, PyTorch and TensorFlow.

> **Status:** starting. The repository structure and conventions are defined
> below; projects are added over time. Contributions are welcome from day one.

## Table of contents

- [Goal](#goal)
- [Planned structure](#planned-structure)
- [Conventions](#conventions)
- [How to use it](#how-to-use-it)
- [Contributing](#contributing)
- [Security](#security)
- [Code of conduct](#code-of-conduct)
- [License](#license)

## Goal

Practical, reproducible examples of machine learning applied to concrete
problems. Every project answers the same questions: what problem is being
solved, what data is used, which techniques were tried, how the result was
evaluated, and what was learned.

## Planned structure

```text
Machine-Learning-Projects/
├── <project-name>/
│   ├── README.md              # problem, data, approach, results, lessons
│   ├── requirements.txt       # pinned dependencies for this project
│   ├── data/
│   │   ├── README.md          # where the data comes from, license, how to download
│   │   └── get_data.py        # download script (datasets are not committed)
│   ├── notebooks/
│   │   └── 01-exploration.ipynb
│   ├── src/
│   │   ├── train.py
│   │   └── evaluate.py
│   └── models/                # ignored by Git; produced by train.py
└── README.md
```

## Conventions

- **One project, one folder**, independent from the others, with its own
  `requirements.txt` and pinned versions.
- **Datasets are not committed.** Each project has a download script and a
  `data/README.md` stating the source and its license. Only small sample files
  (a few KB) may be versioned.
- **Reproducible runs**: fixed random seeds, recorded library versions, and
  notebooks executed top to bottom before committing (outputs cleared when
  large).
- **Honest evaluation**: hold-out or cross-validation, the metric justified in
  the README, and the baseline reported alongside the model.
- **No secrets or personal data** in notebooks, scripts or data samples.

## How to use it

```bash
git clone https://github.com/vitorparras/Machine-Learning-Projects.git
cd Machine-Learning-Projects/<project-name>
python -m venv .venv && source .venv/bin/activate   # on Windows: .venv\Scripts\activate
pip install -r requirements.txt
python data/get_data.py
python src/train.py
```

Then open the notebooks for the analysis and results.

## Contributing

New projects, improvements to existing ones and corrections are welcome. Please
read [CONTRIBUTING.md](CONTRIBUTING.md) first and open a
[suggestion](https://github.com/vitorparras/Machine-Learning-Projects/issues/new?template=content_suggestion.yml)
before starting a large project. The `main` branch is protected and only
receives changes through reviewed pull requests.

## Security

Found a problem in this repository's code, dependencies or configuration?
Follow [SECURITY.md](SECURITY.md) and report it privately.

## Code of conduct

This project follows the [Contributor Covenant](CODE_OF_CONDUCT.md). By
participating you agree to uphold it.

## License

This repository uses two licenses:

- **Code** (programs, scripts, configuration files and code samples):
  [GNU Affero General Public License v3.0](LICENSE) (AGPL-3.0).
- **Content** (documents, explanations, images and other non-code material):
  [Creative Commons Attribution-ShareAlike 4.0 International](LICENSE-CONTENT)
  (CC BY-SA 4.0).

Both require attribution, and both require that modified versions you
distribute, sell or run as a network service remain under the same license.
Copyright © Vitor Hugo Parras.

Datasets keep their own licenses, stated in each project.
