Demonstrates an issue with `babel-plugin-istanbul` and the following code:

```js
let accept = true,
  value = [];
for (let i = 0, len = value.length, val, ftype, fext; i < len; ++i) {
  val = value[i];
  if (accept) {
    ftype = val.type || "";
    fext = "blahblah";
    if (
      !accept.some(function (type) {
        return typeof type === "string"
          ? type === (type.charAt(0) === "." ? fext : ftype)
          : type.test(ftype);
      })
    ) {
      console.log("foo");
    }
  }
}
```
