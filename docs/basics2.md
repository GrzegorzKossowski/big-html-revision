<a href='../README.md' id='top' style='border: 1px solid gold; padding: 5px; color: gold'>← back to README.md</a>

# Colors

Kolory mogą być podawane na kilka sposobów: RGB, HEX, HSL, RGBA, or HSLA lub predefiniowanej nazwy.

```html
<h1 style="background-color:rgb(255, 99, 71);">...</h1>
<h1 style="background-color:#ff6347;">...</h1>
<h1 style="background-color:hsl(9, 100%, 64%);">...</h1>
```

## RGB, RGBA

`rgb(red, green, blue, alpha)`

wartości zawierają się między 0 (czarny) a 255 (biały) - 32 bitowy kanał na każdy kolor, ~16+ milionów możliwości. Alpha od 0 (przezroczyste) do 1 (nieprzezroczyste)

## HEX

`#rrggbb`

Zapis szesnastkowy tych samych wartości.

## HSL, HSLA

`hsl(hue, saturation, lightness)`

`hsla(hue, saturation, lightness, alpha)`

Wartości procentowe, gdzie hue to kąt na kole kolorów, saturation to nasycenie barwą, intensywność, a lightness to jasność koloru (białe-czarne).

# CSS

Css to kaskadowe arkusze stylów nadające widok. Rozróżniamy trzy warstwy:

Inline - używane bezpośrednio w elemencie jako atrybut `<style>`

```html
<h1 style="color:blue;">A Blue Heading</h1>
```

Internal - używane w sekcji `<head>` jako `<style>` element

```html
<head>
    <style>
        body {
            background-color: powderblue;
        }
        h1 {
            color: blue;
        }
        p {
            color: red;
        }
    </style>
</head>
```

External - z zewnętrznego pliku za pomocą elementu `<link>` zawartego w nagłówku `<head>`

```html
<head>
    <link rel="stylesheet" href="styles.css" />
</head>
```

W tej kolejności są też używane pod względem ważności. Ten bliższy elementu jest ważniejszy. Dalszy jest nadpisywany.

`<style>` definiuje style dla dokumentu

`<link>` definiuje ścieżkę dla zewnętrznego dokumentu css

# Links

Linki (hyperlinks) służą do przechodzenia ze strony na stronę. Używają tagu `<a>` (anchor).
Składnia:
`<a href="url">link text</a>`

Atrybut href to referencja do zasobu, strony, mogą to być także przekierowania do aplikacji systemowych - mail, phone itp.
`<a href="mailto:someone@example.com">Send email</a>`

Linki mogą przyjąć kilka stanów, jak active, visited, unvisited. W css muszą być jednak podane w odpowiedniej kolejności.

Linki mają atrybut target, który decyduje o tym, jak zachowa się przeglądarka.

`_self` - Defaultowy. Otwiera w tym samym oknie (zakładce)
`_blank` - Otwiera w nowej zakładce
`_parent` - Otwiera w nadrzędnej sekcji (frame), jeśli jest używana
`_top` - Opens the document in the full body of the window?

Linki mogą być absolutne lub relatywne do dokumentu z którego wychodzą.
Przyjmują także inne atrybuty, jak np. title.

### Bookmarki

Aby przeskoczyć do miejsca w tym samym dokumencie, można utworzyć referencę przez id z `#`

```html
<a href="#C4">Jump to Chapter 4</a>
<h2 id="C4">Chapter 4</h2>
```

# Images

Do osadzania obrazków służy element `<img>`.

```html
<img src="url" alt="alternate text" />
```

Przyjmuje kilka atrybutów.

-   alt - pozwala umieścić zastępczy tytuł obrazka, o ile ten nie załaduje się
-   src - to link do zasobu
-   width, height - wymiary obrazka w pixelach `<img src="img_girl.jpg" alt="Girl in a jacket" width="500" height="600">`

Aby ustawić obrazek w tekście, można użyć float.

```html
<p>
    <img
        src="smiley.gif"
        alt="Smiley face"
        style="float:right;width:42px;height:42px;"
    />
    The image will float to the right of the text.
</p>
```

Dodatkowe taki medialne

`<picture>` pozwala na wskazanie kilku źródeł zależnie od wymiarów oraz ostatecznego obrazka. Przeglądarka będzie pobierać najpierw obrazek dostosowany do wymiaru, a dopiero potem pozostały.

```html
<picture>
    <source media="(min-width:650px)" srcset="img_pink_flowers.jpg" />
    <source media="(min-width:465px)" srcset="img_white_flower.jpg" />
    <img src="img_orange_flowers.jpg" alt="Flowers" style="width:auto;" />
</picture>
```

`<map>` - pozwala na wyznaczanie fragmentów obrazu, które mogą służyć jako linki do innych stron. W `<img>` łączy z mapą atrybut `usemap`.

```html
<img
    src="workplace.jpg"
    alt="Workplace"
    usemap="#workmap"
    width="400"
    height="379"
/>
<map name="workmap">
    <area
        shape="rect"
        coords="34,44,270,350"
        alt="Computer"
        href="computer.htm"
    />
    <area shape="rect" coords="290,172,333,250" alt="Phone" href="phone.htm" />
    <area
        shape="circle"
        coords="337,300,44"
        alt="Cup of coffee"
        href="coffee.htm"
    />
</map>
```

# Favicon

Favikon jest małym obrazkiem, ikoną, która pojawia się w tabie zakładki, obok tytułu (nazwy).
Podaje się go w nagłówku, jako <link> z odpowiednim atrybutem rel.

```html
<link rel="icon" type="image/x-icon" href="/images/favicon.ico" />
```

# Tables

Tabela zawiera komórki wewnątrz rzędów i kolumn.

