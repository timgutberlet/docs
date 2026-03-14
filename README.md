# HalloFelix Dokumentation

Offizielle Dokumentation für HalloFelix - KI-Bürokraft von InsurMagic.

## Development

Installiere die [Mintlify CLI](https://www.npmjs.com/package/mint) um die Dokumentation lokal anzuzeigen:

```bash
npm i -g mint
```

Starte den Development Server:

```bash
mint dev
```

Die Dokumentation ist dann unter `http://localhost:3000` erreichbar.

## Struktur

- Dokumentationsseiten sind MDX-Dateien mit YAML Frontmatter
- Konfiguration in `docs.json`
- Navigation und Struktur werden in `docs.json` definiert

## Deployment

Änderungen werden automatisch nach dem Push auf den main Branch deployed.
