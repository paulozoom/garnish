# Garnish

Garnish for your Sassy CSS cocktails. Use it on top of [Bourbon](http://bourbon.io), or eat it raw.

## Installation

1. Install with `bower install garnish` or [download as zip](https://github.com/paulozoom/garnish/archive/master.zip)
2. Include Garnish in your code with `@include "src/garnish"`

## Usage

### Grayscale Colours
Function to create gray colours at varying degrees of lightness.

```SCSS
.margarita-salt {
  color: gray(40%);
}
```

### Combined Hover/Focus styles

Be nice to keyboard users. The `hover` block mixin wraps your rules in `:hover` and `:focus` states.

```SCSS
.mint {
  color: #4183C4;
  @include hover {
    color: #333;
  }
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

Make your media queries more understandeable with `media-upto`, `media-between`, and `media-from` block mixins.

```scss
// SCSS
h1 {
  @include media-upto(500px)            { font-size: 14px; }
  @include media-between(500px, 900px)  { font-size: 18px; }
  @include media-from(900px)            { font-size: 22px; }
}

// Output
@media screen and (max-width: 499px) {
  h1 { font-size: 14px; }
}

@media screen and (min-width: 500px) and (max-width: 899px) {
  h1 { font-size: 18px; }
}

@media screen and (min-width: 900px) {
  h1 { font-size: 22px; }
}
```

## Development

### Guidelines

- Garnish **should be** library-agnostic, but it **should not** replicate Bourbon’s functionality.
- Garnish **should not** produce any output unless its functions and mixins are used.
- Garnish **should not** make style decisions or assumptions. Defaults are OK, but allow configuration.

### Contributing

Issues and pull requests are welcome.
