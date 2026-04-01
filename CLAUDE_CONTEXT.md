# 🤖 CLAUDE_CONTEXT.md — Leggi questo per primo!

> Questo file è scritto DA Claude PER Claude.
> Ogni volta che apri questo progetto, leggi questo file prima di fare qualsiasi cosa.
> Aggiornalo se fai modifiche importanti alla struttura o alla configurazione.

---

## 📍 Percorso progetto
```
C:\Users\mirco\Desktop\papermodtrae\papermod
```

---

## 🧠 Cos'è questo progetto?
Sito web **SaaS multilingua** costruito con **Hugo** + tema **hugo-saasify-theme**.
Deployment su **Cloudflare Pages**: https://papermod-1rp.pages.dev/
Repository GitHub: `cialdecompatibili-netizen/papermod` (branch: `main`)
CMS: **Decap CMS** (Netlify CMS fork) accessibile su `/admin/`

---

## 🌍 Lingue attive
| Codice | Nome     | Peso | Lingua default? |
|--------|----------|------|-----------------|
| `it`   | Italiano | 1    | ✅ SÌ           |
| `en`   | English  | 2    | ❌              |

**Struttura file multilingua:** `multiple_files`
→ Stesso file con suffisso lingua: `post.it.md`, `post.en.md`
→ Tutti i contenuti stanno nella cartella `content/` (NON sottocartelle per lingua)

---

## 📁 Struttura cartelle chiave
```
papermod/
├── CLAUDE_CONTEXT.md       ← QUESTO FILE (leggi per primo!)
├── GUIDA_PROGETTO.md       ← Guida operativa umana
├── hugo.toml               ← Config Hugo principale (lingue, params, build)
├── tailwind.config.js      ← Config Tailwind CSS
├── postcss.config.js       ← Config PostCSS
├── package.json            ← Script npm (dev, build...)
│
├── content/                ← TUTTI i contenuti del sito
│   ├── _index.it.md / _index.en.md   → Home Page
│   ├── blog/               → Articoli (*.it.md e *.en.md)
│   ├── categories/         → Tassonomia categorie
│   ├── company.it.md/.en.md
│   ├── careers.it.md/.en.md
│   ├── pricing.it.md/.en.md
│   ├── privacy.it.md/.en.md
│   └── license.it.md/.en.md
│
├── data/
│   ├── menus/it.yml        → Menu header + footer in italiano
│   ├── menus/en.yml        → Menu header + footer in inglese
│   ├── settings.it.yml / settings.en.yml → Impostazioni sito per lingua
│   └── settings.yml        → Impostazioni globali
│
├── layouts/                → Override layout (priorità sul tema)
│   ├── index.html          → Home Page layout
│   ├── partials/           → header.html, footer.html, blog-list.html, language-switcher.html
│   └── _default/           → baseof.html, list.html, single.html
│
├── assets/css/             → CSS personalizzato (override tema)
│   ├── main.css
│   └── extended/           → CSS aggiuntivo
│
├── static/
│   ├── admin/config.yml    ← CONFIG CMS DECAP (collezioni, campi, i18n)
│   ├── images/             → Logo, favicon, immagini statiche
│   └── css/style.css
│
├── themes/hugo-saasify-theme/  ← Tema base (NON modificare direttamente)
│   ├── layouts/            → Layout originali del tema
│   ├── assets/             → CSS/JS del tema
│   └── tailwind.config.js
│
├── functions/api/          → Cloudflare Functions per autenticazione CMS
│   ├── auth.js
│   └── callback.js
│
└── public/                 → Output build Hugo (generato, non toccare)
```

---

## ⚙️ File di configurazione critici

### hugo.toml — sezioni importanti
- `defaultContentLanguage = "it"` → italiano è la lingua di default
- `[languages.it]` e `[languages.en]` → blocchi configurazione per lingua
- `contentDir = "content"` → ENTRAMBE le lingue usano la stessa cartella content
- `[params.blog]` → configurazione sidebar blog
- `[params.cta]` → sezione call-to-action globale
- `[markup]` → configurazione highlight codice e table of contents

