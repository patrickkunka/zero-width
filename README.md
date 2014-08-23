Zero-width Web Font
=========

Zero-width web fonts allow us to clear the whitespace between inline-block elements without having to declare `font-size: 0;` on the parent element.

### Background

Various IE versions do not like `font-size: 0;` so `font-size: 0.1px;` is often suggested as an alternative. However, FireFox does not like `font-size: 0.1px` and rounds it up, negating its use. Using a "zero-width" font on our element provides us with whitespace clearing accross all font-face compatible browsers.

### Repo Contents

This repo contains a full set of @font-face ready web fonts, originally ported from Adobe's "Adobe Blank" font which was engineered for this purpose. I have also included an example CSS file that can be included in your project (NB: the files' `src` paths must be set according to your project's file structure).

### Use

Once the files and CSS have been correctly included in your project, you may apply the font to whichever element you which to clear whitespace on. This is typically the parent element that contains inline-block elements:

```html
<div class="grid">
	<div class="item"></div>
	<div class="item"></div>
	<div class="item"></div>
	...
</div>
```

```css
.grid {
	font-family: 'zero-width';
}

.grid .item {
	font-family: 'helvetica'; 
}

/* NB: You will need to override on child items, as 'font-family' is a cascading property */
```

### Avoiding loading flicker

Because @font-face files may take a moment to load, often after the page has rendered, we can use the zero-width font in conjunction with `font-size: 0;` to create bullet proof whitespace clearing with elegant loading.

```css
.grid {
	font-family: 'zero-width';
	font-size: 0;
}

.grid .item {
	font-family: 'helvetica';
	font-size: 1rem; 
}
```

### Further Reading

- [http://blog.typekit.com/2013/03/28/introducing-adobe-blank/](http://blog.typekit.com/2013/03/28/introducing-adobe-blank/)
- [http://css-tricks.com/fighting-the-space-between-inline-block-elements/](http://css-tricks.com/fighting-the-space-between-inline-block-elements/)
- [http://davidwalsh.name/remove-whitespace-inline-block](http://davidwalsh.name/remove-whitespace-inline-block)

### CDN

This font is now kindly available via [http://www.jsdelivr.com/](jsDelivr)'s CDN.

You may reference the following 5 source files in your own CSS, using the @font-face syntax of your choice.

```
//cdn.jsdelivr.net/font-zero-width/latest/zero-width.eot
//cdn.jsdelivr.net/font-zero-width/latest/zero-width.otf
//cdn.jsdelivr.net/font-zero-width/latest/zero-width.svg
//cdn.jsdelivr.net/font-zero-width/latest/zero-width.ttf
//cdn.jsdelivr.net/font-zero-width/latest/zero-width.woff
```

Alternatively, you can @import the ready-made CSS file:

```css
@import url('//cdn.jsdelivr.net/font-zero-width/latest/zero-width.css');
```
