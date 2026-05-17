# DJ Andy Veltjen – Website

One-page landingssite voor DJ Andy Veltjen. Gebouwd met Tailwind CSS (CDN), geanimeerde elementen en inhoud die eenvoudig aanpasbaar is via Markdown-bestanden.

## Inhoud aanpassen

Alle teksten zitten in de map `content/`. Open het gewenste bestand in een teksteditor en sla op.

| Bestand | Wat staat er in |
|---|---|
| `content/hero.md` | Subtitel onder de naam op de hero-sectie |
| `content/about.md` | Tekst in de "Over mij"-sectie |
| `content/music.md` | Intro-tekst in de muziek-sectie |
| `content/services.md` | Werking & ALL IN pakket (referentie) |

De secties in `index.html` hebben ook inline fallback-teksten die zichtbaar zijn zonder server.

## Foto's toevoegen

Plaats uw foto's in de map `assets/`:

| Bestand | Gebruik |
|---|---|
| `assets/hero.jpg` | Actiefoto als achtergrond op de hero (min. 1920×1080 px, landschap) |
| `assets/about.jpg` | Portretfoto in de "Over mij"-sectie (~600×750 px, staand) |

Zonder deze bestanden toont de pagina automatisch een fallback-gradient of placeholder.

## Spotify playlist vervangen

Open `index.html` en zoek naar `spotify-iframe`. Vervang de playlist-ID in de `src`-URL:

```
https://open.spotify.com/embed/playlist/JOUW_PLAYLIST_ID?utm_source=generator&theme=0
```

## Facebook-link instellen

Zoek in `index.html` naar `<!-- Facebook – pas de href aan` en vervang `href="#"` door de URL van uw Facebook-pagina.

## Formulier activeren (e-mail versturen)

Het formulier toont nu een succesmelding (demo). Om echte e-mails te ontvangen:

**Optie A – Formspree (gratis):**
1. Maak een account aan op [formspree.io](https://formspree.io)
2. Maak een nieuw formulier aan en kopieer uw Form ID
3. Voeg `action="https://formspree.io/f/JOUW_ID"` toe aan het `<form>`-element in `index.html`

**Optie B – Netlify Forms:**
1. Deploy via [netlify.com](https://netlify.com)
2. Voeg `data-netlify="true"` toe aan het `<form>`-element

## Lokale preview met Markdown-loading

De `.md`-bestanden worden geladen via `fetch()`. Dit werkt **niet** via `file://` — gebruik een lokale server:

```bash
# Python 3
python3 -m http.server 8080

# Node.js (npx)
npx serve .
```

Open vervolgens `http://localhost:8080` in uw browser.

Bij directe opening van `index.html` (zonder server) blijven de inline fallback-teksten zichtbaar.

## Structuur

```
djandyveltjen/
├── index.html          ← Hoofdpagina (alles in één bestand)
├── content/
│   ├── hero.md         ← Hero subtitel
│   ├── about.md        ← Over mij tekst
│   ├── music.md        ← Muziek intro
│   └── services.md     ← Werking (referentie)
├── assets/
│   ├── hero.jpg        ← Actiefoto (zelf toevoegen)
│   └── about.jpg       ← Portretfoto (zelf toevoegen)
└── README.md           ← Dit bestand
```
