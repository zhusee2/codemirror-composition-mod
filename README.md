CodeMirror Composition Mod
==========================

The editor of [CodeMirror][1] is actually a group of `<div>`s and `<span>`s. The editable area is not a native element like an input box nor a textarea. 

When you use IMEs to composite non-latin charaters like Chinese or Japanese, you'll notice that you cannot see the composition text decorated well (usually _underlined_). You cannot see your cursor moving during compositing either, because the cursor of CodeMirror is a `<div>` rather than a real cursor.

This add-on tries to enhance the composition experience of CodeMirror for IME users with the [Composition Event][2] APIs.

## Usage

This repository contains only source in CoffeeScript. Please compile it to JS, then load it after the main scripts of CodeMiror. You'll also need the stylesheet to force the input of CodeMirror to show up.

```html
<link rel="stylesheet" type="text/css" href="codemirror-composition-mod.css" />
<script type="text/javascript" src="codemirror-composition-mod.js"></script>
```

It adds a new option `enableCompositionMod` to CodeMirror. Setting this option to true in CodeMirror constructor or with `cm.setOption()` to enable this mod.

## Compatibility

Atleast tested on Safari 6+, Firefox 24+ and Chrome 30+ (on Mac.)

## Modification to CodeMirror instance

This mod adds 3 additional properties to the CodeMirror instance:

```js
cm.display.inCompositionMode //(Boolean)
cm.display.compositionHead //(Pos)
cm.display.textMarkerInComposition //(TextMarker)
```

## Demo

An online demo is available on the Logdown editor <http://logdown.com/demo>.  
This mod is original developed for [Logdown][3].


[1]: http://codemirror.net/
[2]: https://developer.mozilla.org/en-US/docs/Web/API/CompositionEvent
[3]: http://logdown.com/