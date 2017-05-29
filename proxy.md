        Proxy 是透過封裝物件，用攔截的方式來修改某些操作的預設行為，比如取得屬性值我們可以為需要攔截的物件提供一個帶有 traps 的函數對象，如物件操作沒有定義 traps 將會指向原始的物件操作上。

```js
const handler = {
  get (target, prop) {
    const val = target[prop];
    console.log(`property ${prop} = ${val}`);
    return val;
  }
};

const p = new Proxy({a: 1}, handler);

console.log(p.a);
// property a = 1
// 1
console.log(p.b);
// property b = undefined
// 1
```



