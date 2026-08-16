# Naming Guide

This guide defines the file naming and numbering conventions used throughout Sci-Dev Hub. Following these rules consistently is what keeps the archive scalable as it grows.

## File Naming

- Problem files: `problem-001.md`, `problem-002.md`, `problem-003.md`, and so on.
- Solution files: `solution-001.md`, `solution-002.md`, `solution-003.md`, and so on.
- Every file name uses lowercase letters only.
- Use hyphens (`-`) to separate words or parts of the name. Do not use spaces or underscores.

## Numbering System

- Numbers are always three digits, zero-padded: `001` through `999`.
- Numbering is independent per science. Each science folder (`mathematics`, `physics`, `chemistry`, `computer-science`) has its own sequence starting at `001`.
- Do not reuse a number within the same science, even if an earlier entry is removed.
- When adding a new problem, use the next unused number in that science's sequence.

## Matching Problems and Solutions

- Every `problem-XXX.md` must have a corresponding `solution-XXX.md` with the same number, in the matching `solutions/` folder.
- A problem should not be merged into the repository without its solution, and vice versa.

## Images

- If a problem or solution references an image (a diagram, figure, or scanned content), store it in an `images/` folder inside the relevant science folder (for example, `sciences/physics/images/`).
- Name image files to match their related entry, for example: `problem-014-fig1.png`, `problem-014-fig2.png`.
- Reference images in Markdown using a relative path, for example: `![description](../images/problem-014-fig1.png)`.
- Creating the `images/` folder is optional and only needed when a science folder actually contains image-based content.

## Examples

Correct:
- `sciences/mathematics/problems/problem-007.md`
- `sciences/mathematics/solutions/solution-007.md`

Incorrect:
- `Problem_7.md` (wrong case, wrong separator, not zero-padded)
- `problem-7.md` (not three digits)
- `problem 007.md` (contains a space)
