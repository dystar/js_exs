#### Напишите аналог _.get в lodash/underscore.

Примеры:
```js
get({ a: { b: 1 } }, 'a.b') // 1
get({ a: { b: 1 } }, 'a.c') // undefined
get({ }, 'a.c') // undefined
```

```js
function get(obj, selector) {
  var path = selector.split(".");
  for (var el of path) {
    if(obj.hasOwnProperty(el))
      obj = obj[el];
    else {
      obj = undefined;
      break;
    }
  }
  console.log(obj);
}
```
