<a href='../README.md' id='top' style='border: 1px solid gold; padding: 5px; color: gold'>← back to README.md</a>

# Basic

html5.2 dokumentacja opublikowana w 2017 r.

-   Html standardowy makup language
-   Html opisuje wygląd strony
-   przekazuje przeglądarce, jak narysować dokument
-   labeluje zawartość tagami formatującymi

Basic html page

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Page Title</title>
    </head>
    <body>
        <h1>My First Heading</h1>
        <p>My first paragraph.</p>
    </body>
</html>
```

```html
<tag>content</tag> <br />
- without closing tag
```

Document structure

```
<!DOCTYPE html> - deklaracja dokumentu HTML5
<html> - root dokumentu
<head> sekcja meta (title, styles, etc.)
<body> - widoczna część dokumentu
```

## H tags - headers

`<h1> - <h6> examples`

<h1>H1 example</h1>
<h6>H6 example</h6>

`<p>` tag paragrafu

`<a>` tag linku, atrybuty m.in. _href_ - link do innego urla

`<img>` tag obrazka, atrybuty m.in. _src_ - link do obrazka

# Elements

Element jest zestawem tag, atrybut, zawartość

`<tagname>Content goes here...</tagname>`

Elementy mogą być zagnieżdżane

# Attributes

Elementy mają atrybuty w pierwszym tagu. Występują w formacie klucz=”wartość”

Przykładowe atrybuty:

-   href link url dla a
-   src źródło obrazu dla img, width wysokość obrazka img, alt zastępczy tekst dla obrazka
-   style używany do dodawania styli na poziomie tagu
-   lang atrybut wskazujący język strony
-   title definiuje popup danego elementu, komentarz, opis po najechaniu myszą

Niektóre atrybuty mogą mieć wartosci boolean
```html
<input type="text" disabled="disabled">
<input type="text" disabled>
```


# Headings

`<h1> - <h6> przykłady`

<h1>H1 example</h1>
<h6>H6 example</h6>

`<h>` tag
Tagi nagłówków (header) zawierają sie w przedziale `<h1>` do `<h6>` malejąco w rozmiarze czcionki. Służą do strukturyzowania ważności treści. Nie mogą zastępować boldowania. Wykorzystywane przez silniki wyszukiwarek do pozycjonowania treści zawartości.

Nagłówki mają defaultowe style, ale można je stylować wedle uznania.
`<h1 style="font-size:60px;">Heading 1</h1>`

# Paragraphs

Paragraf zawsze zaczyna nową linię. Jest blokiem tekstu z automatycznie dodanym marginesem górnym i dolnym.
`<p>This is a paragraph.</p>`

<p>This is a paragraph.</p>

Przeglądarka automatycznie usuwa zbędne, nadmiarowe białe znaki. Trzeba zastosować inny tag, by zachować strukturę tekstu: `<pre>`.

```html
<p>Defines a paragraph</p>
<hr />
Defines a thematic change in the content <br />
Inserts a single line break
<pre>	Defines pre-formatted text</pre>
```

# Styles

Atrybut style służy do stylowania konkretnego tagu. Raczej unikać ze względu na trudność utrzymania kodu. Jest najbliżej, więc jest najważniejszy.

` <tagname style="property:value;">`

# Formatting

Niektóre elementy służą konkretnemu formatowaniu tekstu - boldowanie, kursywa itp.

-   `<b>` - element <b>pogrubiony</b>, bez większego znaczenia
-   `<strong>` - tekst o większej <strong>ważności</strong>
-   `<i>` - <i>kursywa</i>
-   `<em>` - emfaza, podkreślenie - <em>ważne dla czytników dla niewidomych</em>
-   `<mark>` - tekst <mark>podświetlony</mark>, zaznaczony, wyróżniający się
-   `<small>` - czcionka będzie automatycznie <small>pomniejszona</small>
-   `<del>` - tekst widoczny, ale <del>przekreślony</del>
-   `<ins>` - tekst <ins>wstawiony</ins> zamiast <del>usuniętego</del> - de facto podkreślony (underline)
-   `<sub>` - dolny index tekstu, np H<sub>2</sub>O
-   `<sup>` - górny index tekstu, np. 2<sup>2</sup>=4

# Quotations & Citation

`<blockquote>` definiuje sekcję będącą cytatem. Ma atrybut cite, który jest linkiem do źródła.

<blockquote cite="http://www.worldwildlife.org/who/index.html">For 50 years, WWF has been protecting the future of nature...</blockquote>

```html
<blockquote cite="http://www.worldwildlife.org/who/index.html">
    For 50 years, WWF has been protecting the future of nature...
</blockquote>
```

`<q>` służy do krótkich cytatów wewnątrz linii. Dodaje cudzysłów.

<p>WWF's goal is to: <q>Build a future where people live in harmony with nature.</q></p>

```html
<p>
    WWF's goal is to:
    <q>Build a future where people live in harmony with nature.</q>
</p>
```

`<abbr>` służy do rozwijania w atrybucie znaczenia skrótów, dodaje popup i podkreślenie

<p>The <abbr title="Hyper Text Markup Language">HTML</abbr>  is the standard markup language for creating Web pages.</p>

```html
<p>
    The <abbr title="Hyper Text Markup Language">HTML</abbr> is the standard
    markup language for creating Web pages.
</p>
```

`<address>` służy do dodawania danych kontaktowych. Zawsze dodaje breakline na początku i końcu.

<address>
Written by John Doe.<br>
Visit us at:<br>
Example.com<br>
Box 564, Disneyland<br>
USA
</address>

```html
<address>
    Written by John Doe.<br />
    Visit us at:<br />
    Example.com<br />
    Box 564, Disneyland<br />
    USA
</address>
```

`<cite>` służy do oznaczania tytułów książek, artykułów itp w tekście.

<p><cite>The Scream</cite> by Edvard Munch. Painted in 1893.</p>

`<p><cite>The Scream</cite> by Edvard Munch. Painted in 1893.</p>`

`<bdo>` odwraca tekst lustrzanie od prawej strony

<bdo dir="rtl">This text will be written from right to left</bdo> ←

`<bdo dir="rtl">This text will be written from right to left</bdo>`

# Comments

Komentarz może być używany w dowolnym miejscu nie rozrywającym kodu.

`<!-- Write your comments here -->`

    <a href='../README.md' style='border: 1px solid gold; padding: 5px; color: gold'>← back to README.md</a>
    <a href='#top' style='border: 1px solid gold; padding: 5px; color: gold'>↑ back to top</a>