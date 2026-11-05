# Madrid-Rallye

Eine selbstgeführte Stadtrallye durch Lavapiés und das Barrio de las Letras in Madrid, gebaut für das iPhone und für 2–3 Personen. Auf jeweils 1–3 Kulturstationen folgt eine Bar.

| | |
|---|---|
| **Start** | Calle de Buenavista 20, 28012 Madrid |
| **Ziel** | Taberna La Dolores, Plaza de Jesús 4 (628 m vom Start) |
| **Strecke** | 3.136 m (berechnet), keine Etappe über 318 m |
| **Dauer** | ca. 3 Stunden |
| **Stationen** | 14: 10 × Kultur, 4 × Bar, dazu Schlusswort |
| **Sprache** | Deutsch |

## Die Route

1. **Plaza de Lavapiés**: Kachelschild mit dem alten Brunnen
2. **Corrala und Escuelas Pías**: Mietshaus mit Laubengängen, ausgebrannte Barockkirche
3. **San Cayetano**: Barockfassade an der Calle de Embajadores
4. 🍷 **Taberna Antonio Sánchez**: vielleicht die älteste Taberna Madrids
5. **Plaza de Cascorro**: Eloy Gonzalo, der Waisenjunge, der zum Helden wurde
6. 🍷 **Sala Equis**: Kinobar mit bewegter Vergangenheit
7. **Plaza de Tirso de Molina**: ein Mönch auf dem Sockel eines Klosterenteigners
8. **Palacio del Marqués de Perales**: Pedro de Ribera und die Calle de la Magdalena
9. **Plaza de Antón Martín**: „El abrazo“ und die Abogados de Atocha
10. 🍷 **Casa Alberto**: seit 1827, Vermut vom Hahn
11. **Casa de Cervantes**: wo Cervantes 1616 starb
12. **Casa-Museo Lope de Vega**: das Haus des Rivalen in der Calle de Cervantes
13. **Trinitarias Descalzas**: Cervantes’ Grab in der Calle de Lope de Vega
14. 🍷 **Taberna La Dolores**: Kachelfassade von 1908

Bonus-Abstecher am Ende: Plaza de Santa Ana, die Druckerei des Quijote und am NFL-Wochenende das NFL House Madrid.

## Spielen

`index.html` ist eine einzige, eigenständige Datei mit HTML, CSS, JavaScript und allen Inhalten. Sie braucht kein Framework und stellt keine externen Requests; nur die Bilder in `bilder/` werden nachgeladen. Nach dem ersten Laden läuft sie auch bei schlechtem Netz weiter.

**Über GitHub Pages:** Einmal in den Repo-Einstellungen unter *Settings → Pages → Source* **GitHub Actions** wählen. Der Workflow `.github/workflows/pages.yml` veröffentlicht bei jedem Push auf `main`; zusätzlich lässt er sich unter *Actions* manuell starten. Wichtig: Die Arbeit liegt zunächst auf dem Branch `claude/sleepy-dirac-0mia7k`. Erst nach dem Merge nach `main` wird veröffentlicht, weil die Pages-Umgebung standardmäßig nur vom Standard-Branch aus deployen darf. Den Link in Safari öffnen und über *Teilen → Zum Home-Bildschirm* ablegen.

**Lokal:**

```bash
python3 -m http.server 8000
```

Dann `http://localhost:8000` öffnen.

## Spielmechanik

- Pro Station drei Schirme: **Weg** (Google-Maps-Link im Fußgängermodus plus Wegbeschreibung in Worten), **Ort** (Foto und Geschichte), **Aufgabe**.
- Jede Lösung steht vor Ort: ablesen, zählen, erkennen. Die Infotexte liefern Kontext, nie die Lösung.
- Nach 2 Fehlversuchen gibt es einen Tipp, nach 4 die Lösung.
- **Plan B:** Jede Kulturstation hat eine Ersatzaufgabe für den Fall, dass das Objekt verdeckt oder verschwunden ist.
- Bars: Die Bonusfrage ist freiwillig und lässt sich überspringen.
- 10 Sammelbuchstaben ergeben das Schlusswort.
- Tolerante Antwortprüfung: Groß- und Kleinschreibung, Umlaute, Akzente, Satzzeichen und führende Artikel spielen keine Rolle; Zahlen gelten als Ziffer und als Wort (de/es).
- Der Fortschritt wird im `localStorage` gespeichert; ist der Speicher blockiert, läuft die Rallye trotzdem.
- iPhone: `viewport-fit=cover`, Safe-Area-Abstände, Touch-Ziele ab 44 px, Eingabefelder 16 px, Systemschrift, Hell- und Dunkelmodus.

## Inhalte ändern

Alle Texte, Antworten, Tipps, Plan-B-Aufgaben und Bildangaben stehen im Datenblock `const RALLYE = { … }` am Anfang des Skripts in `index.html`.

## Dateien

| Datei | Inhalt |
|---|---|
| `index.html` | die Rallye |
| `bilder/` | 13 Stationsfotos (CC-lizenziert, Nachweise in der App und in der Spielleitung). Station 8 hat noch einen Platzhalter. |
| `SPIELLEITUNG.md` | **Spoiler:** Lösungen, Belege, Plan B, Checkliste, Fotoliste, Etappenrechnung |
| `.github/workflows/pages.yml` | Deployment zu GitHub Pages |

## Bildrechte

Fotos von Flickr unter CC BY, CC BY-SA und CC BY-NC-SA. Die Urheber stehen unter jedem Bild und in `SPIELLEITUNG.md`. Drei Bilder sind NC-lizenziert (nur nicht kommerziell).
