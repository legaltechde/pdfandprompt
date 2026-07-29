# **PDF & Prompt**
### **OCR-Werkzeug für den Browser — lokal, privat, kostenlos**
**Texterkennung direkt im Browser. Kein Server. Keine Cloud. Keine Anmeldung.**

[![100% lokal](https://img.shields.io/badge/100%25%20lokal-keine%20Cloud-059669?style=flat-square)](.)
[![Datenschutz](https://img.shields.io/badge/Datenschutz-keine%20Daten%20verlassen%20dein%20Gerät-059669?style=flat-square)](.)
[![Plattform](https://img.shields.io/badge/Plattform-Desktop%20%7C%20Mobile-4F46E5?style=flat-square)](.)
[![Lizenz](https://img.shields.io/badge/Lizenz-MIT-6B7280?style=flat-square)](.)

---
---

## **📋 Inhaltsverzeichnis**
- [Was ist PDF & Prompt?](#-was-ist-pdf--prompt)
- [Was PDF & Prompt kann](#-was-pdf--prompt-kann)
- [Was PDF & Prompt nicht kann](#-was-pdf--prompt-nicht-kann)
- [100 % lokal — wie das funktioniert](#-100--lokal--wie-das-funktioniert)
- [Zusammenspiel mit KI](#-zusammenspiel-mit-ki)
- [Erste Schritte](#-erste-schritte)
- [Plattformen](#-plattformen)
  - [Desktop](#desktop-windows--macos--linux)
  - [Mobile](#mobile-ios--android)
- [Unterstützte Formate & Sprachen](#-unterstützte-formate--sprachen)
- [URL-Parameter](#-url-parameter)
- [Verwendete Bibliotheken](#-verwendete-bibliotheken)
- [Für wen ist PDF & Prompt?](#-für-wen-ist-pdf--prompt)
- [Lizenz & Nutzung](#-lizenz--nutzung)

---
---

## **💡 Was ist PDF & Prompt?**
**PDF & Prompt** ist eine **einzelne HTML-Datei**, die vollständige OCR-Texterkennung (Optical Character Recognition) direkt im Browser ausführt — **ohne Installation, ohne Server, ohne Internetverbindung nach dem ersten Laden**.

Du lädst ein Dokument hoch, der Browser erkennt den Text, und du bekommst seitenweise extrahierte Inhalte zurück. Diese kannst du direkt kopieren oder als strukturierten Prompt an eine KI-Anwendung übergeben.

> **Kernprinzip:** PDF & Prompt erkennt Text. Eine KI (deiner Wahl) verarbeitet ihn weiter.

---
---

## **✅ Was PDF & Prompt kann**

### **📄 Texterkennung**
- OCR von **PDF-Dateien**, **Bildern** (JPG, PNG, GIF) und **ZIP-Archiven** mit mehreren Dokumenten
- Seitenweise Erkennung mit **Parallelverarbeitung** für schnelle Ergebnisse
- Optionale **Bildverbesserung** (Kontrastverstärkung) vor der Erkennung
- Frei wählbarer **Seitenbereich** (z. B. nur Seiten 1, 3 und 5–7)
- Unterstützung von **36+ Sprachen** (Deutsch, Englisch, Arabisch, Japanisch, Chinesisch u. v. m.)
- Mehrsprachige Erkennung gleichzeitig möglich

### **📋 Text-Aktionen**
| Aktion | Beschreibung |
|--------|-------------|
| **OCR kopieren** | Vollständigen erkannten Text in die Zwischenablage |
| **Übersetzen** | Übersetzungsauftrag für eine KI vorbereiten (Zielsprache frei wählbar) |
| **Zusammenfassung** | Zusammenfassungsauftrag für eine KI erstellen |
| **Struktur** | Strukturierungsauftrag inkl. Inhaltsverzeichnis-Anforderung |
| **Frage stellen** | Kontextbasierte Frage (Cosinus-Ähnlichkeitssuche) als KI-Prompt |

### **🧭 Navigation**
- Seitenweise Navigation durch erkannte Seiten (Desktop-Leiste & mobile Navigationsleiste)
- Direkt zum Seitenbild oder zum erkannten Text springen
- Einzelne Seiten mit einem Klick in die Zwischenablage kopieren
- **Inhaltsverzeichnis** zeigt alle hochgeladenen Dateien mit Seitenbereichen

### **⚙️ Einstellungen (via URL-Parameter)**
- **Zeichen-Limit** für KI-Prompts konfigurierbar
- **Seitenauswahl** für gezielte Textextraktion
- **Farbschema**: Hell / Dunkel / System
- **Sprache** der Benutzeroberfläche

### **🌍 Mehrsprachige Oberfläche**
- Benutzeroberfläche in Deutsch, Englisch, Französisch, Spanisch
- Erweiterbar per eigener `lang/{code}.json`

### **🎨 Design & UX**
- Responsives Design für Desktop und Mobile
- Interaktiver **Ladebildschirm** mit animierten Fortschrittsanzeigen während der OCR
- Spotlight-**Hilfe-System** mit schrittweisen Erklärungen
- Vollständige Steuerung über URL-Hash-Parameter

---
---

## **❌ Was PDF & Prompt nicht kann**
Es ist wichtig zu verstehen, was PDF & Prompt **nicht** tut:

| Was du vielleicht erwartest | Realität |
|-----------------------------|----------|
| Text direkt übersetzen | ❌ PDF & Prompt erstellt nur den **Prompt** — du fügst ihn selbst in eine KI ein |
| Fragen automatisch beantworten | ❌ PDF & Prompt wählt relevante Textstellen aus — die Antwort gibt eine KI |
| Handschrift zuverlässig erkennen | ⚠️ Begrenzte Qualität — OCR ist für gedruckten Text optimiert |
| Scans mit sehr niedrigem Kontrast verarbeiten | ⚠️ Qualität abhängig von der Scan-Qualität |
| Tabellenstrukturen erhalten | ❌ Text wird als Fließtext extrahiert, keine Tabellenformatierung |
| Cloud-Speicherung oder Synchronisation | ❌ Bewusst nicht vorhanden — alles bleibt lokal |
| Ergebnisse automatisch speichern | ❌ Seite schließen = Daten weg (kein lokaler Speicher) |
| Sehr große Dokumente (100+ Seiten) schnell verarbeiten | ⚠️ Browser-OCR ist langsamer als Desktop-Software |
| Ausgeführten PDF-Code oder Formulare verarbeiten | ❌ Nur Bild-zu-Text, keine interaktiven Elemente |

---
---

## **🔒 100 % lokal — wie das funktioniert**
PDF & Prompt verwendet ausschließlich **clientseitige Technologien**:

```
Dein Browser
    │
    ├── Tesseract.js      → OCR-Engine (läuft im Browser, kein Server)
    ├── PDF.js            → PDF-Rendering (Seiten → Bilder)
    ├── PDF-Lib           → PDF-Zusammenführung mehrerer Dateien
    └── JSZip             → ZIP-Archive entpacken
```

**Was bedeutet das für dich?**
- 🟢 **Keine Daten verlassen deinen Computer** — weder das Dokument, noch der erkannte Text
- 🟢 **Keine Anmeldung, kein Konto, kein Tracking**
- 🟢 **Funktioniert offline** — nach dem ersten Laden der Seite (CDN-Ressourcen werden gecacht)
- 🟢 **Keine Nutzungslimits** — du kannst beliebig viele Dokumente verarbeiten
- 🟢 **DSGVO-konform by design** — es gibt schlicht nichts zu übertragen

> Die OCR-Sprachmodelle von Tesseract werden einmalig vom CDN geladen und vom Browser gecacht. Danach arbeitet alles offline.

---
---

## **🤝 Zusammenspiel mit KI**
PDF & Prompt ist kein KI-Tool — es ist das **Bindeglied** zwischen deinen Dokumenten und einer KI deiner Wahl.

### **Workflow**
```
┌─────────────────┐    ┌──────────────────┐    ┌─────────────────┐
│  Dein Dokument  │───▶│   PDF & Prompt   │───▶│   Deine KI      │
│  (PDF / Bild)   │    │  OCR + Prompt    │    │  (ChatGPT etc.) │
└─────────────────┘    └──────────────────┘    └─────────────────┘
                              │
                    Text wird erkannt &
                    Prompt wird kopiert
```

### **Schritt-für-Schritt**
1. **Dokument hochladen** → PDF & Prompt erkennt den Text seitenweise
2. **Aktion wählen** → z. B. „Übersetzen“, „Frage stellen“ oder „Zusammenfassung“
3. **Prompt kopieren** → PDF & Prompt erstellt einen optimierten Prompt mit dem erkannten Text
4. **KI öffnen** → ChatGPT, Claude, Gemini, Mistral oder eine lokale KI
5. **Einfügen & Senden** → Die KI beantwortet, übersetzt oder fasst zusammen

### **Warum dieser Ansatz?**
- Du wählst **selbst**, welche KI du nutzt
- Deine KI-API-Schlüssel bleiben bei dir
- Das Dokument gelangt **nie** zu einer externen KI — nur der (bereits erkannte) Text
- Lange Dokumente werden intelligent auf relevante Abschnitte reduziert (Cosinus-Ähnlichkeit)

---
---

## **🚀 Erste Schritte**

### **Option A — direkt öffnen**
Lade die `pdf-prompt.html` herunter und öffne sie in deinem Browser:

```bash
# Einfach per Doppelklick öffnen, oder:
open pdf-prompt.html      # macOS
start pdf-prompt.html     # Windows
xdg-open pdf-prompt.html  # Linux
```

> ⚠️ **Wichtig:** Die Datei muss zusammen mit dem `lang/`-Ordner liegen:
> ```
> pdf-prompt.html
> lang/
>   de.json
>   en.json   ← (optional, selbst erstellen)
> ```

### **Option B — lokaler Webserver (empfohlen für volle Funktion)**
```bash
# Python
python3 -m http.server 8080

# Node.js
npx serve .

# PHP
php -S localhost:8080
```
Dann `http://localhost:8080/pdf-prompt.html` im Browser öffnen.

### **Nutzung**
1. **Datei hochladen** — PDF, Bild oder ZIP per Klick oder Drag & Drop
2. **OCR-Konfiguration** aufklappen — Sprache und Einstellungen wählen
3. **OCR ausführen** — Ladebildschirm zeigt Fortschritt
4. **Text nutzen** — Seiten navigieren, kopieren, Prompts erstellen

---
---
---

## **📱 Plattformen**

### **Desktop (Windows / macOS / Linux)**
| Browser | Unterstützung |
|---------|--------------|
| Chrome / Chromium | ✅ Vollständig |
| Firefox | ✅ Vollständig |
| Safari (macOS 14+) | ✅ Vollständig |
| Edge | ✅ Vollständig |
| Opera | ✅ Vollständig |

**Desktop-Features:**
- Schwebendes Aktions-Panel rechts mit allen Werkzeugen
- Navigationsleiste unten mit Seitensprung und Kopier-Funktionen
- Tastenkürzel: `Esc` schließt das Hilfe-System

### **Mobile (iOS / Android)**
| Plattform | Browser | Unterstützung |
|-----------|---------|--------------|
| iOS 16+ | Safari | ✅ Vollständig |
| iOS 16+ | Chrome | ✅ Vollständig |
| Android 10+ | Chrome | ✅ Vollständig |
| Android 10+ | Firefox | ✅ Vollständig |
| Android 10+ | Samsung Internet | ✅ Vollständig |

**Mobile-Features:**
- Optimierte Touch-Steuerelemente (große Tipp-Ziele, iOS-Toggle-Switches)
- Schwebendes Aktionsmenü (+ Button) mit Vollbild-Menü
- Navigationsleiste am unteren Bildschirmrand
- Horizontales App-Kachel-Grid für alle Aktionen
- Einstellungen immer im oberen Bereich des Menüs sichtbar

> 📌 **Tipp für iOS/Android:** Seite zum Home-Bildschirm hinzufügen (Safari: Teilen → Zum Home-Bildschirm) für App-ähnliche Nutzung ohne Browser-Chrom.

---
---

## **📂 Unterstützte Formate & Sprachen**

### **Dateiformate**
| Format | Details |
|--------|---------|
| **PDF** | Alle PDF-Versionen, auch mehrseitig |
| **JPG / JPEG** | Fotos, Scans |
| **PNG** | Screenshots, Grafiken mit Text |
| **GIF** | Statische Bilder |
| **ZIP** | Archiv mit mehreren PDFs oder Bildern |

### **OCR-Sprachen (Auswahl)**
| Sprache | Code | Sprache | Code |
|---------|------|---------|------|
| Deutsch | `deu` | Englisch | `eng` |
| Französisch | `fra` | Spanisch | `spa` |
| Italienisch | `ita` | Portugiesisch | `por` |
| Russisch | `rus` | Ukrainisch | `ukr` |
| Chinesisch (vereinfacht) | `chi_sim` | Japanisch | `jpn` |
| Koreanisch | `kor` | Arabisch | `ara` |
| Hebräisch | `heb` | Türkisch | `tur` |
| Polnisch | `pol` | Tschechisch | `ces` |
| Niederländisch | `nld` | Schwedisch | `swe` |

> Mehrere Sprachen gleichzeitig möglich, z. B. `deu+eng` für gemischte Dokumente.
> **Vollständige Liste:** 36 Sprachen von Afar bis Vietnamesisch.

---
---

## **🔗 URL-Parameter**
PDF & Prompt speichert Einstellungen im URL-Hash — keine Cookies, kein LocalStorage.

```
pdf-prompt.html#colorTheme=dark&lang=de&maxCharacters=50000&ocrSuccessAtLeastOnce=true
```

| Parameter | Werte | Standard | Beschreibung |
|-----------|-------|---------|--------------|
| `colorTheme` | `light` `dark` `system` | `system` | Farbschema |
| `lang` | `de` `en` `fr` `es` … | Browser-Sprache | UI-Sprache |
| `maxCharacters` | Zahl | `127000` | Max. Zeichen für KI-Prompts |
| `pagesAtOnce` | Zahl | `10` | Seiten parallel verarbeiten |
| `ocrSuccessAtLeastOnce` | `true` `false` | `false` | Erste OCR bereits durchgeführt |

---
---

## **📦 Verwendete Bibliotheken**
PDF & Prompt ist eine einzelne HTML-Datei ohne Build-System. Alle Abhängigkeiten werden über CDN geladen:

| Bibliothek | Version | Zweck | CDN |
|------------|---------|-------|-----|
| **Tesseract.js** | 6.0.0 | OCR-Engine | cdnjs.cloudflare.com |
| **PDF.js** | 2.10.377 | PDF → Bild-Rendering | cdnjs.cloudflare.com |
| **PDF-Lib** | 1.17.1 | PDF-Dateien zusammenführen | cdnjs.cloudflare.com |
| **JSZip** | 3.10.1 | ZIP-Archive entpacken | cdnjs.cloudflare.com |

Alle vier Bibliotheken sind quelloffen (MIT / Apache 2.0). PDF & Prompt selbst enthält keinen proprietären Code.

> **Offline-Betrieb:** Nach dem ersten Laden werden die CDN-Ressourcen vom Browser gecacht. Bei erneutem Öffnen (auch ohne Internet) funktioniert die App vollständig — solange der Browser-Cache nicht geleert wurde.

---
---

## **👥 Für wen ist PDF & Prompt?**
PDF & Prompt wurde für alle gebaut — ohne Schranken:

- 🎓 **Studierende** — Bücher, Skripte und Vorlesungsfolien als Text extrahieren
- 📰 **Journalisten** — Dokumente, Berichte und Akten schnell durchsuchbar machen
- ⚖️ **Juristen** — Verträge und Schriftsätze für KI-Analyse aufbereiten
- 🏥 **Medizin** — Befunde und Literatur in Text umwandeln
- 🏢 **Unternehmen** — Rechnungen, Formulare und Altbestände digitalisieren
- 🏠 **Privatpersonen** — alte Briefe, Rezepte oder Fotos mit Text erfassen
- 👩‍💻 **Entwickler** — als Basis für eigene OCR-Workflows nutzen

---
---

## **📜 Lizenz & Nutzung**
```
MIT License — mach damit, was du willst.
```

**Das bedeutet konkret:**
- ✅ Kostenlos für private und kommerzielle Nutzung
- ✅ Verändern, anpassen, in eigene Projekte einbauen
- ✅ Weitergeben und verteilen
- ✅ Keine Anmeldung, kein Konto, keine Gebühren — jetzt nicht, nie
- ✅ Kein Opt-in, kein Opt-out — es werden schlicht keine Daten gesammelt

> **PDF & Prompt ist freie Software.** Lad sie herunter, öffne sie im Browser, fang an. Fertig.

---
---
<div align="center">
Gebaut mit ♥ für lokale, private Textverarbeitung

*„Dein Dokument gehört dir. Dein Browser verarbeitet es. Niemand sonst sieht es.“*
</div>