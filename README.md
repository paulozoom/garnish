# Garnish

Garnish for your Sassy CSS cocktails. Use it on top of [Bourbon](http://bourbon.io), or eat it raw.

## Installation

1. Install with `bower install garnish` or [download as zip](https://github.com/paulozoom/garnish/archive/master.zip)
2. Include Garnish in your code with `@include "src/garnish"`

## Usage

### Helpers

**Grayscale Colours**  
A simple mixin to create gray colours at varying degrees of lightness

```SCSS
.margarita-salt {
  color: gray(40%);
}
```

**Combined Hover/Focus styles**  
Be nice to keyboard users. The `hover` block mixin wraps your rules in `:hover` and `:focus` states.

```SCSS
.mint {
  color: #4183C4;
  @include hover {
    color: #333;
  }
}
```

## Development

### Guidelines

- Garnish **should be** library-agnostic (although Bourbon is encouraged), and it **should not** replicate Bourbon’s functionality.
- Garnish **should not** create any output without being called. All code should be mixins and functions.
- Garnish **should not** make style decisions or assumptions. Defaults are OK, but allow configuration.

### Contributing

Issues and pull requests are welcome.
