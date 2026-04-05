# Nguyen Van Minh - Modular LaTeX CV

A maintainable LaTeX CV system with one shared source and multiple company-specific versions.

## Why This Structure

- Keep core content in one place.
- Tailor each CV per role without duplication.
- Update once, propagate everywhere.

## Project Layout

- `base/`: shared CV source
- `base/preamble.tex`: packages, typography, layout
- `base/commands.tex`: reusable macros and default variables
- `base/sections/`: content blocks (`header`, `experience`, `projects`, `education`, `skills`)
- `companies/<company>/`: company-specific CV entry points
- `companies/<company>/main.tex`: section composition/order
- `companies/<company>/overrides.tex`: role-specific overrides (for example skills)
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
2. Copy from `companies/example/`:
   - `main.tex`
   - `overrides.tex`
3. Update `main.tex` to reorder/include sections.
4. Update `overrides.tex` with role-specific settings.

## Skill Customization

Available override macros:

- `\SkillLanguages`
- `\SkillTools`

Example:

```tex
\renewcommand{\SkillLanguages}{Java, Python, SQL}
\renewcommand{\SkillTools}{Spring Boot, Kafka, Redis, Docker}
```

## Included Examples

- `companies/google-swe/`
- `companies/shopee-backend/`

## License

MIT
