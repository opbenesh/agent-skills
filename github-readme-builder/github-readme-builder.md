---
description: Build or enhance a professional GitHub README for any project
---

# GitHub README Builder

## Styles

You can choose from the following predefined styles or mix them as needed:

### 1. Simple CLI Tool (Technical Focus)
*Extracted from high-quality community standards like Simon Willison's tools.*
- **Header**: Repo name + Badges (PyPI, Changelog, Tests, License).
- **Introduction**: 1-2 sentence technical pitch + background link (if available).
- **Installation**: Quick `pip` (or equivalent) install command.
- **Usage**: Primary command syntax + brief explanation of output.
- **Options**: Bulleted list of flags with nested code examples for each.
- **Examples**: Full directory tree visualization + multiple walkthrough scenarios (input/output).
- **Advanced Features**: Detailed sections for specific behaviors (e.g., stdin, XML output).
- **Development**: Setup instructions (venv, editable install, test command).

### 2. General Professional (Feature Focus)
*Ideal for general libraries, web apps, or APIs.*
- **Header**: Icon + Project Name + Badges.
- **Pitch**: High-level value proposition.
- **Features**: Visual list of key capabilities with icons.
- **Prerequisites**: Clear list of environment requirements.
- **Quick Start**: 1-2-3 numbered steps for local setup.
- **Output**: Screenshot or text representation of results.
- **How It Works**: High-level architecture or logic summary.
- **License**: MIT/Apache reference.

## Steps

1. **Analyze the project structure**
   - List all files and directories in the repository root.
   - Identify the main entry point (e.g., `main.py`, `index.js`, `src/`).
   - Look for existing config files, requirements, or package manifests.

2. **Understand the codebase**
   - Read the main application file(s) to understand functionality.
   - Check for configuration files to document setup requirements.
   - Review any existing README content to preserve important info.

3. **Identify key information**
   - Determine which **Style** is most appropriate (CLI vs. General).
   - Extract project name, description, features, and setup steps.
   - Find version history, test workflows, and license for badges.

4. **Build the README**
   - Use the structure defined in the chosen **Style** above.
   - Ensure all code examples are realistic and tested against the code.
   - Use proper markdown formatting and hierarchy.

5. **Style Guidelines**
   - Use emojis for scannability, but keep text technical and concise.
   - Include a configuration table for complex tools.
   - Link to LICENSE file if present.
   - Add shields.io badges for a professional look.

6. **Write the README.md file**
   - Overwrite existing README if present (preserve any critical info).
