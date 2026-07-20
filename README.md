# Kriol di Família

Een kleine leerapp voor **Kriol d Sonsent** (São Vicente-basis, met São Nicolau/Sal-vormen van de familie), om met het gezin Kaapverdiaans Creools te leren. Statische site — geen server, geen account.

## Mappenstructuur

```
/ (root van de repo)
├─ index.html              ← de app
├─ kriol_seed_v1.json      ← alle inhoud (woorden, zinnen, vertalingen, audiopaden)
├─ audio/                  ← de opnames (k0001.mp3 … )
│   ├─ k0001.mp3
│   ├─ …
│   └─ k0019_alt.mp3
└─ .nojekyll              ← zegt GitHub Pages: geen verwerking, serveer alles 1-op-1
```

## Lokaal testen (vóór publiceren)

De app **moet via een webserver** draaien (rechtstreeks openen werkt niet door de JSON-fetch).
In deze map:

```
python3 -m http.server
```

Open daarna **http://localhost:8000** in je browser. Hier werkt ook de audio.

## Publiceren op GitHub Pages (gratis, publieke repo)

1. Maak een **publieke** repository op GitHub (bv. `kriol-familia`).
2. Upload de inhoud van deze map naar de repo (inclusief de map `audio/` en `.nojekyll`).
3. Ga in de repo naar **Settings → Pages**.
4. Bij **Source**: kies branch `main` en map `/ (root)`. Save.
5. Na ±1 minuut staat de app op `https://<gebruikersnaam>.github.io/kriol-familia/`.
6. Deel die link met het gezin. Op de telefoon kunnen ze via "Toevoegen aan beginscherm" een app-icoon maken.

> Optioneel later: een eigen domein (GoDaddy) koppelen via een CNAME-record naar GitHub Pages.

## Inhoud aanpassen of uitbreiden

- **Tekst/vertalingen wijzigen of woorden toevoegen** → bewerk alleen `kriol_seed_v1.json`. De code hoef je niet aan te raken.
- **Audio toevoegen** → zet het mp3-bestand in `audio/` met de naam gelijk aan het `id` (bv. `k0030.mp3`) en zet dat pad in het `audio`-veld van dat item (`"audio/k0030.mp3"`). Gebruik **kleine letters** in bestandsnamen (hoofdlettergevoelig!).
- Velden per item: `kriol` (hoofdvorm, met audio), `kriol_sv` (São Vicente-referentie, optioneel), `alt` + `alt_audio` (varianten), `nl`, `pt` (optioneel), `pron_hint`.

## Voortgang

Streak en herhaling worden per toestel in de browser bewaard (`localStorage`). Elk gezinslid heeft dus zijn eigen voortgang op zijn eigen telefoon.

## Status audio

16 lessen, 165 items, 168 mp3-bestanden. Alle kaarten hebben audio.

## Inhoud v3

- **16 lessen / 165 items.** Les 1–5 (v1): begroeten, ik & jij, thuis & eten, familie, dagritme. Les 6–11 (v2): vraagwoorden, winkel & restaurant, familie & small talk, getallen 0–10, tijd, gevoelens. Les 12–16 (v3): lichaamsdelen, fruit & groente, vlees & vis, aan tafel & bestek, voertuigen. Les 3 kreeg er ook rijst, thee, melk en koekje bij.
- Alle Kriol-vormen van v2/v3 zijn door de native spreker (São Nicolau) ingesproken en gecorrigeerd. Portugees is voor alle items ingevuld.
- De v2-vormen komen uit de conceptlijst (familie-uitspraak). Het `pt`-veld is voor de nieuwe items nog leeg (`null`) — de Portugees-toggle toont daar voorlopig "—".
