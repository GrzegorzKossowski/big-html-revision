<a href='../README.md' id='top' style='border: 1px solid gold; padding: 5px; color: gold'>← back to README.md</a>

# Forms

Formularze służą pobieraniu danych od klienta. Służy do tego element `<form>`.

```html
<form>// form elements</form>
```

`<input>` - element generyczny, zależny od typu podanego w atrybucie.

`<input type="text">` - rysuje pole jednolinijkowe do wporwadzania tekstu
<input type="text">

`<input type="radio">` - rysuje zestaw kółek do wyboru tylko jednego z nich
<input type="radio">

`<input type="checkbox">` - rysuje kwadraty do wyboru, żaden, dowolny lub wszystkie
<input type="checkbox">
<input type="checkbox" checked>

`<input type="submit">` - rysuje przycisk do wysyłania formy
<input type="submit" disabled>

`<input type="button">` - rysuje klikalny przycisk obsługujący dedykowane metody
<input type="button" value='Button' disabled>

### Pole tekstowe

`<input type="text">` definiuje jednoliniowe pole do wprowadzania tekstu

```html
<form>
    <label for="fname">First name:</label><br />
    <input type="text" id="fname" name="fname" /><br />
</form>
```

### Etykieta (label)

`<label>` - definiuje etykietę dla konkretnego pola. Używa atrybutu for, dla powiązania go z polem input. Wtedy można klikać również na nie (np. radio czy checkbox). Label jest czytany przez czytniki stron www.

```html
<form>
    <label for="fname">First name:</label><br />
    <input type="text" id="fname" name="fname" /><br />
</form>
```

### Radio

`<input type="radio">` definiuje radiobutton. Atrybut name łączy kilka radiobuttonów w jedną grupę.

  <input type="radio" id="html" name="fav_language" value="HTML">
    <label for="html">HTML</label><br>
    <input type="radio" id="css" name="fav_language" value="CSS">
    <label for="css">CSS</label><br>

```html
<form>
    <input type="radio" id="html" name="fav_language" value="HTML" />
    <label for="html">HTML</label><br />
    <input type="radio" id="css" name="fav_language" value="CSS" />
    <label for="css">CSS</label><br />
</form>
```

### Checkbox

`<input type="checkbox">` definiuje checkbox

<input type="checkbox" id="vehicle1" name="vehicle1" value="Bike">
  <label for="vehicle1"> I have a bike</label><br>
  <input type="checkbox" id="vehicle2" name="vehicle2" value="Car">
  <label for="vehicle2"> I have a car</label><br>

```html
<form>
    <input type="checkbox" id="vehicle1" name="vehicle1" value="Bike" />
    <label for="vehicle1"> I have a bike</label><br />
    <input type="checkbox" id="vehicle2" name="vehicle2" value="Car" />
    <label for="vehicle2"> I have a car</label><br />
</form>
```

### Submit button

`<input type="submit">` - wyzwala akcję na formularzu `<form>`

<input type="submit" value="Submit">

```html
<form action="/action_page.php">
    <label for="fname">First name:</label><br />
    <input type="text" id="fname" name="fname" value="John" /><br />
    <input type="submit" value="Submit" />
</form>
```

<span style='color:red'>Atrybut name jest wymagany. Jego wartość jest przesyłana przez formularz.</span>

# Form Attributes

Formularz zawiera następujące atrybuty:

`action` - definiuje akcję, która ma być wykonana po submicie formy. W przypadku php jest wysyłana do pliku, który ją obsługuje. W przypadku reacta obrabia się dane i wysyła na api.

```html
<form action="/action_page.php">`</form>
```

`target` - określa, gdzie ma się przekierować forma po otrzymaniu responsa. Defaultowo jest to \_self.

```html
<form action="/action_page.php" target="_blank">`</form>
```

`method` - określa jaką metodą http będą wysyłane dane (GET, POST). Sugerowana metoda POST.

```html
<form action="/action_page.php" method="POST">`</form>
```

`autocomplete` - określa, czy pola mają mieć opcję autouzupełnienia

```html
<form action="/action_page.php" autocomplete="on">`</form>
```

`novalidate` - określa, czy forma będzie walidowana w momencie wysyłania.

```html
<form action="/action_page.php" novalidate>`</form>
```

`accept-charset` - określa akceptowane kodowanie wysyłanych danych

```html
<form action="/action_page.php" accept-charset="utf-8">`</form>
```

`rel` - określa relacje między źródłem a obecnym dokumentem

`enctype` - określa, jak powinny być kodowane dane dla metody post

