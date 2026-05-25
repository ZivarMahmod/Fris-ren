# 03 — Goal: QA, tillgänglighet och deploy-verifiering

**Datum:** 2026-05-25
**Typ:** Autonom byggorder för Claude Code — körs via /goal.
**Vad detta är:** Den enda ingångspunkten för körningen. Läs filen först.

---

## Utgångsläge — var projektet står

- Goal 01 och 02 är körda: sidan i `5-Kod/` är komplett med design,
  innehåll, bokningsknappar och meta — men ännu inte kvalitetssäkrad.
- Projektroten är `Tofifi-Cut-and-Trim/`. Du jobbar **bara** i `5-Kod/`.

## Uppdraget

Sista passet. Kvalitetssäkra sidan: responsivitet, tillgänglighet, prestanda,
SEO-sanity. Fixa det du hittar. Förbered live-verifieringen. Efter den här
briefen är sidan redo att vara ute på riktigt.

## Autonomi-regler

- Fatta alla tekniska val själv. Fråga inte droppvis.
- Allt via kod och CLI.
- En commit per punkt (F1–F5). Verifiera innan du går vidare.
- Pusha inte (kompisen pushar). Genuint mänskliga moment batchas.
- Hittar du en bugg — fixa den. Skapa inga nya features, ändra inte designen.

## Beslut som redan är fattade — stanna inte för dessa

- Designen är låst — du **kvalitetssäkrar**, du designar inte om.
- Alla sökvägar relativa.
- Tillgänglighetsnivå: WCAG 2.1 AA.
- Språk: svenska. Kodkommentarer: engelska.

---

## F1 — Responsiv QA

**Mål:** Sidan är hel och snygg på alla skärmstorlekar.

**Bygg / kontrollera:**

- Testa vid ~375px (mobil), ~768px (surfplatta), ~1280px+ (desktop).
- Ingen vågrät scroll. Inget innehåll som svämmar över eller klipps.
- Text läsbar, bilder skalar rätt, sektioner andas på alla bredder.
- Klickytor (knappar, menylänkar) minst **44×44px**.
- Hero-slides, mobilmeny och alla knappar fungerar på touch.

**Klar när:**

- [ ] Ingen vågrät scroll vid 375 / 768 / 1280px.
- [ ] Alla sektioner läsbara och hela på alla tre bredder.
- [ ] Alla klickytor ≥ 44×44px.
- [ ] Slideshow + mobilmeny fungerar på touch.

## F2 — Tillgänglighet (WCAG 2.1 AA)

**Mål:** Sidan går att använda för alla, inklusive med tangentbord och
skärmläsare.

**Bygg / kontrollera:**

- Färgkontrast: text mot bakgrund minst 4.5:1 (3:1 för stor text). Den varma
  paletten kan ge svag kontrast — fixa de fall som inte når kraven.
- Alla `<img>` har vettig `alt`. Rent dekorativa bilder: `alt=""`.
- Semantisk HTML: `<header> <nav> <main> <section> <footer>`, en `<h1>`,
  logisk rubrikhierarki (inga hoppade nivåer).
- Tangentbord: alla länkar/knappar nåbara med Tab, **synlig fokusmarkering**,
  logisk ordning. Mobilmenyn går att stänga med Esc.
- Slideshow: inte enbart auto. Den ska gå att stega manuellt, och respektera
  `prefers-reduced-motion` (stoppa/dämpa autorotation och animationer när det
  är satt).
- Bokningsknapparna har begriplig länktext ("Boka tid"), inte bara en ikon.

**Klar när:**

- [ ] All text klarar kontrastkraven (4.5:1 / 3:1).
- [ ] Alla bilder har korrekt `alt`.
- [ ] Semantisk HTML, en `<h1>`, korrekt rubrikhierarki.
- [ ] Hela sidan går att nå och använda med tangentbord, synlig fokus.
- [ ] `prefers-reduced-motion` respekteras av slideshow + animationer.

## F3 — Prestanda

