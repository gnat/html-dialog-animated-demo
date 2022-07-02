# Modern animated HTML Dialog in 2022

Minimalist, `<dialog>` example, keeping it simple.

### References
[Adam Argyle / argyleink](https://github.com/argyleink) from Google, extended Dialog Tutorial (2022)

[![Adam Argyle's Dialog Tutorial](http://img.youtube.com/vi/GDzzIlRhEzM/0.jpg)](https://www.youtube.com/watch?v=GDzzIlRhEzM "Adam Argyle's Dialog Tutorial")
* [MDN: dialog](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dialog)
* [MDN: HTMLDialogElement](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDialogElement)
* [Can I use dialog ?](https://caniuse.com/dialog)

### Source (demo.html)

```html
<!DOCTYPE html>
<html lang="en">
	<head>
		<style>
		dialog {
			display: grid;
			position: absolute;
			top: 0;
			right: 0;
			left: 0;
			margin: 0 auto;
			transition: all 2s;
		}
		dialog:not([open])  {
			animation: slideout 2s forwards;
			pointer-events: none;
			opacity: 0;
		}
		dialog[open] {
			animation: slidein 2s forwards;
		}
		@keyframes slidein {
			0% { margin-top: -10vh; }
			100% { margin-top: 10vh; }
		}
		@keyframes slideout {
			0% { margin-top: 10vh; }
			100% { margin-top: -10vh; }
		}
		</style>
	</head>
	<body>
		<dialog>
			Hello World
			<button onclick="document.querySelectorAll('dialog')[0].close()">Close</button>
		</dialog>
		<button onclick="document.querySelectorAll('dialog')[0].showModal()">Open Dialog</button>
	</body>
</html>
```
