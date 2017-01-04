# FontAwesome.js
Simple JS library helper for FontAwesome

## Installation

Download **FontAwesome.js** from GitHub or install via ``bower``:

```sh
$ bower install FontAwesome.js
```

Include the `fa.js` file (or `fa.min.js`) in your page.

```html
<script src="fa.js"></script>
```

Finally include FontAwesome CSS in your page.

**NOTE:** You can to use `FontAwesome.load()` method to add on-the-fly FontAwesome CSS in your page

## Basic Usage

```html
<!DOCTYPE html>
<html>
<head>
  <script src="fa.js"></script>
</head>
<body>
  <h1>Hello, FontAwesome.js!</h1>
  <script>
    // Load FontAwesome CSS
    FontAwesome.load();
    // Prepend "home" icon to h1 element
    FontAwesome.icon('home').prependTo('h1');
  </script>
</body>
</html>

```


## Options

FontAwesome.js uses the same FontAwesome classes to change the look and the behavior of the icons (see http://fontawesome.io/examples/).

| Option       | Description         | Allowed Values               | Default   |
|--------------|---------------------|------------------------------|-----------|
| `size`       | Size of icon        | `lg`, `2x`, `3x`, `4x`, `5x` | (none)    |
| `fixedWidth` | Fix a width of icon | `true`, `false`              | `false`   |
| `border`     | Add a border        | `true`, `false`              | `false`   |
| `pullLeft`   | Pull icon to left   | `true`, `false`              | `false`   |
| `pullRight`  | Pull icon to right  | `true`, `false`              | `false`   |
| `spin`       | Spin animation      | `true`, `false`              | `false`   |
| `pulse`      | Pulse animation     | `true`, `false`              | `false`   |
| `rotate`     | Rotate the icon     | `90`, `180`, `270`           | (none)    |
| `flip`       | Flip the icon       | `horizontal`, `vertical`     | (none)    |
| `url`        | URL of FontAwesome  | -                            | CDN URL   |
| `id`         | Icon ID             | -                            | (none)    |
| `classes`    | Additional class    | -                            | (none)    |
| `tag`        | Default icon tag    | -                            | `i`       |

#### Global options

Can you change the option globally using the `FontAwesome.options` object.

For example:

```js
FontAwesome.options = {
  pullLeft: true,
  url: 'http://example.org/assets/font-awesome/font-awesome.min.css'
}
```

#### FontAwesome.icon method

Can you override the global options with ``FontAwesome.icon`` method:

```js
FontAwesome.icon('spinner', { spin: true })
```

## Methods

#### .load()
#### .load(url)
Add on-the-fly FontAwesome CSS in your page

```js
FontAwesome.load('http://example.org/assets/font-awesome/font-awesome.min.css');
```


#### .css(object)
Apply a CSS style to icon *(chainable method)*

```js
FontAwesome.icon('user').css({color: '#DDD'}).element; // <i class="fa fa-user" style="color:#DDD"></i>
```


#### .prependTo(selector)
Prepend the icon for all matches selector

```js
FontAwesome.icon('user').prependTo('h1'); // <h1><i class="fa fa-user"></i>Title</h1>
```

#### .appendTo(selector)
Append the icon for all matches selector

```js
FontAwesome.icon('user').appendTo('h1'); // <h1>Title<i class="fa fa-user"></i></h1>
```


#### .icon(icon)
#### .icon(icon, options)
Set the icon and options *(chainable method)*


#### .stack(icon)
#### .stack(icon, reverse)
#### .stack(icon, options)
#### .stack(icon, options, reverse)
Set the stack icon *(chainable method)*

```js
FontAwesome.icon('terminal', { inverse: true }).stack('square', { size: 'lg'}, true);
```

```html
<span class="fa-stack fa-lg">
  <i class="fa fa-square fa-stack-2x"></i>
  <i class="fa fa-terminal fa-inverse fa-stack-1x"></i>
</span>
```


## Properties

#### .options
FontAwesome.js options (see Options above)


#### .element
Return a `DOMElement` of the icon (useful to use with another JS library - eg. jQuery)

```js
jQuery('h1').prepend(FontAwesome.icon('user').element);
```


## Compatibility

Currently Supports: FF, Chrome, IE9+ and other modern and decent browsers

----
Copyright (C) 2016, Giuseppe Di Terlizzi <giuseppe.diterlizzi@gmail.com>
