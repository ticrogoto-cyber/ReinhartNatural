# 06 — Analysenzertifikate (COA) & Sicherheitsdatenblätter (SDB)

**Priorität: SEHR HOCH.** Der Kaufpsychologie-Brief ist hier eindeutig (Taktik 1 + 13):
Das chargenbezogene Analysenzertifikat ist **der Kaufauslöser Nr. 1 dieser Nische**, und
das Sicherheitsdatenblatt verwandelt eine Pflicht in ein Kompetenzsignal, das kein
Lifestyle-Shop bietet. Die Website verspricht beides bereits („Analysenzertifikat als
PDF je Charge") — dieses Versprechen muss vor dem ersten Verkauf eingelöst werden.

## Was besorgt werden muss

### 1. COA (Certificate of Analysis) — je Produkt UND je Charge

- **Quelle:** (a) COA des Rohstofflieferanten anfordern (kommt mit jeder Lieferung) und
  (b) idealerweise zusätzlich eine eigene Prüfung durch ein unabhängiges deutsches Labor
  beauftragen (Benchmark Sunday Natural — „unabhängig laborgeprüft" schlägt
  „Hersteller-COA" deutlich).
- **Inhalt mindestens:** Identität, Reinheit/Gehalt (Ph.-Eur.-Methode wo einschlägig),
  Chargennummer, Prüfdatum, Labor mit Anschrift/Akkreditierung.
- **Labore (Beispiele zum Anfragen):** akkreditierte Auftragslabore für Chemikalien-
  analytik (DAkkS-akkreditiert, z. B. regionale Institute für Lebensmittel- und
  Umweltanalytik nehmen auch Reinstoffprüfungen an). Angebote für die vier Stoffe
  einholen; Zeolith zusätzlich auf Schwermetalle prüfen lassen (starkes Signal).

### 2. SDB (Sicherheitsdatenblatt) — je Produkt

- Vom Lieferanten anfordern (verpflichtend mitzuliefern) und auf die eigene Abfüllung
  anpassen (Firmenname als Inverkehrbringer, Notfallnummer). Für die Anpassung gibt es
  Dienstleister; bei unveränderten Stoffen ist es überschaubar.
- CLP-Kennzeichnung der Etiketten daraus ableiten (H-/P-Sätze, Piktogramme — bei
  Methylenblau z. B. „Gesundheitsschädlich beim Verschlucken").

## Einbau in die Website

1. PDFs ablegen unter: `docs/coa/coa-dmso-charge-001.pdf`,
   `docs/sdb/sdb-dmso.pdf` (Schema: `coa-<produkt>-charge-<nnn>.pdf`, `sdb-<produkt>.pdf`).
2. Auf jeder Produktseite (`produkte/*.html`) im Spezifikations-/Legal-Bereich zwei
   Download-Links ergänzen:
   - „Analysenzertifikat Charge N° 001 (PDF)" → COA
   - „Sicherheitsdatenblatt (PDF)" → SDB
3. Auf der Startseite in der Charge-Sektion (`#charge`) den COA-Link der aktuellen
   Charge setzen.
4. In die künftige Versandbestätigung (siehe 04) den COA-Link aufnehmen — das ist das
   gestaltete „Ende" der Peak-End-Regel.

## Solange die PDFs fehlen

Die Produktseiten versprechen das COA im Text. Falls der Launch vor Vorliegen der
Zertifikate erfolgt, Formulierung abschwächen auf „COA je Charge — auf Anfrage /
erscheint mit Charge N° 001". Nicht mit einem Dokument werben, das es noch nicht gibt
(Irreführungsgefahr, § 5 UWG).
