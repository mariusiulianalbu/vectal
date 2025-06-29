# 💻 TECH STACK APROBAT - VECTAL.AI

> **ATENȚIE:** Acest stack tehnologic este FINAL și aprobat de utilizator!  
> **NU se schimbă NIMIC fără aprobare explicită!**

## 🏗️ ARHITECTURA PRINCIPALĂ

### 🌐 FRONTEND
- **Framework:** Next.js 15 cu App Router
- **Limbaj:** TypeScript (pentru IntelliSense în Cursor)
- **Styling:** Tailwind CSS
- **Componente:** Shadcn/ui 
- **State Management:** Zustand (mai simplu decât Redux)
- **Forms:** React Hook Form + Zod validation

**De ce:** Moderni, beginner-friendly, IntelliSense excelent în Cursor

### 🔧 BACKEND
- **API:** Next.js API Routes (full-stack în același proiect)
- **Database Platform:** Supabase (PostgreSQL + Auth + Real-time + Storage)
- **Autentificare:** Supabase Auth (built-in)
- **Validare:** Zod schemas
- **MCP Integration:** @supabase/mcp-server-supabase pentru Cursor AI

**De ce:** Platform complet, MCP support nativ, perfect pentru începători, production-ready din start

### 🤖 AI INTEGRATIONS
- **OpenAI:** SDK oficial pentru GPT models
- **Anthropic:** SDK oficial pentru Claude
- **Google:** SDK oficial pentru Gemini
- **Abstraction Layer:** Custom unified AI interface

**De ce:** SDK-uri oficiale, stabile și bem documentate

### 🛠️ DEVELOPMENT TOOLS
- **Editor:** Cursor AI cu MCP tools
- **Package Manager:** npm (nu pnpm, nu yarn - să rămânem simpli)
- **Linting:** ESLint + Prettier
- **Git Hooks:** Husky pentru pre-commit
- **Type Checking:** TypeScript strict mode

## 🚀 DEPLOYMENT & HOSTING

### 🌍 PRODUCȚIE
- **Hosting:** Vercel (integrare perfectă cu Next.js)
- **Baza de Date:** PostgreSQL pe Neon
- **Domain:** TBD
- **CDN:** Vercel Edge Network (built-in)

### 🔐 SECURITATE
- **Environment Variables:** .env.local pentru dezvoltare
- **API Keys:** Encryption pentru storage
- **HTTPS:** Forțat pe toate endpoint-urile
- **CORS:** Configurate pentru securitate

## 📁 STRUCTURA PROIECTULUI

```
vectal/
├── src/
│   ├── app/                 # Next.js App Router
│   │   ├── (dashboard)/     # Dashboard routes
│   │   ├── api/            # API endpoints
│   │   ├── auth/           # Auth pages
│   │   └── layout.tsx      # Root layout
│   ├── components/
│   │   ├── ui/            # Shadcn/ui components
│   │   ├── forms/         # Form components
│   │   └── features/      # Feature components
│   ├── lib/
│   │   ├── ai/           # AI integrations
│   │   ├── auth.ts       # NextAuth config
│   │   ├── db.ts         # Prisma client
│   │   └── utils.ts      # Utilities
│   ├── types/            # TypeScript types
│   └── styles/           # Global styles
├── prisma/
│   └── schema.prisma     # DB schema
├── public/               # Static files
├── docs/                # Project documentation
└── README.md            # Setup instructions
```

## 🎨 DESIGN SYSTEM

### 🌈 CULORI (APROBATE)
- **Primary:** Indigo (#6366f1)
- **Secondary:** Slate (#64748b)  
- **Success:** Green (#10b981)
- **Warning:** Amber (#f59e0b)
- **Error:** Red (#ef4444)
- **Background:** White/Slate-50
- **Text:** Slate-900/Slate-600

### 📱 RESPONSIVE BREAKPOINTS
- **Mobile:** 640px
- **Tablet:** 768px  
- **Desktop:** 1024px
- **Large:** 1280px

## 🔌 MCP TOOLS FOLOSITE

### 📚 RESEARCH
- **Context7:** Pentru documentația tehnologiilor
- **firecrawl:** Pentru best practices online
- **web_search:** Pentru soluții specifice

### 🔍 DEVELOPMENT  
- **codebase_search:** Pentru analiza codului
- **grep_search:** Pentru căutări exacte
- **GitHub:** Pentru repository management

## ⚡ PERFORMANCE TARGETS

- **First Load:** < 2 secunde
- **Lighthouse Score:** > 90
- **Bundle Size:** < 500KB
- **API Response:** < 500ms

## 🚫 CE NU FOLOSIM

- ❌ **Webpack custom configs** (folosim Next.js defaults)
- ❌ **CSS-in-JS** (folosim Tailwind)
- ❌ **Multiple state managers** (doar Zustand)
- ❌ **Complex build tools** (Next.js built-in)

---

## ⚠️ IMPORTANT PENTRU CURSOR AI

**ACEST STACK NU SE SCHIMBĂ FĂRĂ APROBARE!**

Dacă vrei să propui o schimbare:
1. Documentează motivul în `docs/PROPOSED_CHANGES.md`
2. Întreabă utilizatorul explicit
3. Așteaptă aprobare clară
4. Apoi update acest fișier

**Nu improviza! Nu schimba! Nu "optimizează" pe cont propriu!** 