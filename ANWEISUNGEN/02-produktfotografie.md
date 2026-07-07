# 02 — Produktfotografie

**Ziel:** Die SVG-Illustrationen auf Start- und Produktseiten durch echte Fotografien
ersetzen, sobald die ersten physischen Flaschen der Charge N° 001 existieren.

## Warum das wichtig ist

Der Recherche-Brief (01) zeigt: Diese Nische kauft **Costly Signals** — sichtbar teure
Details (Braunglas, Siegel, nummerierte Charge) signalisieren „wer so abfüllt, spart
nicht am Inhalt". Illustrationen behaupten das nur; Fotos beweisen es. Außerdem ist das
Unboxing der „Peak" (Peak-End-Regel) — Fotos davon sind zugleich Social-Media-Material.

## Shotliste (Minimum)

### A. Freisteller pro Produkt (4 × 2 Motive)

| Motiv | Verwendung |
|---|---|
| Flasche frontal, Etikett scharf, neutraler Fond (Elfenbein #f3efe4 oder Anthrazit #2f3133) | Produktseite Hero, Kollektions-Karte |
| Flasche 3/4-Ansicht mit sichtbarem Verschluss (Pipette/Sprühkopf/Deckel) | Produktseite Galerie |

### B. Stimmungsbilder (Marke)

1. **Alle vier Flaschen als Regal-Ensemble** — ersetzt das SVG-Regal im Hero der Startseite.
2. **Abfüll-Szene:** Hände mit Nitrilhandschuhen, Waage, Trichter, Braunglas — dokumentarisch,
   nicht gestellt wirkend (Manufaktur-Sektion, „Sympathie durch Echtheit").
3. **Chargen-Detail:** Makro der handgestempelten Chargennummer auf dem Etikett (Charge-Sektion).
4. **Unboxing-Flatlay:** Karton, Seidenpapier, Chargenkarte, versiegelte Flasche (Social Media,
   künftige Versand-Mail).

## Technische Vorgaben

- **Licht:** weich, seitlich, leicht warm (Apotheken-Nordlicht). Keine harten Blitzreflexe
  auf dem Glas — Braunglas lebt von einem einzigen, ruhigen Glanzstreifen.
- **Farbwelt:** muss zur Website passen — Elfenbein (#f3efe4), Pergament (#e7dcc3),
  Anthrazit (#2f3133), Tinte (#1b1b1b). Requisiten sparsam: Laborglas, Papier, Messing.
- **Format:** Quelldateien in RAW; Ableitungen als AVIF + WebP + JPEG-Fallback.
  Produktfreisteller mindestens 2000 px Kante, quadratisch UND 4:5.
- **Dateinamen:** `assets/img/produkt-dmso-front.avif`, `-seite.avif`,
  `stimmung-regal.avif`, `stimmung-abfuellung.avif` usw.

## Einbau in die Website (für die nächste Claude-Session)

1. Bilder nach `assets/img/` legen (AVIF + JPEG-Fallback).
2. Auf den Produktseiten den `.product-stage`-Block ersetzen: `<picture>` mit
   `srcset`/`sizes` statt `<svg><use href="#flasche-…">`. Den Hinweis
   „Illustration. Produktfotografie folgt…" entfernen.
3. Auf der Startseite das SVG-Flaschenregal im Hero gegen das Ensemble-Foto tauschen
   (`loading="eager"`, `fetchpriority="high"`); Kollektions-Karten bekommen die Freisteller
   (`loading="lazy"`).
4. `og:image` in allen `<head>`s ergänzen (1200×630-Ableitungen erzeugen).
5. Die SVG-Symbole trotzdem im Sprite behalten — sie bleiben Fallback und werden im
   Footer/Favicon weiterverwendet.

## Falls kein Fotograf: KI-Übergangslösung

Solange keine echten Flaschen existieren, können mit Higgsfield (`generate_image`,
siehe 03) fotorealistische Zwischenbilder erzeugt werden. Prompt-Basis:

> Editorial product photography, amber glass apothecary bottle with cream paper label,
> soft north-light studio, ivory seamless background, subtle film grain, style of
> Aesop/Le Labo campaigns — [Produktname, Verschlussart einsetzen]

**Wichtig:** KI-Bilder nur als Übergang und ohne Text im Bild generieren (Etiketten-Text
rendert KI fehlerhaft) — das echte Etikett ggf. in Photoshop/Affinity draufmontieren.
