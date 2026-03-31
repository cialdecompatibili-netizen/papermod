---
title: "Guide: How to add a new language to your site"
date: 2026-03-31T21:00:00Z
description: "A step-by-step guide to expanding your Hugo site into new languages using the Admin and a few lines of code."
author: "AI Assistant"
categories: ["Tutorial"]
tags: ["hugo", "multilingual", "admin", "guide"]
featured_image: "/images/feature-2.svg"
---

Have you decided to make your site international? Great choice! Thanks to the structure we have set up, adding a new language (such as French, Spanish, or German) is a task that takes less than 5 minutes.

Here are the **3 key steps** to expand your horizons:

### 1. Configure the language in Hugo
The "brain" of your site needs to know that a new language exists. Open the `hugo.toml` file and look for the `[languages]` section. Add a new block for the desired language. For example, for **French**:

```toml
[languages.fr]
  languageCode = "fr-fr"
  languageName = "Français"
  title = "My Site FR"
  weight = 3
  contentDir = "content/fr"
```

### 2. Prepare content folders
Hugo needs a dedicated space where to save the files for the new language. Create these folders on your computer:
- `content/fr/`
- `content/fr/blog/`
- `content/fr/categories/`

*Tip: Copy the `_index.md` file from the `content/it/` folder to the new `content/fr/` folder to immediately have a working Home Page to translate.*

### 3. Enable the language in the Admin
To be able to write and translate directly from the control panel, you need to update the `static/admin/config.yml` file. Find the `locales` line and add the new code:

```yaml
i18n:
  structure: multiple_folders
  locales: [it, en, fr] # <--- Add 'fr' here
  default_locale: it
```

---

### How to translate your articles?
Once you have completed these steps, simply go to the Admin, open an existing article, and use the **language selector** at the top right.

Choose the new language, write the translation, and click **Save**. The system will automatically create the file in the correct folder!

**Need help?** Remember that you can always ask me to do it in one go for you! 🚀
