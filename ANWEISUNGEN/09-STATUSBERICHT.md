# 09 — Statusbericht: Was noch zu erledigen ist

**Stand:** 7. Juli 2026, nach dem Siegel-/Favicon-Release ·
**Basis:** Vollständigkeits-Audit über das gesamte Repository (28 Befunde, konsolidiert)

## Wo wir stehen

Die Website ist fertig gebaut und wird automatisch deployt: Arbeitsbranch →
Merge nach `main` → GitHub-Actions-Workflow liefert per **Whitelist** nur die
öffentlichen Dateien aus (dieser ANWEISUNGEN-Ordner bleibt privat) und
versioniert CSS/JS gegen Cache-Versatz. Design (Substanzfarben, Nachtblau,
Jost/EB Garamond/Cormorant), echtes Siegel-Logo inkl. Favicon und Touch-Icon,
vier Produktseiten, drei Rechtsseiten-Gerüste, Feinzerstäuber-SVG — alles live.

---

## A · LAUNCH-BLOCKER — nur du kannst sie lösen

Die Seite ist bereits öffentlich. Damit gilt: **Punkt 1 ist der dringendste
der gesamten Liste.**

| # | Aufgabe | Wer | Details |
|---|---|---|---|
| 1 | **~29 Platzhalter in den Rechtsseiten füllen** — Impressum (12: Name, Anschrift, Telefon, E-Mail, Registergericht, HRB, USt-IdNr., Verantwortlicher), Datenschutz (6), AGB (7: Versandkosten, Zahlungsarten, Lieferzeit) | **Du** | Datei 07, Checkliste. Ohne vollständiges Impressum drohen Abmahnungen ab Tag 1 der Veröffentlichung. Schick mir die Daten — ich trage sie in Minuten ein. |
| 2 | **Widerrufsbelehrung: Volltext + Muster-Widerrufsformular** einfügen (IHK-/Händlerbund-Generator), inkl. Hinweis § 312g Abs. 2 Nr. 3 BGB (versiegelte Waren) | **Du** (Generator) → **Claude** (Einbau) | Die Seite ist bewusst nur ein Gerüst — Volltext-Generierung war durch Sicherheitsfilter blockiert. |
| 3 | **Anwaltliche Prüfung** vor Verkaufsstart: Rechtsseiten, Produkttexte (HWG-Grenzfälle wie Stoffgeschichte), Etiketten (CLP), später Bewertungskonzept | **Du / Anwalt** | Alternativ Schutzpaket (Händlerbund, IT-Recht Kanzlei, ~10–50 €/Monat inkl. Abmahn-Absicherung). |
| 4 | **DNS-Status bestätigen**: A-Records + www-CNAME beim Registrar, „Enforce HTTPS" in den Pages-Settings | **Du** | Aus meiner Umgebung nicht prüfbar (Proxy). Wenn reinhartnatural.de bei dir lädt: erledigt — dann fehlt nur noch Search Console (Punkt 8). |

## B · HOCH — vor dem ersten Verkauf

| # | Aufgabe | Wer | Details |
|---|---|---|---|
| 5 | **COA- und SDB-PDFs beschaffen**: Lieferanten-COA je Rohstoff + idealerweise unabhängige Laborprüfung; SDB je Produkt auf eigene Firmierung anpassen | **Du / Labor** → **Claude** (Einbau: `docs/coa/`, `docs/sdb/`, Download-Links auf allen Produktseiten + Startseite) | Datei 06. Laut Kaufpsychologie-Brief der Kaufauslöser Nr. 1 dieser Nische. |
| 6 | **Shop-Integration** (Empfehlung: Shopify + Buy Buttons): Button-Lösung § 312j BGB, Chargen-Varianten mit ehrlichem Restbestand | **Du** (Konto + Entscheidung) → **Claude** (CTAs ersetzen, JSON-LD PreOrder→InStock, Checkout-Pflichten-Checkliste in 04) | Bis dahin laufen alle 5 CTAs als mailto an charge@reinhartnatural.de. |
| 7 | **Postfach charge@reinhartnatural.de einrichten** | **Du** | Sonst laufen Vormerkungen und Verteiler-Anmeldungen ins Leere. |
| 8 | **Google Search Console** (+ Bing): Property anlegen, `sitemap.xml` einreichen | **Du** | 10 Minuten, Anleitung in 08. |

