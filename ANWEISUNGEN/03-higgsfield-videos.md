# 03 — Higgsfield: Videos & Bewegtbild

**Status:** Beim Bau der Website war das Higgsfield-Kontingent erschöpft. Diese Datei
enthält fertige Prompts und Einbau-Anweisungen für die nächste Session mit verfügbarem
Kontingent. (Guthaben prüfen: Higgsfield-MCP-Tool `balance` bzw. `show_plans_and_credits`.)

## Video 1 — Hero-Loop für die Startseite (höchste Priorität)

**Zweck:** Subtiler, stummer Hintergrund-Loop hinter/neben dem Hero — Bewegung erzeugt
Wertigkeit, ohne zu schreien. 6–10 s, nahtlos geloopt, keine Schrift, kein Ton.

**Prompt (generate_video, ggf. via generate_image + image-to-video):**

> Slow cinematic macro shot: amber glass apothecary bottle on ivory linen, warm side
> light slowly shifting, dust particles floating in a light beam, a glass pipette
> releasing a single drop in extreme slow motion, shallow depth of field, film grain,
> muted palette of ivory, parchment and deep amber, no text, no people, seamless loop

**Technik-Vorgaben:**
- 1080p reicht (wird ohnehin komprimiert), 24 fps, Loop-fähig (letztes ≈ erstes Frame,
  sonst mit `video_create_quick_cut` einen Ping-Pong-Loop bauen).
- Export als **MP4 (H.264) + WebM**, Ziel < 4 MB. Poster-Frame als JPEG exportieren
  (`video_render_frame`).

**Einbau:** In `index.html` im Hero:
`<video autoplay muted loop playsinline poster="assets/img/hero-poster.jpg">` mit beiden
Quellen; `prefers-reduced-motion` respektieren (CSS: Video ausblenden, Poster zeigen).
Dateien nach `assets/video/`.

## Video 2 — Abfüll-Ritual (Manufaktur-Sektion / Social)

> Documentary style, hands in black nitrile gloves filling amber glass bottles from a
> laboratory funnel on a brass scale, candle-lit apothecary workshop atmosphere but
> clean and precise, dark academia aesthetic, macro details of wax seal being pressed,
> 4k, slow deliberate movements, no faces, no text

15–20 s, 9:16-Ableitung für Instagram/TikTok zusätzlich rendern (`reframe`).

## Video 3 — Produkt-Miniaturen (je Produkt, 5 s, optional)

Ein 5-Sekünder pro Flasche (langsame 180°-Drehung auf Drehteller-Optik, passender
Akzentfarb-Hintergrund je Produkt: Rosa #b26a7a, Blau #3e6a8e, Grün #6f8a70,
Violett #7d6a8e). Verwendung: Hover-Effekt auf den Kollektions-Karten (nice-to-have).

## Rechliche Leitplanke für ALLE Videos

Kein Video darf Anwendung am Menschen zeigen (kein Auftragen auf Haut, kein Einnehmen,
keine Tropfen in Wasser „zum Trinken"). Nur: Objekt, Labor, Handwerk, Material.
Begründung: `01-kaufpsychologie-briefing.md`, Abschnitt 5 (HWG/Präsentationsarzneimittel).

## Checkliste nach Generierung

- [ ] Dateien nach `assets/video/` (MP4 + WebM + Poster)
- [ ] Hero-Video in `index.html` einbauen, `prefers-reduced-motion`-Fallback testen
- [ ] Gesamtgewicht der Startseite < 5 MB halten
- [ ] Social-Ableitungen (9:16) separat sichern, nicht ins Repo (Repo schlank halten,
      ggf. Git LFS erwägen)
