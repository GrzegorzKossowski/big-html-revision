<a href='../README.md' id='top' style='border: 1px solid gold; padding: 5px; color: gold'>← back to README.md</a>

# JavaScript

JS dodaje interaktywność do strony www. Służy do tego tag `<script>`. Można dodawać go w nagłówku `<header>` lub w ciele strony `<body>`.

```html
<!DOCTYPE html>
<html>
    <head>
        <script src="myScript.js" defer></script>
    </head>
    <body>
        <p>some text here</p>
        <script src="myScript.js"></script>
    </body>
</html>
```

Jeśli klient wyłączy obsługę JS, nie zobaczy jego działania. Wtedy należy dodać tag `<noscript>` z opisem sytuacji.

```js
<script>
  document.getElementById("demo").innerHTML = "Hello JavaScript!";
</script>
<noscript>
  Sorry, your browser does not support JavaScript!
</noscript>
```

# File Paths

Rozróżniamy ścieżki absolutne (absolute) czyli pełny link

```html
<img src="https://www.w3schools.com/images/picture.jpg" alt="Mountain" />
```

i relatywne (relative) względem pliku lokalnie

```html
<img src="/images/picture.jpg" alt="Mountain" />
```

# Head

`<head>` element zawiera meta dane dotyczące strony. Wśród tych tanych są m.in.:

`<title>` - tytuł strony (trafia na zakładkę, do ulubionych, do wyników wyszukiwania)

```html
<head>
    <title>A Meaningful Page Title</title>
</head>
```

`<style>` - style strony internal (wewnętrzne)

```html
<style>
    p {
        color: blue;
    }
</style>
```

`<meta>` - dane dodatkowe, takie jak zestaw znaków, słowa kluczowe, autora, ustawienia widoku

```html
<meta charset="UTF-8" />
<meta name="description" content="Free Web tutorials" />
<meta name="keywords" content="HTML, CSS, JavaScript" />
<meta name="author" content="John Doe" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```

`width=device-width` ustawia szerokość strony do szerokości urządzenia, co skaluje widok odpowiednio

`initial-scale=1.0` ustawia początkowe powiększenie przy pierwszym ładowaniu, tu 1:1

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```

`<link>` - linki do źródeł zewnętrznych, m.in. zewnętrznych css

```html
<link rel="stylesheet" href="mystyle.css" />
```

`<script>` - skrypty js

```html
<script>
    function myFunction() {
        document.getElementById('demo').innerHTML = 'Hello';
    }
</script>
```

`<base>` - ustawia bazowy url storny, adres domowy

```html
<head>
    <base href="https://www.w3schools.com/" target="_blank" />
</head>
```

# Layout

Niektóre elementy mają znaczenie sematyczne. Dotyczą pewnych elementów na stronie, które są przypisane do znaczenia.

`<header>` - definiuje nagłówek strony

`<nav>` - definiuje zestaw linków służących do nawigacji po aplikacji, stronie

`<section>` - definiuje sekcję w dokumencie

`<article>` - definiuje niezależny, pełny fragment dokumentu

`<aside>` - definiuje poboczny fragment, sidebar, treść inną, niż główna

`<footer>` - definiuje stopkę strony

`<details>` - definiuje dodatkowe dane, które można pobrać lub odsłonić na życzenie

`<summary>` - definiuje nagłówek, podsumowanie, dla elementu `<details>`

Ponadto layout można ustawiać za pomocą technik css, jak `float`, `flex`, `grid`.

# Responsive

Strona responsywna to taka, która dobrze wygląda na różnych urządzeniach.

Podstawowym tagiem jest `<meta>` ustawiająca szerokość oraz skalowanie

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```

`width` - podawana w % będzie się automatycznie skalować do rozmiaru rodzica.

```html
<img src="img_girl.jpg" style="width:100%;" />
```

`max-width` - ogranicza wielkoś obrazka do podanej.

```html
<img src="img_girl.jpg" style="max-width:100%;height:auto;" />
```

`<picture>` - zależnie od szerokości ekranu mogą być wyświetlane różne źródła.

```html
<picture>
    <source srcset="img_smallflower.jpg" media="(max-width: 600px)" />
    <source srcset="img_flowers.jpg" media="(max-width: 1500px)" />
    <source srcset="flowers.jpg" />
    <img src="img_smallflower.jpg" alt="Flowers" />
</picture>
```

`viewport width` (vw) - zależy od szerokości ekranu. Można użyć do skalowania elementów.

```html
<h1 style="font-size:10vw">Hello World</h1>
```

`medaiQueries` (css) - pozwalają na ustawienie breakpointów, przy których następuje przypisanie stylu.

```html
<style>
    /* Use a media query to add a breakpoint at 800px: */
    @media screen and (max-width: 800px) {
        .left,
        .main,
        .right {
            width: 100%; /* The width is 100%, when the viewport is 800px or smaller */
        }
    }
</style>
```

# Emojis

Wyświetlanie emoji wymaga ustawienia typowania fontu.

`<meta charset="UTF-8">`

`<p>&#128512; - smajlej</p>`

<p>&#128512; - smajlej</p>


<a href='../README.md' style='border: 1px solid gold; padding: 5px; color: gold'>← back to README.md</a>
<a href='#top' style='border: 1px solid gold; padding: 5px; color: gold'>↑ back to top</a>