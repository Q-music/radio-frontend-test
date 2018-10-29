# Opdracht

Voor Qmusic en Joe willen we graag een vereenvoudigde versie van de audio-player, waar je het huidig spelende nummer te zien krijgt (Artiestnaam, Titel en Hoesje) dat live update, en dat je daarop duimpjes kan geven. Daarnaast staat er ook een Play / Stop knop die de AAC/MP3 stream van het station start/stopt.

Hoe het eruit moet zien:
![Example](http://www.defv.be/u/Nu.png)
(meer in detail in Invision)

## Technische requirements

We willen dit zien als HTML pagina die we als iframe kunnen embedden. Onze technische stack:

  * Vue.js
  * Webpack
  * Babel
  * SCSS

De pagina moet werken in de meest recente Google Chrome (maar zie ook pluspunten).

Om van start te gaan mag je de repository clonen naar je computer en een nieuwe branch aanmaken, op die branch mag je alles comitten en pushen naar Github. We bekijken dan straks samen je code!

Voor de iconen kan je Font-Awesome gebruiken voor de play/stop en thumbs-up/thumbs-down. Voor de andere tekst gebruiken we Cervo:

```css
@font-face {
  font-family: "Cervo-Medium";
  src: url('https://fonts.qmusic.be/cervo-medium-webfont.eot');
  src: url('https://fonts.qmusic.be/cervo-medium-webfont.eot?#iefix') format("embedded-opentype"), url('https://fonts.qmusic.be/cervo-medium-webfont.woff2') format("woff2"), url('https://fonts.qmusic.be/cervo-medium-webfont.woff') format("woff"), url('https://fonts.qmusic.be/cervo-medium-webfont.ttf') format("truetype"), url('https://fonts.qmusic.be/cervo-medium-webfont.svg') format("svg");
  font-style: normal;
  font-weight: 600;
}

@font-face {
  font-family: "Cervo-Light";
  src: url('https://fonts.qmusic.be/cervo-light-webfont.eot');
  src: url('https://fonts.qmusic.be/cervo-light-webfont.eot?#iefix') format("embedded-opentype"), url('https://fonts.qmusic.be/cervo-light-webfont.woff2') format("woff2"), url('https://fonts.qmusic.be/cervo-light-webfont.woff') format("woff"), url('https://fonts.qmusic.be/cervo-light-webfont.ttf') format("truetype"), url('https://fonts.qmusic.be/cervo-light-webfont.svg') format("svg");
  font-style: normal;
  font-weight: 600;
}
```

## API

Alle documentatie voor de Qmusic API vind je op https://documenter.getpostman.com/view/3739482/RVfwhARZ

Voor **huidige nummer** kan je initieel de `tracks/plays` call gebruiken, en voor real-time updates de websockets met entity: `plays`, action: `play`.

Voor de **duimpjes** te geven / uit te lezen moet je de "Ratings" calls gebruiken.

De detail van de **audio-stream** vind je in de `/app` call. 

Authenticatie moet je in de pagina niet voorzien, je mag uitgaan van volgende Gigya parameters:

```js
{uid: "_guid_72jPGiBslB8uD5F68uCthQ==", uid_signature: "hsJmUVcQAvMpRe4fAoby2kN2aX4=", signature_date: "1532353073"}
```

## Pluspunten

* Laat het modern aanvoelen: zorg voor animaties zodat het aanvoelt als een applicatie, en niet als een powerpoint waar je doorklikt
* Laat het qua browser compatibility werken in alle moderne browsers én IE11
* Optimaliseer voor filesize. Deze player zouden we als lightweight kunnen gebruiken voor trage/oude toestellen, dan is het belangrijk dat we ook niet teveel data gebruiken
