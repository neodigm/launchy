[![Build Status](https://travis-ci.org/svinkle/launchy.svg?branch=master)](https://travis-ci.org/svinkle/launchy)
[![codecov](https://codecov.io/gh/svinkle/launchy/branch/master/graph/badge.svg)](https://codecov.io/gh/svinkle/launchy)

# Launchy! 🚀

> An accessible modal window! — https://launchy.io

## Features include:
- Easy to use and implement!
- On launch, keyboard focus shifts to the modal window container
- The modal window is described via _optional_ modal heading
- Traps the keyboard focus within the modal when active/visible
- Closes the window on `esc` key press
- Closes the window on overlay mouse `click`
- Sets keyboard focus back to the launcher element on window close
- Add your own custom close controls!
- Add your own custom controls which send focus to somewhere else on the page!
- Transparent border for Windows High Contrast themes

For more details on the accessibility of modal windows:
- WCAG 2.4.3: https://www.w3.org/TR/UNDERSTANDING-WCAG20/navigation-mechanisms-focus-order.html#navigation-mechanisms-focus-order-examples-head
- WAI-ARIA Authoring Practices 1.1: https://www.w3.org/TR/wai-aria-practices-1.1/#dialog_modal

## Demo

- Check out the [demo](https://launchy.io)! 👈
- Try your own HTML with the [CodePen](https://codepen.io/svinkle/pen/pjVepz/) demo!

## Usage

_Launchy!_ is very easy to install and use:

### HTML
Wherever you want to have a _Launchy!_ control + window appear in your HTML content, simply **wrap** your content with a `<div>` and add the `data-launchy` attribute.

Example:

```html
<div data-launchy data-launchy-text="Launch window!" data-launchy-title="My modal window">
    <p>This content will appear in the modal window.</p>
</div>
```

- **Required**: `data-launchy` -- Attribute is required but the value can be anything
- **Required**: `data-launchy-text` -- This is the text that will be output to the launcher control
- Optional: `data-launchy-title` -- The text which appears in the heading of the modal window, recommended for greater a11y context 👍


#### Custom Close Controls

You can add your own custom close controls to any _Launchy!_ modal window!

1. Add the HTML element you wish to use for the control within your content
2. Apply the `data-launchy-close` attribute

Example:

```html
<div data-launchy data-launchy-text="Launch window!" data-launchy-title="My modal window">
    <p>This content will appear in the modal window.</p>
    <a href="#" data-launchy-close="🔥">Ok!</a>
</div>
```

Clicking on the _"Ok!"_ link will hide the modal window and send focus back to the launcher control!

#### Custom Refocus Controls

You can add your own custom "refocus" controls to any _Launchy!_ modal window!

1. Add the HTML element you wish to use for the control within your content
2. Apply the `data-launchy-refocus` attribute
3. Set the value of the `data-launchy-refocus` attribute to the `id` of the element you wish to send focus to

Example:

```html
<div data-launchy data-launchy-text="Launch window!" data-launchy-title="My modal window">
    <p>This content will appear in the modal window.</p>
    <a href="#" data-launchy-refocus="post-title">Send me to the article headline!</a>
</div>

<!-- Somewhere else in your page… -->
<h1 id="post-title" tabindex="-1">My perfect sundae…</h1>
```

Clicking on the _"Send me to the article headline!"_ link will hide the modal window and shift keyboard focus to the `<h1 id="post-title"/>` element!

### CSS

_Launchy!_ has many CSS classes available on its generated elements for custom styles. Check out the [style.scss](https://github.com/svinkle/launchy/blob/master/brochure/css/sass/styles.scss) file for class names and an example on how you might want to style your modal windows!

### JavaScript
For any site, grab the `/dist/launchy.js` file and include it at the bottom of your HTML page/template:

```html
<script src="js/launchy.js"></script>
```

_Launchy!_ will run automatically and generate all the modal windows for you!

### `npm` Package
_Launchy!_ is also available as an npm package!

#### Install
```sh
npm i launchy-modal-window
```

#### Usage
Include the `launchy.js` directly in your app or site template.

```html
<script src="node_modules/launchy-modal-window/launchy.js"></script>
```

## Contributions
See the [CONTRIBUTING](https://github.com/svinkle/launchy/blob/master/CONTRIBUTING.md) file.

## License
See the [LICENSE](https://github.com/svinkle/launchy/blob/master/LICENSE.md) file.
