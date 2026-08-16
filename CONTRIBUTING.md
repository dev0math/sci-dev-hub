# Contributing to Sci-Dev Hub

Thank you for your interest in contributing. This guide explains how to add new problems and solutions, and what is expected of every contribution.

## Before You Start

- This project is owned and maintained by DEV @dev0math.
- All contributions should follow the structure and conventions described below.
- If you are unsure where something belongs, open an issue to ask before submitting a pull request.

## How to Add a New Problem and Solution

1. Choose the correct science folder under `sciences/` (`mathematics`, `physics`, `chemistry`, or `computer-science`).
2. Check the `problems/` folder for that science to find the next available number.
3. Copy `templates/problem-template.md` into `sciences/<science>/problems/` and rename it using the naming convention below.
4. Copy `templates/solution-template.md` into `sciences/<science>/solutions/` and rename it to match the same number.
5. Fill in both files completely. Do not leave placeholder text in a submitted file.
6. Submit both files together in the same pull request.

## File Naming Rules

- Problem files: `problem-XXX.md`
- Solution files: `solution-XXX.md`
- `XXX` is a three-digit, zero-padded number (`001`, `002`, ... `999`).
- A problem and its solution must always share the same number.
- Use lowercase letters and hyphens only. Do not use spaces or underscores in file names.

See `docs/naming-guide.md` for full details.

## Formatting Guidelines

- Write all content in Markdown.
- Use LaTeX for mathematical notation, wrapped in standard Markdown math delimiters (`$...$` for inline expressions, `$$...$$` for block expressions).
- Keep problem statements clear and self-contained. Include all information needed to solve the problem.
- Keep solutions structured and easy to follow: state the key insight first, then walk through the steps, then give the final answer.
- Use code blocks with the appropriate language tag for any code included in Computer Science entries.
- Do not use emojis in problem files, solution files, or documentation.

## Pull Request Process

1. Fork the repository (or create a branch, if you have write access).
2. Add your problem and solution files following the rules above.
3. Open a pull request with a clear title describing the problem being added (for example, "Add problem-045: Physics - Projectile Motion").
4. In the pull request description, briefly note the science, topic, and difficulty level.
5. Wait for review. Changes may be requested to align formatting or content with project standards.
6. Once approved, the pull request will be merged and the progress tracker in the main README will be updated.

## Code of Conduct

- Be respectful and constructive in all discussions, reviews, and comments.
- Credit original sources for any problem that is not your own original work.
- Do not submit plagiarized solutions or content copied without attribution.
- Keep feedback focused on the content, not the contributor.
- Assume good faith, and ask questions if something is unclear rather than assuming.

Thank you for helping build this archive.
