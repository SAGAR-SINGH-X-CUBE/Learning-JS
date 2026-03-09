# Variables

`var` is **function scoped**, while `let` is **block scoped** (including function blocks).

```javascript
function demo() {
  if (true) {
    var x = 10;
    let y = 20;
  }

  console.log(x); // works
  console.log(y); // Error
}
```

---

# JavaScript Data Types & Type Conversion Notes

## Data Types in JavaScript

### Primitive Data Types (Call by Value)

JavaScript has **7 primitive data types**:

- String
- Number
- Boolean
- null
- undefined
- Symbol
- BigInt

Example:

```javascript
let name = "Sagar";   // String
let age = 22;         // Number
let isStudent = true; // Boolean
let x = null;         // null
let y;                // undefined
```

---

### Non-Primitive (Reference) Data Types

Stored **by reference in memory**.

- Object
- Array
- Function

Example:

```javascript
let arr = [1, 2, 3];        // Array
let obj = { name: "Sagar" };// Object

function greet() {
  console.log("Hello");
}
```

---

## typeof Operator

Used to check the **data type**.

```javascript
typeof "hello";       // string
typeof 10;            // number
typeof true;          // boolean
typeof undefined;     // undefined
typeof null;          // object (known JavaScript bug)

typeof {};            // object
typeof [];            // object
typeof function(){};  // function
```

---

## JavaScript is Dynamically Typed

In JavaScript, **we do not need to define the variable type**.

The type is determined **at runtime**.

```javascript
let x = 10;     // number
x = "hello";    // now string
```

---

# Type Conversion

## String → Number

```javascript
let x = "10";
let num = Number(x);

console.log(num); // 10
```

Invalid number example:

```javascript
let x = "10aa";
let num = Number(x);

console.log(num); // NaN
```

Boolean to number:

```javascript
let x = true;
let num = Number(x);

console.log(num); // 1
```

Other conversions:

```
undefined → NaN
null → 0
```

---

## Convert to Boolean

Rules:

```
1  → true
0  → false
"" → false
anything else → true
```

Example:

```javascript
Boolean(1);        // true
Boolean(0);        // false
Boolean("");       // false
Boolean("Sagar");  // true
```

---

# Operations in JavaScript

```javascript
console.log(1 + 2 + "3"); // "33"
console.log("1" + 2 + 3); // "123"
```

Explanation:

```
1 + 2 + "3"

1 + 2 = 3
3 + "3" = "33"


"1" + 2 + 3

"1" + 2 = "12"
"12" + 3 = "123"
```

---

# Special Case: null Comparisons

```javascript
console.log(null > 0);   // false
console.log(null == 0);  // false
console.log(null >= 0);  // true
```

Explanation:

- Comparison operators (`>`, `<`, `>=`, `<=`) convert **null → 0**
- Equality check behaves differently

---

# Equality Operators

## `==` (Loose Equality)

Checks **only value** and performs **type conversion**.

```javascript
5 == "5"; // true
```

---

## `===` (Strict Equality)

Checks **value + data type**.

```javascript
5 === "5"; // false
```

---

# Memory Behavior

## Primitive Types

Stored **directly** and passed **by value**.

```
string
number
boolean
null
undefined
symbol
bigint
```

---

## Non-Primitive Types

Stored **by reference**.

```
array
object
function
```
