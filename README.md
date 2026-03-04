# Git and AI-Assisted Model Building

This repository is a lab demo for learning two skills together:
1. Practical Git workflow (`add -> commit -> push`)
2. AI-assisted data science workflow for model building

The dataset is the City of Vancouver Business Licences open dataset, and the modeling task is binary classification: active (`Issued`) vs inactive (`Cancelled` / `Gone Out of Business`) licences.

## Demo Flow

1. Create or open repo on GitHub
2. Clone and set up environment with `uv`
3. First Git cycle: stage, commit, push project structure
4. Use AI to review and split notebooks by model
5. Run model notebook and generate outputs
6. Second Git cycle: commit and push model/report updates

## How Git Tracks Work

- Untracked/modified files: `git status`
- Stage snapshot content: `git add .`
- Save local history point: `git commit -m "message"`
- Sync to remote repo: `git push`

## Project Structure (Noble's Rules)

```text
lab5-model-building/
├── .gitignore              # what not to push
├── README.md               # project overview
├── requirements.txt        # share dependencies (not .venv/)
├── data/                   # datasets
│   └── business-licences.csv
├── src/                    # notebooks and scripts
│   ├── model_building_complete.ipynb
│   ├── model_logistic_regression.ipynb
│   ├── model_random_forest.ipynb
│   ├── notebooks/
│   └── scripts/
└── reports/                # exported reports/figures
```

Note: depending on notebook working directory, some generated artifacts may appear in `src/reports/` as well.

## Key Concepts in This Repo

- Git version control for reproducible collaboration
- Deliberate project organization (Noble's rules)
- `.gitignore` hygiene (exclude envs, caches, machine-specific files)
- Virtual environment isolation with `uv`
- Separation of concerns (one model notebook per file)
- AI-assisted workflow with human verification

## Quick Start

```bash
uv venv .venv
uv pip install --python .venv/bin/python -r requirements.txt
source .venv/bin/activate
```

Run one notebook at a time from `src/`:
- `src/model_logistic_regression.ipynb`
- `src/model_random_forest.ipynb`
- `src/model_building_complete.ipynb` (combined workflow)

## Data Source

Vancouver Open Data Portal:
https://opendata.vancouver.ca/explore/dataset/business-licences/

## References

- SW Carpentries: Organize Deliberately
- Noble's Rules (PLOS paper)
- SW Carpentries: Version Control with Git (Git Novice)
