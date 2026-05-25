# leverans/ — Tofifi Cut and Trim

Färdig statisk en-sidig hemsida. Vanilla HTML/CSS/JS, inga byggsteg.
Öppna `index.html` direkt eller deploya mappen som-den-är till GitHub Pages.

## Struktur

```
leverans/
├── index.html          ← hela sidan
├── css/style.css       ← all styling (CSS variables, fluid type, responsiv)
├── js/main.js          ← slideshow, mobilmeny, sticky header, scroll-reveal
└── assets/
    ├── favicon.svg
    ├── README.md       ← bildbyte-guide
    └── images/         ← hero-1..3, about, og-image (alla platshållare)
```

## Designval (kort)

- **Palett:** grädde, sand, karamell, nästan-svart, guldaccent. Bakgrund
  alltid varm, aldrig kall vit/grå.
- **Typografi:**
  - *Tenor Sans* — light geometric sans, för uppercase-rubriker och ordmärke
    (versaler, generös letter-spacing).
  - *Cormorant Garamond* — high-contrast serif, för brödtext och italic-
    accenter.
- **Interaktivitet (lugn):** crossfade hero-slideshow (auto 6.5s + manuell),
  Ken Burns subtil zoom, sticky header med backdrop-blur vid scroll, mjuka
  scroll-reveal via IntersectionObserver, slide-in mobilmeny.
- **Tillgänglighet:** WCAG 2.1 AA mål, semantisk HTML, skip-link,
  `prefers-reduced-motion` respekteras (autorotation + animationer
  stängs av), tangentbordsstyrning på slideshow, 44×44 klickytor.
- **Prestanda:** Google Fonts med `display=swap` + preconnect, lazy-load
  bilder under första vyn, fasta `width/height` på alla bilder.

## Byta Boka Direkt-länken

URL:en hydrerades på alla `[data-boka]`-element vid sidladdning.
Sök efter strängen `BOKA-DIREKT-URL` i koden — två ställen att byta:

1. **`js/main.js`** — `const BOKA_URL = 'https://www.bokadirekt.se/';`
2. **`index.html`** — `href`-attributet på varje `<a data-boka …>` (fallback
   för no-JS).

## Lokal koll

Öppna `index.html` i en webbläsare. Allt funkar via `file://`. Karta-iframen
laddar OpenStreetMap (placeholder, Stockholm-vy) — byt embed-URL i sektionen
`#plats` när riktig adress finns.

## Plats för Claude Code

Mappen `leverans/` är redo att kopieras rakt in i `5-Kod/` (rot) som
GitHub Pages-rooten. Inga sökvägar behöver justeras — alla är relativa.