```html
<table>
    <!--- table -->
    <tr>
        <!--- row -->
        <th>Company</th>
        <!--- nagłówek, header -->
    </tr>
    <tr>
        <td>Alfreds Futterkiste</td>
        <!--- komórka, kolumna, table data -->
    </tr>
</table>
```

Szersze info na temat tabel: <a href='https://www.w3schools.com/html/html_tables.asp'>tutaj</a>

# Lists

Listy służą do prezentowania treści zebranych w grupy. Do wyboru są listy nieporządkowane i porządkowane (numerowane), oraz listy opisowe (description).

### `<ul>` - listy nieuporządkowane

Listy unordered oznaczane są symbolami (dots, sqares, itp), listy porządkowane - cyframi lub literami.

`disc` - defaultowe

`circle` - Sets the list item marker to a circle

`square` - Sets the list item marker to a square

`none` - The list items will not be marked

```html
<ul style="list-style-type:disc;">
    <li>Coffee</li>
    <li>Tea</li>
    <li>Milk</li>
</ul>
```

<ul style="list-style-type:disc;">
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ul>

### `<ol>` - listy uporządkowane

Listy uporządkowane mogą mieć rózne markery:

`type="1"` The list items will be numbered with numbers (default)

`type="A"` The list items will be numbered with uppercase letters

`type="a"` The list items will be numbered with lowercase letters

`type="I"` The list items will be numbered with uppercase roman numbers

`type="i"` The list items will be numbered with lowercase roman numbers

Można oznaczyć atrybut startu dla listy

```html
<ol type="1" start="50">
    <li>Coffee</li>
    <li>Tea</li>
    <li>Milk</li>
</ol>
```

<ol type="1" start="50">
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ol>

### `<dl>` - listy opisowe

`<dl>` - lista opisowa

`<dt>` - temat, termin (term)

`<dd>` - opis, description

```html
<dl>
    <dt>Coffee</dt>
    <dd>- black hot drink</dd>
    <dt>Milk</dt>
    <dd>- white cold drink</dd>
</dl>
```

<dl>
  <dt>Coffee</dt>
  <dd>- black hot drink</dd>
  <dt>Milk</dt>
  <dd>- white cold drink</dd>
</dl>

# Block & Inline

Każdy element ma pewien rodzaj zachowania, w szczególności, jak jest rysowany. Niektóre elementy są blokowe `<div>` `<p>`, inne rysowane w linii `<span>` `<strong>`, inne mają defaultowe marginesy `<h>`, `<p>`

Elementy blokowe:

```html
<div style="’border:" 1px solid yellow;’>
    The
    <div>
        element is a block-level element.
        <div></div>
    </div>
</div>
```

<div style="’border: 1px solid yellow;">The <code>div</code> element is a block-level element.<div>

`<address>` `<article>` `<aside>` `<blockquote>` `<canvas>` `<dd>` `<div>` `<dl>` `<dt>` `<fieldset>` `<figcaption>` `<figure>` `<footer>` `<form>< `h1>-`<h6>` `<header>` `<hr>` `<li>` `<main>` `<nav>` `<noscript>` `<ol>` `<p>` `<pre>` `<section>` `<table>` `<tfoot>` `<ul>` `<video>`

Elementy inline:

```html
<p>This is <span>a <span> element inside</span> a paragraph.</p>
```

<p>This is <span style='color: red'>a < span > element inside</> a paragraph.<p>

`<a>` `<abbr>` `<acronym>` `<b>` `<bdo>` `<big>` `<br>` `<button>` `<cite>` `<code>` `<dfn>` `<em>` `<i>` `<img>` `<input>` `<kbd>` `<label>` `<map>` `<object>` `<output>` `<q>` `<samp>` `<script>` `<select>` `<small>` `<span>` `<strong>` `<sub>` `<sup>` `<textarea>` `<time>` `<tt>` `<var>`

# Classes

Atrybut class pozwala na wstawienie odnośnika klasy do arkusza styli css
Możliwe jest wykorzystanie wielu klas w jednym atrybucie.

```html
<h2 class="city main">London</h2>
```

`var el = document.querySelector(".myclass");`

Użycie w JS przez classList()

```js
const div = document.createElement('div');
div.className = 'foo';

// our starting state: <div class="foo"></div>
console.log(div.outerHTML);

// use the classList API to remove and add classes
div.classList.remove('foo');
div.classList.add('anotherclass');

// <div class="anotherclass"></div>
console.log(div.outerHTML);

// if visible is set remove it, otherwise add it
div.classList.toggle('visible');

// add/remove visible, depending on test conditional, i less than 10
div.classList.toggle('visible', i < 10);

console.log(div.classList.contains('foo'));

// add or remove multiple classes
div.classList.add('foo', 'bar', 'baz');
div.classList.remove('foo', 'bar', 'baz');

// add or remove multiple classes using spread syntax
const cls = ['foo', 'bar'];
div.classList.add(...cls);
div.classList.remove(...cls);

// replace class "foo" with class "bar"
div.classList.replace('foo', 'bar');
```

# Id

Atrybut id wykorzystywany jest do unikalnego zaznaczenia elementu na stronie.

```html
<h1 id="myHeader">My Header</h1>
<h1 id="yourHeader">Your Header</h1>
```

Id może być wykorzystywane w linkach jako kotwica do bookmarków.

```html
<a href="#C4">Jump to Chapter 4</a>
<h2 id="C4">Chapter 4</h2>
```

również na innych stronach
`<a href="html_demo.html#C4">Jump to Chapter 4</a>`

Użycie w JS przez getElementById(‘someId’) lub querySelector

```js
document.getElementById('myHeader').innerHTML = 'Have a nice day!';
document.querySelector('#myHeader').innerHTML = 'Have a nice day!';
```


