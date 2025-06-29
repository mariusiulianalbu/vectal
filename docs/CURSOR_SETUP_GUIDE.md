# 🎯 CURSOR AI - SETUP COMPLET PENTRU VECTAL.AI

> **GHID FINAL pentru configurarea optimă a Cursor AI pentru proiectul nostru**

## 🔴 IMPORTANT: CITEȘTE PRIMUL ACEST FIȘIER!

Acest ghid conține **tot ce trebuie să știi** pentru a avea Cursor AI configurat optim pentru proiectul Vectal.ai.

---

## 📋 CURSOR RULES - CE SUNT ȘI CUM LE FOLOSIM?

### 🏗️ **Project Rules** (RECOMANDAT pentru noi)
- **Unde:** `.cursor/rules/*.mdc` files
- **Beneficii:** Versioning, organizare, auto-trigger, team sharing
- **Perfect pentru:** Proiectul nostru Vectal.ai

### 🌍 **User Rules** (Doar pentru preferințe globale)
- **Unde:** Cursor Settings > Rules for AI
- **Beneficii:** Se aplică la toate proiectele
- **Limitări:** Plain text, nu se pot organiza

---

## ⚡ MCP MANAGEMENT - REGULI IMPORTANTE!

### ✅ **BEST PRACTICES CONFIRMATE:**
1. **NU activa toate MCP-urile deodată** - cauze performance issues
2. **Activează doar MCP-urile necesare** pentru task-ul curent
3. **Pentru database work:** Activează Supabase MCP
4. **Pentru web research:** Activează firecrawl
5. **Pentru documentație:** Activează Context7

### 🔧 **MCP-uri ESENȚIALE pentru proiectul nostru:**
- `@supabase/mcp-server-supabase` - pentru database work
- `Context7` - pentru documentație oficială
- `firecrawl` - pentru research online

---

## 🚀 SUPABASE MCP CONFIGURATION

### 📁 **Configurare pentru Windows:**
Creez fișierul `.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "supabase": {
      "command": "cmd",
      "args": [
        "/c",
        "npx",
        "-y",
        "@supabase/mcp-server-supabase@latest",
        "--read-only",
        "--project-ref=<REPLACE-WITH-PROJECT-REF>"
      ],
      "env": {
        "SUPABASE_ACCESS_TOKEN": "<REPLACE-WITH-TOKEN>"
      }
    }
  }
}
```

### 🔐 **Unde găsesc valorile:**
1. **Project Ref:** Supabase Dashboard > Settings > General
2. **Access Token:** Supabase Dashboard > Settings > Access Tokens

---

## 📝 PROJECT RULES PENTRU VECTAL.AI

### 🎯 **Regula Principală pentru Proiect:**
Creez `.cursor/rules/vectal-main.mdc`:

```mdc
---
description: Main rules for Vectal.ai project - AI assistant similar to vectal.ai
globs: ["*.ts", "*.tsx", "*.js", "*.jsx"]
alwaysApply: true
---

# Vectal.ai Project Rules

## Stack Tehnologic FINAL
- Next.js 15 cu App Router
- TypeScript (OBLIGATORIU)
- Tailwind CSS pentru styling
- Shadcn/ui pentru componente
- Supabase pentru database + auth + real-time
- Zustand pentru state management

## Pentru Marius (Începător)
- ÎNTOTDEAUNA explică ce faci și de ce
- Folosește comentarii detaliate în cod
- Păstrează codul simplu și ușor de înțeles
- Nu implementa nimic fără să testezi

## Reguli de Calitate
- TypeScript strict mode
- Error handling pentru toate API calls
- Responsive design obligatoriu
- Accessibility (a11y) considerations

## Supabase Specific
- Folosește Row Level Security pentru securitate
- Real-time subscriptions pentru updates
- Supabase Auth pentru autentificare
- Supabase Storage pentru fișiere

@../docs/TECH_STACK.md
@../docs/CURSOR_AI_ULTRA_RULES.md
```

### 🔧 **Regula pentru Supabase:**
Creez `.cursor/rules/supabase.mdc`:

```mdc
---
description: Supabase integration rules and best practices
globs: ["**/supabase/**/*", "**/lib/supabase*", "**/api/**/*"]
alwaysApply: false
---

# Supabase Integration Rules

## Connection & Setup
- Întotdeauna folosește environment variables pentru keys
- NICIODATĂ nu hardcodez API keys în cod
- Folosește createClient cu corectă configurație

## Database Operations
- Folosește Row Level Security pentru toate tabele
- Validează input-ul cu Zod înainte de database
- Handle errors cu try-catch pentru toate queries
- Folosește TypeScript types generate de Supabase

## Authentication
- Implementează proper session management
- Verifică authentication status în middleware
- Handle logout corect cu supabase.auth.signOut()

## Real-time
- Cleanup subscriptions în useEffect cleanup
- Handle connection errors gracefully
- Use proper typing pentru real-time events

## MCP Integration
- Test connections prin Cursor MCP
- Folosește MCP tools pentru debugging database
- Verifică schema changes prin MCP
```

---

## 🎮 WORKFLOW COMPLET CURSOR AI

### 🔄 **La începutul oricărui chat nou:**
1. ✅ Citesc `docs/CURSOR_AI_ULTRA_RULES.md`
2. ✅ Verific `docs/PROJECT_STATUS.md` 
3. ✅ Consultă `docs/TECH_STACK.md`
4. ✅ Review `docs/IMPLEMENTATION_PLAN.md`

### ⚡ **Pentru fiecare task:**
1. ✅ **ANALIZEZ** compatibilitatea cu stack-ul nostru
2. ✅ **VALIDEZ** că task-ul e potrivit pentru faza curentă
3. ✅ **ACTIVEZ** MCP-urile necesare pentru task
4. ✅ **IMPLEMENTEZ** cu explicații pas cu pas
5. ✅ **TESTEZ** că totul funcționează
6. ✅ **DOCUMENTEZ** în `docs/CHANGES.md`

---

## 🛡️ SAFETY NETS PENTRU MARIUS

### 🔴 **Când să întreb utilizatorul:**
- Dacă ceva nu e clar în cerință
- Dacă task-ul ar schimba tech stack-ul aprobat
- Dacă apar erori pe care nu le pot fixa
- Dacă implementarea e prea complexă pentru faza curentă

### 🟡 **Când să propun alternative:**
- Dacă cererea e prea ambițioasă pentru momentul curent
- Dacă există o cale mai simplă pentru același rezultat
- Dacă implementarea ar introduce buguri

### 🟢 **Când să implementez direct:**
- Task-ul e clar și se potrivește cu planul
- Sunt confident că implementarea e corectă
- Am toate informațiile necesare

---

## 🎯 CURSOR AI - CHECKLISTA FINALĂ

### ✅ **Înainte de orice implementare:**
- [ ] Am citit toate docs/ files?
- [ ] Task-ul e compatibil cu Supabase + Next.js 15?
- [ ] Am activat MCP-urile necesare?
- [ ] Înțeleg ce vrea utilizatorul?

### ✅ **În timpul implementării:**
- [ ] Explic fiecare pas pentru Marius?
- [ ] Testez codul după fiecare schimbare?
- [ ] Folosesc TypeScript strict?
- [ ] Handle errors corect?

### ✅ **După implementare:**
- [ ] Codul funcționează local?
- [ ] Am documentat în CHANGES.md?
- [ ] Am explicat ce am făcut?
- [ ] Am sugerat următorii pași?

---

## 🚀 NEXT STEPS PENTRU MARIUS

1. **Setup Cursor Rules:**
   - Creez fișierele `.cursor/rules/*.mdc` de mai sus
   - Verific că Cursor le recunoaște în Settings > Rules

2. **Setup Supabase MCP:**
   - Creez cont Supabase
   - Configurez `.cursor/mcp.json` cu valorile reale
   - Testez conexiunea prin Cursor

3. **Start Implementation:**
   - Încep cu `docs/IMPLEMENTATION_PLAN.md`
   - Urmez MILESTONE 1.1: Setup Mediu

**Remember: Cu acest setup, Cursor AI va fi expertul tău perfect pentru Vectal.ai!** 🎉 