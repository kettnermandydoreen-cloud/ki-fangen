# HOWTO und Protokoll: KI-Fänger und AI-Quest

Diese Datei ist das Logbuch des Projekts. **Nach jeder Änderung einen Eintrag im Protokoll ergänzen** (Datum, was, warum, wo). Sie enthält keine Zugangsdaten.

## 1. Überblick

| Was | Wert |
|---|---|
| Spiele | KI-Fänger (Hauptordner), AI-Quest (`ai-quest/index.html`) |
| Technik | Reines HTML, CSS, JavaScript. Kein Build, kein Backend. Spielstand im `localStorage` |
| Online | https://ki-fangen.vercel.app/ und https://ki-fangen.vercel.app/ai-quest/ |
| GitHub | https://github.com/kettnermandydoreen-cloud/ki-fangen (Public, Branch `main`) |
| Lokaler Ordner | `~/Desktop/ki-fangen-neu` |
| Vercel | Projekt `ki-fangen`, Hobby-Tarif (nur nicht-kommerziell), Region Frankfurt |
| Design | Designsystem von Mandy Kettner: Paper #F5F4F2, Soft #E9E7E4, Gray #8B8D8E, Ink #292A2C, Lime #C3F36B, eckig, Georgia und Arial |

## 2. Dateien

| Datei | Zweck |
|---|---|
| `index.html`, `style.css` | Oberfläche des KI-Fängers |
| `game.js` | Spiellogik: Bewegung, Kämpfe, Fangen, Shop, Speichern, Zeichnen |
| `data.js` | Tools (`TOOLS`) und Glossar-Fragen (`GLOSS`) |
| `maps.js` | Karten (Startwiese, Datenwald), Figuren, Übergänge |
| `sprites.js` | Pixelwesen, die aus dem Tool-Namen erzeugt werden |
| `audio.js` | Effekte und Musik per Web Audio, keine Audiodateien |
| `vercel.json` | Saubere URLs und Sicherheits-Header |
| `ai-quest/index.html` | Zweites Spiel in einer Datei |

## 3. Anleitungen

**Lokal ansehen**
```
cd ~/Desktop/ki-fangen-neu
python3 -m http.server 8000
```
Dann http://localhost:8000 öffnen.

**Fragen ergänzen** (`data.js`): Eine Zeile im Format `["Frage",["richtig","falsch","falsch","falsch"],0],`. Die richtige Antwort steht immer an Index 0, das Spiel mischt sie. Danach prüfen, dass keine Frage doppelt vorkommt.

**Karten ändern** (`maps.js`): `#` Baum, `.` Weg, `G` hohes Gras, `W` Wasser, `C` Akku-Station, `B` Tor zur AGI, `>` und `<` Übergänge. Alle Zeilen einer Karte müssen gleich lang sein.

**Veröffentlichen**
```
git add -A && git commit -m "Beschreibung" && git push origin main
PATH="$HOME/.local/node/bin:$PATH" vercel deploy --prod --yes
```
Vercel ist **nicht** mit GitHub verbunden. Ein Push veröffentlicht nichts, das Deployen ist ein eigener Schritt. Die Seiten sind öffentlich, deshalb vor jedem Deploy kurz prüfen und Rückfrage halten.

**Vercel mit GitHub verbinden (optional):** Vercel → Projekt → Settings → Git. Root Directory **leer** lassen, Framework Preset „Other“, kein Build Command. Danach deployt jeder Push automatisch.

## 4. Regeln

- Design nur mit den Werten des Designsystems, keine freien Farben oder Rundungen.
- Kein Server-Code, keine Zugangsdaten im Repo. Tokens nie in Dateien oder Remote-URLs schreiben.
- Nie `--force` pushen ohne ausdrückliche Zustimmung.
- Für die Spiele gibt es noch kein Impressum und keine Datenschutzseite (siehe offene Punkte).

## 5. Protokoll

| Datum | Was | Wer | Hinweis |
|---|---|---|---|
| 08.10. | Erstes Quizspiel als Einzeldatei, danach zum Projekt ausgebaut: Canvas-Welt, zwei Karten, Trainer, Shop, Level, Endgegner AGI, KI-Dex, Sound, Speicherstand. Commit `2c5a2ea` | KI (Claude Sonnet) auf Wunsch von Mandy | Zuerst im Portfolio-Repo unter `ki-fangen/`, nur auf Syntax und Daten geprüft, nicht durchgespielt |
| 08.10. | Glossar `Glossar_KI-Manager_gesamt.md` eingebaut: 60 Fragen, ohne Dopplungen | KI | Fragen von Hand aus den Definitionen geschrieben |
| 12.10. | AI-Quest gebaut: 12×9-Karte, 15 Tools, Quiz mit Zeitlimit, Fangchancen, KI-Dex | KI in einem anderen Chat | Nur Syntax geprüft, nicht durchgespielt |
| 13.10. | Spiele in eigenes Repo `ki-fangen` ausgelagert, Git-Verlauf übernommen, `ai-quest/` ergänzt. Commits `603d65f`, `4fc43a4` (`.vercel` ignoriert). Aus dem Portfolio-Repo wieder entfernt (`2754f48` bleibt im Verlauf) | KI in einem anderen Chat | |
| 13.10. | Vercel eingerichtet und veröffentlicht, beide Adressen antworten mit 200 | KI in einem anderen Chat, Anmeldung durch Mandy | Es gab ein weiteres Deployment, dessen Herkunft unklar ist |
| 13.10. | Neues Glossar (`Glossar_KI-Manager_gesamt (1).md`, 30 neue Begriffe) eingebaut: 33 neue Fragen, Pool jetzt 117. Commit `160c345` | KI (Claude Sonnet) | Gepusht, **nicht** deployt. Fragen mit Kurswerten (Datum, 7 Tage, 500 MB) prüfen |
| 13.10. | `UEBERGABE_Spiele.md` gelöscht, diese Datei angelegt | KI | Die Übergabe nannte `160c345` und KI-Fänger fälschlich als nicht vom Chat stammend |

## 6. Offene Punkte

- [ ] Neu deployen, damit die Glossar-Fragen aus `160c345` online sind (öffentlich, vorher Rückfrage).
- [ ] Vercel mit GitHub verbinden, damit Pushes automatisch deployen.
- [ ] `README.md` korrigieren: dort steht noch „Root Directory `ki-fangen`“, im neuen Repo muss es leer bleiben. Hinweis auf `ai-quest/` ergänzen.
- [ ] Impressum und Datenschutz: Spielseiten haben keins. Auf die Seiten des Portfolios verlinken oder die Spiele nur privat teilen. Vercel als Hosting erwähnen.
- [ ] Beide Spiele im Browser durchspielen (Kämpfe, Fangen, Handy-Steuerung, Reduced-Motion).
- [ ] Quizfragen auf Aktualität prüfen (Stand Oktober 2026).
- [ ] AI-Quest: neues Glossar einbauen oder bewusst getrennt lassen.
- [ ] Entscheiden, ob beide Spiele im selben Repo bleiben und ob sie im Portfolio verlinkt werden.
- [ ] Optional: Highscore-Liste über n8n.
