# Description
**imgCheckbox** is a jQuery plugin that makes img tags checkable much like Google's recaptcha image selection tool.

## Usage

You can call `imgCheckbox` without any parameters on any jQuery collection containing `<img>` elements.

```JavaScript
$("img.checkable").imgCheckbox();
```

You can have mulitple sets of imgCheckboxes with different parameters

```JavaScript
$("img.checkableGroup1").imgCheckbox();
$("img.checkableGroup2").imgCheckbox({ "graySelected": false });
```

## Options

Option | Type | Values | Default
---|---|---|---|---
checkMarkImage | URL | Supports anything your browser support in the `background-image` property (of a pseudo selector). | SVG Data URI which draws a white tick on semi transparent green.
graySelected | Boolean | Convenience option: Adds the necessary CSS rules to apply a grayscale filter on selected images. | true
scaleSelected | Boolean | Convenience option: Adds the necessary CSS rules to apply a downscaling filter on selected images. | true
fixedImageSize | Boolean / String | Sets a fixed image size to all images (useful if images vary in size). Values can be "200px" or "120px 200px" (not percentages). | false
checkMarkSize | Boolean / String | Sets a custom size for the image (Useful if your images are very large or very small and the default is not suitable). Values can be "30px" and "20px 30px" (note: percentages do not work). | "30px"
scaleCheckMark | Boolean | Convenience option: Adds the necessary CSS rules to apply a zooming effect on the checkmark as it appears and disappears. | true
fadeCheckMark | Boolean | Convenience option: Adds the necessary CSS rules to fade the checkmark in and out. | false
addToForm | Boolean / jQuery | imgCheckbox can inject the checked elements into the form. If `true`, imgCheckbox will find a parent form and hook into its submission. A jQuery object can be passed in and the `submit` listener will attach to it. | true
styles | Object | For advanced customisation, the full stylesheet is applied using this object. | (see source)
preselect | [Integer] | To preselect certain elements, use the syntax `{ preselect: [0,1,2]}` | []
radio | Boolean / String | Opttion to change checkbox to radio button | false

## Advanced

You can add any custom styles using the `styles` option. For example, to add a blur filter to selected images:

```JavaScript
$("img").imgCheckbox({
	"styles": {
		"span.imgCheckbox.imgChked img": {
			// This property will overwrite the default grayscaling, we need to add it back in
			"filter": "blur(5px) grayscale(50%)",

			// This is just css: remember compatibility
			"-webkit-filter": "blur(5px) grayscale(50%)",

			// Let's change the amount of scaling from the default of "0.8"
			"transform": "scale(0.9)"
		}
	}
});
```

## Compatibility

- Firefox
- Chrome
- Opera
- IE8+ (untested on prior versions)
