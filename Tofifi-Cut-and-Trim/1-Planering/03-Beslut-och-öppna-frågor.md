# 03 — Beslut och öppna frågor

## Låsta beslut — stanna inte för dessa

Allt här är bestämt. Claude Code och Claude Design ska följa det utan att
fråga om eller designa om.

1. **Typ av sida:** en-sidig (one-pager), allt på samma sida med ankarscroll.
2. **Språk:** svenska. Kodkommentarer på engelska.
3. **Omfattning:** Hero med bild-slides, Tjänster, Om oss, Plats & öppettider,
   Boka-sektion, Footer. Interaktiv och snygg — inte minimal, inte en
   "infotavla", inte en bokningssida i sig själv.
4. **Designkänsla:** som Kochi Hair Care — varm palett (grädde/sand/karamell/
   svart/guld), stora luftiga versalrubriker, editorial fotografi, lugn lyx.
   Full tolkning i `3-Design/DESIGN-BRIEF.md`.
5. **Teknik:** ren statisk **HTML + CSS + JS (vanilla)**. Inget ramverk, inget
   byggsteg, ingen pakethanterare, ingen databas, ingen backend.
   *Varför:* sidan är liten och statisk, ska ligga på GitHub Pages och vara
   lätt för kompisen att äga. Ett ramverk eller byggsteg vore bara overhead.
6. **Hosting:** GitHub Pages, branch `main`, mapp `/ (root)`.
7. **Bokning:** en knapp/länk **ut** till Boka Direkt. Ingen bokning på sidan,
   ingen integration, ingen databas. Öppnas i ny flik.
8. **Namn:** "Tofifi Cut and Trim". Ingen bildlogga finns — Claude Design
   formger ett **typografiskt ordmärke**.
9. **Innehåll:** byggs med platshållare nu (se `02-Innehåll-och-sektioner.md`).
   Riktiga uppgifter slottas in senare utan att något behöver byggas om.
10. **Sökvägar:** alla länkar till CSS/JS/bilder är **relativa**
    (`css/style.css`, `./assets/...`) — aldrig absoluta (`/css/...`). Se
    roadmapen för varför (GitHub Pages projekt-sida).

## Parkerat — väntar på kompisen

Det här behövs för att byta ut platshållarna. Det **blockerar inte bygget** —
sidan blir klar med platshållare, uppgifterna slottas in efteråt.

- [ ] **Boka Direkt-URL** — länken till salongens bokningssida på bokadirekt.se.
- [ ] **Tjänster + priser** — riktiga tjänster och prislista.
- [ ] **Adress** — gatuadress för text + Google Maps-karta.
- [ ] **Öppettider** — riktiga tider.
- [ ] **Telefon** — kontaktnummer.
- [ ] **Instagram** — handle/länk, om kompisen har en.
- [ ] **Foton** — interiör, klippningar, ev. porträtt. Hög upplösning.
- [ ] **Om oss-text** — om kompisen vill ha en egen formulering.

När uppgifterna kommer in: byt platshållarna i `5-Kod/` (en liten fix-brief
räcker) och be kompisen pusha igen.

## Att flagga till kompisen — varumärke

Namnet **"Tofifi"** är ett registrerat varumärke (chokladen, tillverkad av
Storck). Att driva en frisörsalong som heter "Tofifi Cut and Trim" *kan*
krocka med det varumärket.

Det här **påverkar inte bygget** — vi bygger på det namn kompisen valt. Men
det är värt att kompisen själv kollar med någon kunnig (t.ex. PRV eller en
jurist) att namnet går bra att använda kommersiellt, innan han trycker pengar
på skyltar, visitkort och domän. Bara en vänlig flagga — inget juridiskt råd.

## Öppna frågor — inga som blockerar

Inga olösta frågor blockerar bygget just nu. Allt som krävs för att Claude
Code ska kunna bygga utan att stanna är låst ovan eller hanterat med
platshållare.
