# Polyglot Language Switcher 2

**Polyglot Language Switcher** is a JavaScript component which allows you to display  a popup with the languages supported by your website. 

This component has 3 implementations:

1. jQuery Plugin
2. AngularJS Directive
3. ReactJS Component

## Usage (jQuery)

Adapt the following HTML to your system and add it to your page:

```html
<div class="my-lang-switcher">
	<ul style="display: none">
		<li><a href="/set-language?lang=en-US" title="English" data-lang-id="en-US"><img src="/images/flags/us.png" alt="United States"> English</a></li>
		<li><a href="/set-language?lang=es-ES" title="Spanish" data-lang-id="es-ES"><img src="/images/flags/es.png" alt="Spain"> Español</a></li>
		<li><a href="/set-language?lang=da-DK" title="Danish (Denmark)" data-lang-id="da-DK"><img src="/images/flags/dk.png" alt="Denmark"> Dansk (Denmark)</a></li>
	</ul>
</div>
```

Include `jquery-polyglot.language.switcher.min.js` and `polyglot-language-switcher-2.min.css` on your page and initiate it by:

```javascript
$(function() {
	$('.my-lang-switcher').polyglotLanguageSwitcher({
		openMode: 'click'
	});
});
```

### Options

- `openMode`: `click` or `hover` (keep in mind that hover is not a good option for mobile devices)
- `hoverTimeout`: defaults to 200 ms
- `animSpeed`: defaults to 200 ms
- `animEffect`: `fade` or `slide`
- `gridColumns`: number of columns in the popup
- `selectedLang`: function that returns the current language. Defaults to returning `$('html').attr('lang')`

### Events

- `popupOpening`
- `popupOpened`
- `popupClosing`
- `popupClosed`

Eg.:

```javascript
$(function() {
	$('.my-lang-switcher').on('popupOpened', function(ev) {
		// do something
	});
});
```
