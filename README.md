# three-font-bug

THREE.js has a bug where some characters appear to have holes.

The Facetype.js project seems to be aware of this, as they have an options to 'reverse the font direction' (but this doesn't work for every font).

```
Reverse font direction.
Use this to fix issues with holes in characters like 'd', 'o' and '8'.
```

see: http://gero3.github.io/facetype.js/

## run the example

use any http server, for example:

```
python -m SimpleHTTPServer
```

## creating a new font for THREE.js

https://gero3.github.io/facetype.js

## converting a font from OTF to TTF

```
brew install fontforge
fontforge -c 'f=fontforge.open("Nexa-Black.otf"); f.generate("Nexa-Black.ttf")'
```

## What is "Facetype.js"

THREE.js only accepts a font in "Facetype.js" format.

"Facetype.js" is an undocumented JSON format that stores the geometry for each character of a font.

If you look closer at Facetype.js, you'll see the facetype font converter loads the original font from TTF/OTF using opentype.js.

(I don't know why it was necessary to create this intermediate step between threejs and opentype, or why it had to be converted to an undocumented format in a separate codebase... but that's how it is.)

## useful links

**Facetype.js (THREE.js font file format)**

https://gero3.github.io/facetype.js

https://github.com/gero3/facetype.js

**THREE.js Documentation**

https://threejs.org/docs/#api/en/loaders/FontLoader

https://threejs.org/docs/#api/en/geometries/TextGeometry

**threejs version used in this demo**

https://cdnjs.cloudflare.com/ajax/libs/three.js/105/three.js
