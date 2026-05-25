# 01 — Vision och mål

## Visionen

En **en-sidig hemsida** för frisörsalongen **Tofifi Cut and Trim**.

Sidan är ett **skyltfönster**, inte ett verktyg. Den ska få någon som aldrig
hört talas om salongen att tänka "den här ser proffsig och fin ut" — och sen
trycka på **Boka tid**. Den knappen leder ut till salongens sida på **Boka
Direkt**, där den faktiska bokningen sker.

Den ska vara **liten, snygg och interaktiv** — bild-slides, mjuka övergångar,
en stilig om-oss-del, plats och tjänster. Den ska kännas levande och
genomtänkt. Den ska **inte** bli en bokningssida i sig, och inte en torr
"infotavla" som bara radar upp text.

Allt görs **bra från början**. Hellre litet och välgjort än stort och slarvigt.

## Referensen — Kochi Hair Care

Kompisen gillar [Kochi Hair Care](https://kochihaircare.me/). Det vi tar
därifrån är **känslan**, inte funktionen (Kochi är en produktbutik — det är vi
inte):

- Varm, lyxig palett — grädde, sand, karamell/tan, djupt nästan-svart, guld.
- Stora, luftiga, lätta rubriker i versaler med generös bokstavsspärr.
- Editorial fotografi som får ta stor plats — bilden bär färgen.
- Mycket luft. Lugnt tempo. Inget stökigt.
- Tunn topprad, ren versal-logotyp, enkel meny som glider in från sidan.

Hela design-tolkningen ligger i `3-Design/DESIGN-BRIEF.md`.

## Målet

**Huvudmål:** En live, snygg en-sidig hemsida för Tofifi Cut and Trim på
GitHub Pages, med en fungerande Boka tid-knapp till Boka Direkt.

Prioritetsordning — om något måste prioriteras bort, börja nerifrån:

**MÅSTE (utan dessa är vi inte klara):**

- En-sidig sida som laddar och ser bra ut på mobil, surfplatta och desktop.
- Synlig, tydlig **Boka tid**-knapp som öppnar Boka Direkt i ny flik.
- Sektionerna i `02-Innehåll-och-sektioner.md` finns med.
- Deployad och verifierat live på GitHub Pages.
- Tillgänglig på rimlig nivå (WCAG 2.1 AA) och snabb att ladda.

**BÖR (gör sidan bra, inte bara funktionell):**

- Interaktiv hero med bild-slides.
- Mjuk ankarscroll mellan sektioner + subtila scroll-animationer.
- Sticky header, hamburgermeny på mobil.
- Snygg favicon och korrekt social delningsbild (Open Graph).

**TREVLIGT (om tid och material finns):**

- Litet bildgalleri.
- Kundrecensioner.
- Egen domän (t.ex. en `.se`-adress) istället för github.io-adressen.

## Så vet vi att vi lyckats

- Sidan ligger live på GitHub Pages-URL:en och ser likadan ut live som lokalt.
- Boka tid-knappen öppnar rätt Boka Direkt-sida i ny flik.
- Inga trasiga bilder, inga trasiga sökvägar, ingen vågrät scroll på mobil.
- En förstagångsbesökare förstår på 5 sekunder: vad det är, och hur man bokar.

## Vad sidan INTE är (non-goals)

- Ingen bokningsmotor — bokning sker hos Boka Direkt, vi länkar bara dit.
- Ingen butik, inga produkter, ingen kundvagn, ingen kassa.
- Ingen inloggning, inga konton.
- Ingen databas, ingen backend, inget byggsteg/ramverk.
- Ingen blogg, inget nyhetsflöde.
