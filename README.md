# Garnish

Garnish for your Sassy CSS cocktails. Use it on top of [Bourbon](http://bourbon.io), or have it raw.

## Installation

1. Install with `bower install garnish` or [download as zip](https://github.com/paulozoom/garnish/archive/master.zip)
2. Include Garnish in your code with `@include "src/garnish"`

## Features

Garnish is a collection of Sass mixins and functions designed to make your life a tiny bit easier.

When you first import Garnish into your project, it doesn’t add any additional code to it. Garnish is a toolbox, and you only use what you want. It doesn’t contain any pre-defined styles, and makes no decisions for you.

### Feature Index
* **[Helpers](#helpers)**
  * [Grayscale Colours](#grayscale-colours)
  * [Combined Hover/Focus styles](#combined-hoverfocus-styles)
  * [Readable Media Queries](#readable-media-queries)
* **[Layout](#layout)**
  * [Simple Grid](#simple-grid)
  * [Side Margin, Side Padding, Centering](#side-margin-side-padding-centering)
* **[Style](#style)**
  * [Border Sandwich](#border-sandwich)
* **[Typography](#typography)**
  * [Weights](#weights)
  * [Hyphenation](#hyphenation)

----

### Helpers

#### Grayscale Colours
Function that outputs gray colours based on percentage of lightness.

```SCSS
// SCSS
.margarita-salt { color: gray(40%); }
.olive          { color: gray(97%); }

// CSS
.margarita-salt { color: #666666; }
.olive          { color: #f7f7f7; }
```

#### Combined Hover/Focus styles

Be nice to keyboard users. The `hover` block mixin wraps your rules in `:hover` and `:focus` states.

```SCSS
// SCSS
.mint {
  color: #4183C4;
  @include hover { color: #333333; }
}

// CSS
.mint {
  color: #4183C4;
}
.mint:hover,
.mint:focus {
  color: #333333;
}
```

#### Readable Media Queries

Friendly media queries with `media-upto`, `media-between`, and `media-from` block mixins.

```scss
// SCSS
.cherry-jar-title {
  @include media-upto(500px)            { font-size: 14px; }
  @include media-between(500px, 900px)  { font-size: 18px; }
  @include media-from(900px)            { font-size: 22px; }
}

// Output
@media screen and (max-width: 499px) {
  .cherry-jar-title { font-size: 14px; }
}

@media screen and (min-width: 500px) and (max-width: 899px) {
  .cherry-jar-title { font-size: 18px; }
}

@media screen and (min-width: 900px) {
  .cherry-jar-title { font-size: 22px; }
}
```

----

### Layout

#### Simple Grid

Makes a percentage-based grid in one mixin call, with optional vertical gutter (3% by default). Columns must be children of the element within which the mixin is called from.

````scss
// Make a 4 column grid with 3% gutters (horizontal and vertical)
.container {
  @include simple-grid(4);
}
// Make a 6 column grid with 5% gutters and no vertical gutter
.container {
  @include simple-grid(6, 5%, false);
}
```

#### Side Margin, Side Padding, Centering

Short syntax mixins for either horizontal or vertical margin/padding, but not both.

* `padding-h($value)`
* `padding-v($value)`
* `margin-h($value)`
* `margin-v($value)`
* `centered`, i.e. `margin-h(auto)`

Example:

```scss
/* Using Garnish */
.box {
  @include padding-h(1em);
}

/* Alternative: two declarations */
.box {
  padding-left: 1em;
  padding-right: 1em;
}

/* Alternative: single declaration, but with vertical values */
.box {
  padding: 0 1em;
}
```

----

### Style

#### Border Sandwich

Helps to create top and bottom dividers on a series of elements of the same type.

```SCSS
// SCSS
.pineapple-wedges {
  @include border-sandwich(1px solid #F0AE3D);
}

// Set the $breadless to true to remove outer borders
.lemon-wedges {
  @include border-sandwich(1px solid #FCF54C, true);
}

//CSS
.pineapple-wedges                 { border-bottom:  1px solid #F0AE3D; }
.pineapple-wedges:first-of-type   { border-top:     1px solid #F0AE3D; }

.lemon-wedges:not(:first-of-type) { border-top:     1px solid #FCF54C; }
```

**Default Border Sandwich:**

\----------------------------  
  :pineapple: wedge  
\----------------------------  
  :pineapple: wedge  
\----------------------------  
  :pineapple: wedge  
\----------------------------  


**Breadless Border Sandwich:**

  :lemon: wedge  
\----------------------------  
  :lemon: wedge  
\----------------------------  
  :lemon: wedge  


**Browser Support:**
* Desktop: Chrome 1.0+, Firefox 3.5+, IE 9.0+, Opera 9.5+, Safari 3.2+  
* Mobile: Android 2.1+, Firefox Mobile 1.0+, IE Mobile 9.0+, Opera Mobile 10.0+, Safari Mobile 3.2+

----

### Typography

#### Weights

Keyword-based font-weight function. Based on Typekit’s most weight-rich typefaces.

```scss
// SCSS
strong {
  font-weight: weight(semibold);
}

// Output
strong {
  font-weight: 600;
}
```

Reference:

| Keyword             | Weight |
| ------------------- | ------ |
| `thin`              | 100    |
| `extralight`        | 200    |
| `light`             | 300    |
| `book` or `regular` | 400    |
| `medium`            | 500    |
| `semibold`          | 600    |
| `bold`              | 700    |
| `extrabold`         | 800    |
| `black`             | 900    |

#### Hyphenation

Add all the vendor prefixes for hyphenation easily. 

```scss
// SCSS
.cocktail-description { @include hyphenated; }
.cocktail-title-long { @include hyphenated(manual); }

// Output
.cocktail-description {
  -webkit-hyphens: auto;
     -moz-hyphens: auto;
      -ms-hyphens: auto;
          hyphens: auto;
}
.cocktail-title-long {
  -webkit-hyphens: manual;
     -moz-hyphens: manual;
      -ms-hyphens: manual;
          hyphens: manual;
}
```

## Development

### Guidelines

- Garnish **should be** library-agnostic, but it **should not** replicate Bourbon’s functionality.
- Garnish **should not** produce any output unless its functions and mixins are used.
- Garnish **should not** make style decisions or assumptions. Defaults are OK, but allow configuration.

### Contributing

Issues and pull requests are welcome.
