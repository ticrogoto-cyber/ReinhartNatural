# 07 — Rechtsseiten fertigstellen (VOR LAUNCH ZWINGEND)

Die Rechtsseiten in `rechtliches/` sind strukturell fertig, enthalten aber bewusst
**Platzhalter** (im HTML als `<span class="placeholder">[…]</span>` markiert, auf der
Seite farblich hervorgehoben) für Daten, die nur der Inhaber kennt. Ohne vollständiges
Impressum drohen Abmahnungen ab dem ersten Tag der Veröffentlichung.

## Checkliste: Platzhalter füllen

### `rechtliches/impressum.html`
- [ ] Vor- und Nachname der Geschäftsführung
- [ ] Ladungsfähige Anschrift (Straße, Hausnummer, PLZ)
- [ ] E-Mail-Adresse und Telefonnummer
- [ ] Registergericht (bei Berliner UG i. d. R. Amtsgericht Charlottenburg) + HRB-Nummer
- [ ] USt-IdNr. (falls noch keine vorhanden: beim BZSt beantragen; bis dahin die Zeile
      entfernen, nicht leer stehen lassen)
- [ ] Inhaltlich Verantwortlicher nach § 18 Abs. 2 MStV

### `rechtliches/datenschutz.html`
- [ ] Verantwortlicher (Name, Anschrift, E-Mail)
- [ ] Newsletter-Dienstleister eintragen, sobald entschieden (siehe 05)
- [ ] „Stand: [Monat Jahr]" setzen

### `rechtliches/agb.html`
- [ ] Anschrift in § 1
- [ ] Versandkosten und Freigrenze in § 3 (erst festlegen!)
- [ ] Zahlungsarten in § 4 (abhängig von Shop-Entscheidung, siehe 04)
- [ ] Lieferzeit in § 5
- [ ] „Stand: [Monat Jahr]"

### `rechtliches/widerruf.html` — **noch unvollständig!**
Diese Seite ist bisher nur ein Gerüst. Der vollständige Belehrungstext samt
Muster-Widerrufsformular muss eingefügt werden:
- [ ] Text mit einem Generator erzeugen (kostenlos: IHK-Muster; oder Händlerbund /
      IT-Recht Kanzlei im Schutzpaket) — dabei die gesetzliche Musterbelehrung
      (Anlage 1 zu Art. 246a EGBGB) als Basis verwenden
- [ ] Kontaktdaten einsetzen
- [ ] Entscheiden: Wer trägt die Rücksendekosten? (muss in der Belehrung stehen)
- [ ] Hinweis auf Ausschluss/Erlöschen prüfen: **versiegelte Waren, die aus Gründen des
      Gesundheitsschutzes oder der Hygiene nicht zur Rückgabe geeignet sind, wenn die
      Versiegelung entfernt wurde** (§ 312g Abs. 2 Nr. 3 BGB) — für versiegelte
      Chemikalienflaschen relevant und sollte aufgenommen werden

## Danach: Anwaltliche Prüfung (dringend empfohlen)

Ein auf E-Commerce/Wettbewerbsrecht spezialisierter Anwalt (oder ein Schutzpaket von
Händlerbund / IT-Recht Kanzlei / Trusted Shops, ca. 10–50 €/Monat inkl.
Abmahn-Absicherung) sollte vor Launch prüfen:

1. Alle vier Rechtsseiten
2. **Die Produkttexte** auf HWG-Konformität — die Seiten wurden bewusst ohne Heil-,
   Wirk- und Anwendungsaussagen geschrieben (nur Stoffdaten, Geschichte, Lagerung),
   aber die Grenze ist fließend und die Abmahnindustrie aktiv. Besonders prüfen lassen:
   Stoffgeschichte-Absätze (medizinhistorische Fakten wie „Paul Ehrlich nutzte
   Methylenblau zur Vitalfärbung" sind Geschichte, keine Werbeaussage — aber genau
   solche Sätze sollten juristisch abgesegnet sein)
3. Etiketten (CLP-Kennzeichnung, siehe 06)
4. Das Bewertungs-/Moderationskonzept, sobald Bewertungen eingeführt werden

## Kontext

Warum diese Strenge nötig ist, steht ausführlich in
`01-kaufpsychologie-briefing.md`, Abschnitt 5 (HWG, Präsentationsarzneimittel-Falle,
Novel-Food-Status von Zeolith, PAngV, Button-Lösung).
