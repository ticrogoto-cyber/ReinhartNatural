# 05 — Chargen-Brief (Newsletter) anbinden

**Status quo:** Die Startseite hat eine Chargen-Brief-Sektion (`#verteiler`) mit einem
`mailto:`-CTA. Das funktioniert, skaliert aber nicht und erlaubt kein sauberes
Double-Opt-in. Ziel: echter Newsletter-Dienst.

## Warum der Chargen-Brief strategisch wichtig ist

Aus dem Kaufpsychologie-Brief (Taktik 7): Die Newsletter-Anmeldung ist der kleine erste
Schritt (**Commitment/Konsistenz**) — wer sich einträgt, kauft später. Das Versprechen:
**Abonnenten erfahren 48 Stunden früher von neuen Chargen** (ehrliche Exklusivität +
Wartelisten-Mechanik bei ausverkauften Chargen).

## Dienst-Auswahl (DSGVO im Blick)

| Dienst | Bewertung |
|---|---|
| **Brevo** (ehem. Sendinblue) | EU-Server, kostenloser Plan, deutsches Interface — *empfohlen für den Start* |
| **Mailchimp** | Verbreitet, aber US-Anbieter → Standardvertragsklauseln nötig |
| **Buttondown / Listmonk (selbst gehostet)** | Puristisch, passt zur Marke, mehr Handarbeit |

## Umsetzung

1. Konto anlegen, Liste „Chargen-Brief" mit **Double-Opt-in** (Pflicht in DE).
2. Anmeldeformular einbinden: Auf GitHub Pages gibt es kein Backend — das Formular
   POSTet direkt an den Dienst (Brevo/Mailchimp bieten Form-Endpoints) oder über ein
   schlankes Serverless-Relay. Das Formular ersetzt den `mailto:`-CTA in der
   `#verteiler`-Sektion der `index.html` (eine E-Mail-Zeile + Absenden-Button,
   Klassen `.btn.btn-solid` weiterverwenden).
3. **Datenschutzerklärung aktualisieren:** In `rechtliches/datenschutz.html` ist unter
   „8. Chargen-Brief (Newsletter)" ein Platzhalter für den Dienstleister — eintragen
   und ggf. AVV-Hinweis ergänzen.
4. Bestätigungs- und Willkommensmail im Markenton aufsetzen (ruhig, präzise, keine
   Ausrufezeichen; Absender „Reinhart Natural — Chargen-Brief").

## Redaktionsformat (Vorschlag)

Eine Ausgabe pro Charge, nicht mehr. Struktur:

1. **Chargen-Meldung:** „Charge N° 002 — DMSO, 300 Flaschen, abgefüllt am …, COA liegt vor."
2. **Ein Stoffporträt-Auszug** (Geschichte/Chemie, niemals Anwendung — HWG!)
3. **Ein Blick in die Werkstatt** (Foto, ein Satz)
4. Abmeldelink, Impressumspflichten im Footer

## Rechtliche Leitplanken

- Double-Opt-in dokumentieren (Zeitstempel + IP der Bestätigung aufbewahren)
- Jede Ausgabe: Abmeldelink + vollständiges Impressum
- Inhaltlich gelten dieselben HWG-Regeln wie für die Website — **keine** Wirk- oder
  Anwendungsaussagen, auch nicht in Betreffzeilen („Was DMSO alles kann" wäre bereits
  kritisch). Siehe `01-kaufpsychologie-briefing.md`, Abschnitt 5.
