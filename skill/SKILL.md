---
name: ch-media-cicd-check
description: "Prüft, überarbeitet und erstellt PowerPoint-Präsentationen nach dem CH Media Corporate Design. Verwende diesen Skill immer, wenn eine Präsentation, einzelne Folien oder ein Briefing auf Konformität mit dem CH Media Corporate Identity / Corporate Design geprüft, korrigiert oder neu erstellt werden soll. Trigger auch bei: 'CI/CD-Check', 'CH Media Folien', 'Folienbibliothek', 'CH Media Präsentation prüfen', 'CH Media konform', 'Designcheck', 'Folienreview', 'CH Media Audit', 'Corporate Design Prüfung', oder wenn jemand eine .pptx-Datei im Kontext von CH Media erwähnt. Trigger ebenfalls, wenn Inhalte oder Briefings in eine CH-Media-konforme Folienstruktur überführt werden sollen."
---

# CH Media CI/CD Check

Dieser Skill prüft, korrigiert und erstellt PowerPoint-Präsentationen gemäss dem verbindlichen CH Media Corporate Design.

**Wichtig:** CI/CD steht hier für Corporate Identity / Corporate Design, nicht für Continuous Integration / Continuous Delivery.

---

## Asset-Repository

Assets (Icons, Medienmarken, Sticker) und Fonts sind in einem externen GitHub-Repository gehostet:
**Repo:** `https://github.com/semmeli01/chm-cicd-assets`
**Raw-Basis-URL:** `https://raw.githubusercontent.com/semmeli01/chm-cicd-assets/main`

Die Dateien werden **bei Bedarf** heruntergeladen (z. B. beim Erstellen einer PPTX). Verwende folgendes Bash-Skript, um Assets oder Fonts herunterzuladen:

### Fonts herunterladen & installieren

```bash
REPO_RAW="https://raw.githubusercontent.com/semmeli01/chm-cicd-assets/main"
FONT_DIR="$HOME/.local/share/fonts"
mkdir -p "$FONT_DIR"

# Font-Liste (alle verfügbaren Fonts)
FONTS=(
  "Zuume_Bold.ttf" "Zuume_Black.ttf" "Zuume_Black_Italic.ttf"
  "Zuume_ExtraBold.ttf" "Zuume_ExtraBold_Italic.ttf"
  "Zuume_ExtraLight.ttf" "Zuume_ExtraLight_Italic.ttf"
  "Zuume_Light.ttf" "Zuume_Light_Italic.ttf"
  "Zuume_Medium.ttf" "Zuume_Medium_Italic.ttf"
  "Zuume_Regular.ttf" "Zuume_SemiBold.ttf" "Zuume_SemiBold_Italic.ttf"
  "Zuume_Thin.ttf" "Zuume_Thin_Italic.ttf"
  "CHMedia-Black.otf" "CHMedia-BlackItalic.otf"
  "CHMedia-Bold.otf" "CHMedia-BoldItalic.otf"
  "CHMedia-Book.otf" "CHMedia-BookItalic.otf"
  "CHMedia-Light.otf" "CHMedia-LightItalic.otf"
  "CHMedia-Regular.otf" "CHMedia-RegularItalic.otf"
  "CHMedia-SemiBold.otf" "CHMedia-SemiBoldItalic.otf"
  "CHMedia-Thin.otf" "CHMedia-ThinItalic.otf"
)

for f in "${FONTS[@]}"; do
  curl -sL "$REPO_RAW/fonts/$f" -o "$FONT_DIR/$f"
done
fc-cache -f
```

### Assets herunterladen (einzeln, bei Bedarf)

```bash
REPO_RAW="https://raw.githubusercontent.com/semmeli01/chm-cicd-assets/main"
ASSET_DIR="/tmp/ch-media-assets"
mkdir -p "$ASSET_DIR/icons/blau" "$ASSET_DIR/icons/negativ" "$ASSET_DIR/medienmarken" "$ASSET_DIR/sticker"

# Beispiel: Ein Icon herunterladen
curl -sL "$REPO_RAW/assets/icons/blau/Megafon.png" -o "$ASSET_DIR/icons/blau/Megafon.png"

# Beispiel: Eine Medienmarke herunterladen
curl -sL "$REPO_RAW/assets/medienmarken/Sticker_Logo_watson.png" -o "$ASSET_DIR/medienmarken/Sticker_Logo_watson.png"
```

