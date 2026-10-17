# Deko.Luxury

Website von LUXURY EVENTS by DEKO.LUXURY – online unter https://dekoluxury.world (GitHub Pages).

## Google-Bewertung automatisch anzeigen

Im Info-Streifen und im Footer steht die aktuelle Google-Bewertung, z. B. „4,9 von 5 Sternen · 37 Google-Bewertungen“.
Sie wird **einmal täglich automatisch** bei Google abgefragt (`.github/workflows/bewertungen.yml`,
`tools/bewertungen.mjs`) und in `assets/data/bewertungen.json` gespeichert. Ändert sich die Note
(z. B. von 4,9 auf 4,7) oder die Anzahl, zeigt die Website ab dem nächsten Tag den neuen Wert.
Solange keine Daten da sind, steht dort „auf Google ansehen“.

Einmalige Einrichtung:

1. https://console.cloud.google.com öffnen, ein Projekt anlegen und ein Abrechnungskonto verbinden
   (Google verlangt das; ein Abruf pro Tag liegt im kostenlosen Monatskontingent).
2. Unter „APIs & Dienste → Bibliothek“ die **Places API (New)** aktivieren.
3. Unter „APIs & Dienste → Anmeldedaten“ einen **API-Schlüssel** erstellen und auf „Places API (New)“ beschränken.
4. Hier im Repository: **Settings → Secrets and variables → Actions → New repository secret**,
   Name `GOOGLE_PLACES_API_KEY`, Wert = der API-Schlüssel. Den Schlüssel nirgends sonst eintragen.
5. **Actions → „Google-Bewertungen aktualisieren“ → Run workflow** starten. Im Protokoll steht,
   welcher Eintrag gefunden wurde und welche Bewertung gespeichert ist.
6. Optional: Die dort angezeigte Place-ID unter **Settings → Secrets and variables → Actions → Variables**
   als `GOOGLE_PLACE_ID` speichern, dann wird immer genau dieser Eintrag abgefragt.

## Anfrageformular

Anfragen gehen über den Dienst FormSubmit an deko.luxury@gmx.de (Einstellung oben in `assets/js/main.js`).
Beim allerersten Absenden kommt eine Mail „Activate Form“ – einmal bestätigen, danach kommt jede Anfrage an.
