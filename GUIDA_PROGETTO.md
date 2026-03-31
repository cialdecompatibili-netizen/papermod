# 📘 Guida Rapida Progetto Saasify

Questa guida spiega come gestire il sito e come aggiungere nuove lingue in futuro.

## 🚀 Struttura del Progetto
Il sito è costruito con **Hugo** e usa il tema **Saasify**.
Le lingue sono organizzate in cartelle separate dentro `content/`:
- `content/it/` -> Italiano (Lingua principale)
- `content/en/` -> Inglese

## 🌍 Come aggiungere una nuova lingua (es. Francese)

### 1. Configurazione Hugo
Apri il file `hugo.toml` e aggiungi questo blocco sotto `[languages]`:
```toml
[languages.fr]
  languageCode = "fr-fr"
  languageName = "Français"
  title = "Saasify FR"
  weight = 3
  contentDir = "content/fr"
```

### 2. Creazione Cartelle
Crea la cartella per i nuovi file:
- `content/fr/`
- `content/fr/blog/`
- `content/fr/categories/`

### 3. Configurazione Admin (CMS)
Apri `static/admin/config.yml` e aggiungi `fr` alla lista delle lingue:
```yaml
i18n:
  structure: multiple_folders
  locales: [it, en, fr] # Aggiungi 'fr' qui
  default_locale: it
```

---

## 🛠 Gestione Contenuti dall'Admin
Accedi a `http://localhost:1313/admin/` per gestire tutto senza toccare il codice.

### 📝 Tradurre una pagina
1. Entra in una pagina (es. Homepage).
2. Usa il selettore in alto a destra per cambiare lingua.
3. Scrivi il testo tradotto e salva. Il file verrà creato automaticamente nella cartella corretta.

### 🖼 Immagini
Tutte le nuove immagini caricate dall'Admin finiscono in `static/images/uploads/`.

### 📁 Categorie
Puoi dare un titolo e una descrizione a ogni categoria nella sezione **"Gestore Categorie"**. Questo aiuterà molto il posizionamento su Google.

---

## 🤖 Nota per l'Assistente AI
- **Configurazione**: Leggi sempre `hugo.toml` e `static/admin/config.yml` per capire le lingue attive.
- **Contenuti**: I file sono divisi per lingua in `content/it/`, `content/en/`, ecc.
- **Layout**: I layout personalizzati sono nel tema Saasify in `themes/hugo-saasify-theme/layouts/`.
