# KI-Fänger

Zwei Browser-Quizspiele über KI-Wissen (reines HTML, CSS, JavaScript, ohne Build-Schritt und ohne Backend).

- **KI-Fänger** (Hauptordner): Pokémon-ähnliches Spiel, in dem man KI-Tools fängt. Einstieg: `index.html`.
- **AI-Quest** (`ai-quest/index.html`): zweites Quizspiel in einer einzigen Datei.

## Lokal testen

`python3 -m http.server 8000` in diesem Ordner, dann http://localhost:8000 (KI-Fänger) und http://localhost:8000/ai-quest/ (AI-Quest).

## Vercel

Das Spiel liegt im Hauptordner des Repos. Beim Import in Vercel das Feld **Root Directory leer lassen**, Framework Preset „Other“, kein Build Command.

## Hinweise

- Der Spielstand liegt nur im localStorage des Browsers.
- Fragen: `data.js` (Antwort an Index 0 ist richtig). Karten: `maps.js`.
- Protokoll und Anleitungen: `HOWTO.md`. Offene Punkte: `TODO.md`.
