# Design-brief — Tofifi Cut and Trim

**Till:** Claude Design
**Från:** Zivar
**Datum:** 2026-05-25

Det här dokumentet är självständigt — allt du behöver står här. Läs det helt
innan du börjar.

---

## 1. Vad du ska göra

Designa och bygg en **färdig, snygg, interaktiv en-sidig hemsida** för en
frisörsalong som heter **Tofifi Cut and Trim**.

Du levererar den **faktiska sidan i kod** — HTML + CSS + JS. En annan agent
(Claude Code) kopplar sen in den i ett repo, fixar bokningslänk och deployar.
Du äger **utseendet och känslan**. Maxa det. Det ska vara riktigt fint.

Det är en liten sida. Lägg kvaliteten på hantverket, inte på omfånget.

---

## 2. Om projektet

- **Tofifi Cut and Trim** — en frisörsalong.
- Sidan är ett **skyltfönster**: den visar upp salongen och får besökaren att
  trycka på **Boka tid**. Den knappen leder ut till salongens sida på Boka
  Direkt (svensk bokningstjänst). Själva bokningen sker **inte** på sidan.
- **En sida**, allt på samma sida, menyn scrollar till ankare.
- Ren statisk sida — ingen databas, ingen backend, ingen butik.
- Hostas på **GitHub Pages**.
- Språk: **svenska**.

---

## 3. Designreferens — Kochi Hair Care

Salongsägaren gillar **Kochi Hair Care**: https://kochihaircare.me/
**Studera den live innan du börjar.** Vi tar känslan därifrån — inte
funktionen (Kochi är en produktbutik; vår sida är en salong utan butik).

**Det som gör Kochi-känslan, och som du ska fånga:**

- **Varm, lyxig palett.** Grädde, sand, beige, karamell/tan, ett djupt
  nästan-svart, och en guldaccent. Bakgrunden är ljus och varm — aldrig kall
  vit, aldrig kall grå. Färgen kommer mest från fotografin.
- **Stora, lätta, luftiga rubriker.** Versaler, tunn vikt, generös
  bokstavsspärr. Eleganta och lugna — inte tjocka och skrikiga.
- **Editorial fotografi som får ta stor plats.** Helbredd, ofta delad layout
  (foto på ena sidan, varm texturerad yta på den andra).
- **Mycket luft.** Stora marginaler, lugnt tempo, inget stökigt eller trångt.
- **Tunn topprad** högst upp (Kochi har "WORLDWIDE SHIPPING").
- **Ren versal-logotyp** med en liten undertext (Kochi: "KOCHI" + "Dubai").
- **Solida, rektangulära CTA-knappar** i nästan-svart med versal text.
- **Meny som glider in från sidan** (mörk panel) när man öppnar hamburgaren.
- Helhetskänsla: **lugn, långsam, exklusiv.** Premiumbarbershop/salong.

**Det du ska ignorera från Kochi:** kundvagn, produkter, "shop now", pris-per-
produkt, valuta-/landväljare, prenumerationsruta. Inget av det finns hos oss.

**Lyckligt sammanträffande:** namnet Tofifi (chokladen — choklad, karamell,
hasselnöt, grädde) pekar på exakt samma varma palett som Kochi redan har. Luta
in i det. Varma, aptitliga neutraler. Inte barnsligt eller godis-aktigt —
sofistikerat och vuxet.

---

## 4. Namn och varumärke

- Namnet är **"Tofifi Cut and Trim"**.
- Det finns **ingen logotyp**. Du formger ett **typografiskt ordmärke** — rent,
  versalt, med bokstavsspärr i Kochi-anda. En liten undertext är välkommen,
  t.ex. "FRISÖRSALONG". Håll det enkelt och stilrent.
- Formge också en **enkel favicon** i samma anda (t.ex. "T" eller "TC" i
  paletten). Levereras gärna som en liten SVG eller PNG.

---

## 5. Vad du ska leverera

Den faktiska, fungerande sidan som statiska filer:

- `index.html` — hela sidan, semantisk HTML5.
- `css/style.css` — all styling. (Eller flera CSS-filer om du föredrar.)
- `js/main.js` — all interaktivitet. (Vanilla JS.)
- `assets/` — bilder, ikoner, typsnitt, favicon. Platshållarbilder är ok
  (se punkt 10).

