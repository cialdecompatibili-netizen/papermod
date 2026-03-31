---
title: "Guida: Come aggiungere una nuova lingua al tuo sito"
date: 2026-03-31T21:00:00Z
description: "Una guida passo-passo per espandere il tuo sito Hugo in nuove lingue utilizzando l'Admin e poche righe di codice."
author: "Assistente AI"
categories: ["Tutorial"]
tags: ["hugo", "multilingua", "admin", "guida"]
featured_image: "/images/feature-2.svg"
---

Hai deciso di rendere il tuo sito internazionale? Ottima scelta! Grazie alla struttura che abbiamo impostato, aggiungere una nuova lingua (come il Francese, lo Spagnolo o il Tedesco) è un'operazione che richiede meno di 5 minuti.

Ecco i **3 passaggi fondamentali** per espandere i tuoi orizzonti:

### 1. Configura la lingua in Hugo
Il "cervello" del tuo sito deve sapere che esiste una nuova lingua. Apri il file `hugo.toml` e cerca la sezione `[languages]`. Aggiungi un nuovo blocco per la lingua desiderata. Ad esempio, per il **Francese**:

```toml
[languages.fr]
  languageCode = "fr-fr"
  languageName = "Français"
  title = "Mio Sito FR"
  weight = 3
  contentDir = "content/fr"
```

### 2. Prepara le cartelle dei contenuti
Hugo ha bisogno di uno spazio dedicato dove salvare i file della nuova lingua. Crea queste cartelle sul tuo computer:
- `content/fr/`
- `content/fr/blog/`
- `content/fr/categories/`

*Suggerimento: Copia il file `_index.md` dalla cartella `content/it/` alla nuova cartella `content/fr/` per avere subito una Home Page funzionante da tradurre.*

### 3. Abilita la lingua nell'Admin
Per poter scrivere e tradurre direttamente dal pannello di controllo, devi aggiornare il file `static/admin/config.yml`. Trova la riga `locales` e aggiungi il nuovo codice:

```yaml
i18n:
  structure: multiple_folders
  locales: [it, en, fr] # <--- Aggiungi 'fr' qui
  default_locale: it
```

---

### Come tradurre i tuoi articoli?
Una volta completati questi passaggi, ti basterà entrare nell'Admin, aprire un articolo esistente e usare il **selettore di lingua** in alto a destra. 

Scegli la nuova lingua, scrivi la traduzione e clicca su **Salva**. Il sistema creerà automaticamente il file nella cartella corretta!

**Vuoi un aiuto?** Ricorda che puoi sempre chiedere a me di farlo in un colpo solo per te! 🚀
