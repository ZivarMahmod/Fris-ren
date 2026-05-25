# 01 — Goal: Scaffold och deploy-grund

**Datum:** 2026-05-25
**Typ:** Autonom byggorder för Claude Code — körs via /goal.
**Vad detta är:** Den enda ingångspunkten för körningen. Läs filen först.

---

## Utgångsläge — var projektet står

- Nytt projekt. Mappen `5-Kod/` är tom.
- Projektroten är `Tofifi-Cut-and-Trim/`. Du bygger **bara** i `5-Kod/`.
- Planeringsdokument du får läsa vid behov: `0-LÄS-MIG-FÖRST.md`,
  `1-Planering/`, `2-Byggplan/00-Roadmap.md`.
- Designen byggs separat av Claude Design och kommer i ett senare steg
  (Goal 02). Den här briefen rör **inte** den slutliga designen.

## Uppdraget

Sätt upp filstrukturen för hemsidan i `5-Kod/`, skapa en **enkel
platshållarsida**, och förbered allt för GitHub Pages. Målet är att
deploy-pipen ska gå att verifiera **innan** den riktiga designen kommer in.

`5-Kod/` blir GitHub-repot. Inget planeringsmaterial får hamna där.

## Autonomi-regler

- Fatta alla tekniska val själv. Fråga inte droppvis.
- Allt via kod och CLI — `git` i terminalen, aldrig manuella moment.
- En commit per punkt (F1–F4). Verifiera innan du går vidare.
- Att skapa GitHub-repot, pusha och sätta Pages-inställningen är **kompisens**
  jobb — se "Batchade uppföljningar". Vänta inte på det, stanna inte för det.

## Beslut som redan är fattade — stanna inte för dessa

- Teknik: ren statisk **HTML + CSS + JS (vanilla)**. Inget ramverk, inget
  byggsteg, ingen pakethanterare.
- Hosting: GitHub Pages, branch `main`, mapp `/ (root)`.
- **Alla sökvägar till CSS/JS/bilder är relativa** (`css/style.css`,
  `./assets/...`) — aldrig absoluta (`/css/...`). En GitHub Pages projekt-sida
  ligger under en underväg, så absoluta sökvägar bryts.
- Språk på sidan: svenska. Kodkommentarer: engelska.
- `index.html` ligger i repo-roten (`5-Kod/index.html`).

---

## F1 — Filstruktur

**Mål:** Skapa mappstrukturen för sidan i `5-Kod/`.

**Bygg:**

```
5-Kod/
├── index.html
├── css/style.css
├── js/main.js
├── assets/images/
├── .nojekyll
├── .gitignore
└── README.md
```

- Skapa mapparna `css/`, `js/`, `assets/images/`.
- Filerna fylls i F2–F3. `js/main.js` får vara tom (eller ha en kort
  `// Placeholder — interaktivitet kommer i Goal 02`-kommentar) i det här
  steget.

**Klar när:**

- [ ] Mapparna `css/`, `js/`, `assets/images/` finns i `5-Kod/`.
- [ ] Filerna `index.html`, `css/style.css`, `js/main.js` finns.

## F2 — Platshållarsida

**Mål:** En enkel, ren platshållarsida som visar att sidan lever.

**Bygg:**

- `index.html`: giltig HTML5, `<html lang="sv">`, `<meta charset="utf-8">`,
  `<meta name="viewport" content="width=device-width, initial-scale=1">`,
  `<title>Tofifi Cut and Trim</title>`. Länka `css/style.css` **relativt**.
- Innehåll: centrerat — rubriken **"Tofifi Cut and Trim"**, en underrad
  `Frisörsalong · hemsidan är på väg`. Lugnt och prydligt, inget mer.
- `css/style.css`: minimal styling — varm bakgrundston (t.ex. en gräddvit
  som `#F3ECE3`), mörk text, centrerat innehåll, ett rimligt typsnitt.
  Det här är en tillfällig sida; lägg ingen möda på finess.

**Klar när:**

- [ ] `index.html` öppnad i webbläsare visar rubrik + underrad, centrerat.
- [ ] CSS länkas relativt och laddar (ingen 404 i konsolen).
- [ ] HTML validerar (inga öppna taggar, korrekt struktur).
- [ ] Inga absoluta sökvägar (`/...`) någonstans.

## F3 — Deploy-filer

**Mål:** Filerna som behövs för GitHub Pages och för att kompisen ska kunna
sätta upp deployen.

**Bygg:**

- `.nojekyll`: tom fil i repo-roten.
- `.gitignore`: ignorera OS-/editor-skräp (`.DS_Store`, `Thumbs.db`,
  `.vscode/`, m.m.).
- `README.md` på **svenska**, kort, med:
  - En rad om vad repot är (hemsida för Tofifi Cut and Trim).
  - **GitHub Pages-setup, steg för steg** för kompisen:
    1. Skapa ett publikt GitHub-repo, t.ex. `tofifi-cut-and-trim`.
    2. Pusha innehållet hit till `main`.
    3. Settings → Pages → Source: "Deploy from a branch" → Branch `main`
       → mapp `/ (root)` → Save.
    4. Sidan ligger efter en stund på
       `https://<användarnamn>.github.io/tofifi-cut-and-trim/`.
  - En rad om hur man kör sidan lokalt (öppna `index.html`, eller
    `python3 -m http.server`).

**Klar när:**

- [ ] `.nojekyll` finns (tom) i repo-roten.
- [ ] `.gitignore` finns och täcker OS-/editor-skräp.
- [ ] `README.md` finns med Pages-stegen tydligt punktade.

## F4 — Git

**Mål:** Initiera git-repot lokalt med en första commit.

**Bygg:**

- `git init` i `5-Kod/`. Branch: `main`.
- Stega alla filer, gör en första commit: `chore: scaffold och deploy-grund`.
- Pusha **inte** — det finns ingen remote än (kompisens jobb).

**Klar när:**

- [ ] `5-Kod/` är ett git-repo på branch `main`.
- [ ] Alla filer från F1–F3 är committade.
- [ ] `git status` är rent (inga ospårade/oincheckade filer).

---

## Batchade uppföljningar — kräver människa, blockerar inte bygget

Du som Claude Code gör inte det här. Lista det i din slutrapport så kompisen
kan göra det:

1. Skapa ett publikt GitHub-repo (förslag: `tofifi-cut-and-trim`).
2. Lägg till remote och pusha `main`.
3. Sätt GitHub Pages-källan (Settings → Pages → branch `main` → `/ (root)`).
4. Verifiera att platshållarsidan syns live på github.io-URL:en.

## När du är klar

- Sammanfatta vad som byggdes (F1–F4) och var det ligger.
- Lista de batchade uppföljningarna ovan.
- Stoppa efter F4. Bygg inte vidare på designen — det är Goal 02.

## /goal att klistra in

```
/goal

Kör 2-Byggplan/01-Goal-scaffold-och-deploy.md — sätt upp filstruktur,
platshållarsida och deploy-grund i 5-Kod/. Autonomt.

Villkor:
- 01-Goal-scaffold-och-deploy.md är enda ingångspunkten. Läs den först.
- Autonomt: alla tekniska val själv, allt via kod/CLI, fråga aldrig droppvis.
- En commit per punkt (F1–F4). Pusha inte — ingen remote finns än.
- Alla sökvägar relativa. Inga absoluta sökvägar.
- Stoppa efter F4.
```

## Versionshistorik

| Datum | Ändring |
|---|---|
| 2026-05-25 | Första versionen. |
