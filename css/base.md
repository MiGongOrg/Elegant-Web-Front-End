---
discription: You own style! 😎
---

# Base

## Keyframe

### Before

```css
@keyframes down {
  0% {
    top: 0;
  }
  100% {
    top: 100%;
  }
}
```

### After

```css
@keyframes down {
  from {
    top: 0;
  }
  to {
    top: 100%;
  }
}
```

### Other

```css
@keyframes down {
  to {
    top: 100%;
  }
}
```

## Alternate

### Before

```css
.animation {
  animation-name: down;
  animation-duration: 5s;
  animation-timing-function: linear;
  animation-iteration-count: infinite;
  animation-direction: alternate;
}
@keyframes down {
  0% {
    top: 0;
  }
  100% {
    top: 100%;
  }
}
```

### After

```css
.animation {
  animation: down 5s linear infinite alternate;
}
@keyframes down {
  to {
    top: 100%;
  }
}
```

### Other

```css
.animation {
  animation: down 5s linear infinite;
}
@keyframes down {
  50% {
    top: 100%;
  }
}
```

## Spacing

### Before

```css
li {
  margin-top: 20px;
}
li:first-child {
  margin-top: 0;
}
```

### After

```css
li:not(:first-child) {
  margin-top: 20px;
}
```

### Other

```css
ul * + * {
  margin-top: 20px;
}
```