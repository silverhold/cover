# cover
HTML and CSS for the component you see too much on the web

## Usage

### Download
You can download cover-component via bower using the following command:
```
$ bower install silverhold-cover
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

#### In a specific div
```html
<div class="cover">
    <div class="cover__overlay" style="background-color: rgb(0, 0, 10); opacity: 0.3;"></div>

    <div class="cover__bg" style="background-image: url('path/to/img.jpg');"></div>

    <div class="cover__body cover__body--[x]-[y]">
        ...
    </div>
</div>
```

```twig
{% embed '../../cover.html.twig' with {
    'background': 'path/to/img.jpg',
    'overlay': {
        'color': 'rgb(0, 0, 10)',
        'opacity': '0.3'
    },
} %}
    {% block content_full %}
        ...
    {% endblock %}
{% endembed %}
```
Into the twig embed you can just set to `true` the `overlay` parameter. It will generate an *overlay* with the `rgb(0, 0, 0)` color and an *opacity* of `0.5`.

#### Directly with the `.cover__bg` element

```html
<section class="cover">
    <div class="cover__bg" style="background-image: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), url('path/to/img.jpg');"></div>

    <div class="cover__body cover__body--[x]-[y]">
        ....
    </div>
</section>
```

```twig
{% embed '../../cover.html.twig' with {
    'background': background,
    'overlay': {
        'gradient': 'linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5))'
    },
} %}
    {% block content_full %}
        ...
    {% endblock %}
{% endembed %}
```


#### Sass variables
* `$cover--overlay` bool - will generate css required for overlays or not


### height
The variable `$cover--height` can be defined as a number and it will applied with the property `height`.
But `$cover--height` can also be a map with as values the height and as key the responsive tag from [silverhold responsive](https://github.com/silverhold/responsive) with a 'mobile-first' philosophy.

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
