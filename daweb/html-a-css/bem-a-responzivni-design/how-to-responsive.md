## Kódování responzivních stránek

### Meta značka viewport

Prvním krokem pro tvorbu responzivního webu je přidat `meta` značku `viewport` v hlavičce HTML se správným nastavením atributu `content`. To zajistí, že se obsah stránky bude přizpůsobovat šířce zařízení a že nebude prohlížečem nijak _přizoomovaný_ nebo _odzoomovaný_. Bez použití této značky použije prohlížeč defaultní rozměr 980px a stránku dostatečně oddálí, aby se vmáčkla na menší zařízení. (HTML šablona generovaná přes emmet má toto nastavení automaticky a není třeba ho přidávat).

```html
<html>
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>Document Title</title>
  </head>
  <body>
    ...
  </body>
</html>
```

::fig[Meta viewport]{src=assets/meta-viewport.png}

## Techniky responzivního webdesignu

Máme tři hlavní techniky responzivního webdesignu:

- flexibilní layout
- flexibilní obrázky
- media queries

V této lekci si projdeme flexibilní layout.

### Flexibilní layout

Pro tvorbu flexibilního layoutu pomáhá designérům rozvržení stránky do gridu, neboli mřížky. Jde o systém sloupců a řádků, kde elementy zabírají vždy nějaký poměr stránky nehledě na velikost zařízení. Při změně velikosti zařízení si prvky na stránce drží svůj poměr, nebo se zalomí pod sebe, pokud už je prostor nedostačující. Oproti neresponzivním webům tak třeba několikasloupcový grid nepřeteče mimo viewport menšího zařízení, ale zmenší se jeho počet sloupců.

::fig[grid-responzivni]{src=assets/grid-gif.gif}

#### Relativní jednotky

Pružného layoutu, který se přizpůsobí jakékoli velikosti stránek, dosáhneme pomocí relativních jednotek jako jsou procenta, `vw` a `vh`. Díky nim budou elementy na stránce zabírat stejný poměr prostoru nehledě na velikost zařízení. Mřížku např. tří sloupců, které budou na všech zařízeních zabírat 1/3 stránky, tak jednoduše vytvoříme pomocí procent a funkce `calc()`.

```css
width: calc(100% / 3);
```

#### Flexbox

Další nástroj pro tvorbu responzivního layoutu už znáte - je to flexbox. S ním snadno zařídíte např. responzivní galerii obrázků, které se budou zalamovat pod sebe při zmenšení obrazovky. Zásadní je tady vlastnost `flex-wrap`, pomocí které nastavíme automatické zalamování.

```css
.container {
  display: flex;
  flex-wrap: wrap;
}
```

#### CSS Grid

Poslední nástroj, který musíme zmínit, ale který není součástí našeho kurzu je CSS Grid. V rámci samostudia si můžete pročíst, [jak se s ním nastavují řádky a sloupce layoutu](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout).
