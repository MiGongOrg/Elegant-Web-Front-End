---
discription: You own style! 😎
---

# Base

## Variable

> `var` `let` `const`

### Before

```javascript
var apple  = 0;
var banana = 1;
var orange = 2;
```

### After

```javascript
var apple  = 0,
    banana = 1,
    orange = 2;
```

### Other

```javascript
var apple  = 0
  , banana = 1
  , orange = 2;
```

---

## Value

### Before

```javascript
counter = counter + 1;
```

### After

```javascript
counter += 1;
```

### Other

```javascript
counter++;
```

---

## Function

> ES 5 VS ES 6 return sum

### Before

```javascript
var sum = function (x) {
  return x + x;
};
console.log(sum(2)); // 4
```

### After

> This is ES 6 code, you can also see the ES 5 output

{% es6 -%}
let sum = x => x + x
console.log(sum(2)); // 4
{%- endes6 %}

---

## Array loops

### Before

```javascript
var array = [0, 1, 2, 3, 4, 5];
for (var i = 0; i < array.length; i++) {
  var item = array[i]
  console.log(item); // 0 1 2 3 4 5
};
```

### After

```javascript
var array = [0, 1, 2, 3, 4, 5];
array.forEach(function (item) {
  console.log(item); // 0 1 2 3 4 5
});
```

### Other

> This is ES 6 code, you can also see the ES 5 output

{% es6 -%}
let array = [0, 1, 2, 3, 4, 5];
array.forEach(item => console.log(item)); // 0 1 2 3 4 5
{%- endes6 %}

---