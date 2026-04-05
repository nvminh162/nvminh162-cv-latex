# Nguyen Van Minh - Modular LaTeX CV

A maintainable LaTeX CV system with one shared source and multiple company-specific versions.

## Why This Structure

- Keep core content in one place.
- Tailor each CV per role without duplication.
- Update once, propagate everywhere.

## Project Layout

- `base/`: shared CV source
- `base/preamble.tex`: packages, typography, layout
- `base/commands.tex`: reusable macros
- `base/sections/`: content blocks (`header`, `experience`, `projects`, `education`, `skills`)
- `companies/<company>/`: company-specific CV entry points
- `companies/<company>/main.tex`: section composition/order
- `companies/<company>/sections/`: company-specific sections (only files that differ)
- `main.tex`: top-level entry file (recommended for Overleaf)

## Overleaf Usage

1. Upload the full repository.
2. In `Menu > Main document`, choose:
   - `main.tex` (recommended), or
   - `companies/<company>/main.tex` for a specific version.
3. Click Recompile.

Do not compile include files directly (such as `base/preamble.tex` or `base/sections/*`).

## Create a New Company CV

1. Create `companies/<new-company>/`.
2. Add `main.tex` for that company.
3. Import shared sections from `base/sections/`.
4. For any section that needs custom content, create `companies/<new-company>/sections/<section>.tex` and import it in `main.tex`.

## Customization Pattern

Use direct component imports in each company `main.tex`:

```tex
\input{../../base/sections/header}
\input{../../base/sections/experience}
\input{../../base/sections/projects}
\input{sections/skills} % company-specific
\input{../../base/sections/education}
```

This keeps the architecture explicit and easy to maintain.

## Included Examples

- `companies/google-swe/`
- `companies/shopee-backend/`

## License

MIT
