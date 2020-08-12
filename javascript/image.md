---
discription: You own style! 😎
---

# Image

## Image To Base64

```javascript
var imageToBase64 = function(file) {
  return new Promise((resolve, reject) => {
    var reader = new FileReader();
    var base64Result = null;
    reader.readAsDataURL(file);
    reader.onload = function() {
      base64Result = reader.result;
    }
    reader.onerror = function(error) {
      reject(error);
    }
    reader.onloadend = function() {
      resolve(base64Result);
    }
  })
}
```

---

## Base64 To Image

```javascript
var base64ToImage = function(base64Data, filename) {
  var arr = base64Data.split(',');
  var mime = arr[0].match(/:(.*?);/)[1];
  var bstr = atob(arr[1]);
  var n = bstr.length;
  var u8arr = new Uint8Array(n);
  while (n--) {
    u8arr[n] = bstr.charCodeAt(n);
  }
  return new File([u8arr], filename, { type: mime });
}
```