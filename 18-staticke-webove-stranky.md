# 18. Statické webové stránky

## Značkovací jazyky

Značkovací jazyky slouží k strukturování a formátování dokumentů. Na rozdíl od programovacích jazyků nepopisují algoritmy, ale způsob, jakým má být obsah zobrazen nebo strukturován.

Hlavní značkovací jazyky:

- **HTML (HyperText Markup Language)** - základní jazyk pro tvorbu webových stránek
- **XML (eXtensible Markup Language)** - obecný značkovací jazyk určený pro strukturování a výměnu dat
- **Markdown** - jednoduchý značkovací jazyk pro formátování prostého textu
- **SGML (Standard Generalized Markup Language)** - předchůdce HTML a XML

Značkovací jazyky fungují na principu vkládání značek (tagů) do textu, které určují, jak se má text zobrazit nebo jaká je jeho sémantická role.

## HTML dokument, element a atribut

### HTML dokument

HTML dokument je textový soubor, který obsahuje značky a text. Každý HTML dokument má příponu `.html` nebo `.htm`.

### Element

**Element** (prvek) je základní stavební blok HTML dokumentu, který se skládá z:
- Počáteční značky (opening tag): `<značka>`
- Obsahu
- Koncové značky (closing tag): `</značka>`

Například: `<p>Toto je odstavec.</p>`

Některé elementy nemají žádný obsah a jsou tzv. *prázdné* (self-closing), například: `<img src="obrazek.jpg" alt="Popis obrázku">` nebo `<br>`.

### Atribut

**Atributy** poskytují dodatečné informace o elementu a jsou vždy umístěny v počáteční značce. Mají tento formát:

```html
<značka atribut="hodnota">Obsah</značka>
```

Například v elementu `<a href="https://www.example.com">Odkaz</a>` je `href` atribut s hodnotou `https://www.example.com`.

Běžné atributy:
- `id` - jedinečný identifikátor elementu
- `class` - třída elementu pro CSS stylování
- `style` - inline CSS styly
- `src` - zdroj pro obrázky, skripty atd.
- `href` - odkaz pro hypertextové odkazy
- `alt` - alternativní text pro obrázky

## Struktura HTML dokumentu

Standardní struktura HTML dokumentu vypadá takto:

```html
<!DOCTYPE html>
<html lang="cs">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Název stránky</title>
    <link rel="stylesheet" href="style.css">
    <script src="script.js"></script>
</head>
<body>
    <!-- Obsah stránky -->
    <header>
        <h1>Nadpis stránky</h1>
    </header>
    <main>
        <p>Hlavní obsah stránky.</p>
    </main>
    <footer>
        <p>Patička stránky.</p>
    </footer>
</body>
</html>
```

### Základní části:

1. **Deklarace typu dokumentu** (`<!DOCTYPE html>`) - informuje prohlížeč o verzi HTML
2. **Kořenový element** (`<html>`) - obaluje celý dokument
3. **Hlavička** (`<head>`) - obsahuje metadata a odkazy na externí soubory
   - `<meta>` - metadata o dokumentu
   - `<title>` - název stránky zobrazený v záložce prohlížeče
   - `<link>` - připojení externích zdrojů (např. CSS)
   - `<script>` - připojení nebo definice JavaScriptu
4. **Tělo dokumentu** (`<body>`) - obsahuje viditelný obsah stránky

### Sémantické strukturování obsahu:

- `<header>` - záhlaví stránky nebo sekce
- `<nav>` - navigační sekce
- `<main>` - hlavní obsah stránky
- `<article>` - samostatný obsah
- `<section>` - tematická skupina obsahu
- `<aside>` - boční panel, související obsah
- `<footer>` - patička stránky nebo sekce

## Párové značky

Většina HTML elementů jsou párové, což znamená, že mají počáteční a koncovou značku:

```html
<h1>Nadpis první úrovně</h1>
<p>Odstavec textu.</p>
<div>Blokový element pro seskupení obsahu.</div>
<span>Řádkový element pro seskupení obsahu.</span>
```

Hlavní párové značky:

### Nadpisy:
```html
<h1>Nadpis první úrovně</h1>
<h2>Nadpis druhé úrovně</h2>
<!-- ... -->
<h6>Nadpis šesté úrovně</h6>
```

### Odstavce a formátování textu:
```html
<p>Odstavec textu.</p>
<strong>Tučný text</strong>
<em>Kurzíva</em>
<mark>Zvýrazněný text</mark>
<code>Kód</code>
<pre>Předformátovaný text</pre>
```

