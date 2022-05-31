# Modules

- Providing mechanisms for splitting JavaScript programs up into separate modules that can be imported when needed.

- JavaScript modules allow you to break up your code into separate files.

- Modules are always in Strict Mode (no need to define "use strict")

- Modules don't have a shared, global Scope. Instead each Module has its own Scope

```javascript
// external.js
export let price = 100;
export function test() {
    return 'test';
}
export default defaultString = 'default';

// script.js
import {price} from 'external.js';
import defaultString from 'external.js';
import {test as key} from 'external.js'; // alies name for test 
console.log(price); // 100
console.log(key()); // test
console.log(defaultString); // default
```

## Class

- get and set methods is use to assign value to variable.

```javascript
class Person {
    constructor(name) {
        this.name = name;
    }

    greet() {
        console.log(`name is ${this.name}`);
    }
}

class Ganesh extends Person {
    constructor(age) {
        this.age = age;
        super('ganesh');
        super.greet();
    }
}
const person = new Person('name');
person.greet(); // name is ganesh

class Helper {
    static hello() {
        console.log('this function will call without object creation');
    }
}
Helper.hello(); // this function will call without object creation
```
