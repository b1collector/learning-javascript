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

### Truthiness & Falsiness

```javascript
var und; // undefined
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

```javascript
console.log("undefined equality");
console.log(undefined == null); // true
console.log(undefined === null); // false

console.log("numeric equality");
console.log(1 === 1.0); //true

console.log("string equality");
console.log(0 == "0"); //true
console.log(0 === "0"); //false
console.log(true == "true"); // false
console.log("string" === "string"); //true

console.log("object equality");
var obj = {};
console.log({} == {}); // false
console.log(obj == {}); //false
console.log(obj === obj); // true
console.log([] == []); // false
```

## 2. Functions

### Hoisted Function Definitions

```javascript
var msg = "Hello world!";
sayMsg1(msg);
sayMsg2(msg);

function sayMsg1(msg) {
  console.log("sayMsg1 says: " + msg);
}

var sayMsg2 = function (msg) {
  console.log("sayMsg2 says: " + msg);
}

```

<details>
  <summary>How does the browser see this code?</summary>
  <p>
```javascript
var msg = "Hello world!";

function sayMsg1(msg) {
  console.log("sayMsg1 says: " + msg);
}

var sayMsg2;

sayMsg1(msg);
sayMsg2(msg);

sayMsg2 = function (msg) {
  console.log("sayMsg2 says: " + msg);
}
```
  </p>
</details>

### Hoisted Function Scope

```javascript
function fn(x) {
  if (x % 2 === 0) {
    var y = "even";
  } else {
    y = "odd";
  }
  return y;
}

var i;
for (i = 0; i < 10; i++) {
  console.log(fn(i));
}
```

<details>
  <summary>How does the browser see this code?</summary>
  <p>
```javascript
function fn(x) {
  var y;
  if (x % 2 === 0) {
    y = "even";
  } else {
    y = "odd";
  }
  return y;
}

var i;
for (i = 0; i < 10; i++) {
  console.log(fn(i));
}
```
  </p>
</details>

### Native Modules via Closures

```javascript
var teams = (function (defaultTeams) {
  function buildAssignments(){
    var i;
    var l = defaultTeams.length;
    var o = {};
    for(i = 0; i < l; i++){
      o[defaultTeams[i] = [];
    }
    return o;
  }

  var names = defaultTeams;
  var workAssignments = buildAssignments();



  function getTeams(){
    return names.slice();
  }

  function getWork(team) {
    if(names.indexOf(team) !== -1){
      return workAssignments[team];
    }
    return [];
  }

  function assignWork(team, work){
    if (names.indexOf(team) === -1) {
      return;
    }

    workAssignements[team].append(work);
  }

  return {
    teams: getTeams,
    work: getWork,
    assignWork: assignWork
  };
})(["cinnamon", "gold", "blue", "green"]);

console.log(teams.teams); // access module value
console.log(names); // undefined
```

### Arguments

```javascript
function sum() {
  var i;
  var l = arguments.length;
  var sum = 0;
  for(i = 0; i < l; i++) {
    sum += arguments[i];
  }
  return sum;
}

sum(1,2,3,5,8,13,21);
```

### Higher-order Functions

```javascript
function aggregate(fn, init, arr){
}
```

### Partial Application

## 3. Objects

