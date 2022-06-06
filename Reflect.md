# Reflect

- The use of Reflect API in JavaScript enables you to invoke Object methods, get and set object property values, construct objects, extend and manipulate its properties at run-time. It also permits the creation of dynamic code-handling frameworks and programs.
- All Object methods in a single namespace.
- The Reflect API could be described as a collection or “central place” which houses all kind of object and function related functions (for creation, property management etc.) 

```javascript
class Person {
}

let config = {
 greet() {
    console.log('Hello there!');
 }
}

let person = Reflect.construct(Person, []);
Reflect.setPrototypeOf(person, config); // define prototype of object
Reflect.defineProperty(target, propertyKey, attributes);
// define propetry of object
const obj1 = {};
(Reflect.defineProperty(obj1, 'prop', {value: 60}));
console.log(obj1.prop); // 60

var x = [10,20,30,40,50];
console.log(Reflect.get(x, '1')); // 20
var x = [10,20,30,40,50];
Reflect.deleteProperty(x, '1');
```

## Proxy

- A JavaScript Proxy is an object that wraps another object (target) and intercepts the fundamental operations of the target object.  

```javascript
const target = {
  message1: "hello",
  message2: "everyone"
};
const handler1 = {};
const proxy1 = new Proxy(target, handler1);
console.log(proxy1.message1); // hello
console.log(proxy1.message2); // everyone


let person { age: 20, name: 'Max'};
let handler {
    get: function(target, name) {
        return name in target ? target[name] : 'Not available';
    }
}
var proxy = new Proxy({}, handler);
Reflect.setPrototypeOf(person, proxy);
console.log(person.hobbies); // 'Not available'

const handler2 = {
    set(target, property, value) {
        if (property === 'age') {
            if (typeof value !== 'number') {
                throw new Error('Age must be a number.');
            }
            if (value < 18) {
                throw new Error('The user must be 18 or older.')
            }
        }
        target[property] = value;
    }
};
const proxyUser = new Proxy(person, handler2);
proxyUser.age = 'foo'; // Error: Age must be a number.
```
