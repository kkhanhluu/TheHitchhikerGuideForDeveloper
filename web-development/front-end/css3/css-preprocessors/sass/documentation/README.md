# SASS Documentation

## Variables

```sass
$font-stack:    Helvetica, sans-serif;
$primary-color: #333;

body {
    font: 100% $font-stack;
    color: $primary-color;
}
```

```css
body {
    font: 100% Helvetica, sans-serif;
    color: #333;
}
```

## Nesting

```sass
nav {
    ul {
        margin: 0;
        padding: 0;
        list-style: none;
    }

    li {
        display: inline-block;
    }

    a {
        display: block;
        padding: 6px 12px;
        text-decoration: none;
    }
}
```

```css
nav ul {
    margin: 0;
    padding: 0;
    list-style: none;
}

nav li {
    display: inline-block;
}

nav a {
    display: block;
    padding: 6px 12px;
    text-decoration: none;
}
```

## Partials

You can create partial Sass files that contain little snippets of CSS that you can include in other Sass files. This is a great way to modularize your CSS and help keep things easier to maintain. A partial is simply a Sass file named with a leading underscore. You might name it something like +_partial.scss. The underscore lets Sass know that the file is only a partial file and that it should not be generated into a CSS file. Sass partials are used with the @import directive.

## Import

```sass
// _reset.scss

html,
body,
ul,
ol {
    margin:  0;
    padding: 0;
}
```

```sass
// base.scss

@import 'reset';

body {
    font: 100% Helvetica, sans-serif;
    background-color: #efefef;
}
```

```css
html, body, ul, ol {
    margin: 0;
    padding: 0;
}

body {
    font: 100% Helvetica, sans-serif;
    background-color: #efefef;
}
```

## Mixins

```sass
@mixin border-radius($radius) {
    -webkit-border-radius: $radius;
    -moz-border-radius: $radius;
    -ms-border-radius: $radius;
    -o-border-radius: $radius;
    border-radius: $radius;
}

.box { @include border-radius(10px); }
```

```css
.box {
    -webkit-border-radius: 10px;
    -moz-border-radius: 10px;
    -ms-border-radius: 10px;
    -o-border-radius: 10px;
    border-radius: 10px;
}
```

## Inheritance

```sass
// This CSS won't print because %equal-heights is never extended.
%equal-heights {
    display: flex;
    flex-wrap: wrap;
}

// This CSS will print because %message-shared is extended.
%message-shared {
    border: 1px solid #ccc;
    padding: 10px;
    color: #333;
}

.message {
    @extend %message-shared;
}

.success {
    @extend %message-shared;
    border-color: green;
}

.error {
    @extend %message-shared;
    border-color: red;
}

.warning {
    @extend %message-shared;
    border-color: yellow;
}
```

```css
.message, .success, .error, .warning {
    border: 1px solid #cccccc;
    padding: 10px;
    color: #333;
}

.success {
    border-color: green;
}

.error {
    border-color: red;
}

.warning {
    border-color: yellow;
}
```

## Operators

```sass
.container { width: 100%; }


article[role="main"] {
    float: left;
    width: 600px / 960px * 100%;
}

aside[role="complementary"] {
    float: right;
    width: 300px / 960px * 100%;
}
```

```css
.container {
    width: 100%;
}

article[role="main"] {
    float: left;
    width: 62.5%;
}

aside[role="complementary"] {
    float: right;
    width: 31.25%;
}
```