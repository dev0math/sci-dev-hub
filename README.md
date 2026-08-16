# Sci-Dev Hub

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Markdown](https://img.shields.io/badge/Docs-Markdown-000000?logo=markdown&logoColor=white)](https://www.markdownguide.org/)
[![LaTeX](https://img.shields.io/badge/Math-LaTeX-008080?logo=latex&logoColor=white)](https://www.latex-project.org/)
[![Python](https://img.shields.io/badge/Code-Python-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![C++](https://img.shields.io/badge/Code-C%2B%2B-00599C?logo=cplusplus&logoColor=white)](https://isocpp.org/)
[![Java](https://img.shields.io/badge/Code-Java-ED8B00?logo=openjdk&logoColor=white)](https://www.java.com/)
[![Maintained by dev0math](https://img.shields.io/badge/Maintained%20by-dev0math-blueviolet)](https://github.com/dev0math)

A comprehensive, open-source archive of solved scientific problems across multiple disciplines. This repository provides detailed, step-by-step solutions to challenging problems, organized for easy browsing and long-term growth.

This is a long-term project. Content will be added continuously over months and years. The structure is designed to remain clean, organized, and scalable as the archive grows to hundreds or thousands of entries.

## Sciences Covered

- Mathematics
- Physics
- Chemistry
- Computer Science

## Technologies & Tools

| Purpose                     | Technology |
|------------------------------|------------|
| Documentation & content       | Markdown |
| Mathematical & scientific notation | LaTeX |
| Computer Science code samples | Python, C++, Java |
| Version control & hosting     | Git, GitHub |
| License                       | MIT License |

## Project Goals

- Build a high-quality, well-organized reference of solved problems across the sciences.
- Provide clear, step-by-step reasoning so learners can follow the full solution path, not just the final answer.
- Maintain a consistent format across all disciplines so the archive stays easy to navigate as it scales.
- Support long-term, continuous contributions without requiring structural reorganization.

## Repository Structure

```
sci-dev-hub/
│
├── README.md
├── LICENSE
├── CONTRIBUTING.md
│
├── sciences/
│   ├── mathematics/
│   │   ├── README.md
│   │   ├── problems/
│   │   └── solutions/
│   │
│   ├── physics/
│   │   ├── README.md
│   │   ├── problems/
│   │   └── solutions/
│   │
│   ├── chemistry/
│   │   ├── README.md
│   │   ├── problems/
│   │   └── solutions/
│   │
│   └── computer-science/
│       ├── README.md
│       ├── problems/
│       └── solutions/
│
├── templates/
│   ├── problem-template.md
│   └── solution-template.md
│
└── docs/
    └── naming-guide.md
```

Each science has its own folder containing a `problems/` directory and a matching `solutions/` directory. There is no further subdivision by topic within these folders — this keeps the structure simple and predictable as it scales.

## How to Browse

1. Choose a science folder under `sciences/`.
2. Open `problems/` to see the problem statements, or `solutions/` to see the worked solutions.
3. Each problem file has a matching solution file with the same number (for example, `problem-014.md` pairs with `solution-014.md`).

See `docs/naming-guide.md` for the full naming and numbering convention.

## How to Contribute

See `CONTRIBUTING.md` for the full guide, including formatting rules and the pull request process. In short:

1. Choose a science and pick the next available problem number.
2. Use `templates/problem-template.md` and `templates/solution-template.md` as your starting point.
3. Follow the naming convention described in `docs/naming-guide.md`.
4. Submit a pull request for review.

## Naming Conventions

- Problem files: `problem-001.md`, `problem-002.md`, and so on.
- Solution files: `solution-001.md`, `solution-002.md`, and so on.
- Numbers are always three digits, zero-padded (`001` through `999`).
- Every problem number must have a matching solution number.

Full details are in `docs/naming-guide.md`.

## Progress Tracker

| Science          | Problems Added | Solutions Added | Last Updated |
|------------------|-----------------|------------------|--------------|
| Mathematics      | 2               | 2                | 2026-08-16   |
| Physics          | 1               | 1                | 2026-08-16   |
| Chemistry        | 1               | 1                | 2026-08-16   |
| Computer Science | 1               | 1                | 2026-08-16   |

## License

This project is licensed under the MIT License. See `LICENSE` for details.

## Ownership

This project is owned and maintained by DEV @dev0math. All rights reserved by the project owner.

## Contact

For questions, suggestions, or collaboration inquiries, please open an issue in this repository or reach out to DEV @dev0math directly.
