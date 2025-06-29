# 🐛 ISSUES & PROBLEME - VECTAL.AI

> **Ultimul Update:** 3 ianuarie 2025

## 🔴 ISSUES ACTIVE

*Momentan nu există issues active*

---

## 📝 FORMAT PENTRU NOIS ISSUE:

### 🆔 ISSUE #001: [Titlu Scurt]
- **Data:** DD/MM/YYYY
- **Prioritate:** 🔴 Critica / 🟡 Medie / 🟢 Mică
- **Status:** 🔄 În progres / ⏳ Așteptare / ✅ Rezolvat
- **Categoria:** Bug / Feature / Performance / Security

**Descriere:**
Descrierea detaliată a problemei

**Pași pentru reproducere:**
1. Fă X
2. Apoi Y  
3. Vezi Z

**Soluții încercate:**
- [ ] Soluția A
- [ ] Soluția B

**Soluția finală:**
*Se completează când e rezolvat*

**Note:**
Observații suplimentare

---

## ✅ ISSUES REZOLVATE

*Când avem issues rezolvate, le mutăm aici*

---

## 🎯 BEST PRACTICES

### Când documentez un issue:
1. **Fii specific** - nu scrie "nu merge", ci "formularul de login returnează eroare 500"
2. **Include screenshots** dacă e UI related
3. **Menționează browser/OS** dacă e relevant
4. **Prioritizează corect** - nu totul e critic
5. **Update status** când lucrezi la el

### Când rezolv un issue:
1. **Testează soluția** înainte să marchezi ca rezolvat
2. **Documentează soluția** pentru viitor
3. **Commit cu referință** la issue
4. **Informează utilizatorul** dacă e major

---

## 🔧 TROUBLESHOOTING COMMON

### Problems cu Next.js:
- Module not found → `npm install`
- Port în uz → schimbă portul în `package.json`
- Build error → verifică sintaxa TypeScript

### Probleme cu Prisma:
- Schema changes → rulează `npx prisma db push`
- Migration error → șterge `prisma/dev.db` și recreează
- Connection error → verifică `DATABASE_URL`

### Probleme cu AI APIs:
- Rate limit → implementează retry cu delay
- Invalid API key → verifică în `.env.local`
- Model unavailable → failover la alt model

---

**Remember: Orice problema mică documentată acum = timp economisit mai târziu!** 