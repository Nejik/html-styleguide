HTML Styleguide
===================

For writing maintainable and scalable HTML documents

  * [General](#general)
    * [Use DOCTYPE](#use-doctype)
    * [Write tags and attributes in lower case](#write-tags-and-attributes-in-lower-case)
    * [Add closing tags](#add-closing-tags)
    * [Omit Forward slash](#omit-forward-slash)
    * [Write one list item per line](#write-one-list-item-per-line)
    * [Add single line break between components](#add-single-line-break-between-components)
    * [Add alt attribute to img](#add-alt-attribute-to-img)
  * [HTML](#html)
    * [Add lang attribute](#add-lang-attribute)
  * [HEAD](#head)
    * [Use UTF-8](#use-utf-8)
    * [Specify character encoding at first](#specify-character-encoding-at-first)
    * [Don’t use legacy character encoding format](#dont-use-legacy-character-encoding-format)
    * [Add `<link>` to `<head>`](#add-link-to-head)
  * [BODY](#body)
    * [Add body element](#add-body-element)
    * [Add `<script>` before `</body>`](#add-script-before-body)
  * [Attributes](#attributes)
    * [Use double quotes](#use-double-quotes)
    * [Omit boolean attribute value](#omit-boolean-attribute-value)
    * [Don’t put white spaces around tags and attribute values](#dont-put-white-spaces-around-tags-and-attribute-values)
    * [Set attributes order](#set-attributes-order)
  * [Forms](#forms)
    * [Use `<label>`](#use-label)
    * [Use `type` with `<button>`](#use-type-with-button)
  

* [Reminders](#reminders)


# General
* Avoid UNNECESSARY markup, such as surrounding a block element in a `<div>`

## Use DOCTYPE

DOCTYPE is required for activating standard mode.

DOCTYPE is not for DTD anymore, be simple.

Don’t use XML Declaration.

Bad:
```html
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN"
      "http://www.w3.org/TR/html4/strict.dtd">
<html>
  ...
</html>
```
Good:
```html
<!DOCTYPE html>
<html>
  ...
</html>
```



## Tags and attributes in lower case
Tags and attributes should be in lowercase

Bad:
```html
<DIV>
  <UL>
    <li>Item 1</li>
    <li>Item 2</li>
  </UL>
</DIV>
<INPUT TYPE="text">
```
Good:
```html
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
</ul>
<input type="text">
```

## Add closing tags
Add closing tags to elements that aren't self-closing

Bad:
```html
<body>
<ul>
  <li>Item 1
  <li>Item 2
</ul>
```
Good:
```html
<body>
  <ul>
    <li>Item 1</li>
    <li>Item 2</li>
  </ul>
</body>
```
*Exception is unclosed `<li>` tags, when you use `display:inline-block;` to avoid unnecessary space between items

## Forward slash
Don't add the forward slash for self-closing elements (img, br, hr, input)

Bad:
```html
<ul>
  <li>Item 1
  <li>Item 2
</ul>
```
Good:
```html
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
</ul>
```

## Write one list item per line

Bad:
```html
<ul>
  <li>Item 1</li><li>Item 2</li><li>Item 3</li>
</ul>

<tr>
  <td>Cell 1</td><td>Cell 2</td><td>Cell 3</td>
</tr>
```
Good:
```html
<ul>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ul>

<tr>
  <td>Cell 1</td>
  <td>Cell 2</td>
  <td>Cell 3</td>
</tr>
```

## Single line break between components
Put a single line break between blocks/components.

Bad:
```html
<section class="component1">
  ...
</section>
<section class="component2">
  ...
</section>
```
Good:
```html
<section class="component1">
  ...
</section>

<section class="component2">
  ...
</section>
```

## Add alt attribute to img
`alt` attribute helps those who cannot process images or have image loading disabled. If img used as presentation element(you should try to avoid this), you can leave `alt` empty

Bad:
```html
<img src="/img/logo.png">
```
Good:
```html
<img alt="Description of image" src="/img/logo.png">
```

# HTML
## Add lang attribute
`lang` attribute will help translating an HTML document

Bad:
```html
<html>
```
Good:
```html
<html lang="en-US">
```


# BODY

## Add body element
Sometimes body element is complemented in unexpected position by a browsers

Bad:
```html
<html>
  <head>
    ...
  </head>
  ...
</html>
```
Good:
```html
<html>
  <head>
    ...
  </head>
  <body>
    ...
  </body>
</html>
```

## Add `<script>` before `</body>`
Add all your scripts before `</body>`

Bad:
```html
<!DOCTYPE html>
<html lang="ru">
  <head>
    <script src="app.js"></script>
  </head>
  <body>…</body>
</html>
```
Good:
```html
<!DOCTYPE html>
<html lang="ru">
  <head>…</head>
  <body>
    <!-- your page -->
    <script src="app.js"></script>
  </body>
</html>
```

# HEAD

## Use UTF-8
Specify document character encoding, UTF-8 is not default in all browsers yet

Good:
```html
<head>
  <meta charset="UTF-8">
</head>
```

## Specify character encoding at first
Spec requires the character encoding is specified within the first 1024 bytes of the document.

Bad:
```html
<head>
  <meta content="width=device-width" name="viewport">
  ...
  <meta charset="UTF-8">
</head>
```
Good:
```html
<!DOCTYPE html>
<head>
  <meta charset="UTF-8">
  <meta content="width=device-width" name="viewport">
  ...
</head>
```

## Don’t use legacy character encoding format
HTTP headers should be specified by a server, be simple.

Bad:
```html
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
```
Good:
```html
<meta charset="UTF-8">
```

## Add `<link>` to `<head>`
Add all your links to stylesheets in `<head>`

Bad:
```html
<html lang="ru">
  <head>…</head>
  <body>
    <link rel="stylesheet" href="styles.css">
  </body>
</html>
```
Good:
```html
<html lang="ru">
  <head>
    <link rel="stylesheet" href="styless.css">
  </head>
  <body>…</body>
</html>
```

# Attributes

## Double quotes
Surround values for attributes in double quotes.
Even though quotes around attributes is optional, always put quotes around attributes for readability.

Bad:
```html
<input type='radio' class='input'>
```
Good:
```html
<input type="radio" class="input">
```

## Omit boolean attribute value
Boolean attributes(checked, disabled, required), do not need a value.

Bad:
```html
<input type='radio' required='true'>
```
Good:
```html
<!DOCTYPE html>
<input type='radio' required>
```

## Don’t put white spaces around tags and attribute values
Just don't do this

Bad:
```html
<section class=" component " ></h1>
```
Good:
```html
<section class="component"></h1>
```

## Attributes order
Follow this order for attributes:

* href, type, value
* class
* id
* name 
* for, value, etc
* data-attributes
* checked, disabled, required

Bad:
```html
<input required class="input" type="radio" >
```
Good:
```html
<input type="radio" class="input" required>
<a href="#" class="link"></a>
```





# Forms

## Use `<label>`
Every form input that has text attached should utilize a `<label>` tag. Especially radio or checkbox elements.
Omit `for` attribute if possible(1st variant).

Bad:
```html
<input type="radio" id="choose"> Radio button
```
Good:
```html
<label>
  <input type="radio"> Radio button
</label>

<input type="radio" id="choose">
<label for="choose">Radio button</label>
```

## Use `type` with `<button>`
Form buttons should always include an explicit `type`. Use primary buttons for the `type="submit"` button and regular buttons for `type="button"`

Bad:
```html
<form>
  <input type="text">
  <button>Say hi</button>
  <button>Submit form</button>
</form>
```
Good:
```html
<form>
  <input type="text">
  <button type="button">Say hi</button>
  <button type="submit">Submit form</button>
</form>
```

























# Reminders
* HTML is about structure and meaning, not style or behavior (don't use h(1,2,3) elements to make you font larger)
* Don't use styling tags such as `<bold>` and `<hr>`
* Paragraphs of text should always be placed in a `<p>` tag. Never use multiple `<br>` tags
* Items in list form should always be in `<ul>`, `<ol>`, or `<dl>`. Never use a set of `<div>` or `<p>`
* Omit type attribute for CSS. In HTML5, default `type` attribute’s value of `style` element is `text/css`
* Omit type attribute for JavaScript. In HTML5, the default `type` attribute’s value of `script` element is `text/javascript`
* Forget about hgroup element. W3C spec removes this element