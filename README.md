# Nguyen Van Minh - Curriculum Vitae with LaTeX

> Personal modular LaTeX CV system by **Nguyen Van Minh (nvminh162)**

---

## Overview

This repository is a **modular LaTeX-based CV system** designed to efficiently manage and generate multiple tailored resumes for different companies and roles.

Instead of maintaining separate CV files, this project follows a **single-source-of-truth architecture**, allowing reusable content and easy customization per application.

---

## Key Features

* **Modular structure** — reusable sections and components
* **Company-specific CVs** — tailored resumes per job
* **No duplication** — maintain content in one place
* **Automated build** — generate all CVs with a script
* **Clean output management** — organized PDF exports

---

## Project Structure

```
nvminh162-cv-latex/
│
├── base/                      # Core reusable content
│   ├── main.tex
│   ├── preamble.tex
│   ├── sections/
│   ├── components/
│   ├── styles/
│   └── assets/
│
├── companies/                # Company-specific CVs
│   ├── google-swe/
│   ├── shopee-backend/
│   └── vng-intern/
│
├── output/                   # Generated PDFs
├── scripts/                  # Build scripts
│
├── .gitignore
├── README.md
└── LICENSE
```

---

## How It Works

### Base Layer (`base/`)

Contains all shared content:

* education
* experience
* projects
* skills

This acts as the **single source of truth**.

---

### Custom Layer (`companies/`)

Each folder represents a tailored CV for a specific role/company.

Example:

```
companies/google-swe/
companies/shopee-backend/
```

Each includes:

* `main.tex` → entry point
* `overrides.tex` → customization logic

---

### Overrides System

Customize CV per company by:

* reordering sections
* highlighting relevant experience
* excluding irrelevant content

---

## Build Instructions

### 1. Build a specific CV

```bash
cd companies/google-swe
pdflatex main.tex
```

---

### 2. Build all CVs (recommended)

```bash
bash scripts/build.sh
```

Outputs will be generated in:

```
output/
```

---

## Best Practices

* Keep all shared content inside `base/`
* Avoid duplicating sections across CVs
* Use `overrides.tex` for customization
* Name folders clearly:

  * `google-swe`
  * `shopee-backend`
  * `vng-intern`

---

## Output

Generated CVs are stored in:

```
output/*.pdf
```

These files are ready to:

* attach to job applications
* share via GitHub

---

## Author

**Nguyen Van Minh**
GitHub: https://github.com/nvminh162

---

## License

This project is licensed under the MIT License.

---

## Philosophy

> Treat your CV like a system — not a document.

---
