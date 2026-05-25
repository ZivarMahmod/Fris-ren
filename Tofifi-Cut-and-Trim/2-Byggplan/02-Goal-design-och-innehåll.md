# 02 — Goal: Design och innehåll

**Datum:** 2026-05-25
**Typ:** Autonom byggorder för Claude Code — körs via /goal.
**Vad detta är:** Den enda ingångspunkten för körningen. Läs filen först.

---

## Utgångsläge — var projektet står

- Goal 01 är kört: `5-Kod/` har filstruktur, platshållarsida och git-repo.
- Claude Design har levererat den färdiga designen (HTML + CSS + JS) till
  `3-Design/leverans/`.
- Projektroten är `Tofifi-Cut-and-Trim/`. Du bygger **bara** i `5-Kod/`.

**Förutsättning:** `3-Design/leverans/` innehåller designens filer. Om mappen
är tom — stoppa och rapportera "designen saknas, kör Spår A först". Bygg inte
en egen design.

## Uppdraget

Ersätt platshållarsidan med Claude Designs riktiga design, koppla in
bokningsknappen, och lägg till favicon + meta-taggar. Efter den här briefen är
sidan komplett med platshållarinnehåll och redo för QA (Goal 03).

## Autonomi-regler

- Fatta alla tekniska val själv. Fråga inte droppvis.
- Allt via kod och CLI.
- En commit per punkt (F1–F4). Verifiera innan du går vidare.
- Pusha inte (kompisen pushar). Genuint mänskliga moment batchas.

## Beslut som redan är fattade — stanna inte för dessa

- Innehållskälla: `1-Planering/02-Innehåll-och-sektioner.md`. Krockar den med
  något — **den vinner.**
- Sektioner som ska finnas: Hero med bild-slides, Tjänster, Om oss, Plats &
  öppettider, Boka-sektion, Footer.
- **Alla sökvägar relativa** (`css/...`, `js/...`, `./assets/...`) — aldrig
  absoluta. GitHub Pages projekt-sida.
- Boka tid-knapparna länkar **ut** till Boka Direkt, öppnas i ny flik. Den
  riktiga URL:en är inte känd än — använd platshållaren nedan.
- Språk: svenska. Kodkommentarer: engelska.
- Behåll `index.html` i repo-roten.

---

## F1 — Integrera designen

**Mål:** Claude Designs design ersätter platshållarsidan i `5-Kod/`.

**Bygg:**

- Flytta in designens filer från `3-Design/leverans/` i `5-Kod/`:
  `index.html` i roten, CSS i `css/`, JS i `js/`, bilder/typsnitt i `assets/`.
- Behåll en rimlig struktur. Designens egen filuppdelning får behållas om den
  är vettig, så länge `index.html` ligger i roten.
- **Gå igenom varje sökväg** i HTML/CSS/JS och säkerställ att de är relativa.
  Gör om eventuella `/css/...` till `css/...`.
- Ta bort rester av platshållarsidan från Goal 01.
- Behåll `.nojekyll`, `.gitignore`, `README.md`.

**Klar när:**

- [ ] `index.html` öppnad lokalt visar den riktiga designen, inte
      platshållarsidan.
- [ ] Alla sektioner renderar: hero-slides, tjänster, om oss, plats &
      öppettider, boka-sektion, footer.
- [ ] Slideshow och mobilmeny fungerar.
- [ ] Inga 404 i konsolen. Inga absoluta sökvägar någonstans.

## F2 — Bokningsknappen

**Mål:** Varje "Boka tid"-knapp/länk leder ut till Boka Direkt.

**Bygg:**

- Hitta **alla** Boka tid-knappar/länkar (header, hero, tjänster,
  boka-sektion, footer).
- Var och en: `<a>` med
  `href="https://www.bokadirekt.se/"` (platshållare),
  `target="_blank"`, `rel="noopener noreferrer"`.
- Lägg en tydlig kommentar vid varje:
  `<!-- TODO: byt till salongens riktiga Boka Direkt-URL -->`.
- Använd helst en delad konstant/variabel eller sök-och-ersätt-vänligt mönster
  så att alla länkar går att byta på ett ställe senare.

