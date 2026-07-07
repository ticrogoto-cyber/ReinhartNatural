# 04 — Shop-Integration (echter Checkout)

**Status quo:** Die Website nimmt Vorbestellungen per `mailto:`-Link entgegen. Das ist
bewusst als Übergang gebaut — rechtssicher verkaufen und skalieren geht nur mit echtem
Checkout inkl. Button-Lösung (§ 312j BGB: „zahlungspflichtig bestellen").

## Empfehlung

Für 4 Produkte mit Chargen-Logik sind drei Wege realistisch, sortiert nach Empfehlung:

### Option A — Shopify (Starter oder Basic) mit Buy Buttons *(empfohlen)*
- Die statische GitHub-Pages-Seite bleibt das Schaufenster (Marke, Stoffporträts, SEO);
  Shopify liefert Warenkorb + Checkout via **Buy Button JS** oder verlinkte Produkt-URLs.
- Vorteile: PCI-konform, deutsche Rechtstexte-Apps, Bestandsführung je Charge über
  Varianten („Charge N° 001"), Trusted-Shops-Integration möglich.
- Zu tun: Shopify-Konto, 4 Produkte + Grundpreise anlegen, deutsche Pflichtseiten
  verknüpfen, Buy-Button-Snippets in die Produktseiten einsetzen (die vorhandenen
  `mailto:`-CTAs ersetzen; Klassen `.btn.btn-primary` beibehalten).

### Option B — Snipcart / ein Headless-Cart
- Bleibt komplett auf der eigenen Domain, nur JS-Einbindung + Preis-Attribute im HTML.
- Vorteil: maximale Design-Kontrolle. Nachteil: Rechtstexte, Steuern, Zahlungsarten
  selbst konfigurieren; mehr Eigenverantwortung.

### Option C — Vollumzug zu Shopify-Theme
- Nur falls die statische Seite langfristig zu unflexibel wird. Das Design-System
  (`assets/css/style.css`) lässt sich in ein Shopify-Theme portieren. Aufwand hoch.

## Chargen-Logik (Kern der Marke — unbedingt umsetzen)

Aus dem Kaufpsychologie-Brief (Taktik 2): **ehrliche Knappheit** über nummerierte
Kleinchargen. Im Shop je Produkt eine Variante pro Charge führen
(„Charge N° 001 — 100 Stück"); der Restbestand wird auf der Produktseite angezeigt
(„noch 43 von 100"). Kein Countdown, keine künstliche Verknappung — nur Wahrheit.

## Pflichten beim Checkout (vor Livegang prüfen)

- [ ] Bestellbutton-Beschriftung: „zahlungspflichtig bestellen" o. ä. (§ 312j BGB)
- [ ] Pflichtinfos unmittelbar vor dem Button: Merkmale, Gesamtpreis, Versandkosten
- [ ] Grundpreise (€/L bzw. €/kg) auch im Warenkorb sichtbar (PAngV)
- [ ] AGB + Widerrufsbelehrung als Checkbox/Link im Checkout
- [ ] Bestellbestätigungs-Mail mit Vertragstext, Widerrufsbelehrung, Rechtstexten
- [ ] Altersgrenze/Abgabebeschränkungen prüfen (Chemikalienabgabe an Privatpersonen —
      für die vier Produkte derzeit unproblematisch, aber bei Sortimentserweiterung
      erneut prüfen; ggf. Verwendungszweck-Abfrage wie bei Apotheken üblich)

## Nach der Integration auf der Website ändern

1. Alle `mailto:`-CTA-Buttons („Vorbestellen per E-Mail") auf den Produktseiten und der
   Startseite durch echte Kauf-Buttons ersetzen.
2. JSON-LD `offers.availability` von `PreOrder` auf `InStock` je Charge umstellen.
3. FAQ-Eintrag zur Vorbestellung aktualisieren.
4. `06-coa-sdb-dokumente.md` umsetzen — COA-Link gehört in die Versandbestätigung
   (Peak-End-Regel: das Ende der Customer Journey gestalten).
