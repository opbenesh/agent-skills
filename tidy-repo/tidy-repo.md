---
description: Perform repository cleanup, documentation audits, and maintenance chores
---

# Tidy Repo

Use this skill to perform maintenance and hygiene checks on an existing repository.

## Steps

### 1. Documentation Audit
- **README.md**: 
    - Review the current `README.md`.
    - Ensure features, installation steps, and usage examples match the current codebase.
    - **Note**: Do not change the overall style or formatting established in the file.
- **CAPITAL-LETTERS.md**:
    - Identify files like `CONTRIBUTING.md`, `ARCHITECTURE.md`, `CHANGELOG.md`, etc., in the root.
    - Audit their content for accuracy.
    - If a file seems redundant or unnecessary for a project of this scale, notify the user.

### 2. Dependency Check
- **Requirements**:
    - Scan the codebase for imported libraries.
    - Compare against `requirements.txt`, `pyproject.toml`, or `setup.py`.
    - Update the requirement files to include missing dependencies or remove unused ones.

### 3. Git Hygiene
- **.gitignore**:
    - Review `.gitignore` to ensure it covers common environment-specific junk (e.g., `.DS_Store`, `__pycache__`, `.venv`, `.env`).
    - Remove entries that are no longer relevant.

### 4. Clutter & Structure Audit
- **Unnecessary Files**:
    - Perform a shallow search for:
        - Logs (`*.log`).
        - Temporary files (`*.tmp`, `*.swp`).
        - Obsolete/commented-out backup files (`main_old.py`, etc.).
    - **Note**: Ignore any files that are already listed in `.gitignore`.
    - Notify the user of any findings and ask for permission to delete.
- **Absolute Paths Audit**:
    - Scan `README.md`, `LICENSE`, and any `.yml`/`.yaml` files for absolute paths (e.g., paths starting with `/Users/`, `/home/`, or `C:\Users\`).
    - Recommend replacing them with relative paths (`./`) or placeholders (`~`, `${HOME}`).
- **Folder Structure**:
    - Evaluate if files are placed correctly according to common standards (e.g., tests in `tests/`, source in `src/` or root consistently).
    - Notify the user of any violations or confusing placements.

## Guidelines
- Always notify the user before deleting files or making major structural suggestions.
- **Ignore Git-ignored files**: Do not notify the user about clutter or structure violations for files that are already explicitly ignored in `.gitignore`.
- Respect the existing documentation style.
- Focus on "tidying" rather than refactoring core logic.