```html
<form
    action="/action_page_binary.asp"
    method="post"
    enctype="multipart/form-data"
>
    `
</form>
```

`application/x-www-form-urlencoded` - defaultowe, wszystkie znaki są kodowane, spacje zamioeniane na +, a specjalne znaki kodowane do ASCII HEX

`multipart/form-data` - wykorzystywane, jeśli jest ładowany plik binarny

`text/plain` - wysyła bez kodowania, nierekomendowane

# Form Elements

Formularz może zawierać nastepujące elementy:

`<input>` - wielorodzajowy element, zależny od atrybutu type (text, radio, checkbox…)

```html
<input type="text" id="fname" name="fname" />
```

`<label>` - etykieta elementu. Jeśli powiązana z nim poprzez atrybut for, wtedy w niektórych przypadkach klikalna.

```html
<label for="cars">Choose a car:</label>
```

`<select>` - rozwijana lista wyboru. Można ustalić, jak dużo elementów jest widocznych na raz. Atrybut multiple pozwala na wybór większej ilości elementów.

<select id="cars" name="cars">
  <option value="volvo" selected>Volvo</option>
  <option value="saab">Saab</option>
  <option value="fiat">Fiat</option>
  <option value="audi">Audi</option>
</select>

```html
<select id="cars" name="cars" size="3" multiple>
    <option value="volvo">Volvo</option>
    <option value="saab">Saab</option>
    <option value="fiat">Fiat</option>
    <option value="audi">Audi</option>
</select>
```

`<textarea>` - wieloliniowe pole tekstowe. Można ustalić ilość kolumn i rzędów lub za pomocą css.

`<button>` - definiuje klikalny element - przycisk

`<fieldset>` - pozwala na zgrupowanie elementów borderem i dodanie labela przez `<legend>`

`<legend>` - labeluje fieldset

`<datalist>` - definiuje predefiniowaną listę wyboru dla inputa (a’la select), z możliwością wpisywania własnych.

```html
<form action="/action_page.php">
    <input list="browsers" />
    <datalist id="browsers">
        <option value="Internet Explorer"></option>
        <option value="Firefox"></option>
        <option value="Chrome"></option>
        <option value="Opera"></option>
        <option value="Safari"></option>
    </datalist>
</form>
```

`<output>` - element, który może przyjmować wynik operacji, wyniku działania funkcji, np. dodawania.

`<option>` - definiuje element selecta

```html
<option value="volvo">Volvo</option>
```

`<optgroup>` - definiuje grupy w selekcie

```html
<select name="cars" id="cars">
    <optgroup label="Swedish Cars">
        <option value="volvo">Volvo</option>
        <option value="saab">Saab</option>
    </optgroup>
    <optgroup label="German Cars">
        <option value="mercedes">Mercedes</option>
        <option value="audi">Audi</option>
    </optgroup>
</select>
```

# Input Types

`<input type="button">`

`<input type="checkbox">`

`<input type="color">` - colorpicker

`<input type="date">`

`<input type="datetime-l`ocal"> - wybiera datę i godzinę bez strefy czasowej

`<input type="email">` - przyjmuje email, pozwala go zwalidować na podstawowym poziomie

`<input type="file">` - pozwala na pobranie pliku do formularza

`<input type="hidden">` - pole ukryte

`<input type="image">`

`<input type="month">` - wybór miesiąca i roku

`<input type="number">`

`<input type="password">` - pole na hasło - zakryte

`<input type="radio">`

`<input type="range">`

`<input type="reset">` - przycisk resetujący pola formy

`<input type="search">`

`<input type="submit">` - przycisk włączający wysyłanie formy

`<input type="tel">`

`<input type="text">` - pole textowe

`<input type="time">`

`<input type="url">`

`<input type="week">`

Niektóre restrykcje dotyczące inputów:

`checked` - ustawia stan radiobuttona lub checkboxa

`disabled` - wyłącza dostępność elementu

`max` - ustawia maksymalny zakres

`maxlength` - ustawia maksymalną długość

`min` - ustawia minimalny zakres

`pattern` - ustawia regex do validowania pola

`readonly` - ustawia czy pole może być zmienione

`required` - ustawia, czy pole jest wymagane do działania formularza

`size` - ustawia ilość znaków, które przyjmuje pole

`step` - przyjmuje interwał numeryczny dla pola, krok

`value` - ustawia defaultową wartość pola

# Input Attributes

...

# Input Form Attributes

...

<a href='../README.md' style='border: 1px solid gold; padding: 5px; color: gold'>← back to README.md</a>
<a href='#top' style='border: 1px solid gold; padding: 5px; color: gold'>↑ back to top</a>
