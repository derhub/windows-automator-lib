# windows-automator-lib 



## Installation

Download node at [nodejs.org](http://nodejs.org) and install it, if you haven't already.

```sh
npm install windows-automator-lib --save
```

##Description
This is the wrapper of windows-OS keyboard/mouse simulator implemented in C++.

## Usage
[Examples here](https://github.com/samick17/windows-automator-lib/tree/master/examples)

  **Import module**

	const WinAutomatorLib = require('windows-automator-lib');
	const Core = WinAutomatorLib.Core;
	const HotkeyModifiers = WinAutomatorLib.HotkeyModifiers;
	const VK = WinAutomatorLib.VK;

  **window operation**

  *getAllWindows()*

	Core.getAllWindows();

will return like this

>[{ name: 'README.md - MarkdownPad ', hwnd: 721602 },
  { name: 'windows-automator-li', hwnd: 787412 },
  { name: 'Program Manage', hwnd: 65860 } ]

  *getWindowRect(hwnd)*
if hwnd is undefined use DesktopWindow hwnd instead

	Core.getWindowRect();

>{ x: 0, y: 0, w: 1440, h: 900 }

  *getWindowSize(hwnd)*
if hwnd is undefined use DesktopWindow hwnd instead

	Core.getWindowSize();

>{ w: 1440, h: 900 }


  *getActiveWindowRect()*

  *setActivwWindowRect()*

  *setActivwWindowRectByBame()*

	var hwnd = 123456;//you can find window hwnd by "getAllWindows()"
	setActiveWindow(hwnd);
	console.log(getActiveWindow());

>{w: yourWindowWidth, h: yourWindowHeight}


  **mouse/keyboard**

  *sendText(text)*

	Core.sendText('abcde');
	Core.sendText('這是中文');

  *mouseMove(x, y)*
move to position by global screen coord

  *mouseMoveRelative(x, y)*
move to position by "ActivwWindow" coord

  *mouseLeftDown()*

  mouseLeftUp()*

  *mouseLeftClick()*

  *mouseMiddleDown()*
  
  *mouseMiddleUp()*

  *mouseMiddleClick()*

  *mouseRightDown()*

  *mouseRightClick()*

  *mouseRightUp()*

  *mouseWheel(val)*

  **register hot key**

	var keyId = 1;//defined by yourself
	var success = Core.regHotKey(keyId, keyEventConfig.modKey, keyEventConfig.key);
	//TODO if register failed, do something
	var msg = Core.getHotKeyMsg();
	//TODO if msg is blablabla, handle event

## Dependencies

- [node-abi-version](https://github.com/samick17/windows-automator-lib): Get abi version by node/iojs version

## Dev Dependencies


None

## License

MIT

_Generated by [package-json-to-readme](https://github.com/zeke/package-json-to-readme)_
