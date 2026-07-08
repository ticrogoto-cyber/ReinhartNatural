# 10 — Master-Prompt: Higgsfield-Sprint (Bild + Video + Einbau)

> **Verwendung:** Sobald Higgsfield-Credits verfügbar sind, den kompletten
> Text unterhalb der Linie als Auftrag an Claude geben (Copy & Paste genügt —
> oder einfach schreiben: „Führe ANWEISUNGEN/10 aus"). Der Prompt ist
> selbsterklärend für eine frische Session mit Zugriff auf dieses Repo.

---

## AUFTRAG AN CLAUDE: Higgsfield-Sprint für reinhartnatural.de

Du arbeitest im Repo `ticrogoto-cyber/ReinhartNatural`. Entwickle auf dem
Branch `claude/reinhart-natural-website-1gz0rn`; Release = Merge nach `main`
(Freigabe dafür beim Inhaber einholen, falls nicht ausdrücklich erteilt).
Der Pages-Workflow deployt per Whitelist und versioniert CSS/JS automatisch.
Higgsfield ist als MCP-Server verbunden.

### Schritt 0 — Vorprüfung

1. `balance` bzw. `show_plans_and_credits` aufrufen: Credits vorhanden?
   Wenn knapp: Prioritätsreihenfolge unten beachten.
2. `models_explore(action:'recommend')` mit dem jeweiligen Ziel aufrufen,
   bevor du ein `generate_*`-Tool wählst.
3. Lies vorab: `ANWEISUNGEN/02-produktfotografie.md` (Bild-Specs) und
   `ANWEISUNGEN/03-higgsfield-videos.md` (Video-Specs, Logo-Endcards).

### Marken-Konstanten (verbindlich)

- **Farben:** Porzellan `#fbfbf9` · Nachtblau `#20242f` · Tiefnacht `#14161d`
  · Tinte `#17191c` · Koralle `#c98a76` (DMSO) · Ozeanblau `#517495`
  (Methylenblau) · Moosgrün `#77906f` (Magnesiumöl) · Lavendel-Grau `#9d97ad`
  (Zeolith) · Messing `#b2a075` · Siegel-Magenta `#a84661`
- **Logo:** `assets/img/siegel.png` (dunkel, transparent, 1600 px),
  `assets/img/siegel-hell-512.png` (hell, für dunkle Flächen) — beide im
  Repo, aber bewusst nicht deployt.
- **Look:** Editorial-Apotheke; Braunglas, Cremepapier-Etiketten,
  mattschwarze Verschlüsse (Pipette bei DMSO/Methylenblau, Feinzerstäuber
  bei Magnesiumöl, Schraubdeckel beim Zeolith-Glas); weiches Nordlicht,
  dezentes Film-Grain, ruhig und präzise.

### Rechtliche Leitplanke (gilt für JEDES Asset)

Kein Asset darf Anwendung am Menschen zeigen oder nahelegen: kein Auftragen
auf Haut, kein Einnehmen, keine Tropfen in Trinkgläser, keine Körperteile
mit Produktkontakt, keine Krankheits- oder Wirk-Symbolik (Gelenke, Gehirn
etc.). Erlaubt: Objekt, Labor, Handwerk, Material, Hände in Nitrilhandschuhen
bei der Abfüllung (ohne Gesichter). Begründung: HWG-Positionierung als
Laborchemikalien, siehe `01-kaufpsychologie-briefing.md` Abschnitt 5.
Alt-Texte der neuen Bilder ebenfalls HWG-neutral formulieren.

### Etappe 1 — Bilder (`generate_image`)

**1.1 Produkt-Zwischenbilder** (ersetzen die SVG-Illustrationen, bis echte
Fotos existieren) — je Produkt ein Frontal-Freisteller:

> Editorial product photography, single amber glass apothecary bottle with
> cream paper label, matte black [dropper cap / fine-mist spray head / screw
> cap jar], soft north-light studio, seamless porcelain-white background
> (#fbfbf9), subtle film grain, style of Aesop and Le Labo campaigns,
> centered composition, no text on label

- **Ohne Text im Bild generieren** (KI-Etikettentext ist fehlerhaft) — das
  echte Etikett bleibt der SVG-/Foto-Ebene vorbehalten; alternativ Label
  aus `siegel.png` + Typo lokal mit Pillow montieren.
- Gebinde: DMSO 250 ml Pipette · Methylenblau 100 ml Pipette (kleiner!) ·
  Magnesiumöl 250 ml Feinzerstäuber · Zeolith 250 g Weithals-Schraubglas.
- Nachbearbeitung: `upscale_image` auf 2K; falls Fond unruhig:
  `remove_background` + lokal auf Porzellan komponieren.

**1.2 Hero-Ensemble:** alle vier Gebinde als gestaffelte Gruppe, gleiche
Lichtführung, Querformat — ersetzt das SVG-Regal im Hero (oder dient als
Poster für Video 2.1).

**1.3 Manufaktur-Szene:** Hände in schwarzen Nitrilhandschuhen füllen
Braunglas über Messingwaage/Trichter, dokumentarisch, keine Gesichter —
für die Manufaktur-Sektion.

**1.4 og:image-Produktmotive:** aus 1.1 je Produkt eine 1200×630-Ableitung
(Flasche rechts, Porzellan links) — ersetzt das Interim-`og-standard.png`
auf den Produktseiten; Startseite bekommt das Ensemble aus 1.2.

**Ablage:** `assets/img/` nach Namensschema aus Datei 02; Ableitungen
AVIF + WebP + JPEG lokal erzeugen (Pillow/avifenc), `<picture>`-Einbau.

### Etappe 2 — Videos (`generate_video`)

Prompts, Längen und Technik stehen fertig in **Datei 03**:

- **2.1 Hero-Loop** (höchste Prio): 6–10 s Makro-Loop (Pipette, Tropfen,
  Staubpartikel im Lichtstrahl), nahtlos, stumm; MP4+WebM < 4 MB,
  Poster-Frame via `video_render_frame`; Einbau mit
  `prefers-reduced-motion`-Fallback.
- **2.2 Abfüll-Ritual:** 15–20 s dokumentarisch; 9:16-Ableitung via `reframe`
  für Social (nicht ins Repo).
- **2.3 Produkt-Miniaturen:** 4 × 5 s Drehteller vor Substanzfarb-Fond
  (Koralle/Ozean/Moos/Lavendel) — optional, nur bei ausreichend Credits.
- **Endcard/Wasserzeichen:** Siegel-Anweisungen in Datei 03, Abschnitt
  „Logo-Assets für Videos".

### Etappe 3 — Einbau

1. Produktseiten: `.product-stage`-SVG → `<picture>` mit den 1.1-Bildern;
   Hinweis „Illustration. Produktfotografie folgt…" entfernen.
2. Startseite: SVG-Flaschenregal → Ensemble-Bild oder Hero-Video (2.1).
3. og:image-Tags auf die neuen Motive umstellen (Interim `og-standard.png`
   bleibt Fallback der Rechtsseiten); JSON-LD der Produktseiten bekommt
   `"image"`-Property (Pflichtfeld für Google Product Rich Results).
4. SVG-Symbole im Sprite als Fallback BEHALTEN.
5. Startseiten-Gesamtgewicht < 5 MB halten; Videos nach `assets/video/`,
   Whitelist im Pages-Workflow um `assets/video` prüfen (assets/ wird
   komplett kopiert — nur Größe im Blick behalten).

### Etappe 4 — QA + Release

1. Playwright-Screenshots: Desktop 1440 px + Mobil 390 px (Chromium:
   `/opt/pw-browsers/chromium`, `NODE_PATH=/opt/node22/lib/node_modules`).
2. QA-Durchlauf wie etabliert: Linkintegrität, HWG-Sweep über ALLE neuen
   Texte/Alt-Texte, Konsolenfehler, Seitengewicht.
3. Commit auf den Arbeitsbranch → Freigabe → Merge nach `main` →
   Actions-Lauf grün abwarten (Cache-Busting erledigt den Rest).

### Prioritätsreihenfolge bei knappen Credits

1. **1.1** Produkt-Zwischenbilder (größter visueller Sprung)
2. **1.4** og:image-Motive (Social-Vorschau)
3. **2.1** Hero-Loop
4. **1.2 / 1.3** Ensemble + Manufaktur
5. **2.2 / 2.3** Ritual + Miniaturen

### Abnahmekriterien

- Keine SVG-Illustration mehr als primäres Produktbild sichtbar
- Kein Asset verletzt die HWG-Leitplanke
- Startseite < 5 MB, keine Konsolenfehler, Mobil sauber
- og:image + JSON-LD-image auf allen Produktseiten produktspezifisch
