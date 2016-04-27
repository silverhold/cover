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
`.cover--overlay` add a background that could be setted with the `$cover-overlay` variable:
* `$cover-overlay` can be a color, and the overlay will be a plain color
* `$cover-overlay` can be a list with of 2 colors, and the overlay will be a gradient, the first colors at the top of the gradient and the second color at the bottom of the gradient.
