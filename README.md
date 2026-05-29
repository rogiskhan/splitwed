# SplitWed — Guida al deploy su GitHub Pages + dominio Aruba

Sito statico della landing page SplitWed (lista d'attesa).
Hosting: **GitHub Pages**. Dominio: **Aruba**. Form: **FormSubmit**.

---

## ✅ PRIMA DI PUBBLICARE — 3 cose da personalizzare

1. **Email che riceve le iscrizioni** — in `index.html` cerca:
   `https://formsubmit.co/ajax/iltuoindirizzo@tuodominio.it`
   e sostituisci `iltuoindirizzo@tuodominio.it` con la tua email reale.

2. **Dominio** — nel file `CNAME` sostituisci `tuodominio.it` con il tuo dominio.

3. **Dati nella privacy** — in `privacy.html` sostituisci tutti i campi
   evidenziati (P.IVA, indirizzo, ragione sociale, email privacy).

4. **Font** — scarica gli 11 file `.woff2` come spiegato in
   `fonts/SCARICA-I-FONT.txt` e mettili nella cartella `fonts/`.

---

## 📦 1. Carica i file su GitHub

File e cartelle da caricare nel repository:
```
/index.html
/privacy.html
/CNAME
/README.md
/fonts/fonts.css
/fonts/  + gli 11 file .woff2
```

- Crea un repository pubblico su github.com (es. `splitwed`).
- "Add file → Upload files" → trascina tutto → Commit.

## 🚀 2. Attiva GitHub Pages

- Repository → **Settings → Pages**
- Source: **Deploy from a branch** → Branch `main`, cartella `/ (root)` → Save
- Dopo 1-2 minuti il sito è online su `https://TUO-USERNAME.github.io/splitwed/`

## 🌐 3. Collega il dominio Aruba

**Su GitHub:** Settings → Pages → Custom domain → scrivi `tuodominio.it` → Save.

**Sul pannello Aruba** (Gestione DNS del dominio):

Record **A** per il dominio principale (`tuodominio.it`):
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

Record **CNAME** per il sottodominio www:
```
www  →  TUO-USERNAME.github.io
```

Attendi la propagazione DNS (da minuti a qualche ora), poi su GitHub
Settings → Pages spunta **Enforce HTTPS**.

---

## 📧 Come funziona il form (FormSubmit)

- Le iscrizioni arrivano via email all'indirizzo configurato.
- **Prima iscrizione:** FormSubmit ti invia una email di **attivazione** —
  cliccaci una volta sola per abilitare il form. Da lì in poi funziona.
- All'iscritto parte in automatico una email di benvenuto (`_autoresponse`).
- Niente account, niente costi, niente PHP.

> Nota GDPR: i dati del form transitano dai server di FormSubmit. Questo è
> già dichiarato nella privacy policy tra i responsabili del trattamento.

---

## 🔁 In alternativa: hosting Aruba con PHP

Se in futuro preferisci usare lo spazio web Aruba (con PHP) invece di
GitHub Pages, puoi tornare allo script `invia.php` (rimosso da questa
versione perché GitHub Pages non esegue PHP). Chiedi pure e te lo ripristino.
