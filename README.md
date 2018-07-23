# Opdracht

Voor Qmusic en Joe willen we graag een vereenvoudigde versie van de audio-player, waar je het huidig spelende nummer te zien krijgt (Artiestnaam, Titel en Hoesje) dat live update, en dat je daarop duimpjes kan geven. Daarnaast staat er ook een Play / Stop knop die de AAC/MP3 stream van het station start/stopt.

Voorbeeld van hoe het eruit zou kunnen zien:
![Example](http://www.defv.be/u/You_make_us_Q_-_Qmusic_2018-07-23_15-20-45.jpg)

## Technische requirements

We willen dit zien als HTML pagina die we als iframe kunnen embedden. Onze technische stack:

  * Vue.js
  * Webpack
  * Babel
  * SCSS

De pagina moet werken in de meest recente Google Chrome (maar zie ook pluspunten).

Om van start te gaan mag je de repository forken naar je eigen gebruiker en daarnaar comitten. We bekijken dan straks samen je code op die Github.

## API

Alle documentatie voor de Qmusic API vind je op https://documenter.getpostman.com/view/3739482/RVfwhARZ

Voor **huidige nummer** kan je initieel de `tracks/plays` call gebruiken, en voor real-time updates de websockets met entity: `plays`, action: `play`.

Voor de **duimpjes** te geven / uit te lezen moet je de "Ratings" calls gebruiken.

De detail van de **audio-stream** vind je in de `/app` call. 

Authenticatie moet je in de pagina niet voorzien, je mag uitgaan van volgende Gigya parameters:

```
{uid: "_guid_72jPGiBslB8uD5F68uCthQ==", uid_signature: "hsJmUVcQAvMpRe4fAoby2kN2aX4=", signature_date: "1532353073"}
```

## Pluspunten

* Laat het modern aanvoelen: zorg voor animaties zodat het aanvoelt als een applicatie, en niet als een powerpoint waar je doorklikt
* Laat het qua browser compatibility werken in alle moderne browsers én IE11
* Optimaliseer voor filesize. Deze player zouden we als lightweight kunnen gebruiken voor trage/oude toestellen, dan is het belangrijk dat we ook niet teveel data gebruiken