Krav på leveransen:

- **Vanilla HTML/CSS/JS.** Inget ramverk (React m.fl.), inget byggsteg, ingen
  pakethanterare. Filerna du skriver är filerna som ligger live.
- **Allt fungerar genom att man öppnar `index.html`** — inga server-beroenden.
- Lägg leveransen så att Zivar kan spara den i mappen `3-Design/leverans/`.

---

## 6. Sektioner och innehåll

En sida, sektionerna uppifrån och ner. All `[PLATSHÅLLARE]`-text är påhittad
och byts mot riktiga uppgifter senare — designa ändå som om den vore äkta, så
sidan ser färdig ut direkt.

**1. Topprad + Header**
- Tunn topprad: `[PLATSHÅLLARE] Drop in eller boka online`. (Får utelämnas om
  designen blir stramare utan.)
- Header, sticky (ligger kvar vid scroll).
- Ordmärke "Tofifi Cut and Trim" till vänster.
- Navigation (ankarscroll): **Tjänster · Om oss · Plats**.
- **Boka tid**-knapp, framträdande, alltid synlig.
- Mobil: hamburgermeny som öppnar en inglidande panel.

**2. Hero med bild-slides**
- Helbredd. 2–4 bilder i en slideshow (auto-rotation + manuell stegning).
- Stor versalrubrik, gärna en per slide:
  - `SKARPT KLIPPT. SKÖNT MOTTAGEN.`
  - `DITT HÅR, VÅRT HANTVERK.`
  - `EN STOL SOM VÄNTAR PÅ DIG.`
- Underrubrik: `[PLATSHÅLLARE] Frisörsalong med känsla för detaljer — mitt i
  [ort].`
- Knapp: **Boka tid**.

**3. Tjänster**
- Salongens tjänster, presenterade **visuellt och snyggt** (kort/rutor) — inte
  som en torr prislista. Varje: namn, kort beskrivning, pris.
  - Herrklippning — Klassiskt eller modernt, alltid välavslutat. — `[PLATSHÅLLARE] — kr`
  - Skägg & rakning — Trimmat, format och vårdat. — `[PLATSHÅLLARE] — kr`
  - Damklippning — Klippning och form efter ditt hår. — `[PLATSHÅLLARE] — kr`
  - Barnklippning — Lugnt och enkelt för de minsta. — `[PLATSHÅLLARE] — kr`
  - Klipp & skägg (paket) — Hela paketet i en sittning. — `[PLATSHÅLLARE] — kr`
- Avsluta med en kort rad + **Boka tid**-knapp.

**4. Om oss**
- Stilig presentation, text + bild sida vid sida.
- Rubrik: `Om salongen`
- Text: `[PLATSHÅLLARE] Tofifi Cut and Trim är en frisörsalong där hantverket
  får ta plats. Vi tar oss tid, lyssnar in vad du vill ha, och ser till att du
  går härifrån nöjd. Välkommen in — som ny eller gammal kund.`

**5. Plats & öppettider**
- Lugnt och fint presenterat — **inte** en rå tabell-vägg.
- Adress: `[PLATSHÅLLARE] Gatuadress 1, 123 45 Ort`
- Inbäddad Google Maps (`<iframe>`, kräver ingen API-nyckel) — neutral
  platshållarplats tills riktig adress finns.
- Öppettider: Mån–Fre `[PLATSHÅLLARE] 10–18`, Lör `[PLATSHÅLLARE] 10–15`,
  Sön `[PLATSHÅLLARE] Stängt`.
- Telefon: `[PLATSHÅLLARE] 0XX-XXX XX XX`.

**6. Boka-sektion (avslutande uppmaning)**
- Stor, lugn avslutande sektion.
- Rubrik: `Redo för en ny stil?`
- Rad: `Boka din tid online — snabbt och enkelt.`
- Stor **Boka tid**-knapp.

**7. Footer**
- Ordmärke + kort tagline.
- Adress + telefon (samma platshållare som sektion 5).
- Instagram-länk: `[PLATSHÅLLARE]`.
- Liten **Boka tid**-länk.
- `© 2026 Tofifi Cut and Trim`.

