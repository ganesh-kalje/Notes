## Let and const block
let allow us to declare variable inside scope or limited to particular scope of block statement.\
Difference between let and var\
- let is block scope => var is function scope
- let does not allow to redeclare variables. => var allows to redeclare variables
- Hoisting does not occur in let. => Hoisting occurs in var

```
console.log(a);
var a; // undefined (not an error)

console.log(a);
let a; // Uncaught ReferenceError: a is not defined
```

## const
- varibale declared using const cannot be reassigned, cannot be redeclared and in have Block Scope.
- Globale constant do not become property of window object like var.
- You must specify its value in the same statement in which it's declared

## Fat arrow function
- An arrow function expression is a compact alternative to a traditional function expression or declaration
- short hand version to declare function
```
const fn = () => "name"; // not require return keyword  
```
## Disadvantegeous 
- Arrow function dont have thir own binding for this, arguments and super
- Arrow functions don't have access to the new.target keyword.
- new.target like wheather object is create with new or not
- not suitable for call,bind and apply
- fat arrow function and this with arrow functions there are no binding of this.

## Function default paramenter
- function parameters default to undefined. but es6 we can assign default value to parmenter in function
```
function fn(number, cmp = 10) {
    return number * cmp; //it will return 200
}

fn(20);

function fn(number = 10, cmp) {
    return number* cmp; // it will return error
}

fn(20);
```

## Object literal extenstion
- ES6 makes the object literal more succinct and powerful by extending the syntax in some ways.
```
let name = 'max';
let obj = {name , [name] : 'man'} 
// {name: 'max', max: 'man'}
```
- when declaring object it will look for surrounding varibale and create object property and value for it.
- same for function decalration and use in object decalraition

## Rest opertator
- In function defination last parameters can be prefixed with ... (FULL stop characters), which will cause all remaining parameters
to be placed within statndard javascript array.
```
function myFun(a,  b, ...manyMoreArgs) {}

myFun("one", "two", "three", "four", "five", "six")
// ["three", "four", "five", "six"]
```

## Spread syntax
- spread syntax can be use to all elmenet from object or array need to be included in a list of some kind.

```
function sum(x, y, z) { 
    // x = 1 y = 2 and z =3
    return x + y + z;
}

const numbers = [1, 2, 3];
console.log(sum(...numbers)) expected output: 6
```
- When we invoke the function, we pass it all the values in the array using the spread syntax and the array name
```
let parts = ['shoulders', 'knees'];
let lyrics = ['head', ...parts, 'and', 'toes'];
//  ["head", "shoulders", "knees", "and", "toes"]
```

## Template literal
Template literal use for string interpolation and multiline string. Template literals are literals delimited with backtick (`) characters,
template literals can also contain other parts called placeholders, which are embedded expressions delimited by a dollar sign and curly braces: ${expression}

## Destrcturing array and object
Destrcturing expression makes it possible to unpack values from arrays, or properties from objects, into distinct variables.
```
let a, b, rest;
[a, b] = [10, 20];
console.log(a); // 10
console.log(b); // 20

// Swaping value
let a = 1;
let b = 3;
[a, b] = [b, a];
console.log(a); // 3
console.log(b); // 1
```
