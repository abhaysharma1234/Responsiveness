# JavaScript Function Concepts

## 1. Function Hoisting

**Hoisting** means JavaScript moves **function declarations to the top of their scope** during compilation, so they can be called before they appear in the code.

### Example

```javascript
greet();

function greet() {
  console.log("Hello World");
}
```

Output

```
Hello World
```

### Function Expression is Not Fully Hoisted

```javascript
greet();

var greet = function () {
  console.log("Hello");
};
```

Output

```
TypeError: greet is not a function
```

Reason: Only the variable declaration is hoisted, not the function definition.

---

# 2. What Happens When a Function Has No Return Statement

If a function does not return a value, JavaScript automatically returns:

```
undefined
```

### Example

```javascript
function add(a, b) {
  let sum = a + b;
}

let result = add(2, 3);
console.log(result);
```

Output

```
undefined
```

### Correct Version

```javascript
function add(a, b) {
  return a + b;
}

console.log(add(2, 3));
```

Output

```
5
```

---

# 3. Different Ways of Declaring a Function

## 1. Function Declaration

```javascript
function add(a, b) {
  return a + b;
}
```

---

## 2. Function Expression

```javascript
const add = function (a, b) {
  return a + b;
};
```

---

## 3. Arrow Function (ES6)

```javascript
const add = (a, b) => {
  return a + b;
};
```

Short version

```javascript
const add = (a, b) => a + b;
```

---

## 4. Anonymous Function

Function without a name, commonly used as a callback.

```javascript
setTimeout(function () {
  console.log("Hello");
}, 1000);
```

---

# 4. Pass by Value vs Pass by Reference

## Pass by Value

Primitive values are copied when passed to a function.

Primitive types:
- Number
- String
- Boolean
- Null
- Undefined

Example:

```javascript
function modify(x) {
  x = x + 10;
}

let num = 5;
modify(num);

console.log(num);
```

Output

```
5
```

The original value does not change because only a copy is passed.

---

## Pass by Reference

Objects and arrays are passed by reference, meaning the function works with the same memory location.

Example:

```javascript
function modify(obj) {
  obj.value = 20;
}

let data = { value: 10 };

modify(data);

console.log(data.value);
```

Output

```
20
```

Because both variables refer to the same object in memory.

---

# Summary

| Concept | Key Idea |
|------|------|
| Function Hoisting | Function declarations move to the top of scope |
| No Return Statement | Function returns `undefined` |
| Function Declaration | Standard named function |
| Function Expression | Function stored in a variable |
| Arrow Function | Short ES6 syntax |
| Pass by Value | Primitive values are copied |
| Pass by Reference | Objects/arrays share memory |
