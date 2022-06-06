# Symbols

- Symbols is new premitive type like numbers, string or boolean.
- symbol represent unique indentifier.
- symbols not iterable. cannot have for loop on it
- As they are unique symbols are useful as object keys.

```javascript
    let symbol = Symbol('debug');
    let obj = {
        name: 'max',
        symbol: 22
    }
    console.log(obj); // {name: 'max'}
    console.log(obj[symbol]); // 22

    Symbol.for('age') == Symbol.for('age');
    // above both symbol same because they have same id
```

## iterators and generators

- iterators allow you to iterate over an object (arrays are also objects)
- Generators are a useful tool that allows us to create iterators by defining a function.

```javascript
// iterators example
let array = [1, 2, 3];
let it = array[Symbol.iterator]();
it.next(); // {done: false, value: 1}
it.next(); // {done: false, value: 2}
it.next(); // {done: false, value: 3}
it.next(); // {done: true, value: undefined}

// generators example
function *stringGenerator() {
  yield '1';
  yield '2';
  yield '3';
}
let it = stringGenerator(); 
it.next(); // {done: false, value: 1}
it.next(); // {done: false, value: 2}
it.next(); // {done: false, value: 3}
it.next(); // {done: true, value: undefined}
```
