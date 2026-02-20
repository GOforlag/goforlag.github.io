# Banner-dokumentation

Denne side (`banner.html`) er et showcasebibliotek over tilgængelige bannertyper. Dokumentationen beskriver de felter og egenskaber, der skal konfigureres i CMS'et for hvert bannerformat.

---

## Fælles egenskaber

Disse felter findes på **alle** bannertyper:

| Felt | Type | Påkrævet | Beskrivelse |
|---|---|---|---|
| `title` | Tekst | Nej | Bannerets overskrift (`<h1>`) |
| `lead` | Tekst | Nej | Kort beskrivende brødtekst under overskriften |
| `buttonText` | Tekst | Nej | Teksten på CTA-knappen (f.eks. "Læs mere") |
| `buttonUrl` | URL | Nej | Link bag CTA-knappen |
| `layout` | Valg | Nej | `standard` (billede til venstre) eller `spejlvendt` (billede til højre) |

---

## 1. Standard banner med baggrundsbillede

Et vandret banner med bogomslag på den ene side og tekstindhold på den anden. Bruges til bogannonceringer.

**Eksempel på HTML-output:**
```html
<div
  class="banner [banner--left] [banner--content-bg]"
  style="background-image: url(BAGGRUNDSBILLEDE); background-size: cover; background-position: center"
>
  <div class="banner__image-wrapper">
    <img class="banner__image" src="BOGOMSLAG" style="width: [BREDDE]px" />
  </div>
  <div class="banner__content" style="flex: 0 0 [INDHOLDSBREDDE]px">
    <h1 class="banner__title">TITEL</h1>
    <div class="banner__lead">BRØDTEKST</div>
    <a href="KNAP-URL" class="banner__button">KNAPTEKST</a>
  </div>
</div>
```

**Felter:**

| Felt | Type | Påkrævet | Beskrivelse |
|---|---|---|---|
| `backgroundImage` | Billedfil | Ja | Baggrundsbillede bag hele banneret (f.eks. `.webp`, `.jpg`, `.svg`) |
| `coverImage` | Billedfil | Nej | Bogomslaget der vises som billedelement |
| `coverImageWidth` | Tal (px) | Nej | Bredde på bogomslaget i pixels. Standard: `200` |
| `contentWidth` | Tal (px) | Nej | Bredde på tekstblokken i pixels. Standard: `500` |
| `layout` | Valg | Nej | `standard`: omslag til venstre / `spejlvendt`: omslag til højre (tilføjer `.banner--left`) |
| `darkContentBg` | Til/fra | Nej | Tilføjer halvgennemsigtigt mørkt lag bag tekstblokken (`.banner--content-bg`) |
| `title` | Tekst | Nej | Overskrift |
| `lead` | Tekst | Nej | Brødtekst |
| `buttonText` | Tekst | Nej | Knaptekst |
| `buttonUrl` | URL | Nej | Knaplink |

---

## 2. Lyst banner

Samme struktur som standard banneret, men med mørk tekst og grøn knap. Bruges når baggrundsbilledet er lyst.

**Felter:** Identiske med standard banneret, men typen sættes til `lyst` (tilføjer `.banner--light`).

| Felt | Type | Påkrævet | Beskrivelse |
|---|---|---|---|
| `backgroundImage` | Billedfil | Ja | Lyst baggrundsbillede |
| `coverImage` | Billedfil | Nej | Bogomslaget |
| `coverImageWidth` | Tal (px) | Nej | Bredde på bogomslaget. Standard: `200` |
| `contentWidth` | Tal (px) | Nej | Bredde på tekstblokken. Standard: `500` |
| `layout` | Valg | Nej | `standard` eller `spejlvendt` |
| `title` | Tekst | Nej | Overskrift |
| `lead` | Tekst | Nej | Brødtekst |
| `buttonText` | Tekst | Nej | Knaptekst |
| `buttonUrl` | URL | Nej | Knaplink |

---

## 3. Hero-banner med statisk billede

Fylder hele bannerbredden med et baggrundsbillede. Tekstindholdet er centreret oven på et halvgennemsigtigt mørkt overlay. Velegnet til atmosfæriske fotografier.

**Eksempel på HTML-output:**
```html
<div
  class="banner banner--image-hero"
  style="background-image: url(BAGGRUNDSBILLEDE)"
>
  <div class="banner__overlay"></div>
  <div class="banner__content">
    <h1 class="banner__title">TITEL</h1>
    <div class="banner__lead">BRØDTEKST</div>
    <a href="KNAP-URL" class="banner__button">KNAPTEKST</a>
  </div>
</div>
```

**Felter:**

