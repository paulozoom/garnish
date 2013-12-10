# Garnish

Garnish for your Sassy CSS cocktails. Made to be used on top of [Bourbon](http://bourbon.io).

## Usage

1. [Download as zip](https://github.com/paulozoom/garnish/archive/master.zip). (Bower coming soon)
2. Include Garnish in your code with `@include "src/garnish"`

## Included Mixins

### Helpers

**Grayscale Colours**  
This is a function which acts on a colour value to return a greyscale version. You can vary the lightness by a percentage going from darkest at 0% to lightest at 100%.

```SCSS
.margarita-salt {
  color: gray(#7ED162, 40%);
}
```

## Development

### Rules

- Including Garnish should create no output. All code should be mixins and functions.
- Garnish code should make no style decisions or assumptions. Defaults are OK.
- Although using Bourbon is encouraged, Garnish should be library-agnostic.

### Contributing

Issues and pull requests are welcome.