**Klar när:**

- [ ] Alla Boka tid-länkar pekar på platshållar-URL:en.
- [ ] Alla har `target="_blank"` + `rel="noopener noreferrer"`.
- [ ] Varje länk har TODO-kommentaren.
- [ ] Klick öppnar Boka Direkt i ny flik (testat lokalt).

## F3 — Favicon, ikoner och meta

**Mål:** Webbläsarflik, hemskärmsikon och social delning ser proffsigt ut.

**Bygg:**

- Favicon: skapa en enkel favicon utifrån ordmärket "Tofifi Cut and Trim"
  (t.ex. ett "T" eller "TC" i designens varma färger). Lägg `favicon.ico` +
  PNG-ikoner (inkl. en `apple-touch-icon` 180×180) i `assets/`. Länka i
  `<head>` relativt.
- `<head>`-meta: `charset`, `viewport`, `<title>`, `<meta name="description">`
  (kort svensk beskrivning av salongen), `<html lang="sv">`.
- Open Graph + Twitter-taggar: `og:title`, `og:description`, `og:type`,
  `og:image`, `twitter:card`. `og:image` → `assets/og-image.jpg` (en
  platshållarbild i rätt format, ~1200×630, byts mot riktigt foto senare).

**Klar när:**

- [ ] Favicon syns i webbläsarfliken.
- [ ] `apple-touch-icon` + PNG-ikoner finns och länkas relativt.
- [ ] `<title>`, `description` och `lang="sv"` finns.
- [ ] OG-/Twitter-taggar finns med `og:image` satt.

## F4 — Innehållskoll mot planeringen

**Mål:** Sidans innehåll matchar `1-Planering/02-Innehåll-och-sektioner.md`.

**Bygg:**

- Jämför sidan mot dokumentet. Alla sektioner och alla platshållartexter ska
  finnas (rubriker, tjänstelista, om oss-text, öppettider, kontakt, footer).
- Saknas något — lägg till det i designens stil.
- Lämna `[PLATSHÅLLARE]`-texter som de är (de byts mot kompisens uppgifter
  senare) men se till att de ser ut som riktigt innehåll, inte trasigt.
- Plats-sektionen: inbäddad Google Maps (`<iframe>`, ingen API-nyckel) med en
  neutral platshållarplats tills riktig adress finns.

**Klar när:**

- [ ] Varje sektion i `02-Innehåll-och-sektioner.md` finns på sidan.
- [ ] Tjänstelistan har alla rader från dokumentet.
- [ ] Google Maps-`iframe` finns i plats-sektionen.
- [ ] Inga trasiga eller tomma platshållare.

---

## Batchade uppföljningar — kräver människa, blockerar inte bygget

Lista i slutrapporten:

1. Kompisen pushar uppdaterad `main` till GitHub.
2. Kompisen/Zivar verifierar live-sidan.
3. Riktiga uppgifter (Boka Direkt-URL, tjänster, priser, adress, tider,
   telefon, foton) slottas in senare via en liten fix-brief — se
   `1-Planering/03-Beslut-och-öppna-frågor.md`.

## När du är klar

- En commit per punkt (F1–F4). Pusha inte.
- Sammanfatta vad som ändrades och flagga öppna TODO:s (Boka Direkt-URL m.m.).
- Stoppa efter F4. QA är Goal 03.

## /goal att klistra in

```
/goal

Kör 2-Byggplan/02-Goal-design-och-innehåll.md — integrera Claude Designs
design, koppla bokningsknappen, lägg till favicon + meta. Autonomt.

Villkor:
- 02-Goal-design-och-innehåll.md är enda ingångspunkten. Läs den först.
- Designen finns i 3-Design/leverans/. Saknas den — stoppa och rapportera.
- Autonomt: alla tekniska val själv, allt via kod/CLI, fråga aldrig droppvis.
- En commit per punkt (F1–F4). Pusha inte.
- Alla sökvägar relativa. Boka tid-länkar = platshållar-URL till Boka Direkt.
- Stoppa efter F4.
```

## Versionshistorik

| Datum | Ändring |
|---|---|
| 2026-05-25 | Första versionen. |
