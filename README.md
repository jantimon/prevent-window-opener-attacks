# prevent-window-opener-attacks

As soon as the user clicks a link with `taget="_blank"` this script will replace the default behaviour with a `window.open` call and set `window.opener = null`.

## Usage

### ES Modules

Fixes the attack vector on document ready automatically

```js
  import('prevent-window-opener-attacks');
```

### CommonJS & AMDJS

Fixes the attack vector on document ready automatically

```js
  require('prevent-window-opener-attacks');
```

### ES Modules - direct call

Allows to call the fix explicitely

```js
  import { preventWindowOpenerAttacks } from 'prevent-window-opener-attacks/src/lib';
  preventWindowOpenerAttacks();
```

### CommonJS - direct call

Allows to call the fix explicitely

```js
  const { preventWindowOpenerAttacks } = require('prevent-window-opener-attacks/dist/lib.js');
  preventWindowOpenerAttacks();
```

### AMD JS - direct call

Allows to call the fix explicitely

```js
  require('prevent-window-opener-attacks/dist/lib.js', function({preventWindowOpenerAttacks}) {
  	preventWindowOpenerAttacks();
  });
```

## Test your site

Copy the following code in your dev-tools and click on the generated link on the bottom of your page. If your page redirect after clicking the generated link, you will need this fix.

```js
(function() {
	var a = document.createElement("a");
	a.href="https://reeko.github.io/prevent-window-opener-attacks/example/evil-page.html";
	a.target="_blank";
	a.innerHTML = "Click me!"
	document.body.appendChild(a);
})();
```
