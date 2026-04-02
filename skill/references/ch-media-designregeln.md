# CH Media Corporate Design – Verbindliche Regeln

Diese Regeln sind die einzige Autorität für CI/CD-Prüfungen. Erfinde keine Regeln, die hier nicht stehen. Kennzeichne Annahmen explizit.

---

## 1. Typografie

| Element | Schrift | Stil |
|---------|---------|------|
| Headlines | Zuume bold | Versalien / Grossbuchstaben |
| Lauftext, Quellen | CH Media Book | Normal |
| Sublines, Subheadings, Einleitungstexte, Kurztexte, Auszeichnungen | CH Media Bold | Normal |

- Headlines kompakt auf zwei, drei oder mehr Zeilen umbrechen; lange einzeilige Titel vermeiden.
- Laufweite der Zuume nie verändern.
- Text grundsätzlich linksbündig.
- Standard-Textgrösse in PowerPoint: 15 pt, alternativ 12 pt.

### Technisches Font-Mapping (für PPTX-Erstellung)

Die Schriftdateien werden aus dem GitHub-Repository heruntergeladen. Vor der PPTX-Erstellung müssen sie installiert werden – siehe Abschnitt «Asset-Repository» in der SKILL.md für das vollständige Download-Skript.

| CI/CD-Bezeichnung | fontFace in PptxGenJS | bold-Flag | Datei(en) |
|---|---|---|---|
| Zuume bold (Headlines) | `"Zuume"` | `bold: true` | `Zuume_Bold.ttf` |
| CH Media Book (Lauftext) | `"CH Media Book"` | – | `CHMedia-Book.otf` |
| CH Media Bold (Subheadings) | `"CH Media"` | `bold: true` | `CHMedia-Bold.otf` |

