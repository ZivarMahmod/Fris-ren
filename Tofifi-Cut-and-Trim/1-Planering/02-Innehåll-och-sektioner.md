# 02 — Innehåll och sektioner

**Det här dokumentet är sanningskällan för sidans innehåll.** Både Claude
Design och Claude Code följer det. Krockar det med något annat dokument —
**det här vinner.**

All text nedan markerad `[PLATSHÅLLARE]` är påhittad och ska bytas mot
kompisens riktiga uppgifter senare. Sidan byggs ändå klar nu — platshållarna
gör att den ser färdig ut direkt.

Språk: **svenska**. Tilltal: varmt, kort, självsäkert — aldrig pratigt.

---

## Sidordning (uppifrån och ner)

1. Topprad (tunn) + Header/navigation
2. Hero med bild-slides
3. Tjänster
4. Om oss
5. Plats & öppettider
6. Boka-sektion (avslutande uppmaning)
7. Footer

Allt på **en sida**. Menyn scrollar till ankare på samma sida.

---

## 1. Topprad + Header

**Topprad (tunn remsa högst upp):** en kort rad, t.ex.
`[PLATSHÅLLARE] Drop in eller boka online`. Liten text, lugn. Får utelämnas
om designen blir stramare utan den.

**Header:** ligger kvar vid scroll (sticky).

- Logotyp: ordmärke **"Tofifi Cut and Trim"** (ingen bildlogga finns — Claude
  Design formger ordmärket typografiskt). Liten undertext tillåten, t.ex.
  `Frisörsalong`.
- Navigationslänkar (ankarscroll): **Tjänster · Om oss · Plats**
- **Boka tid**-knapp — framträdande, alltid synlig i headern.
- Mobil: hamburgermeny som öppnar en meny (gärna en panel som glider in).

---

## 2. Hero med bild-slides

Det första man ser. Full bredd. **2–4 bilder** i en slideshow som roterar
automatiskt och går att stega manuellt.

- Rubrik (stor, versaler, luftig). Förslag att rotera med slidesen:
  - `[PLATSHÅLLARE] SKARPT KLIPPT. SKÖNT MOTTAGEN.`
  - `[PLATSHÅLLARE] DITT HÅR, VÅRT HANTVERK.`
  - `[PLATSHÅLLARE] EN STOL SOM VÄNTAR PÅ DIG.`
- Underrubrik (en mening): `[PLATSHÅLLARE] Frisörsalong med känsla för
  detaljer — mitt i [ort].`
- Knapp: **Boka tid** (leder till Boka Direkt).
- Bilder: `[PLATSHÅLLARE]` — interiör, klippning, stämning. Tills riktiga
  foton finns används tydligt märkta platshållarbilder.

---

## 3. Tjänster

Salongens tjänster — presenterade **snyggt och visuellt** (kort/rutor), inte
som en torr prislista. Varje tjänst: namn, kort beskrivning, pris.

Platshållartjänster (kompisen bekräftar de riktiga + priser):

| Tjänst | Beskrivning | Pris |
|---|---|---|
| Herrklippning | `[PLATSHÅLLARE]` Klassiskt eller modernt, alltid välavslutat. | `[PLATSHÅLLARE] — kr` |
| Skägg & rakning | `[PLATSHÅLLARE]` Trimmat, format och vårdat. | `[PLATSHÅLLARE] — kr` |
| Damklippning | `[PLATSHÅLLARE]` Klippning och form efter ditt hår. | `[PLATSHÅLLARE] — kr` |
| Barnklippning | `[PLATSHÅLLARE]` Lugnt och enkelt för de minsta. | `[PLATSHÅLLARE] — kr` |
| Klipp & skägg (paket) | `[PLATSHÅLLARE]` Hela paketet i en sittning. | `[PLATSHÅLLARE] — kr` |

Under tjänsterna: en kort rad + **Boka tid**-knapp.
Inget bokningsformulär här — bara länken ut till Boka Direkt.

---

## 4. Om oss

En stilig presentationsdel — text + bild sida vid sida.

- Kort rubrik: `[PLATSHÅLLARE] Om salongen`
- 1–2 stycken: `[PLATSHÅLLARE] Tofifi Cut and Trim är en frisörsalong där
  hantverket får ta plats. Vi tar oss tid, lyssnar in vad du vill ha, och ser
  till att du går härifrån nöjd. Välkommen in — som ny eller gammal kund.`
- Bild: `[PLATSHÅLLARE]` — salongen eller frisören i arbete.

Håll det varmt och kort. Ingen lång historia.

---

## 5. Plats & öppettider

Var salongen ligger och när den har öppet. Presenteras lugnt och fint —
**inte** som en rå tabell-vägg.

- Adress: `[PLATSHÅLLARE] Gatuadress 1, 123 45 Ort`
- Karta: inbäddad **Google Maps** (`<iframe>` — kräver ingen API-nyckel).
  Tills riktig adress finns: en neutral platshållare för kartan.
- Öppettider (platshållare):
  - Mån–Fre: `[PLATSHÅLLARE] 10–18`
  - Lördag: `[PLATSHÅLLARE] 10–15`
  - Söndag: `[PLATSHÅLLARE] Stängt`
- Kontakt: telefon `[PLATSHÅLLARE] 0XX-XXX XX XX`

---

## 6. Boka-sektion (avslutande uppmaning)

En stor, lugn avslutande sektion vars enda jobb är att få besökaren att boka.

- Rubrik: `[PLATSHÅLLARE] Redo för en ny stil?`
- En rad: `[PLATSHÅLLARE] Boka din tid online — snabbt och enkelt.`
- Stor **Boka tid**-knapp (leder till Boka Direkt).

---

## 7. Footer

- Ordmärke "Tofifi Cut and Trim" + kort tagline.
- Adress + telefon (samma platshållare som sektion 5).
- Instagram-länk: `[PLATSHÅLLARE]` (utelämnas om kompisen inte har Instagram).
- Liten **Boka tid**-länk.
- Copyright: `© 2026 Tofifi Cut and Trim`.

---

## Boka tid-knappen — gäller överallt

Alla **Boka tid**-knappar/länkar på sidan pekar på **samma** mål: salongens
sida på Boka Direkt. De öppnas i ny flik (`target="_blank"`,
`rel="noopener noreferrer"`).

URL:en är **inte känd än** (kommer från kompisen). Tills dess används
`https://www.bokadirekt.se/` som platshållare, med en tydlig TODO i koden.
Se `03-Beslut-och-öppna-frågor.md`.
