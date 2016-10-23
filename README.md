# Learning JavaScript: A Guided Introduction

These exercises were created to guide a lunch & learn to introduce junior software developers
to the eccentric nature of JavaScript.

## Variables & Types

### Strings

```javascript
var str1 = 'Hello World';
var str2 = "Hello World";

console.log(str1);
console.log(str2);
console.log(str1 === str2);
```

> Hello World
>
> Hello World
>
> true

### Truthiness & Falsiness

```javascript
var und;
var n = null;
var arr1 = [ "", "false", "true", und, n, -1, 0, 1, true, false, [], [1,2,3], {}, {a:1}];

var i = 0;
var len = arr1.length;
for(i; i < len; i++) {
  var str = "'" + arr1[i] + "' (" + typeof(arr1[i]) + ") is considered " + (arr1[i] ? "true" : "false");

  console.log(str);
}
```

### Equality

### Null, undefined

## 2. Functions

## 3. Objects

## 4. Functional Programming

## 5. Object-oriented Programming