| Felt | Type | Påkrævet | Beskrivelse |
|---|---|---|---|
| `backgroundImage` | Billedfil | Ja | Baggrundsbillede – fylder hele banneret |
| `lightMode` | Til/fra | Nej | Slår overlay fra og bruger mørk tekst (til lyse SVG-baggrunde). Tilføjer `.banner--light`, fjerner `.banner__overlay` |
| `backgroundColor` | Farve (hex) | Nej | Fallback-baggrundsfarve hvis billedet ikke dækker (bruges primært med SVG). Standard: `#f9f6f0` |
| `minHeight` | Tal (px) | Nej | Minimumshøjde på banneret. Standard: `400` |
| `title` | Tekst | Nej | Overskrift |
| `lead` | Tekst | Nej | Brødtekst |
| `buttonText` | Tekst | Nej | Knaptekst |
| `buttonUrl` | URL | Nej | Knaplink |

---

## 4. Loopende videobanner

En video afspilles automatisk, lydløst og i loop som baggrund. Tekstindholdet er centreret oven på et overlay. Bruges til stemningsvideoer uden lyd.

**Eksempel på HTML-output:**
```html
<div class="banner banner--video">
  <video class="banner__video" autoplay muted loop playsinline>
    <source src="VIDEOFIL.mp4" type="video/mp4" />
  </video>
  <div class="banner__overlay"></div>
  <div class="banner__content">
    <h1 class="banner__title">TITEL</h1>
    <div class="banner__lead">BRØDTEKST</div>
    <a href="KNAP-URL" class="banner__button">KNAPTEKST</a>
  </div>
</div>
```

**Felter:**

| Felt | Type | Påkrævet | Beskrivelse |
|---|---|---|---|
| `videoFile` | Videofil (mp4) | Ja | Videofilen der bruges som baggrund |
| `title` | Tekst | Nej | Overskrift |
| `lead` | Tekst | Nej | Brødtekst |
| `buttonText` | Tekst | Nej | Knaptekst |
| `buttonUrl` | URL | Nej | Knaplink |

> **Bemærk:** Videoen skal altid leveres som `.mp4`. Den afspilles lydløst – brug denne type udelukkende til atmosfæriske baggrundsvideoer. Til videoer med lyd, se type 5.

---

## 5. Klikbar videobanner med afspilningsknap

En video i 16:9-format med en afspilningsknap. Videoen afspilles **ikke** automatisk. Bruges til reklamefilm og produktvideoer **med lyd**.

**Eksempel på HTML-output:**
```html
<div class="banner banner--video banner--16-9 banner--player">
  <video class="banner__video" playsinline>
    <source src="VIDEOFIL.mp4" type="video/mp4" />
  </video>
  <div class="banner__overlay"></div>
  <button class="banner__play-btn" aria-label="Afspil video"></button>
  <div class="banner__content">
    <h1 class="banner__title">TITEL</h1>
    <div class="banner__lead">BRØDTEKST</div>
    <a href="KNAP-URL" class="banner__button">KNAPTEKST</a>
  </div>
</div>
```

**Felter:**

| Felt | Type | Påkrævet | Beskrivelse |
|---|---|---|---|
| `videoFile` | Videofil (mp4) | Ja | Videofilen – vises i 16:9-format |
| `title` | Tekst | Nej | Overskrift – vises i bunden af banneret før afspilning |
| `lead` | Tekst | Nej | Brødtekst – vises i bunden før afspilning |
| `buttonText` | Tekst | Nej | Knaptekst |
| `buttonUrl` | URL | Nej | Knaplink |

> **Bemærk:** Videoen må **ikke** have `muted` eller `autoplay`. Lyd afspilles, når brugeren klikker. Under afspilning skjules tekst og overlay, og native videokontroller (pause, lydstyrke, fuldskærm) vises. Når videoen slutter, vises afspilningsknap og tekst igen.

---

## Oversigt over alle felter

| Felt | Loopende video | Klikbar video | Standard billede | Lyst billede | Hero billede |
|---|:---:|:---:|:---:|:---:|:---:|
| `backgroundImage` | – | – | ✅ | ✅ | ✅ |
| `videoFile` | ✅ | ✅ | – | – | – |
| `coverImage` | – | – | ✅ | ✅ | – |
| `coverImageWidth` | – | – | ✅ | ✅ | – |
| `contentWidth` | – | – | ✅ | ✅ | – |
| `layout` (spejlvendt) | – | – | ✅ | ✅ | – |
| `darkContentBg` | – | – | ✅ | – | – |
| `lightMode` | – | – | – | – | ✅ |
| `backgroundColor` | – | – | – | – | ✅ |
| `minHeight` | – | – | – | – | ✅ |
| `title` | ✅ | ✅ | ✅ | ✅ | ✅ |
| `lead` | ✅ | ✅ | ✅ | ✅ | ✅ |
| `buttonText` | ✅ | ✅ | ✅ | ✅ | ✅ |
| `buttonUrl` | ✅ | ✅ | ✅ | ✅ | ✅ |
