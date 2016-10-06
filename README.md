![Donkeytail Craft CMS Fieldtype](http://www.simplygoodtwerk.com/uploads/donkeytail/donkeytail-logo.png)

## A Craft CMS fieldtype for content managing points on images

**Donkeytail Lite** is a Craft CMS fieldtype that allows you to quickly and easily content manage points on images. You can use it for locations on a faux map, showcasing multiple products within an image, or even pinning the tail on a&nbsp;donkey.

- **[Video demo](https://vimeo.com/185669453)**
- **[Documentation](https://github.com/simplygoodwork/donkeytail-plugin#usage)**
- **[Changelog](https://github.com/simplygoodwork/donkeytail-plugin/releases)**
- **[Issues & bugs](https://github.com/simplygoodwork/donkeytail-plugin/issues)**

Follow the [@simplygoodwork](https://twitter.com/simplygoodwork) Twitter account for updates.

## Requirements

- Craft 2.5+
- Tested in PHP version 7

## Installation

1. Copy the `donkeytail/` folder to your `craft/plugins/` folder
2. Go to Settings > Plugins in your Craft control panel and install the plugin.

## Usage

### Terminology

In Donkeytail the image you’re adding points to is called the *canvas* and the points you’re adding are called *dots*.

### Settings

-  **Canvas asset**: The canvas image with which you’ll add your dots to
-  **Show siblings**: Enable this to show dots from other entries in the current section. These will be shown with half opacity
-  **Dot type**: Choose either a  circle or a traditional map style pin. The circle will use the center as the anchor point while the pin uses the bottom middle
-  **Dot width**: The width (in pixels) to show dots on the canvas, it’s probably best to have this match your front end as close as possible
-  **Dot color**: Choose a color for the dot fill (dots have a white border by default).

### Template tags

The field returns 3 strings:

- `leftPercentage`: The left percentage value of the dot’s anchor point in relation to the canvas
- `topPercentage`: The top percentage value of the dot’s anchor point in relation to the canvas
- `topLeftStyles`: Returns the top and left percentages as CSS style properties and values. For example `top:42.1210%;left:88.1337%;`.

### Real world example

You’ll need to render the canvas asset yourself as you normally would within a template. (the field doens’t offer this incase you’d like to use a different, perhaps simplified version in the control panel)

A real world example would likely have the canvas in a parent container with `position:relative`. The dots can then be set to `position:absolute` and their positions output using an inline style attribute and `{{ entry.fieldName.topLeftStyles }}`. Don't forget to use negative margins or similar to move your front-end marker’s point to the match the anchor point of the dot.

### Did you know?

You can hold shift while clicking on a sibling dot to jump straight to that entry.

## The future

The current version of Donkeytail, **Donkeytail Lite**, is limited to a single image asset per fieldtype. [Follow us on Twitter](http://twitter.com/simplygoodwork) to keep up-to-date with our plans for Donkeytail Pro, a more robust option for your multi asset needs.

Happy pinning!
