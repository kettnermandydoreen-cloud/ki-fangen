# Projekt-Gedächtnis: KI-Fänger

Diese Datei wird von OpenCode automatisch gelesen. Sprache der Kommunikation und der Spiele: Deutsch.

## Dokumentation (verbindlich)

- **`HOWTO.md`** dokumentiert, was gemacht wurde: Überblick, Dateien, Anleitungen (lokal testen, Fragen ergänzen, Karten ändern, deployen), Regeln und das Protokoll aller Schritte. Der Abschnitt „Offene Punkte“ verweist nur auf `TODO.md`.
- **`TODO.md`** listet nur, was noch offen ist, gegliedert in „Vor dem Teilen“, „Betrieb“, „Entscheidungen“ und „Ideen“.
- Nach **jeder Änderung** einen Eintrag im Protokoll in `HOWTO.md` ergänzen (Datum, was, wer, Hinweis). Erledigte Punkte in `TODO.md` abhaken oder entfernen, neue Punkte dort ergänzen. Offene Punkte nie in `HOWTO.md` führen.
- Vor Arbeitsbeginn `HOWTO.md` und `TODO.md` lesen.
- Keine Zugangsdaten in diese Dateien schreiben.

## Projekt

- Ein Browser-Quizspiel, reines HTML, CSS, JavaScript, ohne Build und ohne Backend. Spielstand nur im `localStorage`.
- Online: https://ki-fangen.vercel.app/
- Repo: https://github.com/kettnermandydoreen-cloud/ki-fangen

## Regeln

- Design nur mit den Werten des Designsystems von Mandy Kettner: Paper #F5F4F2, Soft #E9E7E4, Gray #8B8D8E, Ink #292A2C, Lime #C3F36B, eckig, Georgia für Überschriften, Arial für Text.
- Kein Server-Code. Fragen in `data.js`: Antwort an Index 0 ist richtig, keine doppelten Fragen.
- Tokens nie in Dateien, Remote-URLs oder Commits. Nie `--force` pushen ohne ausdrückliche Zustimmung.
- Vercel ist nicht mit GitHub verbunden: Ein Push veröffentlicht nichts. Das Spiel ist öffentlich, deshalb vor jedem Deploy Rückfrage halten.
- Keine erfundenen Rechtsangaben. Fragen mit Kurswerten (Datum, Limits) als prüfbedürftig behandeln.
