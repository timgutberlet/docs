# HalloFelix Hilfezentrum – Regeln für neue Artikel

Live unter https://hilfezentrum.hallofelix.de (Mintlify). Alles, was auf `main` landet, ist sofort live.
Deshalb jeder Artikel per Pull Request; Mintlify zeigt die Änderung nach dem Merge in etwa einer Minute.

## Ablauf (so schnell wie möglich)

1. Thema nennen, z. B. „Schreib einen Hilfeartikel zu privaten WhatsApp-Kontakten“.
2. Claude liest die echten Texte der App (Repo `InsurMagic-GmbH/hallofelix-app`, Stand `master-prod`), damit jeder Button-Name stimmt.
3. Claude legt die `.mdx`-Datei an, trägt sie in `docs.json` ein, prüft mit `npx mint broken-links` und öffnet einen PR.
4. Ein Mensch liest den PR und merged. Fertig.

## Schreibregeln

- **Sie-Form**, kurze Sätze, ein Gedanke pro Satz. Keine Werbesprache.
- Für Makler ohne Technikwissen schreiben. Fachwörter (Webhook, API, Token) nur, wenn es nicht anders geht, und dann kurz erklärt.
- Button- und Menünamen **fett** und genau so, wie sie in der App stehen.
- Jeder Schritt in der App bekommt einen direkten Link, z. B. [WhatsApp-Einstellungen](https://app.hallofelix.de/whatsapp/settings).
- Nur beschreiben, was in Produktion für alle Kunden an ist. Nichts hinter einem Feature-Flag, nichts Internes (Admin, HalloFelix-Team-Funktionen).
- Länge: so kurz wie möglich. Ein Artikel beantwortet eine Frage.

## Aufbau eines Artikels

```mdx
---
title: "Kurzer Titel"
description: "Ein Satz: was man hier lernt"
---

Ein bis zwei Sätze: was die Funktion tut und wem sie hilft.

## So richten Sie es ein

<Steps>
  <Step title="…">…</Step>
</Steps>

## Gut zu wissen

- Grenzen, wer was darf, was passiert mit bestehenden Daten.

## Häufige Fragen

<AccordionGroup>
  <Accordion title="…">…</Accordion>
</AccordionGroup>
```

Erlaubte Bausteine: `<Steps>`, `<Note>`, `<Tip>`, `<Warning>`, `<Info>`, `<AccordionGroup>`, `<Frame>` für Screenshots, Tabellen.

## Dateien und Navigation

- Ordner nach Bereich: `whatsapp/`, `funktionen/`, `rufweiterleitung/`, `integrationen/`, `mcp/`, `infos-hilfe/`.
- Dateiname = URL, kleingeschrieben, Bindestriche, keine Umlaute (`private-kontakte.mdx`).
- Neue Seite immer in `docs.json` unter `navigation.tabs[0].groups` in die passende Gruppe eintragen, sonst ist sie nicht im Menü.
- Screenshots nach `images/<bereich>/`, eingebunden mit `<Frame><img src="/images/whatsapp/beispiel.png" alt="…" /></Frame>`. Keine echten Kundendaten auf Screenshots.

## Prüfen

- `npx mint broken-links` muss sauber sein.
- Lokale Vorschau: `npx mint dev` → http://localhost:3000

## Verknüpfung mit Produkt-Updates

Produkt-Updates (WhatsApp-Gruppe, Changelog, E-Mail) sind kurz und verlinken für Details hierher.
Gibt es zu einer neuen Funktion noch keinen Artikel, zuerst den Artikel schreiben, dann das Update.
