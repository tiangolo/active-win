# active-win [![Build Status](https://travis-ci.org/sindresorhus/active-win.svg?branch=master)](https://travis-ci.org/sindresorhus/active-win)

Get the title / window id / app name / process ID of the [active window](https://en.wikipedia.org/wiki/Active_window) *(macOS, Linux and Windows)*

## Notice

This package is here for development and testing purposes. Please use the [official version](https://github.com/sindresorhus/active-win).

## Install

```
$ npm install --save active-win
```


## Usage

```js
const activeWin = require('active-win');

activeWin().then(result => {
	console.log(result);
	/*
	{
		title: 'npm install',
		id: 54,
		app: 'Terminal',
		pid: 368
	}
	*/
});
```


## API

### activeWin()

Returns a `Promise` for the result `Object`.

### activeWin.sync()

Returns the result `Object`.


## Result

- `title` - Window title
- `id` - Window ID (in macOS and Linux)
- `app` - App owning the window
- `pid` - Process ID of the app owning the window


## Operating system support

It works with macOS, Linux and Windows 7+.

**Note**: In Windows, there isn't a clear notion of a "Window ID". So, when used in Windows, it returns the memory address of the window "handle" in the `id` property of the object, that "handle" is unique per window, so it can be used to identify them. To learn more about it refer to the [official Windows documentation](https://msdn.microsoft.com/en-us/library/windows/desktop/ms632597(v=vs.85).aspx#window_handle).


## Related

- [active-win-cli](https://github.com/sindresorhus/active-win-cli) - CLI for this module


## License

MIT © [Sindre Sorhus](https://sindresorhus.com)
