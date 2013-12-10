# Garnish

Garnish for your Sassy CSS cocktails. Use it on top of [Bourbon](http://bourbon.io), or have it raw.

## Installation

1. Install with `bower install garnish` or [download as zip](https://github.com/paulozoom/garnish/archive/master.zip)
2. Include Garnish in your code with `@include "src/garnish"`

## Features

Garnish is a collection of Sass mixins and functions designed to make your life a tiny bit easier.

When you first import Garnish into your project, it doesn’t add any additional code to it. Garnish is a toolbox, and you only use what you want. It doesn’t contain any pre-defined styles, and makes no decisions for you.

### Border Sandwich

Helps to create top and bottom borders on elements.

```SCSS
// SCSS
.pineapple-wedges {
  @include border-sandwich(1px solid #F0AE3D);
}

// Set the $breadless to true after your style declaration to remove top and bottom borders on the first and last elements
.lemon-wedges {
  @include border-sandwich(1px solid #F0AE3D, true);
}

//CSS
.pineapple-wedges { border-bottom: $border; }
.pineapple-wedges:first-of-type { border-top: $border; }

.lemon-wedges:not(:first-of-type) { border-top: $border; }
```

**Default Sandwich**  
\----------------------------  
  :pineapple: Wedge
\----------------------------  
  :pineapple: Wedge
\----------------------------  
  :pineapple: Wedge  
\----------------------------  


** Breadless **  
  :lemon: Wedge  
\----------------------------  
  :lemon: Wedge  
\----------------------------  
  :lemon: Wedge  


### Grayscale Colours
Function that outputs gray colours based on percentage of lightness.

```SCSS
// SCSS
.margarita-salt { color: gray(40%); }
.olive   { color: gray(97%); }

// CSS
.margarita-salt { color: #666666; }
.olive   { color: #f7f7f7; }
```

### Combined Hover/Focus styles

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

### Side Margin, Side Padding, Centering

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


### Readable Media Queries

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


### Hyphenation

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
