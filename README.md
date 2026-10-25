# Deko.Luxury

Website von LUXURY EVENTS by DEKO.LUXURY – online unter https://dekoluxury.world (GitHub Pages).

## Google-Bewertung ändern

Die Bewertung steht an vier Stellen (Startbereich, Info-Streifen, Karte in der Galerie, Footer)
und wird aus **einer** Zeile ganz oben in `assets/js/main.js` gefüllt:

```js
bewertung: { note: 5.0, anzahl: 13 },
```

Ändert sich etwas bei Google, einfach die Zahlen anpassen (Punkt statt Komma, z. B. `{ note: 4.9, anzahl: 12 }`).
Die Sterne füllen sich passend (4,9 = fast fünf volle Sterne). `bewertung: null` blendet die Bewertung aus.

## Anfrageformular

Anfragen gehen über den Dienst FormSubmit an deko.luxury@gmx.de (Einstellung oben in `assets/js/main.js`).
Beim allerersten Absenden kommt eine Mail „Activate Form“ – einmal bestätigen, danach kommt jede Anfrage an.
