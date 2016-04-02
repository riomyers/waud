# ![waud logo](https://raw.githubusercontent.com/adireddy/waud/master/logo.png)
Web Audio Library with HTML5 audio fallback.

[![Build Status](https://travis-ci.org/adireddy/waud.svg?branch=master)](https://travis-ci.org/adireddy/waud) [![npm version](https://badge.fury.io/js/waud.js.svg)](https://badge.fury.io/js/waud.js) [![Code Climate](https://codeclimate.com/github/adireddy/waud/badges/gpa.svg)](https://codeclimate.com/github/adireddy/waud)
[![Code Climate Issues](https://img.shields.io/codeclimate/issues/github/adireddy/waud.svg)](https://codeclimate.com/github/adireddy/waud/issues)

| <img src="https://raw.githubusercontent.com/alrra/browser-logos/master/safari/safari_32x32.png" alt="Safari"> | <img src="https://raw.githubusercontent.com/alrra/browser-logos/master/chrome/chrome_32x32.png" alt="Chrome"> | <img src="https://raw.githubusercontent.com/alrra/browser-logos/master/firefox/firefox_32x32.png" alt="Firefox"> | <img src="https://raw.githubusercontent.com/alrra/browser-logos/master/edge/edge_32x32.png" alt="Edge"> | <img src="https://raw.githubusercontent.com/alrra/browser-logos/master/opera/opera_32x32.png" alt="Opera"> |
|:--:|:--:|:--:|:--:|:--:|
| Latest ✓ | Latest ✓ | Latest ✓ | Latest ✓ | Latest ✓ |

### Installation

`npm install waud.js`

For haxe users:

`haxelib install waud`

### [API Documentation](http://adireddy.github.io/docs/waud/)

### Example

Example: 
```js
var snd = new WaudSound("assets/loop.mp3", { autoplay: false, loop: true, volume: 0.5, onload: _playBgSound });
```

### Audio Sprite

Use [waudsprite](https://github.com/adireddy/waudsprite) to generate audio sprite.

```js
var audSprite = new WaudSound("assets/sprite.json");
audSprite.play("glass");
```

### Issues

Found any bug? Please create a new [issue](https://github.com/adireddy/waud/issues/new).

### Demo

- [JavaScript](http://adireddy.github.io/demos/waud/js.html)
- [Haxe](http://adireddy.github.io/demos/waud/)

### Usage

```js
Waud.init();
Waud.enableTouchUnlock(touchUnlock);
Waud.autoMute();

var _bgSnd = new WaudSound("assets/loop.mp3", {
	"autoplay": false, "loop":true, "volume": 0.5, "onload": _playBgSound
});

var snd2 = new WaudSound("assets/sound1.wav", {
	"autoplay": false,
	"loop":true,
	"onload": function (snd) { snd.play(); },
	"onend": function (snd) { console.log("ended"); },
	"onerror": function (snd) { console.log("error"); }
});

//Touch unlock event for iOS devices
function touchUnlock() {
	if (!_bgSnd.isPlaying()) _bgSnd.play();
}

function _playBgSound(snd) {
	if (!snd.isPlaying()) snd.play();
}
```

### Licensing Information

<a rel="license" href="http://opensource.org/licenses/MIT">
<img alt="MIT license" height="40" src="http://upload.wikimedia.org/wikipedia/commons/c/c3/License_icon-mit.svg" /></a>

This content is released under the [MIT](http://opensource.org/licenses/MIT) License.

### Contributor Code of Conduct ###

[Code of Conduct](https://github.com/CoralineAda/contributor_covenant) is adapted from [Contributor Covenant, version 1.4](http://contributor-covenant.org/version/1/4)