**Wichtig:** In PptxGenJS den `fontFace`-Wert exakt wie in der Tabelle verwenden. Die Schrift „Zuume" wird über das `bold`-Flag zum Bold-Schnitt, nicht über den Dateinamen. Die Schrift „CH Media Book" ist ein eigenständiger Fontname (nicht „CH Media" + Book-Flag).

### Typografie-Verstösse (Beispiele)

- Headline nicht in Versalien → **kritisch**
- Falsche Schrift (z. B. Arial statt Zuume) → **kritisch**
- Lauftext in CH Media Bold statt Book → **mittel**
- Text zentriert statt linksbündig → **mittel**
- Textgrösse weicht stark von 15 pt / 12 pt ab → **gering** bis **mittel**

---

## 2. Farben

| Rolle | Farbe | Hex |
|-------|-------|-----|
| Hauptfarbe | CH Media Blau | `#0000f5` |
| Highlightfarbe | Gelb | `#ffff00` |
| Grundfarbe | Weiss | `#ffffff` |
| Grundfarbe | Schwarz | `#000000` |

- Blau ist die dominante aktive Farbe.
- Gelb nur als Akzent / Highlight verwenden.
- Viel Weissraum ist erwünscht.
- Farb-Abstufungen (Schattierungen) nur für Diagramme, Charts oder Benutzerführung.
- Keine unnötigen Zusatzfarben einführen.

### Farb-Verstösse (Beispiele)

- Gelb als Flächenfarbe statt als Akzent → **kritisch**
- Fremde Farben (z. B. Grün, Rot als Hauptfarbe) → **kritisch**
- Zu wenig Weissraum → **mittel**
- Farb-Abstufungen ausserhalb von Diagrammen → **mittel**

---

## 3. Logo

- Nur das neue CH Media Logo verwenden.
- Wort-Bild-Marke nie auftrennen.
- Heller Hintergrund → Logo in Blau.
- Dunkler Hintergrund → Logo in Weiss.
- Schwarz nur in Ausnahmefällen.
- Logo nie verzerren, drehen, verfremden, mit Schatten, transparent oder mit Verlauf einsetzen.
- Schutzraum einhalten.
- Auf Bildern nur auf ruhigem Hintergrund mit genügend Kontrast platzieren.
- Logo eher linksbündig an Ober- oder Unterkante positionieren.

### Logo-Verstösse (Beispiele)

- Veraltetes Logo → **kritisch**
- Logo verzerrt oder gedreht → **kritisch**
- Wort-Bild-Marke aufgetrennt → **kritisch**
- Logo auf unruhigem Bildhintergrund → **mittel**
- Logo nicht linksbündig → **gering**

---

## 4. Bildwelt

- Authentische Reportagefotografie.
- Echte, bodenständige, natürliche Momente.
- Keine künstlich inszenierten, sterilen oder stockartigen Motive.
- Fokus: CH Media Alltag, Nutzer:innen & Medien, Schweiz & Menschen.
- Bilder vorzugsweise in Schwarz-Weiss.
- Medienmarken-spezifisches Bildmaterial in Farbe belassen.
- Stimmiger Kontrast: weder flach noch übertrieben hart.

### Bildwelt-Verstösse (Beispiele)

- Stock-Fotos mit generischen Business-Motiven → **kritisch**
- Alle Bilder in Farbe ohne Grund → **mittel**
- Bilder flach / kontrastarm → **gering**

---

## 5. Gestaltungselemente

- Lineare Elemente und Icons mit einheitlicher Strichstärke (PowerPoint-Richtwert: 1 pt).
- Lineare Elemente mit abgerundeten Abschlüssen / Ecken.
- CH Media Symbol als Gestaltungselement immer gelb.
- Pro Anwendung nur ein grosses Symbol als Gestaltungselement.
- Symbol plakativ, asymmetrisch, dynamisch platzieren – nicht zum Füllen von Leerraum.
- Symbol darf randabfallend / angeschnitten sein, aber nie in Proportion oder Anordnung verändert.
- Gelbe Scribbles optional, sparsam einsetzen.
- Abgerundete Ecken nur in vorgesehenen CH Media Varianten.

### Gestaltungselement-Verstösse (Beispiele)

- Mehrere grosse Symbole gleichzeitig → **kritisch**
- Symbol proportional verändert → **kritisch**
- Strichstärke inkonsistent → **mittel**
- Scribbles inflationär eingesetzt → **mittel**
- Eckige statt abgerundete Linienabschlüsse → **gering**

---

## 6. Folienbibliothek / Layoutlogik

### Folienfamilien

| Folientyp | Typischer Einsatz |
|-----------|-------------------|
| Titel | Einstieg, Deckblatt |
| Agenda | Überblick, Ablauf |
| Kapiteltrenner | Strukturierung, Abschnittswechsel |
| Statement / Quote | Zitate, Kernbotschaften |
| Text-Bild | Erklärende Inhalte mit Bild |
| Zielsetzung | Ziele, Meilensteine |
| Listen | Aufzählungen, Bullets |
| Karten / Regionen | Geografische Darstellungen |
| Diagramme | Datenvisualisierung |
| Timelines | Zeitliche Abläufe |
| Icon-Folien | Symbolgestützte Inhalte |
| Sticker-Folien | Spielerische / dynamische Inhalte |
| Keyvisual-Folien | Visuelle Leitbilder, Kampagnenmotive |

### Layoutregeln

- Nie frei neue Designsysteme erfinden.
- Immer zuerst den passendsten Folientyp aus der Bibliothek wählen.
- Tabellen nach Einfügen auf Tabellenformat «Benutzerdefiniert» setzen.
- Sticker sparsam, eher zum Schluss, leicht schräg / spielerisch / dynamisch.
- Sticker nicht gleichmässig verteilen, nicht zum Auffüllen von Weissraum.
- Bestehende Libraries bevorzugen: Icon Library, Sticker Library, Scribble Library, Pfeil Library, Logo Library, Keyvisual Library.

### Layout-Verstösse (Beispiele)

- Komplett freies Layout ohne Bibliotheksbezug → **kritisch**
- Sticker als Lückenfüller → **mittel**
- Tabelle nicht auf «Benutzerdefiniert» gesetzt → **gering**

---

## Schweregrad-Definitionen

| Schweregrad | Bedeutung |
|-------------|-----------|
| **kritisch** | Klarer Verstoss gegen eine Kernregel des CH Media CI/CD. Muss korrigiert werden. |
| **mittel** | Abweichung, die die Markenwirkung beeinträchtigt. Sollte korrigiert werden. |
| **gering** | Kleiner Verbesserungspunkt. Kann korrigiert werden. |

---

## 7. Asset-Bibliothek

Alle Assets werden bei Bedarf aus dem GitHub-Repository heruntergeladen nach `/tmp/ch-media-assets/`. Siehe Abschnitt «Asset-Repository» in der SKILL.md für Download-Anweisungen.

**Pfad-Basis nach Download:** `/tmp/ch-media-assets/`

### Verwendung in PptxGenJS

```javascript
// Icon auf Folie einfügen (nach Download in /tmp/ch-media-assets/)
slide.addImage({
  path: "/tmp/ch-media-assets/icons/blau/Megafon.png",
  x: 0.6, y: 1.0, w: 0.6, h: 0.6
});
```

### 7.1 Icons (223 Stück)

**Pfad (nach Download):** `/tmp/ch-media-assets/icons/blau/{Name}.png` (blau auf transparent, 542×542 px)
**Negativ-Variante (nach Download):** `/tmp/ch-media-assets/icons/negativ/{Name}_neg.png` (weiss auf transparent, für dunkle Hintergründe)

- Lineare Darstellung, einheitliche Strichstärke, abgerundete Ecken – CI/CD-konform
- Blau-Variante auf hellen Hintergründen, Negativ auf dunklen/blauen Hintergründen
- **Nie** die Farbe der Icons ändern – nur die passende Variante wählen

**Verfügbare Icons (Auswahl nach Kategorie):**

| Kategorie | Icons |
|---|---|
| Medien & Kommunikation | Bildschirm, Bildschirm_News, Bildschirm_News_Welt, Fernseher, Fernseher_Sendung, Filmklappe, Fotokamera, Handy, Handy_News, Handy_digital_News, Laptop, Megafon, Mikrofon, Mikrofon_2, Play, Radio, Sendebus, Sendemast, Sprechblasen, Sprechblasen_Information, Sprechblasen_Like, Sprechblasen_Musiknote, Tablet, Tablet_Stift, Video, Videokamera, Videokamera_Stativ, Zeitung, Zeitung_News |
| Business & Strategie | Balkendiagramm, Balkendiagramm_sinkend, Balkendiagramm_steigend, Kreisdiagramm, Meeting, Referieren, Schachfigur_Springer, Stufen_Ziel, Unternehmen, Unternehmen_Hochhaus, Vortragen, Vortragen_Podest, analysieren, analysieren_Markt, Brainstorming, Besprechen |
| Personen | Frau, Frau_Mikrofon, Frau_Mikrofon_Headset, Gruppe, Gemeinsam, Kundendienst_Frau, Kundendienst_Mann, Mann, Mann_Mikrofon, Mann_Mikrofon_Headset, Person_Klemmbrett, Person_Pfeile, Person_Wachstum, Person_Zahnräder, zwei_Gesichter |
| Schweiz | Helvetia, Käse, Schweiz, Schweizer_Flagge, Schweizer_Flagge_2, Schweizer_Flagge_3, Schweizer_Franken, Schweizerkarte_Hauptort, Schweizerkarte_News, Schweizerkarte_Standort, Schweizerkarte_Standort_2, Taschenmesser |
| Pfeile & Navigation | Pfeil_links, Pfeil_oben, Pfeil_oben_links, Pfeil_oben_rechts, Pfeil_rechts, Pfeil_unten, Pfeil_unten_links, Pfeil_unten_rechts, Pfeile, Wegweiser, Standort |
| Status & Feedback | Achtung, Falsch, Richtig, Kreuz, Stern, Idee, Information, Vorsicht |
| Technologie & Digital | Cloud_Speicher, Digital, Drucker, Gehirn, Gehirn_Vernetzen, Headset, Kopfhörer, Mausklick, Wissenschaft, Zahnräder, Zahnrad_Bleistift |
| Events & Freizeit | Anstossen, Gitarre_spielen, Konfetti, Martini, Musiknoten, Party, Pokal, Skifahren, Spotlight, Fussball, VIP_Zugang |
| Transport | Auto, Bus, Flugzeug, Schiff, Velo, Zug |
| Dokumente & Planung | Akte, Broschüre, Buch, Brief, Kalender, Kalender_Zeit, Klemmbrett_Todos, Notizen, Notizen_austauschen, Schreibwaren |

### 7.2 Medienmarken (65 Stück)

**Pfad (nach Download):** `/tmp/ch-media-assets/medienmarken/Sticker_Logo_{Marke}.png`

Sticker-Logos aller CH Media Marken. Verwenden für Marken-Referenzen und Partner-Slides.

**Verfügbar:** 3Plus, 4Plus, 5Plus, 6Plus, 7Plus, AargauerZeitung, AppenzellerZeitung, BadenerTagblatt, bz, flashback, GrenchnerTagblatt, LimmattalerZeitung, Limmatwelle, LuzernerZeitung, NidwaldnerZeitung, ObwaldnerZeitung, OltnerTagblatt, **oneplus**, Radio24, Radio32, RadioArgovia, RadioCentral, RadioEviva, RadioFM1, RadioMelody, RadioPilatus, S1, SchweizamWochenende, SolothurnerZeitung, SunshineRadio, Tagblatt, Tele1, TeleM1, TeleZueri, ThurgauerZeitung, ToggenburgerTagblatt, TRC, TV24, TV25, TVO, UrnerZeitung, VirginRadio, **watson**, WilerZeitung, ZugerZeitung, u.v.m.

### 7.3 Sticker (23 Stück)

**Pfad (nach Download):** `/tmp/ch-media-assets/sticker/Sticker_{Name}.png`

Illustrative, spielerische Sticker. CI/CD-Regel: sparsam einsetzen, eher zum Schluss, leicht schräg/dynamisch platzieren. Nie als Lückenfüller.

**Verfügbar:**

| Typ | Sticker |
|---|---|
| Gattungen | Druck & Publishing, Online, Radio, Streaming, TV, Zeitung |
| Werte | Ehrlichkeit, Leidenschaft, Mut, Offenheit, Respekt, Toleranz |
| Sonstige | ALLES + IMMER MEDIENANGEBOT, CH MEDIA ÜBERRASCHT (6 Varianten), Kamera, NÄHER DRAN BESSER KENNEN, Streaming, TEAM |
