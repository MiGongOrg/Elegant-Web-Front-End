---
discription: You own style! 😎
---

# Advanced

## String To Array

### Before

```javascript
var str = 'hello world';
console.log(str.split('')); // ["h", "e", "l", "l", "o", " ", "w", "o", "r", "l", "d"]
```
### After

{% es6 -%}
let str = 'hello world';
console.log([...str]); // ["h", "e", "l", "l", "o", " ", "w", "o", "r", "l", "d"]
{%- endes6 %}

## Array Dedupe

### Before

```javascript
var array = [1, 1, 2, 2, 3, 3];
var af = array.filter(function (el, i, a) {
  return i === a.indexOf(el)
});
console.log(af); // [1, 2, 3]
```

### After

{% es6 -%}
let array = [1, 1, 2, 2, 3, 3];
console.log([...new Set(array)]); // [1, 2, 3]
{%- endes6 %}