**Wichtig:** Lade nur die Assets herunter, die tatsächlich für die aktuelle Präsentation benötigt werden. Nicht alle 500+ Dateien auf einmal herunterladen.

---

## Designregeln laden

Vor jeder Prüfung oder Erstellung: Lies die verbindlichen Regeln in `references/ch-media-designregeln.md`. Diese Regeln sind die einzige Autorität. Erfinde keine Regeln, die dort nicht stehen. Kennzeichne Annahmen immer explizit.

---

## Workflow

### Schritt 1 – Aufgabe verstehen

Bevor du prüfst oder erstellst, kläre:

1. **Ziel** der Präsentation (informieren, überzeugen, schulen, pitchen …)
2. **Zielpublikum** (Management, Kunden, intern, extern …) – ableiten, falls nicht explizit genannt
3. **Präsentationstyp** einordnen: Management-Deck, Debriefing, Strategie, Sales, Projekt-Update, Schulung, Event, Kampagne …

Falls Informationen fehlen, frage nach. Triff keine stillen Annahmen über den Zweck.

---

### Schritt 2 – CI/CD Audit

Prüfe jede Folie gegen die sechs Regelkategorien:

| # | Kategorie | Referenz |
|---|-----------|----------|
| 1 | Typografie | Zuume bold Versalien für Headlines, CH Media Book/Bold, 15 pt, linksbündig |
| 2 | Farben | Blau #0000f5 dominant, Gelb #ffff00 nur Akzent, viel Weissraum |
| 3 | Logo | Neues Logo, nicht auftrennen, Farblogik je Hintergrund, Schutzraum |
| 4 | Bildwelt | Reportagefotografie, Schwarz-Weiss bevorzugt, keine Stock-Ästhetik |
| 5 | Gestaltungselemente | 1 pt Strichstärke, abgerundete Ecken, Symbol gelb, max. 1 grosses Symbol |
| 6 | Layoutlogik | Folientyp aus Bibliothek wählen, keine freien Layouts, Sticker sparsam |

Für jeden Verstoss bestimme den **Schweregrad**:

- **kritisch** – Kernregel verletzt, muss korrigiert werden
- **mittel** – beeinträchtigt Markenwirkung, sollte korrigiert werden
- **gering** – kleiner Verbesserungspunkt

---

### Schritt 3 – Bibliotheks-Logik anwenden

Ordne jeder Folie den passendsten Folientyp zu:

Titel · Agenda · Kapiteltrenner · Statement / Quote · Text-Bild · Zielsetzung · Listen · Karten / Regionen · Diagramme · Timelines · Icon-Folien · Sticker-Folien · Keyvisual-Folien

Wenn das aktuelle Layout nicht passt, nenne ein alternatives Layout und begründe kurz.

---

### Schritt 4 – Korrekturen ausarbeiten

Pro Folie:

- Konkrete Korrektur formulieren (was genau ändern, wie)
- Auf Wunsch: Titel, Subtitles und Body-Text direkt neu schreiben
- Auf Wunsch: Neue Folienstruktur vorschlagen

Formuliere präzise, streng und umsetzungsorientiert. Vermeide generische Designfloskeln. CH Media Stil hat immer Vorrang vor allgemeinen PowerPoint-Best-Practices.

---

### Schritt 5 – Ergebnis ausgeben

Verwende dieses Ausgabeformat:

```
## 1. Kurzfazit

Ampelbewertung: 🟢 Grün / 🟡 Gelb / 🔴 Rot
[1–3 Sätze: Wie stark ist die Präsentation CH-Media-konform?]

## 2. Wichtigste Verstösse

[Priorisierte Liste der gravierendsten CI/CD-Probleme, max. 5–7 Punkte]

## 3. Folie-für-Folie Review

### Folie [Nr.]: [Beschreibung / Titel]
- **Problem:** [Was stimmt nicht]
- **Betroffene Regel:** [Typografie / Farben / Logo / Bildwelt / Gestaltung / Layout]
- **Schweregrad:** kritisch / mittel / gering
- **Empfohlener Folientyp:** [z. B. Kapiteltrenner, Text-Bild …]
- **Korrektur:** [Konkrete Massnahme]
- **Textvorschlag:** [Optional: Neuer Titel, Subtitle, Body]

[Wiederholen für jede Folie]

## 4. Empfohlene Gesamtverbesserung

[Strukturelle Empfehlungen: Weissraum, Textreduktion, Visualisierung,
 Reihenfolge, fehlende Folienarten …]

## 5. Fehlende Assets / Offene Fragen

[z. B. ungeeignetes Bild, fehlendes Logo, unklare Markenreferenz,
 fehlender Kontext für eine Folie]

## 6. Ready-to-use Version (nur auf Wunsch)

Folie 1: [Typ] – [Titel]
  Layout: ...
  Headline: ...
  Body: ...

Folie 2: [Typ] – [Titel]
  ...
```

---

## Erstellen neuer Präsentationen

Wenn der Nutzer keine bestehende Datei liefert, sondern ein Briefing oder Rohinhalte:

1. **Schriften herunterladen & installieren** (immer als Erstes – siehe Abschnitt «Asset-Repository» oben für das vollständige Skript)
2. Lies die Designregeln in `references/ch-media-designregeln.md`.
3. Strukturiere den Inhalt in Folien gemäss Bibliotheks-Logik.
4. Verwende die korrekten Font-Mappings aus den Designregeln:
   - Headlines: `fontFace: "Zuume"` + `bold: true` (immer Versalien)
   - Lauftext: `fontFace: "CH Media Book"`
   - Subheadings/Labels: `fontFace: "CH Media"` + `bold: true`
5. Beachte Farbschema (Blau #0000F5 dominant, Gelb #FFFF00 nur Akzent, viel Weissraum).
6. Markiere, wo Bilder, Icons oder Assets aus den CH Media Libraries nötig sind.
7. Wenn du eine .pptx-Datei erstellst, verwende den PPTX-Skill für die technische Umsetzung – aber das Design richtet sich ausschliesslich nach den Regeln dieses Skills.

---

## Guardrails

- **Keine erfundenen Regeln.** Nur anwenden, was in `references/ch-media-designregeln.md` steht.
- **Annahmen explizit kennzeichnen.** Wenn du nicht sicher bist, schreib es hin.
- **Qualität über Quantität.** Lieber wenige, klare, hochwertige Empfehlungen als generische Tipps.
- **CH Media Stil vor allgemeinen Best Practices.** Die CH Media Regeln haben Vorrang.
- **Sprache: Deutsch.** Alle Ausgaben auf Deutsch.
- **Präzise, streng, umsetzungsorientiert.** Schreib so, dass ein Designer sofort umsetzen kann.

---

## Wenn der Nutzer eine .pptx-Datei liefert

1. **Schriften herunterladen & installieren** (immer als Erstes – siehe Abschnitt «Asset-Repository» oben für das vollständige Skript)
2. Text extrahieren: `python -m markitdown datei.pptx`
3. Thumbnails erzeugen für visuellen Check (siehe PPTX-Skill)
4. CI/CD Audit gemäss Schritt 2–5 durchführen
5. Falls gewünscht: korrigierte Version erstellen (PPTX-Skill für Technik, dieser Skill für Design)

---

## Beispiel-Prompts

1. «Prüfe diese Präsentation auf CH Media CI/CD-Konformität.»
2. «Überarbeite die Folien so, dass sie dem CH Media Corporate Design entsprechen.»
3. «Ich habe ein Briefing für eine Strategiepräsentation – erstelle mir eine CH-Media-konforme Folienstruktur.»
4. «Folie 3 und 7 passen nicht zum CI/CD – was muss ich ändern?»
5. «Mach mir aus diesen Stichpunkten eine CH-Media-konforme Präsentation.»