### Seznamy:
```html
<ul>
    <li>Položka nečíslovaného seznamu</li>
    <li>Další položka</li>
</ul>

<ol>
    <li>Položka číslovaného seznamu</li>
    <li>Další položka</li>
</ol>

<dl>
    <dt>Termín</dt>
    <dd>Definice termínu</dd>
</dl>
```

### Tabulky:
```html
<table>
    <thead>
        <tr>
            <th>Hlavička 1</th>
            <th>Hlavička 2</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Buňka 1</td>
            <td>Buňka 2</td>
        </tr>
    </tbody>
</table>
```

### Formuláře:
```html
<form action="/submit" method="post">
    <label for="jmeno">Jméno:</label>
    <input type="text" id="jmeno" name="jmeno">
    
    <textarea name="zprava" rows="4" cols="50"></textarea>
    
    <select name="moznosti">
        <option value="1">První možnost</option>
        <option value="2">Druhá možnost</option>
    </select>
    
    <button type="submit">Odeslat</button>
</form>
```

## Nepárové značky

Nepárové (self-closing) značky nemají koncovou značku, protože neobsahují žádný obsah:

```html
<img src="obrazek.jpg" alt="Popis obrázku">
<br> <!-- Zalomení řádku -->
<hr> <!-- Horizontální čára -->
<input type="text" name="jmeno">
<meta charset="UTF-8">
<link rel="stylesheet" href="style.css">
```

## Připojení dalších dokumentů

HTML dokument může být propojen s dalšími soubory, jako jsou styly, skripty, obrázky a další prvky.

### Připojení stylů CSS:

```html
<!-- Externí stylový soubor -->
<link rel="stylesheet" href="style.css">

<!-- Interní styl v hlavičce -->
<style>
    body {
        background-color: lightblue;
    }
    p {
        color: navy;
    }
</style>

<!-- Inline styl přímo v elementu -->
<p style="color: red; font-size: 16px;">Tento text je červený.</p>
```

### Připojení skriptů JavaScript:

```html
<!-- Externí soubor s JavaScriptem -->
<script src="script.js"></script>

<!-- Interní JavaScript -->
<script>
    function pozdrav() {
        alert("Ahoj světe!");
    }
</script>

<!-- Inline JavaScript v elementu -->
<button onclick="alert('Ahoj!')">Klikni na mě</button>
```

### Vkládání obrázků:

```html
<img src="obrazek.jpg" alt="Popis obrázku" width="300" height="200">
```

### Vkládání videa:

```html
<video width="320" height="240" controls>
    <source src="video.mp4" type="video/mp4">
    Váš prohlížeč nepodporuje tag video.
</video>
```

### Vkládání audia:

```html
<audio controls>
    <source src="audio.mp3" type="audio/mpeg">
    Váš prohlížeč nepodporuje tag audio.
</audio>
```

### Připojení favicony:

```html
<link rel="icon" href="favicon.ico" type="image/x-icon">
```

## Hypertext

Hypertext je text, který obsahuje odkazy (hyperlinky) na jiné texty. Tento koncept je základem webu a umožňuje propojení dokumentů.

### Vytvoření hypertextového odkazu:

```html
<a href="https://www.example.com">Navštivte Example.com</a>
```

### Typy odkazů:

1. **Absolutní URL** - úplná webová adresa:
   ```html
   <a href="https://www.example.com/stranka.html">Odkaz</a>
   ```

2. **Relativní URL** - adresa relativní k aktuálnímu dokumentu:
   ```html
   <a href="podstranka.html">Podstránka</a>
   <a href="../nadrazena-stranka.html">Nadřazená stránka</a>
   ```

3. **Odkaz na ID v dokumentu** (kotva):
   ```html
   <a href="#sekce1">Přejít na sekci 1</a>
   
   <!-- Někde jinde v dokumentu -->
   <h2 id="sekce1">Sekce 1</h2>
   ```

4. **Odkaz na e-mail**:
   ```html
   <a href="mailto:info@example.com">Napište nám</a>
   ```

5. **Odkaz na telefonní číslo**:
   ```html
   <a href="tel:+420123456789">Zavolejte nám</a>
   ```

### Atributy odkazu:

- `target` - určuje, kde se má odkaz otevřít:
  ```html
  <a href="https://www.example.com" target="_blank">Otevřít v novém okně</a>
  ```
  - `_blank` - nové okno/záložka
  - `_self` - stejné okno/záložka (výchozí)
  - `_parent` - rodičovský rámec
  - `_top` - celé okno