**Boka tid-knapparna:** alla på sidan ska vara `<a>`-länkar. Sätt
`href="https://www.bokadirekt.se/"` som platshållare och
`target="_blank" rel="noopener noreferrer"`. Claude Code byter till salongens
riktiga URL senare — gör gärna länkarna lätta att hitta/byta på ett ställe.

---

## 7. Interaktivitet

Sidan ska kännas **levande**, men lugn — aldrig pillrig. Vanilla JS.

- **Hero-slideshow** — auto-rotation + manuella kontroller (prickar och/eller
  pilar). Mjuka övergångar.
- **Mjuk ankarscroll** när man klickar i menyn.
- **Subtila scroll-animationer** — sektioner tonar/glider mjukt in. Diskret.
- **Sticky header** som gärna ändrar sig lätt vid scroll (t.ex. blir mer
  kompakt eller får bakgrund).
- **Mobilmeny** — hamburgare som öppnar en inglidande panel; stängbar.
- Fina hover-tillstånd på knappar och länkar.

---

## 8. Tekniska ramar — MÅSTE följas

Det här är inte stilval. Bryts något här går sidan sönder live eller blir
otillgänglig.

- **Relativa sökvägar överallt.** `css/style.css`, `js/main.js`,
  `./assets/...`. **Aldrig** absoluta (`/css/...`). Sidan ligger på en GitHub
  Pages projekt-sida under en underväg — absoluta sökvägar bryts då.
- **Fungerar som rena statiska filer.** Ingen backend, inget byggsteg.
- **Responsivt, mobil först.** Måste vara helt och snyggt vid ~375px,
  ~768px och ~1280px+. Ingen vågrät scroll. Klickytor minst 44×44px.
- **Tillgänglighet — WCAG 2.1 AA:**
  - Textkontrast minst 4.5:1 (3:1 för stor text). Varm palett kan ge svag
    kontrast — välj toner som klarar det.
  - Semantisk HTML: `<header> <nav> <main> <section> <footer>`, **en `<h1>`**,
    logisk rubrikhierarki.
  - Alla bilder har `alt`. Dekorativa: `alt=""`.
  - Tangentbord: allt nåbart, **synlig fokusmarkering**, logisk ordning.
  - Respektera `prefers-reduced-motion` — dämpa/stoppa autorotation och
    animationer när användaren bett om mindre rörelse.
  - Slideshow får inte vara enbart auto — den ska gå att stega manuellt.
- **Prestanda:** komprimerade, rätt dimensionerade bilder; `loading="lazy"`
  under första vyn; `width`/`height` eller `aspect-ratio` så layouten inte
  hoppar; webbtypsnitt med `font-display: swap`.
- `<html lang="sv">`. Kodkommentarer på engelska.

---

## 9. Vad du INTE ska göra

- Ingen butik, inga produkter, ingen kundvagn, ingen kassa, inga priser i
  "shop"-mening.
- Ingen bokningsmotor eller bokningsformulär på sidan — bara länken ut.
- Ingen inloggning, inga konton, ingen prenumerationsruta.
- Inget ramverk, inget byggsteg, ingen databas, ingen backend.
- Inget flerspråk — bara svenska.
- Överbygg inte. En sida, gjord riktigt bra. Sluta där.

---

## 10. Platshållare — bilder och text

- **Bilder:** riktiga foton finns inte än. Använd tydligt märkta
  platshållarbilder i rätt proportioner (helst egna, neutrala, varma i tonen
  så de passar paletten — inte slumpartade stockbilder som krockar).
  Dokumentera vilka foton som behövs och i vilka mått, så de är lätta att
  byta: hero-slides, om oss-bild, ev. tjänste-/stämningsbilder.
- **Text:** lämna `[PLATSHÅLLARE]`-texterna men låt dem se ut som riktigt
  innehåll. De byts mot salongens riktiga uppgifter senare.
- Allt platshållarinnehåll ska gå att byta utan att designen behöver göras om.

---

## Sammanfattat

En sida. Varm, lugn, lyxig — Kochi-känsla, Tofifi-palett. Stora luftiga
versalrubriker, editorial fotografi, mjuk interaktivitet. Bygg den som färdig
HTML/CSS/JS, relativa sökvägar, tillgänglig och snabb. Boka tid-knappen är
sidans viktigaste element — gör den omöjlig att missa.

Maxa hantverket. Lycka till.
