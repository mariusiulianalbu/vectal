# 📚 Cursor Rules pentru Vectal.ai

## Ce sunt Cursor Rules?
Cursor Rules sunt instrucțiuni care ghidează comportamentul AI-ului în Cursor. Acestea asigură consistență și respectarea standardelor proiectului.

## Structura Folderelor

```
.cursor/
└── rules/
    ├── always/         # Rules aplicate MEREU
    │   ├── pre-implementation-validation.mdc
    │   └── teaching-mode-marius.mdc
    ├── project/        # Rules pentru fișiere specifice  
    │   ├── typescript-nextjs-standards.mdc
    │   └── supabase-integration.mdc
    └── development/    # Rules pentru development workflow
```

## Tipuri de Rules

### 1. **Always Rules** (`alwaysApply: true`)
- Se aplică la FIECARE interacțiune
- Pentru: validări critice, teaching mode
- Exemplu: `pre-implementation-validation.mdc`

### 2. **Auto-Attached Rules** (cu `globs`)
- Se aplică automat când lucrezi cu anumite fișiere
- Pentru: standarde de cod, formatare
- Exemplu: `typescript-nextjs-standards.mdc` pentru `*.ts, *.tsx`

### 3. **Agent Rules** (cu `description`)
- AI decide când să le aplice bazat pe context
- Pentru: integrări specifice, features complexe
- Exemplu: `supabase-integration.mdc`

### 4. **Manual Rules** (fără glob/description)
- Aplicate doar când le menționezi explicit
- Pentru: operații rare sau periculoase

## Cum să adaugi o Rule nouă

1. Creează fișier `.mdc` în folderul potrivit
2. Adaugă frontmatter YAML:
```yaml
---
description: Pentru agent rules
globs: **/*.ts  # Pentru auto-attach
alwaysApply: false  # sau true pentru always
---
```
3. Scrie regula în Markdown
4. Include exemple Valid/Invalid

## Best Practices
- Keep rules focused (max 50 linii)
- Always include examples
- Use clear, actionable language
- Reference docs with @docs/filename.md

## Debugging
- Dacă o regulă nu se aplică, verifică:
  - Este în `.cursor/rules/`?
  - Are extensia `.mdc`?
  - Frontmatter-ul e valid YAML?
  - Pentru glob rules: fișierul match pattern? 