# ZUME.studio Website – Claude Projekt-Dokumentation

## Projekt-Übersicht

| Info | Wert |
|------|------|
| **Domain** | zume.studio |
| **Registrar** | Porkbun (~18€/Jahr) |
| **Hosting** | GitHub Pages |
| **Repository** | https://github.com/ucetin75/zume-studio |
| **Lokaler Pfad** | `/Users/ugurcetin/Documents/xCode_Projekte/zume-studio/` |

---

## Dateistruktur

```
zume-studio/
├── index.html              # Haupt-Website (Single-Page App – ALLES hier!)
├── privacy.html            # Separate Privacy-Seite (Legacy/Backup)
├── CNAME                   # Domain-Konfiguration: zume.studio
├── CLAUDE_PROJECT.md       # Diese Dokumentation
└── Bilder_und _andere_Assets_für_Website/
    ├── Icons/
    │   ├── ZUME_AppIcon-iOS-Default-1024x1024@1x.png
    │   ├── PARANOID_App_Icon-iOS-Default-1024x1024@1x.png
    │   ├── CRYPTOR-iOS-Default-1024x1024@1x.png
    │   ├── Focus-On-iOS-Default-1024x1024@1x.png
    │   └── 3DME_icon.png                          # ⚠️ Landscape-Format!
    ├── ZUME_Studio_LOGO/
    │   └── ZUME_Studio_LOGO.003.png
    ├── Download_on_App_Store/
    │   ├── Black_lockup/SVG/Download_on_the_App_Store_Badge_DE_RGB_blk_092917.svg
    │   └── White_lockup/SVG/Download_on_the_App_Store_Badge_DE_RGB_wht_092917.svg
    └── Sceenshots_f_Webseite/
        ├── ZUME_Screenshots/     (5 Screenshots)
        ├── PARANOID_Screenshots/ (3 Screenshots)
        ├── CRYPTOR_Screenshots/  (3 Screenshots)
        └── 3DME_Screenshots/     (4 Screenshots, TV-Format 400x225px)
```

**⚠️ ACHTUNG:** Der Ordnername hat ein Leerzeichen: `Bilder_und _andere_Assets_für_Website/`

---

## Website-Architektur

### Single-Page App

Die Website ist eine **Single-Page App** – alle Inhalte sind in `index.html`:
- CSS (inline im `<style>` Tag)
- HTML (alle Panels)
- JavaScript (inline im `<script>` Tag)

### Navigation

- **Sidebar links:** App-Icons zur Navigation zwischen Apps
- **Topbar rechts:** Privacy + Imprint Buttons
- **Hash-Navigation:** Direktlinks wie `#zume`, `#privacy-zume` funktionieren

### Panel-IDs

| Panel ID | Inhalt | Beschreibung |
|----------|--------|--------------|
| `welcome` | Startseite | Wird angezeigt wenn kein Hash |
| `zume` | ZUME App | ✅ Live im App Store |
| `paranoid` | PARANOID App | 🎭 Coming Soon |
| `cryptor` | CRYPTOR App | ₿ Coming Soon |
| `focus` | FOCUS-ON App | 🎧 In Development |
| `3dme` | 3DME App | ✅ Live im App Store |
| `privacy` | Privacy Policy | Mit App-Tabs + Sprach-Umschalter |
| `imprint` | Impressum | Mit Sprach-Umschalter |

---

## Design-Spezifikationen

### CSS Variablen (Farben)

```css
:root {
    --bg-dark: #000000;
    --bg-sidebar: #0a0a0a;
    --text-primary: #ffffff;
    --text-secondary: rgba(255, 255, 255, 0.6);
    --border-color: rgba(255, 255, 255, 0.1);
}
```

### App-Akzentfarben

| App | Farbe | CSS Variable |
|-----|-------|--------------|
| ZUME | Türkis | `#00d4aa` |
| PARANOID | Rot | `#e63946` |
| CRYPTOR | Orange/Gold | `#f7931a` |
| FOCUS-ON | Türkis | `#00d4aa` |
| 3DME | Blau | `#4a90d9` |

### Typografie

**Body-Text:**
```css
font-family: -apple-system, BlinkMacSystemFont, 'SF Pro Display', 'Segoe UI', Roboto, sans-serif;
```

**Überschriften (H1):**
```css
font-family: "Phosphate", "Impact", "Arial Black", sans-serif;
font-weight: 400;
letter-spacing: 2px;
text-transform: uppercase;
```

### Größen-Referenz

| Element | Größe |
|---------|-------|
| Sidebar-Breite | 140px |
| App-Icons (Sidebar) | 80×80px |
| App-Icons (Sidebar) border-radius | 18px |
| App-Icons (Header) | 120×120px |
| App-Icons (Header) border-radius | 28px |
| Logo | 110px breit |
| 3DME Icon (wide-icon) | height: 80px, max-width: 120px |
| iOS Screenshots | 220×440px, border-radius 20px |
| tvOS Screenshots | 400×225px, border-radius 12px |
| App Store Badge | height: 50px |

### 3DME Sonderbehandlung

Das 3DME-Icon ist im Landscape-Format und braucht spezielle CSS-Klassen:

```css
/* Sidebar */
.app-nav-item.wide-icon .app-icon {
    width: auto;
    height: 80px;
    max-width: 120px;
    border-radius: 14px;
}

/* Header */
.app-header-icon.wide {
    width: auto;
    height: 100px;
    max-width: 180px;
    border-radius: 20px;
}
```

