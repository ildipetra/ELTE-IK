# HTML

## Tagek
> *dőlt* -> akadálymentességhez/amúgyis kötelező

| Tag | Funkció | Paraméterek, megjegyzések |
| --- | ----    | ---- |
| \<p> | Bekezdés | |
| \<br> | Sortörés | páratlan |
| \<hr> | vízszintes elválasztó vonal |páratlan|
| | **CÍMSOR, LISTÁK**    |  |
| \<hx> | x-es szintű címsor | |
| \<ul> | felsorolás lista||
| \<ol> | számozott lista||
| \<li> | listaelemek||
| | **MÉDIA**    |  |
| \<a> | link | href="webcím/#id_a_htmlen_belül/mailto:emailcím" target="_blank" [új dolalon nyílik meg] |
| \<pre> | előre formázott szöveg ||
| \<code> | kód||
| \<figure> | ábra, illusztráció ||
| \<figcaption> | felirat ||
| \<img> | kép | *src="url"* *alt="képleírás"* title="kiegészítő infó" width="" height=""|
| \<audio> | hang | *src="url.mp3/ogg vorbis"* controls [irányítható gombokkal] loop [folyamatos ismétlés] muted [némítva indul el automatikusan] |
| \<video> | videó | *src="url.mp4/webm"* controls [irányítható gombokkal] loop [folyamatos ismétlés] muted [némítva indul el automatikusan] autoplay [automatikusan elindult] poster [kép (poszter) elérhetősége, amely az indítás előtt látszik]|
| \<iframe> | keret, ppt | *src="url"* *alt="képleírás"* width="" height="" allowfullscreen [engedélyezett a teljes képernyős megjelenés] |
| | **SZÖVEG**    |  |
| \<i> | dőlt ||
| \<em> | hangsúlyos ||
| \<b> | bold, félkövér ||
| \<strong> | erős kiemelés ||
| \<q> | idézet ||
| \<cite> | hivatkozás ||
| \<abbr> | rövidítés ||
| \<time> | idő jelölése | datetime="2008-07-13T20:13" |
| | **TÁBLÁZAT**    |  |
| \<table> | táblázat ||
| \<tr> | sor ||
| \<th> | fjléc cella | scope="col/row" [amire vonatkozik a fejléc] |
| \<td> | adatcella ||
| \<caption> | táblázat felirata ||
| \<details> | táblázat részletei ||
| \<summary> | táblázatbeli blokk felirata ||
| | **BEOSZTÁS**    |  |
| \<div> | csoportosító elemek | (id)|
| \<span> | soron belüli elemek csoportosítása jó | lang="" |
| \<main> |  Fő tartalmi egység meghatározása. |
| \<article> |  Önállóan értelmes tartalmi egység (pl. cikk) |
| \<header> |  Fejléc |
| \<footer> |  Lábléc |
| \<section> |  Szakasz |
| \<nav> |  Navigációs elemek |
| \<aside> |  Kapcsolódó, járulékos információ (jellemzően oldalsáv) |
| \<address> |  Kontakt információ |
| \<article> | cikk | Önálló, más helyen is érthető és megosztható |
| \<section> | szekció | Egy nagyobb egység része, de nem önálló |
| \<address> | kontakt információk | (footerbe általában)|
|  | **FORMSOK**    |  |
| \<form> | form | action="" method="get/post" enctype="text/plain"|
| \<meter> | mérce(?) |value="5" low="3" high="7" optimum="8" min="0" max="10"  !a két tag közti szöveg nem jelenik meg a böngészőben!|
| \<input> | űrlap elem, a type határozza meg, hogy micsoda | type="" value="felirata" |
|*\<label>* | cimke | for="hozzá kapcsolódó űrlapelem id-je"|
| \<textarea> |  ||
| \<fieldset> | űrlapbeli mezők csoportosítása ||
| \<legend> | fieldset neve ||


### input typeok

#### Elküldés gomb
- type="submit"  
- value="felirata"  

#### Alaphelyzet gomb
- type="reset"  
- value="felirata"  

#### Egysoros beviteli mező
- type="text/url/email"  
- name="űrlapelem_neve" 
- id="egyedi azonosító, a címkével való összekötésre"
- size="mező szélessége karakterekben"
- minlength="beírandó szöveg minimális hossza" 
- maxlength="beírandó szöveg maximális hossza"
- placeholder="mezőben megjelenő szöveg (súgó), amely eltűnik gépeléskor"
- required [Ha szerepel, akkor kötelező megadni az adatot]
- value="a mező alapértelmezett értéke"

#### Rádiógombok/jelölőnégyzet
- type="radio/checkbox"  
- name="űrlapelem_neve [RÁDIÓGOMBOKNÁL MINDEGYIKNEK AZONOS NEVŰNEK KELL LENNIE]"  
- id="egyedi azonosító, a címkével való összekötésre"  
- required [Ha szerepel, akkor kötelező megadni az adatot]  
- checked [Ha szerepel, akkor alapból ki lesz jelölve]  
- value="a választókapcsolóhoz tartozó érték"

#### Textarea 
- name="az űrlapelem neve"
- id="egyedi azonosító, a címkével való összekötésre"
- cols="oszlopok száma (karakterben)"
- rows="sorok száma (karakterben)"
- minlength="beírandó szöveg minimális hossza"
- maxlength="beírandó szöveg maximális hossza"
- placeholder="mezőben megjelenő szöveg (súgó), amely eltűnik gépeléskor"
- required [Ha szerepel, akkor kötelező megadni az adatot]

## Emmet jelölések
- html:5 (alap [title + lang átállítandó])
   - \<link rel="stylesheet" href="cssnév.css">
- ul>li*5
- ul>li#idnév$*db
- figure>img+figcaption

## Billentyűparancsok
- ctrl+h    find+replace
- alt+w     tag wrap  
- F2        tag lecserélése
- alt+shift+i  add cursor to line ends
- ctrl+k ctrl+s   keyboard shortcut list in vscode

https://syntaxsimplified.com/cheatsheet/HTML/hypertext_markup_language.html

Néhány gyakran használt globális paraméter:
- **title**: az elemhez tartozó feliratot adhatjuk meg, amely legtöbbször
akkor jelenik meg, ha az elem fölé visszük az egeret, de speciális
jelentése is lehet.
- **accesskey**: gyorsbillentyű megadására szolgál. Bármilyen (1 karakter
hosszú) karaktert megadhatunk. A kis- és nagybetűk különböznek.
- **id**: az elemet egyedi azonosítóval láthatjuk el.
   - hivatkozás rá: #név
- **class**: az elemet stílus osztályba sorolhatjuk.
- **lang**: segítségével megadhatjuk az adott elem nyelvét. (pl. hu, en, enus, stb.)

> Megjegyzés: <!– ... -->

## CSS
- color
- background-color
- text-align
- font-style
- font-weight
- font-variant
- letter-spacing
- font-size
- font-family

@media

\#id

.class

https://i0.wp.com/www.pushaune.com/wp-content/uploads/2017/11/ULTIMATE_CSS_cheat_sheet_by_PUShAUNE_vertical.jpg?ssl=1



## Hasznos weboldalak

- HTML validátor https://validator.w3.org/
- CSS validátor https://jigsaw.w3.org/css-validator/
- Speciális karakterek https://www.web2generators.com/html-based-tools/online-html-entities-encoder-and-decoder#google_vignette
- Hasznos input elemek https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/input
- Színek https://redketchup.io/color-picker
- Betűtípusok http://www.google.com/fonts
- CSS plate (**nagyon** jó tanuláshoz!!) https://flukeout.github.io/
