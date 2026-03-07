var is function scoped, while let is block scoped (including function blocks).

```javascript
function demo() {
  if (true) {
    var x = 10;
    let y = 20;
  }

  console.log(x); // works
  console.log(y); // Error
}
