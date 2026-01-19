---
description: Bootstrap a new repository with essential configuration and documentation
---

# Repo Bootstrapper

This skill automates the setup of a new repository by ensuring it has a README, License, secret detection, and a virtual environment.

## Steps

### 1. Documentation Check (README.md)
- Check if `README.md` exists in the repository root.
- If missing, invoke the `github-readme-builder` skill to generate a professional README.

### 2. License Setup (MIT)
- Check if a `LICENSE` or `LICENSE.txt` exists.
- If missing:
    - Copy the template from direct sibling file `./LICENSE_TEMPLATE`.
    - Update `[YEAR]` with the current year.
    - Update `[FULL NAME]` with "Ben Esh".
    - Write it to the project root as `LICENSE`.

### 3. Secret Detection (pre-commit)
- Check if `.pre-commit-config.yaml` exists.
- If missing, create it with the following content to detect secrets (Gitleaks) and prevent absolute paths:
    ```yaml
    repos:
      - repo: https://github.com/gitleaks/gitleaks
        rev: v8.18.2
        hooks:
          - id: gitleaks
      - repo: local
        hooks:
          - id: no-absolute-paths
            name: No Absolute Paths
            entry: '(/Users/|/home/|C:\\Users\\)'
            language: pygrep
            types: [text]
            exclude: .pre-commit-config.yaml
    ```
- Run `pre-commit install` to activate the hook.

### 4. GitHub Actions (CI)
- Create `.github/workflows/ci.yml` to automate testing and security scanning.
- The workflow should:
    - Run on `push` and `pull_request` to the main branch.
    - Run **Gitleaks** to catch secrets in CI.
    - Install dependencies and run **tests** (e.g., `pytest`).
- Example template:
    ```yaml
    name: CI
    on: [push, pull_request]
    jobs:
      test:
        runs-on: ubuntu-latest
        steps:
          - uses: actions/checkout@v4
            with:
              fetch-depth: 0
          - name: Set up Python
            uses: actions/setup-python@v5
            with:
              python-version: '3.11'
          - name: Gitleaks Scan
            uses: gitleaks/gitleaks-action@v2
            env:
              GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          - name: Install dependencies
            run: |
              python -m pip install --upgrade pip
              pip install -r requirements.txt
          - name: Run tests
            run: python -m pytest
    ```

### 6. Environment Variables (.env)
- Check if `.env` exists.
- If missing:
    - If `.env.example` exists, copy it to `.env`.
    - Otherwise, create a template `.env` based on known project requirements.
    - Notify the user to fill in the required secrets.

## Guidelines
- Always confirm before overwriting any existing files.
- Prefer creating a `venv` named `venv` in the project root.
- Use `github-readme-builder` for high-quality README generation.
