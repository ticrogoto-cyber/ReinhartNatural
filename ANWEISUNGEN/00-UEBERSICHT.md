# ANWEISUNGEN — Was noch zu tun ist

Dieses Verzeichnis sammelt alles, was für den Launch von **reinhartnatural.de** noch
erledigt werden muss, aber beim Bau der Website nicht automatisch erledigt werden konnte
(fehlende Zugänge, erschöpfte Kontingente, Daten, die nur der Inhaber hat, oder Schritte,
die eine juristische Prüfung brauchen).

## Status der Website

**Fertig und im Repository:**

- ✅ Startseite (`index.html`) — Hero, Kollektion, Prinzipien, Charge, Manufaktur, FAQ, Chargen-Brief-CTA
- ✅ 4 Produktseiten (`produkte/`) — DMSO, Methylenblau, Magnesiumöl, Zeolith, jeweils mit Spezifikationstabelle, Stoffporträt, Grundpreis (PAngV), JSON-LD
- ✅ Design-System (`assets/css/style.css`) — Farben, Typografie, Komponenten
- ✅ Selbstgehostete Schriften (`assets/fonts/`) — DSGVO-konform, keine Google-Server
- ✅ SVG-Illustrationen — Siegel-Logo + 4 Braunglas-Flaschen als Inline-Sprite
- ✅ Impressum, Datenschutzerklärung, AGB (`rechtliches/`) — **mit Platzhaltern, siehe 07**
- ✅ `CNAME`, `.nojekyll`, `robots.txt`, `sitemap.xml`, `favicon.svg`
- ✅ Finales Siegel-Logo freigestellt: `assets/img/siegel*.png` (dunkle + helle
  Variante, transparent; Original in `siegel-original.png`) — überall eingebaut
- ✅ `.github/workflows/pages.yml` — deployt per Whitelist NUR die öffentlichen
  Dateien; dieser `ANWEISUNGEN/`-Ordner bleibt privat (Pages-Source muss auf
  „GitHub Actions" stehen, siehe 08)

**Offen — je eine Datei pro Thema:**

| Nr. | Datei | Thema | Priorität |
|---|---|---|---|
| 01 | `01-kaufpsychologie-briefing.md` | Forschungs-Brief Kaufpsychologie (Referenzdokument) | Lesen! |
| 02 | `02-produktfotografie.md` | Echte Produktfotos ersetzen die SVG-Illustrationen | Hoch |
| 03 | `03-higgsfield-videos.md` | Video-Generierung (Higgsfield-Kontingent war erschöpft) | Mittel |
| 04 | `04-shop-integration.md` | Echter Checkout statt Vorbestellung per E-Mail | Hoch |
| 05 | `05-chargen-brief-newsletter.md` | Newsletter-Anmeldung technisch anbinden | Mittel |
| 06 | `06-coa-sdb-dokumente.md` | Analysenzertifikate (COA) + Sicherheitsdatenblätter (SDB) als PDF | **Sehr hoch** |
| 07 | `07-rechtliches-fertigstellen.md` | Platzhalter füllen, Widerrufsbelehrung, anwaltliche Prüfung | **Vor Launch zwingend** |
| 08 | `08-domain-github-pages.md` | Nur noch: DNS beim Registrar + Search Console (Pages läuft) | Hoch |

## Empfohlene Reihenfolge

1. **08** — DNS beim Registrar setzen, falls noch offen (Pages-Deploy läuft bereits).
2. **07** — Platzhalter in den Rechtsseiten füllen; ohne vollständiges Impressum drohen Abmahnungen.
3. **06** — COA-PDFs beim Labor beauftragen; das ist laut Recherche der Kaufauslöser Nr. 1 dieser Nische.
4. **02** — Produktfotografie beauftragen oder selbst machen.
5. **04** — Shop-System entscheiden und anbinden.
6. **05** — Newsletter-Dienst anbinden.
7. **03** — Videos generieren, sobald Higgsfield-Kontingent wieder verfügbar.

## Grundregel für ALLE Inhalte (auch künftige!)

Die Produkte werden als **Laborchemikalien/Rohstoffe** verkauft. Deshalb darf **nirgends**
(Website, Newsletter, Social Media, Verpackung, Bewertungen) stehen:

- Krankheitsnamen in Produktnähe, Heil-/Linderungs-/Wirkversprechen
- Dosierungen, Einnahme- oder Anwendungsempfehlungen („Tropfen morgens…")
- Wörter wie „entgiftet", „heilt", „wirkt gegen", „Alternative zu [Medikament]"
- Symbolbilder mit Körperbezug (Gelenke, Gehirn), Kategorienamen wie „Detox"
- Kundenbewertungen mit Heilberichten (müssen moderiert/gekürzt werden)

Hintergrund und Details: `01-kaufpsychologie-briefing.md`, Abschnitt 5.