---

## Apps & App Store Links

| App | Bundle ID | Apple ID | App Store Link | Status |
|-----|-----------|----------|----------------|--------|
| ZUME | Cetin.ZUME-pro | 6758212967 | https://apps.apple.com/app/id6758212967 | ✅ Live |
| 3DME | – | 6760424460 | https://apps.apple.com/app/id6760424460 | ✅ Live |
| PARANOID | – | – | – | 🎭 Coming Soon |
| CRYPTOR | – | – | – | ₿ Coming Soon |
| FOCUS-ON | – | – | – | 🎧 In Development |

---

## Hash-Navigation (Direktlinks)

Die Website unterstützt Hash-Navigation für Direktlinks:

| URL | Zeigt |
|-----|-------|
| `https://zume.studio` | Welcome → dann ZUME |
| `https://zume.studio/#zume` | ZUME App-Seite |
| `https://zume.studio/#3dme` | 3DME App-Seite |
| `https://zume.studio/#privacy` | Privacy → "All Apps" Tab |
| `https://zume.studio/#privacy-zume` | Privacy → ZUME Tab |
| `https://zume.studio/#privacy-3dme` | Privacy → 3DME Tab |
| `https://zume.studio/#imprint` | Impressum |

**Für App Store Connect:**
- Support-URL: `https://zume.studio/#zume`
- Privacy Policy URL: `https://zume.studio/#privacy-zume`

---

## Privacy Policy Struktur

### App-Tabs
- All Apps (`general`) – Allgemeine Datenschutzrichtlinie
- ZUME (`zume`) – Spezifisch für ZUME
- PARANOID (`paranoid`)
- CRYPTOR (`cryptor`)
- 3DME (`3dme`)

### Sprachen
- 🇬🇧 Englisch (default)
- 🇩🇪 Deutsch

### Wichtiger ZUME-Abschnitt: TrueDepth API

Dieser Abschnitt wurde für Apple App Review hinzugefügt:

```
📱 Face Detection & TrueDepth API

ZUME nutzt die TrueDepth-Kamera und Apples Vision/ARKit Frameworks für:
- Emotion Coach: Gesichtsausdrücke für Stimmungsanalyse
- Celebrity Match: Gesichtsvergleich mit lokalem Core ML Model
- Mirror Mode: Echtzeit-Gesichtserkennung

Datenschutz-Hinweise:
✅ Alle Daten werden nur in Echtzeit verarbeitet
✅ Keine Speicherung (weder lokal noch Cloud)
✅ Keine Übertragung (kein Server-Backend)
✅ Keine Weitergabe an Dritte
✅ Frame für Frame analysiert und sofort verworfen
```

---

## Impressum / Kontakt

```
Ugur Cetin
Bostonring 41/4
71686 Remseck am Neckar
Deutschland

E-Mail: ucetin.mail@icloud.com
```

---

## Deployment

### Änderungen hochladen

```bash
cd /Users/ugurcetin/Documents/xCode_Projekte/zume-studio
git add .
git commit -m "Beschreibung der Änderung"
git push
```

GitHub Pages ist aktiviert → Änderungen sind nach ~1-2 Minuten live.

### GitHub Pages Einstellungen
- Settings → Pages
- Source: main branch
- Folder: / (root)
- Custom domain: zume.studio
- Enforce HTTPS: ✅

---

## Wichtige Hinweise für Claude

### Do's ✅
1. **Alles in einer Datei:** CSS, HTML, JS sind alle in `index.html`
2. **3DME Icon:** Immer `wide-icon` Klasse verwenden
3. **Privacy-Tabs:** Bei Änderungen BEIDE Sprachen (EN + DE) aktualisieren
4. **App Store Badges:** Offizielles Apple SVG aus `Black_lockup/SVG/` verwenden
5. **Nach Änderungen:** Git commit + push nicht vergessen

### Don'ts ❌
1. **Nicht vergessen:** Ordnername hat Leerzeichen: `Bilder_und _andere_Assets_für_Website/`
2. **Nicht verwechseln:** `privacy.html` ist Legacy – Hauptinhalt ist in `index.html`
3. **Nicht ändern:** CNAME Datei (enthält nur `zume.studio`)

### JavaScript-Struktur

Die wichtigsten Funktionen in `index.html`:

```javascript
// Panel-Navigation
function showPanel(panelId) { ... }

// Hash-Navigation
function handleHashNavigation() { ... }

// Privacy Tab-Wechsel
function updatePrivacyContent() { ... }

// Variablen
let currentLang = 'en';        // Aktuelle Sprache
let currentPrivacyApp = 'general';  // Aktiver Privacy-Tab
```

---

## Changelog

| Datum | Änderung |
|-------|----------|
| März 2026 | Website erstellt |
| März 2026 | TrueDepth API Abschnitt zu Privacy hinzugefügt |
| März 2026 | Hash-Navigation implementiert |
| März 2026 | ZUME im App Store live! 🎉 |
| März 2026 | 3DME im App Store live! |

---

## Offene Aufgaben / Ideen

- [ ] App Preview Videos einbinden
- [ ] Blog/News Sektion hinzufügen
- [ ] Mehrsprachige App-Beschreibungen (aktuell nur EN)
- [ ] Dark/Light Mode Toggle
- [ ] Analytics (datenschutzkonform, z.B. Plausible)