**Mål:** Sidan laddar snabbt.

**Bygg / kontrollera:**

- Bilder: rimlig filstorlek och pixelmått. Komprimera. Använd modernt format
  (WebP där det går) med rimlig fallback.
- `loading="lazy"` på bilder under första vyn. Hero-bilden laddas direkt.
- Bilder har `width`/`height` (eller `aspect-ratio`) så layouten inte hoppar.
- Inga onödiga eller oanvända CSS/JS-bibliotek. Vanilla räcker.
- Webbtypsnitt laddas vettigt (`font-display: swap`, bara de vikter som
  används).

**Klar när:**

- [ ] Bilder komprimerade och rätt dimensionerade.
- [ ] `loading="lazy"` på bilder under viken.
- [ ] Ingen layoutförskjutning när bilder laddar.
- [ ] Inga oanvända bibliotek; typsnitt laddas effektivt.

## F4 — SEO-sanity

**Mål:** Sidan är begriplig för sökmotorer och vid delning.

**Bygg / kontrollera:**

- `<title>` och `<meta name="description">` finns och är beskrivande.
- Exakt en `<h1>`, korrekt rubrikhierarki (samma koll som F2).
- Open Graph / Twitter-taggar finns (från Goal 02) och `og:image` funkar.
- Lägg till en enkel `robots.txt` (tillåt allt) i repo-roten.
- `lang="sv"` på `<html>`.

**Klar när:**

- [ ] `<title>` + `description` beskrivande.
- [ ] En `<h1>`, korrekt hierarki.
- [ ] OG-/Twitter-taggar verifierade.
- [ ] `robots.txt` finns i repo-roten.

## F5 — Förbered live-verifiering

**Mål:** Allt klart för att kontrollera den live sidan efter push.

**Bygg / kontrollera:**

- Slutkoll lokalt via en riktig webbserver (t.ex. `python3 -m http.server`) —
  inte bara `file://` — så relativa sökvägar testas på riktigt.
- Inga fel eller 404 i konsolen.
- Skriv en kort **live-checklista** i slutrapporten som kompisen/Zivar kör
  efter push (se nedan).

**Klar när:**

- [ ] Sidan körd via lokal webbserver utan fel/404 i konsolen.
- [ ] Live-checklistan finns i slutrapporten.

---

## Batchade uppföljningar — kräver människa, blockerar inte bygget

1. Kompisen pushar uppdaterad `main`.
2. **Live-checklista** (kompisen/Zivar) på github.io-URL:en:
   - [ ] Sidan laddar; ser ut som lokalt.
   - [ ] Alla bilder syns (inga trasiga).
   - [ ] Slideshow + mobilmeny fungerar.
   - [ ] Varje Boka tid-knapp öppnar Boka Direkt i ny flik.
   - [ ] Ingen vågrät scroll på mobil.
   - [ ] (Valfritt) Kör Lighthouse i Chrome DevTools — sikta grönt på
     Tillgänglighet och Prestanda.

## När du är klar

- En commit per punkt (F1–F5). Pusha inte.
- Sammanfatta vad som kontrollerades och vad som fixades.
- Inkludera live-checklistan ovan.
- Lista kvarvarande TODO:s (riktiga uppgifter från kompisen).

## /goal att klistra in

```
/goal

Kör 2-Byggplan/03-Goal-qa-och-tillgänglighet.md — kvalitetssäkra sidan:
responsivitet, tillgänglighet, prestanda, SEO. Autonomt.

Villkor:
- 03-Goal-qa-och-tillgänglighet.md är enda ingångspunkten. Läs den först.
- Autonomt: alla tekniska val själv, allt via kod/CLI, fråga aldrig droppvis.
- Kvalitetssäkra och fixa buggar — designa inte om, bygg inga nya features.
- En commit per punkt (F1–F5). Pusha inte.
- Stoppa efter F5.
```

## Versionshistorik

| Datum | Ändring |
|---|---|
| 2026-05-25 | Första versionen. |
