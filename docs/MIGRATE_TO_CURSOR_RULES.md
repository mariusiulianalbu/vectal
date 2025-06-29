# 🔄 GHID MIGRARE CURSOR RULES

## Problemă Identificată
Momentan ai documentația în `docs/` dar Cursor AI nu poate să o folosească ca rules pentru că:
- Rules trebuie să fie în `.cursor/rules/`
- Trebuie să aibă extensia `.mdc` nu `.md`
- Trebuie să aibă frontmatter YAML corect

## Pași pentru Migrare:

### 1. Creează structura corectă:
```bash
# În PowerShell:
mkdir .cursor
mkdir .cursor/rules
mkdir .cursor/rules/always
mkdir .cursor/rules/project
mkdir .cursor/rules/development
```

### 2. Convertește CURSOR_AI_ULTRA_RULES.md în rules .mdc:

#### a) **Pre-Implementation Validation Rule**
Salvează ca: `.cursor/rules/always/pre-implementation-validation.mdc`
```mdc
---
description: 
globs: 
alwaysApply: true
---

# Pre-Implementation Validation

## MANDATORY: Înainte de orice implementare:
1. ✅ Verifică TECH_STACK.md
2. ✅ Verifică PROJECT_STATUS.md  
3. ✅ Verifică IMPLEMENTATION_PLAN.md
4. ✅ Confirmă cu userul dacă e ok

## Example Valid:
"Am verificat TECH_STACK.md și voi folosi Next.js 15 cu Supabase așa cum e specificat."

## Example Invalid:
"Voi folosi Firebase pentru auth." (când în TECH_STACK e Supabase)
```

#### b) **Intelligent Refusal Rule**
Salvează ca: `.cursor/rules/always/intelligent-refusal.mdc`
```mdc
---
description: 
globs: 
alwaysApply: true
---

# Intelligent Refusal System

Când user cere ceva care nu respectă documentația:
1. 🛑 STOP - Nu implementa
2. 💬 Explică de ce nu e ok
3. 📋 Arată ce zice documentația
4. ✅ Oferă alternativa corectă
```

#### c) **TypeScript Standards**
Salvează ca: `.cursor/rules/project/typescript-standards.mdc`
```mdc
---
description: Apply TypeScript best practices and standards for all TS/TSX files
globs: **/*.ts, **/*.tsx
alwaysApply: false
---

# TypeScript Standards

- Use TypeScript strict mode
- Prefer interfaces over types
- Use functional components
- Explicit return types for functions
```

### 3. Referințe între documente:

În `.cursor/rules/always/documentation-first.mdc`:
```mdc
---
description: 
globs: 
alwaysApply: true
---

# Documentation First Approach

Always check these files before any action:
- @docs/TECH_STACK.md
- @docs/PROJECT_STATUS.md
- @docs/IMPLEMENTATION_PLAN.md
- @docs/ENHANCED_FEATURES.md

Aceste fișiere rămân în docs/ dar sunt referențiate din rules.
```

### 4. Workflow Rules Chain:

Pentru workflow-ul pe care îl dorești (un fișier duce la altul):

`.cursor/rules/always/workflow-sequence.mdc`:
```mdc
---
description: 
globs: 
alwaysApply: true
---

# Development Workflow Sequence

## Pentru task nou:
1. Check @docs/PROJECT_STATUS.md → vezi ce phase suntem
2. Check @docs/IMPLEMENTATION_PLAN.md → vezi exact ce task
3. Check @docs/TECH_STACK.md → vezi ce tehnologii
4. Check @docs/CURSOR_AI_ULTRA_RULES.md → vezi regulile
5. Implement conform cu toate cele de mai sus

## Teaching Mode pentru Marius:
- Explică fiecare pas
- Arată comenzile exacte
- Screenshot-uri când e posibil
```

### 5. Settings Cursor pentru rules:

În Cursor Settings → General → Rules:
- ✅ Enable "Include .cursorrules file" (pentru legacy support)
- Poți adăuga și User Rules globale aici

### 6. Testare:
După ce creezi structura, testează cu:
- Deschide un fișier .ts → ar trebui să aplice TypeScript rules
- În chat întreabă despre proiect → ar trebui să consulte docs
- Cere o implementare → ar trebui să valideze mai întâi

## Structură Finală Recomandată:
```
vectal/
├── .cursor/
│   └── rules/
│       ├── always/          # Rules aplicate mereu
│       │   ├── pre-validation.mdc
│       │   ├── workflow.mdc
│       │   └── teaching-mode.mdc
│       ├── project/         # Rules pentru fișiere specifice
│       │   ├── typescript.mdc
│       │   ├── react.mdc
│       │   └── supabase.mdc
│       └── development/     # Rules pentru development
│           ├── git-workflow.mdc
│           └── testing.mdc
├── docs/                    # Documentația rămâne aici
│   ├── TECH_STACK.md       # Referențiat din rules
│   ├── PROJECT_STATUS.md   
│   └── etc...
```

## ⚠️ IMPORTANT:
- NU șterge fișierele din docs/ - ele sunt referențiate
- .mdc files sunt pentru rules behavior
- .md files din docs sunt pentru documentație
- Cursor va citi ambele, dar doar .mdc influențează comportamentul 