# Tofifi Cut and Trim — hemsida

**Vad det här är:** All planering och byggplan för en hemsida till en
frisörsalong. Du planerar och verifierar. Claude Design gör designen.
Claude Code bygger och deployar.

**Status:** 2026-05-25 — planering klar, redo att bygga.

---

## Vad bygger vi?

En liten, snygg, **interaktiv en-sidig** hemsida för frisörsalongen
**Tofifi Cut and Trim**. Den ska:

- visa upp salongen — bild-slides, tjänster, om oss, plats
- ha en tydlig **Boka tid**-knapp som leder till salongens Boka Direkt-sida
- ligga live på **GitHub Pages**

Ingen databas. Ingen butik. Ingen inloggning. Sidan är ett skyltfönster —
själva bokningen sker hos Boka Direkt.

**Designkänsla:** som **Kochi Hair Care** — varm palett (grädde, sand,
karamell, svart + guld), stora luftiga rubriker, editorial fotografi, lugn
lyxig minimalism.

---

## Var börjar jag läsa?

I den här ordningen:

1. `1-Planering/01-Vision-och-mål.md` — vad vi vill, och målet.
2. `1-Planering/02-Innehåll-och-sektioner.md` — sidans sektioner + text.
3. `1-Planering/03-Beslut-och-öppna-frågor.md` — vad som är låst, vad som
   väntar på kompisen.
4. `2-Byggplan/00-Roadmap.md` — hela vägen från tom mapp till live sida.

---

## Två spår — vem gör vad

| Spår | Vem | Vad |
|---|---|---|
| **Design** | Claude Design | Bygger den snygga sidan (HTML + CSS + JS). Du ger den `3-Design/DESIGN-BRIEF.md`. |
| **Bygg & deploy** | Claude Code | Kopplar ihop, fixar bokningsknapp, deployar, kvalitetssäkrar. Kör briefsen i `2-Byggplan/`. |

Kompisen skapar GitHub-repot och pushar.

---

## Så kör du igång (kort)

1. Ge `3-Design/DESIGN-BRIEF.md` till Claude Design. Spara leveransen i
   `3-Design/leverans/`.
2. Kör goal-briefsen i `2-Byggplan/` i ordning **01 → 02 → 03**. Varje brief
   har ett färdigt `/goal` längst ner att klistra in i Claude Code.
3. Verifiera efter varje körning (roadmapen säger hur).

Goal 01 (scaffold) kan köras direkt — parallellt med att Claude Design jobbar.
Goal 02 kräver att designen är levererad.

---

## Mappstruktur

```
Tofifi-Cut-and-Trim/
├── 0-LÄS-MIG-FÖRST.md          ← du är här
├── 1-Planering/
│   ├── 01-Vision-och-mål.md
│   ├── 02-Innehåll-och-sektioner.md
│   └── 03-Beslut-och-öppna-frågor.md
├── 2-Byggplan/
│   ├── 00-Roadmap.md
│   ├── 01-Goal-scaffold-och-deploy.md
│   ├── 02-Goal-design-och-innehåll.md
│   └── 03-Goal-qa-och-tillgänglighet.md
├── 3-Design/
│   ├── DESIGN-BRIEF.md          ← ge till Claude Design
│   └── leverans/                ← Claude Designs HTML/CSS/JS hamnar här
└── 5-Kod/                       ← Claude Code bygger hemsidan här (= GitHub-repot)
```

---

## Väntar på kompisen

Sidan byggs klar med platshållare nu. Det här slottas in sen — full lista i
`1-Planering/03-Beslut-och-öppna-frågor.md`:

- Boka Direkt-länk (bokningssidans URL)
- Tjänster + priser
- Adress + öppettider
- Telefon, ev. Instagram
- Foton (interiör, arbeten)
- Bekräfta namnet (se varumärkesnoteringen i 03)
