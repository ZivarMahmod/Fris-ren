# 00 — Roadmap (byggplanen)

Hela vägen från tom mapp till en live, snygg hemsida. Det här är
**ingångspunkten för bygget**. Goal-briefsen (01, 02, 03) är de enskilda
stegen.

---

## Översikt — två spår

```
SPÅR A — DESIGN (Claude Design)
  DESIGN-BRIEF.md  ──►  färdig HTML + CSS + JS  ──►  3-Design/leverans/

SPÅR B — BYGG & DEPLOY (Claude Code)
  Goal 01 ──► Goal 02 ──► Goal 03 ──► live på GitHub Pages
  scaffold   integrera   QA +
  + deploy   designen    verifiering
```

Spår A och **Goal 01** kan köras parallellt. **Goal 02 kräver att Spår A är
klart** (designen levererad). Goal 03 körs sist.

---

## Teknikval — låst

**Ren statisk HTML + CSS + JS (vanilla).** Inget ramverk, inget byggsteg,
ingen pakethanterare, ingen databas.

*Varför:* sidan är liten, statisk och ska ligga på GitHub Pages. Ett ramverk
(React m.fl.) eller ett byggsteg skulle bara lägga på komplexitet utan att ge
något — och göra det svårare för kompisen att äga sidan själv. Filerna man
skriver är filerna som ligger live. Enklast möjliga som uppfyller kraven.

---

## Filstruktur för själva sidan (i `5-Kod/`)

`5-Kod/` blir **GitHub-repot**. Inget planeringsmaterial hamnar där.

```
5-Kod/
├── index.html
├── css/
│   └── style.css
├── js/
│   └── main.js
├── assets/
│   ├── images/        ← foton (platshållare nu)
│   ├── favicon-filer  ← favicon.ico, apple-touch-icon m.fl.
│   └── og-image.jpg   ← bild för social delning
├── .nojekyll          ← tom fil, stänger av Jekyll-bearbetning
├── .gitignore
└── README.md          ← repo-info + GitHub Pages-setup för kompisen
```

(Om Claude Designs leverans har en annan men rimlig filuppdelning är det ok —
huvudsaken är att `index.html` ligger i repo-roten och allt länkas relativt.)

---

## GitHub Pages — så funkar deployen

1. Kompisen skapar ett **publikt** GitHub-repo, t.ex. `tofifi-cut-and-trim`.
2. Innehållet i `5-Kod/` pushas till `main`-branchen.
3. På GitHub: **Settings → Pages → Source: "Deploy from a branch" →
   Branch: `main` → Mapp: `/ (root)` → Save.**
4. Efter en stund ligger sidan på:
   `https://<användarnamn>.github.io/tofifi-cut-and-trim/`

**Viktigast av allt — relativa sökvägar.** En GitHub Pages *projekt-sida*
ligger inte på domänroten, den ligger under `/tofifi-cut-and-trim/`. Därför:

- Rätt: `css/style.css`, `js/main.js`, `./assets/images/foto.jpg`
- Fel: `/css/style.css` — den absoluta sökvägen pekar på domänroten och
  bryts. Det här är den i särklass vanligaste GitHub Pages-buggen. Varje
  goal-brief upprepar regeln.

`.nojekyll` (tom fil i repo-roten) stänger av GitHubs Jekyll-bearbetning —
bra praxis för rena statiska sidor och hindrar att mappar som börjar med `_`
ignoreras.

Egen domän (t.ex. en `.se`-adress) är parkerat — inte med i scope nu.

---

## Stegen — goal-briefs

| Steg | Brief | Vad | Förutsätter |
|---|---|---|---|
| A | `3-Design/DESIGN-BRIEF.md` | Claude Design bygger designen | — |
| 1 | `01-Goal-scaffold-och-deploy.md` | Mappstruktur + platshållarsida + deploy-grund | — |
| 2 | `02-Goal-design-och-innehåll.md` | Integrera designen, bokningsknapp, meta/favicon | Steg A + 1 klara |
| 3 | `03-Goal-qa-och-tillgänglighet.md` | Responsiv QA, tillgänglighet, prestanda, live-koll | Steg 2 klart |

**Varför Goal 01 är ett eget steg:** den får deploy-pipen verifierad **innan**
designen kommer in. En enkel platshållarsida pushas, kompisen sätter Pages-
inställningen, och vi ser att sidan faktiskt blir live. "Pushat ≠ deployat" —
hittar vi ett deploy-problem vill vi hitta det tidigt, inte efter designen.

---

## Så kör du loopen (för varje goal-brief)

1. Öppna Claude Code **i projektmappen `Tofifi-Cut-and-Trim/`** — inte i
   `5-Kod/`. Code måste kunna läsa briefsen i `2-Byggplan/` och designen i
   `3-Design/leverans/`, men bygger sidan i `5-Kod/`.
2. Öppna goal-briefen. Längst ner finns ett färdigt `/goal` att klistra in.
3. Kompisen kör briefen i Claude Code via det `/goal`:t.
4. Claude Code bygger autonomt, en commit per punkt.
5. Kompisen pushar till GitHub.
6. **Du verifierar** mot briefens *Klar när*-listor — lita inte på Claude
   Codes "klart"-rapport, kontrollera mot koden och mot den live sidan.
7. Fel? Skriv en fix-brief i samma format (`NN-FX-...md`). Annars: nästa brief.

---

## Verifiering — vad du kollar efter varje steg

- **Efter Goal 01:** ligger platshållarsidan live på github.io-URL:en? Inga
  trasiga sökvägar? Då funkar deploy-pipen.
- **Efter Goal 02:** alla sektioner på plats, slideshow rullar, mobilmeny
  funkar, varje Boka tid-knapp öppnar Boka Direkt i ny flik. Lokalt och live.
- **Efter Goal 03:** sidan är snygg och hel på mobil/surfplatta/desktop, inga
  tillgänglighetsbrister, snabb, och den **live** sidan ser ut som lokalt.

Verktyg: titta på den körande sidan i webbläsaren, krymp fönstret för
responsivitet, och kör gärna en Lighthouse-koll (inbyggt i Chrome DevTools)
för tillgänglighet och prestanda.

---

## När allt är klart

- Sidan ligger live, snygg och komplett, med platshållarinnehåll.
- Återstår: kompisens riktiga uppgifter (se `1-Planering/03`). När de kommer
  in räcker en liten fix-brief för att byta platshållarna.