### static/admin/config.yml — CMS Decap
- `backend.repo = "cialdecompatibili-netizen/papermod"`
- `i18n.structure = "multiple_files"` → file separati per lingua
- `i18n.locales = [it, en]` → lingue CMS attive
- **Collezioni disponibili:**
  - `settings` → Impostazioni sito (pagina home, pagina blog, logo, social)
  - `blog` → Articoli del blog
  - `categories` → Gestore categorie
  - `pages` → Pagine generiche
  - `home_page_special` → Home Page con campi speciali
  - `menus` → Menu italiano e inglese

---

## 🚀 Comandi utili (da eseguire nella root del progetto)

```powershell
# Avviare server di sviluppo Hugo
hugo server -D

# Build completo del sito
hugo

# Avviare con TailwindCSS in watch mode (se configurato in package.json)
npm run dev

# Build produzione
npm run build
```

---

## ⚠️ Cose importanti da sapere / errori comuni

1. **NON modificare i file in `themes/hugo-saasify-theme/`** — i file in `layouts/` e `assets/` del progetto hanno la priorità e fanno override del tema. Modifica sempre lì.

2. **Nomi file contenuti:** devono terminare con `.it.md` o `.en.md` (es: `articolo.it.md`). Se un file non ha suffisso lingua, Hugo lo tratta come default (italiano).

3. **Categorie:** le categorie del blog si gestiscono in `content/categories/` come file `.md`. Il widget CMS usa `relation` per collegarle agli articoli.

4. **Immagini caricate dal CMS** → vanno in `static/images/uploads/` e si referenziano con `/images/uploads/nomeimmagine.jpg`.

5. **Autenticazione CMS locale:** per lavorare in locale con il CMS, decommentare `local_backend: true` in `static/admin/config.yml`.

6. **Menus:** i menu non sono in `hugo.toml` ma nei file YAML: `data/menus/it.yml` e `data/menus/en.yml`.

7. **`content_backup/`** → cartella di backup vecchi contenuti, non usata dal sito attivo.

---

## 🔧 Ultima sessione di lavoro — aggiorna questa sezione!

**Data ultima modifica:** _(da aggiornare)_
**Cosa stavamo facendo:**
- Impostazione iniziale del file CLAUDE_CONTEXT.md
- Progetto funzionante con Hugo + tema Saasify + CMS Decap
- Multilingua IT/EN attivo con struttura `multiple_files`
- Fix collezione `categories` nel CMS: aggiunto `i18n: true`, campi completi (descrizione breve, descrizione completa markdown, immagine, SEO block), `draft` default a `false`

**TODO / cose in sospeso:**
- Verificare che la pagina categoria su Hugo mostri effettivamente il campo `body` (descrizione lunga) nel layout — potrebbe servire un override del layout tassonomia in `layouts/taxonomy/categories.html`

---

## 📝 Note rapide per operazioni comuni

### Aggiungere una nuova lingua (es. Francese)
1. In `hugo.toml`: aggiungi blocco `[languages.fr]` con `contentDir = "content"`
2. In `static/admin/config.yml`: aggiungi `fr` a `i18n.locales: [it, en, fr]`
3. Crea file `data/menus/fr.yml` per il menu francese
4. Aggiungi sezione menu FR in `static/admin/config.yml` sotto `menus`
5. I contenuti: crea `.fr.md` affiancati agli `.it.md` esistenti

### Aggiungere una nuova pagina
1. Crea `content/nomepagina.it.md` e `content/nomepagina.en.md`
2. Frontmatter minimo: `title`, `draft: false`, `layout` (optional)
3. Aggiungi voce al menu in `data/menus/it.yml` e `data/menus/en.yml`

### Modificare il layout Home Page
→ Modifica `layouts/index.html` (NON il file nel tema)

### Modificare header/footer
→ Modifica `layouts/partials/header.html` o `layouts/partials/footer.html`
