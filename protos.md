### Что здесь произойдет?
```js
function MyClass (name) {
  this.options.name = name;
}

MyClass.prototype.options = {
  name: 'default'
};

var foo = new MyClass('foo');
var bar = new MyClass('bar');

console.log( foo.options.name, bar.options.name );
```

this.options.name будет записан в объект-прототип для foo и bar, т.к. свойства options в них нет. Поэтому при создании новых экземпляров мы будем перезаписывать это свойство в прототипе.
