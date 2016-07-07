# cover
HTML and CSS for the component you see too much on the web

## Usage

### Download
You can download cover-component via bower using the following command:
```
$ bower install trowel-cover
```

### basic markup
```html
<div class="cover">
    <div class="cover__body cover__body--[x]-[y]">
        lorem ipsum
    </div>
</div>
```
`[x]` and `[y]` are the position of the element.

### with overlay
```html
<div class="cover cover--overlay">
    <div class="cover__body cover__body--[x]-[y]">
        lorem ipsum
    </div>
</div>
```
`.cover--overlay` add a background that could be setted with the `$cover--overlay` variable:
* `$cover--overlay` can be a color, and the overlay will be a plain color
* `$cover--overlay` can be a list with of 2 colors, and the overlay will be a gradient, the first colors at the top of the gradient and the second color at the bottom of the gradient.


### height
The variable `$cover--height` can be defined as a number and it will applied with the property `height`.
But `$cover--height` can also be a map with as values the height and as key the responsive tag from [trowel responsive](https://github.com/Trowel/responsive) with a 'mobile-first' philosophy.

```scss
// Default value
$cover--height: (
  'default': 200px,
  'sm': 300px,
  'md': 400px,
  'lg': 500px,
) !default;
```

`default` is not a responsive tag, and will generate an height without media query.

### Sizes
You can set several height for your cover with the `$cover--sizes` variable which is a sass map.
As key, we set the tag of your size (it will generate class `.cover--{key}` to apply on your `.cover` element).
As value you can set a number or a map on the same pattern than the `$cover--height` variable.

```scss
// Default value
$cover--sizes: (
  'small': (
    'default': 100px,
    'sm': 200px,
    'md': 300px,
    'lg': 400px,
  ),
  'large': (
    'default': 200px,
    'sm': 300px,
    'md': 400px,
    'lg': 600px,
  ),
) !default;
```
