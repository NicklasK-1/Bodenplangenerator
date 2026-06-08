# Grundriss-Editor

Ein vollständig eigenständiger, browserbasierter Grundriss-Editor für taktische Karten – entwickelt für **Shadowrun 6th Edition**, nutzbar für jedes Tabletop-System. Keine Installation – einfach die HTML-Datei öffnen.

> **Lizenz:** MIT © 2025 Nicklas  
> Abhängigkeit: [JSZip 3.10.1](https://stuk.github.io/jszip/) (MIT)

---

## Schnellstart

1. `grundriss.html` im Browser öffnen (Chrome, Firefox, Edge – aktuell)
2. Werkzeug aus der linken Leiste wählen oder Tastenkürzel benutzen
3. Zeichnen, anpassen, speichern

---

## Werkzeuge & Tastenkürzel

| Taste | Werkzeug | Beschreibung |
|-------|----------|--------------|
| **V** | Auswählen | Elemente klicken, verschieben, drehen, Eigenschaften bearbeiten |
| **W** | Wand | Polylinien beliebigen Winkels; Shift = 15°-Rastung; Enter / Doppelklick / Rechtsklick beendet; Startpunkt treffen schließt Raum |
| **R** | Raum | Rechteck aufziehen → erzeugt vier Wände |
| **T** | Tür | Auf eine Wand klicken; Breite & Schlag im Panel anpassbar |
| **F** | Fenster | Auf eine Wand klicken |
| **G** | Garagentor | Auf eine Wand klicken; Paneel-Unterteilung skaliert mit Breite |
| **S** | Säule | Einzelklick platziert; eckig oder rund, Breite/Tiefe einstellbar |
| **O** | Objekt | Graues Symbol mit schwarzem X-Kreuz; frei drehbar; Farbe wählbar |
| **P** | Treppe | Lauflänge, Treppenbreite, Stufenanzahl; Richtungspfeil; drehbar |
| **L** | Fahrstuhl | Box mit Diagonalkreuz + Türmarkierung; drehbar |
| **B** | Fußboden | Beliebiges Polygon (Klicken = Eckpunkte setzen; Enter / Doppelklick schließt); Farbe wählbar |
| **X** | Text | Klick platziert Inline-Eingabe; Doppelklick auf Text öffnet Editor; Schriftgröße, Farbe, Fettdruck, Drehung |
| **I** | SR6-Symbole | Öffnet den SR6-Kartensymbol-Browser |
| **A** | Eigene Assets | Öffnet den eigenen Asset-Browser |
| **E** | Löschen | Element anklicken |
| **Entf** | Löschen | Ausgewähltes Element entfernen |

### Navigation

| Eingabe | Aktion |
|---------|--------|
| Mausrad | Zoom (zentriert auf Cursor) |
| Mittlere Maustaste oder Leertaste + Ziehen | Karte verschieben |
| **Ctrl+Z** | Rückgängig |
| **Ctrl+Y** / **Ctrl+Shift+Z** | Wiederherstellen |
| **Ctrl+C** | Kopieren |
| **Ctrl+V** | Einfügen (jedes weitere Einfügen versetzt um einen Rasterabstand) |
| **Ctrl+D** | Duplizieren (Kopieren + sofort Einfügen) |
| **Esc** | Abbrechen / Auswahl aufheben |

---

## Ebenen-System

Der Editor unterstützt beliebig viele Ebenen (Stockwerke und Keller).

- **+ Ebene** — neue Ebene oberhalb der aktiven
- **+ Keller** — neue Ebene unterhalb aller bestehenden (UG 1, UG 2 …); im Panel als `↓B` markiert
- **Doppelklick** auf Ebenennamen → umbenennen
- **Ebene darunter zeigen** — alle tiefer liegenden Ebenen werden halbtransparent eingeblendet, mit abnehmender Sichtbarkeit je weiter unten (direkt darunter am deutlichsten)
- **Ebene darüber zeigen** — die nächsthöhere Ebene wird als schwachen Ghost angezeigt
- **Fußboden als Sichtsperre** — Fußböden der aktiven und dazwischen liegender Ebenen verdecken, was darunter liegt; korrekte Verdeckung auch im PNG-Export

---

## Fußböden (Polygon-System)

Fußböden sind vollständige Polygone – keine Rechtecke.

1. Werkzeug **B** wählen
2. Eckpunkte durch Klicken setzen (beliebige Winkel und Anzahl)
3. Startpunkt erneut anklicken **oder** Enter / Doppelklick → Polygon schließen
4. Im Auswählen-Modus:
   - Kleine bernsteinfarbene Punkte zeigen alle Eckpunkte aller Böden
   - Eckpunkt direkt anklicken und ziehen → verformen
   - Fläche anklicken und ziehen → verschieben
5. Farbe im Panel frei wählbar

---

## Öffnungen (Türen, Fenster, Garagentore)

- Auf eine Wand klicken → Öffnung wird mittig platziert und in die Wand eingeschnitten
- Im Auswählen-Modus entlang der Wand verschieben
- Eigenschaften: Breite, Typ umschalten (Tür ↔ Fenster ↔ Tor), Tür spiegeln

---

## Sperren

Ausgewähltes Element → Toggle **🔓 Gesperrt** im Panel:

- Gesperrte Elemente können **nicht verschoben, verformt, rotiert oder gelöscht** werden
- Sind weiterhin **auswählbar** (um die Sperre aufzuheben)
- Werden mit einem kleinen **🔒-Symbol** in der Karte markiert
- Gilt für alle Elementtypen: Wände, Böden, Objekte, Texte, Symbole …

---

## SR6-Symbole & Eigene Assets

### SR6-Symbole (Taste I)

Lädt die offizielle SR6-Kartensymbol-ZIP ein. Einmalig laden, dann steht die komplette Bibliothek für die gesamte Session zur Verfügung:

- Kameras (sichtbar / verborgen / Sichtbereich)
- Magische Barrieren, Magschlösser (biometrisch, DNA, Karte, RFID, Tastatur)
- NSC, Nummerierungen, Scanner, Schlösser, Verborgene Systeme, Sonstiges

### Eigene Assets (Taste A)

Lädt beliebige ZIP-Dateien mit eigenen Bildsymbolen:

- **Formate:** PNG, JPEG, SVG
- **Struktur:** Unterordner werden automatisch als Kategorien übernommen
- Mehrere ZIPs gleichzeitig ladbar; jede ZIP erscheint als eigene Gruppe mit Entfernen-Button
- Suche filtert über alle geladenen Quellen

**Beide Browser:** Symbol anklicken → Browser schließt sich → Klick auf Karte platziert das Symbol. Größe, Drehung und Position nachträglich mit dem Auswählen-Werkzeug anpassen.

---

## Raster & Snapping

| Einstellung | Beschreibung |
|-------------|--------------|
| Raster (m) | Rastergröße in Metern (Standard: 0,5 m) |
| Am Raster fangen | Punkte rasten auf Rasterkreuzungen |
| An Endpunkten fangen | Fängt an bestehenden Wand-Endpunkten (inkl. Unterlage-Ebene) |
| **Shift** während Wand/Drehen | Winkel rastet auf 15°-Schritte |

---

## Bemaßung & Maßstab

- **Bemaßung anzeigen** — Wandlängen werden als blaue Labels angezeigt
- **Maßstabsleiste** — immer unten links; 10 m mit 1-m-Unterteilung, wechselnde Segmentfüllung; skaliert bei kleinem Viewport automatisch auf 5 / 2 / 1 m
- Alle Maße in Metern; 1 Rastereinheit = 0,5 m (Standard)

---

## PNG-Export

**Exportiert immer die aktive Ebene** – inklusive aller aktivierten Unterlage-Ebenen mit Fußboden-Verdeckung.

| Option | Beschreibung |
|--------|--------------|
| Auflösung (px/m) | Standard 120 px/m; höher = schärfer |
| Hintergrund | Farbe wählbar |
| Transparent | Hintergrund wird weggelassen |
| Raster im PNG | Gitterlinien mitexportieren |
| Bemaßung im PNG | Wandmaße mitexportieren |

Dateiname enthält automatisch den Ebenennamen.

---

## Projekt speichern & laden

- **Speichern** → `grundriss.json` herunterladen
- **Laden** → gespeicherte JSON-Datei öffnen; ältere Projekte (ohne Ebenen oder Polygon-Böden) werden automatisch migriert
- **Hinweis:** SR6-Symbole und eigene Assets werden **nicht** in der JSON gespeichert – nur der Pfad innerhalb der ZIP. Beim Laden eines Projekts die jeweiligen ZIPs erneut laden, damit Symbole erscheinen.

---

## Tipps

- **Mehrere Räume anlegen:** Raum-Werkzeug (R) für schnelle Rechtecke; Wand-Werkzeug (W) für L-Formen, Schrägwände und Sonderformen
- **Ebenen ausrichten:** „Ebene darunter zeigen" einschalten – Endpunkte der Unterlage-Ebene fangen ebenfalls ein
- **Referenzelemente fixieren:** Grundriss-Ebene zeichnen, alle Wände sperren → darüber ungehindert Möbel, Symbole und Böden platzieren
- **Großer Grundriss:** Raum-Werkzeug erstellt vier Wände auf einmal; danach mit dem Wand-Werkzeug Innenwände ergänzen
- **Komplexe Böden:** Polygon-Fußboden mit vielen Punkten zeichnen um L-förmige Räume, Treppenhäuser oder Innenhöfe korrekt abzubilden