- `rel` - vztah mezi aktuální a odkazovanou stránkou:
  ```html
  <a href="https://www.example.com" rel="nofollow">Odkaz</a>
  ```
  - `nofollow` - říká vyhledávačům, aby nesledovaly odkaz
  - `noopener` - zabraňuje novému oknu přístupu k původnímu oknu (bezpečnost)
  - `noreferrer` - neposílá informace o původní stránce

## Vložené dokumenty a objekty

### Iframe (Inline Frame)

Iframe umožňuje vložit jeden HTML dokument do druhého:

```html
<iframe src="https://www.example.com" width="600" height="400" frameborder="0"></iframe>
```

Atributy iframu:
- `src` - URL zdroje
- `width` a `height` - rozměry
- `frameborder` - šířka rámečku
- `sandbox` - omezení funkcí vloženého obsahu
- `allow` - povolení specifických funkcí (např. kamery, mikrofonu)

### Vložení objektu (Object)

Element `<object>` je univerzální způsob vkládání externího obsahu:

```html
<object data="dokument.pdf" type="application/pdf" width="600" height="400">
    <p>Váš prohlížeč nedokáže zobrazit PDF. <a href="dokument.pdf">Stáhněte si soubor</a>.</p>
</object>
```

### Vložení interaktivního obsahu (Embed)

Element `<embed>` slouží k vložení externího obsahu, který vyžaduje plugin:

```html
<embed src="flash.swf" type="application/x-shockwave-flash" width="300" height="200">
```

### Vložení SVG (Scalable Vector Graphics)

SVG můžete vložit přímo do HTML:

```html
<svg width="100" height="100">
    <circle cx="50" cy="50" r="40" stroke="black" stroke-width="3" fill="red" />
</svg>
```

## Obrázkové mapy

Obrázkové mapy umožňují definovat klikatelné oblasti na obrázku, kde každá oblast může být spojena s jiným odkazem.

### Klientská obrázková mapa:

```html
<img src="mapa.jpg" alt="Mapa" usemap="#mapovacimapa">

<map name="mapovacimapa">
    <!-- Obdélníková oblast -->
    <area shape="rect" coords="34,44,270,350" href="oblast1.html" alt="Oblast 1">
    
    <!-- Kruhová oblast -->
    <area shape="circle" coords="337,300,44" href="oblast2.html" alt="Oblast 2">
    
    <!-- Mnohoúhelníková oblast -->
    <area shape="poly" coords="140,121,181,116,204,160,204,222,191,270,140,329,85,271,72,231,72,174,94,134" href="oblast3.html" alt="Oblast 3">
</map>
```

### Části obrázkové mapy:

1. **`<img>` element** s atributem `usemap`, který odkazuje na mapu
2. **`<map>` element** s jedinečným jménem
3. **`<area>` elementy** definující klikatelné oblasti

### Atributy elementu `<area>`:

- `shape` - tvar oblasti:
  - `rect` - obdélník
  - `circle` - kruh
  - `poly` - mnohoúhelník
  - `default` - celý obrázek
  
- `coords` - souřadnice oblasti (v pixelech):
  - Pro `rect`: "levý,horní,pravý,dolní"
  - Pro `circle`: "střed-x,střed-y,poloměr"
  - Pro `poly`: "x1,y1,x2,y2,...,xn,yn"
  
- `href` - URL odkazu
- `alt` - alternativní text (pro přístupnost)
- `target` - kde se má odkaz otevřít

### Použití obrázkových map:

1. **Geografické mapy** - kliknutí na různé regiony
2. **Navigační prvky** - komplexní grafická navigace
3. **Interaktivní diagramy** - různé části diagramu vedou na různé odkazy

## Výhody a nevýhody statických webových stránek

### Výhody:
- Rychlé načítání - nevyžadují zpracování na serveru
- Jednoduché nasazení - stačí je nahrát na webhosting
- Bezpečnost - minimální riziko napadení
- Snadná archivace - stránky jsou jen soubory
- Nízké nároky na hosting

### Nevýhody:
- Omezená interaktivita bez JavaScriptu
- Složitá aktualizace rozsáhlých webů
- Nepodporují dynamický obsah bez skriptů
- Žádná personalizace pro uživatele
- Žádná databázová funkcionalita

## Souhrn

Statické webové stránky jsou základem všech webových technologií. Přestože moderní webové aplikace často využívají složité dynamické technologie, pochopení principů HTML a struktury statických stránek je nezbytné pro každého webového vývojáře.

HTML poskytuje strukturu a sémantiku, CSS přidává vizuální styl a JavaScript interaktivitu. I když statické stránky mají své limity, jejich jednoduchost, rychlost a nízké nároky na zdroje z nich stále činí praktické řešení pro mnoho typů webů.
