# 08 — GitHub Pages aktivieren & Domain verbinden (SOFORT, 10 Minuten)

Die Website liegt im Repo `ticrogoto-cyber/ReinhartNatural` auf dem Branch
`claude/reinhart-natural-website-1gz0rn`. Damit sie unter **reinhartnatural.de** live
geht, sind drei Schritte nötig.

## Schritt 1 — Branch mergen

GitHub Pages sollte vom Default-Branch (`main`) ausgeliefert werden:

1. Auf GitHub einen Pull Request vom Branch `claude/reinhart-natural-website-1gz0rn`
   nach `main` öffnen und mergen (oder den Branch direkt als `main` setzen).

## Schritt 2 — GitHub Pages einschalten

1. Repo → **Settings → Pages**
2. Source: **GitHub Actions** wählen — NICHT „Deploy from a branch"!
3. Der Workflow `.github/workflows/pages.yml` läuft bei jedem Push auf `main`
   automatisch (oder manuell über den Actions-Tab → „Website zu GitHub Pages
   deployen" → Run workflow). Nach 1–2 Minuten ist die Seite unter
   `https://ticrogoto-cyber.github.io/ReinhartNatural/` erreichbar.

**Warum GitHub Actions statt „Deploy from a branch":** Der Workflow deployt nur
die öffentlichen Website-Dateien (Whitelist). Bei „Deploy from a branch" würde
der GESAMTE Repo-Inhalt ausgeliefert — auch dieser `ANWEISUNGEN/`-Ordner wäre
dann unter reinhartnatural.de/ANWEISUNGEN/ öffentlich abrufbar. Diese internen
Unterlagen (insbesondere das Kaufpsychologie-Briefing) dürfen niemals auf der
Verkaufsdomain erscheinen. Also: nie auf „Deploy from a branch" umstellen.

Die Dateien `.nojekyll` (verhindert Jekyll-Verarbeitung) und `CNAME` (enthält
`reinhartnatural.de`) liegen bereits im Repo und werden vom Workflow mitkopiert.

## Schritt 3 — DNS beim Domain-Anbieter setzen

Beim Registrar von reinhartnatural.de (z. B. IONOS, Strato, Namecheap):

**A-Records für die Apex-Domain `reinhartnatural.de`:**

```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

**CNAME-Record für `www`:**

```
www.reinhartnatural.de → ticrogoto-cyber.github.io
```

Danach in Repo-Settings → Pages die Custom Domain `reinhartnatural.de` eintragen
(füllt/prüft die CNAME-Datei) und **„Enforce HTTPS"** aktivieren, sobald das
Zertifikat ausgestellt ist (kann bis zu 24 h dauern, meist < 1 h).

## Schritt 4 — Verifizieren

- [ ] `https://reinhartnatural.de` lädt mit gültigem Zertifikat
- [ ] `https://www.reinhartnatural.de` leitet auf die Apex um
- [ ] `https://reinhartnatural.de/sitemap.xml` und `/robots.txt` erreichbar
- [ ] Google Search Console: Property anlegen, Sitemap einreichen
- [ ] Als Bonus: Domain zusätzlich bei Bing Webmaster Tools anmelden

## Hinweis zur Weiterentwicklung

Künftige Änderungen (Fotos, Shop-Buttons, COA-PDFs) einfach auf `main` pushen —
GitHub Pages deployt automatisch. Kein Build-Schritt nötig: Die Seite ist bewusst
reines HTML/CSS/JS ohne Framework.
