### Что выведется при нажатии, и как это исправить?

```html
<button>Zero</button>
<button>One</button>
<button>Two</button>
<button>Three</button>
<button>Four</button>
```
```js
var buttons = document.querySelectorAll('button');

for (var i = 0; i < buttons.length; i++) {
  buttons[i].onclick = function () {
    alert(i);
  }
}
```
#### Решение 1, IIFE:

```js
var buttons = document.querySelectorAll('button');

for (var i = 0; i < buttons.length; i++) {
  buttons[i].onclick = (function(n) {
    return (
      function() {
        alert(n)
      }
    )
  })(i)
}
```
#### Решение 2, let
```js
var buttons = document.querySelectorAll('button');

for (let i = 0; i < buttons.length; i++) {
  buttons[i].onclick = function () {
    alert(i);
  }
}
```
#### Решение 3, dataset
```js
var buttons = document.querySelectorAll('button');

for (var i = 0; i < buttons.length; i++) {
  buttons[i].dataset.i = i;
  buttons[i].onclick = function () {
    alert(this.dataset.i);
  }
}
```