## C · MITTEL — Ausbau

| # | Aufgabe | Wer | Details |
|---|---|---|---|
| 9 | **Echte Produktfotografie** (Shotliste + Technikvorgaben in 02) | **Du / Fotograf** → **Claude** (Einbau `<picture>`, Hero-Ensemble, og:image) | Bis dahin: KI-Zwischenbilder aus dem Higgsfield-Sprint. |
| 10 | **Higgsfield-Sprint: Bilder, Videos, og:image, Einbau** | **Claude** | Sobald Credits verfügbar. Kompletter Auftrag liegt fertig in **Datei 10 (Master-Prompt)** — einfach den Inhalt als Auftrag geben. |
| 11 | **Newsletter technisch anbinden** (Brevo empfohlen, Double-Opt-in) | **Du** (Konto) → **Claude** (Formular statt mailto, Datenschutz § 8 ergänzen) | Datei 05. |
| 12 | **Interim-Texte ersetzen bei Chargen-Start**: „folgt mit Charge N° 001" (Spezifikationstabellen, Versand-FAQ), Illustration-Hinweise | **Claude** | Beim Launch von N° 001 in einem Rutsch. |

## D · NIEDRIG — Pflege

| # | Aufgabe | Wer |
|---|---|---|
| 13 | `sitemap.xml`-lastmod bei Inhaltsänderungen nachziehen (oder später automatisieren) | Claude |
| 14 | JSON-LD `image`-Property + og:image-**Produktmotive**, sobald echte Bilder existieren (Teil von Punkt 9/10; Interim-og:image mit Siegel ist bereits live) | Claude |

---

## Im Zuge dieses Berichts bereits erledigt

- **Startseiten-Formulierung entschärft:** „das Analysenzertifikat steht als
  PDF…" → „erscheint …, sobald die Charge abgefüllt ist" (Irreführungsrisiko
  § 5 UWG, da die PDFs noch nicht existieren); Charge-Fakten ergänzt um
  „ab Charge N° 001".
- **Interim-og:image + Twitter-Card auf allen 9 Seiten:** Siegel auf Porzellan
  (1200×630, `assets/img/og-standard.png`) — geteilte Links zeigen ab sofort
  ein Vorschaubild statt nichts.
- **Print-Stylesheet ergänzt:** Reveal-Abschnitte drucken jetzt vollständig
  (vorher blieben ungescrollte Bereiche leer), Ankündigungsleiste/Navigation/
  Deko werden beim Druck ausgeblendet — relevant für ausgedruckte
  Spezifikationstabellen.
- **Seitengewicht:** Hero nutzt jetzt ein 256-px-Siegel (−112 KB Startseite);
  weitere 1,25 MB unreferenzierte Brand-Assets vom Deploy ausgenommen
  (bleiben im Repo für Video-Endcards).
- **Barrierefreiheit:** dekoratives Hamburger-Icon für Screenreader versteckt
  (einziger Fund der ARIA-Prüfung — alles andere war sauber).
- **Tote CSS-Klasse** `.todo-banner` entfernt.
- **Doku-Korrekturen:** 08 als weitgehend erledigt markiert (nur DNS/Search
  Console offen), Übersicht in 00 angepasst, falscher Zeolith-Farbwert in 03
  (#7d6a8e → #9d97ad), falsche CSS-Klassen-/Label-Referenzen in 04/05.
- **Technik-Audit ohne weitere Befunde:** alle 6 Schriftdateien in Nutzung,
  `prefers-reduced-motion` deckt alle Animationen ab, Headless-Test von
  Start- und Produktseite ohne Konsolenfehler und ohne 404s.

## Merkzettel Zuständigkeiten

**Nur du:** Rechtsdaten (1), Widerrufs-Generator (2), Anwalt (3), DNS (4),
Labor/COA (5), Shop-Konto (6), Postfach (7), Search Console (8), Fotograf (9),
Newsletter-Konto (11), Higgsfield-Credits (10).
**Ich übernehme jeweils den kompletten Einbau**, sobald du Daten, PDFs,
Konten oder Credits lieferst — eine kurze Nachricht genügt.
