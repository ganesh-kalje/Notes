# Promice

- Promises are used to handle asynchronous operations in JavaScript.
- The Promise object represents the eventual completion (or failure) of an asynchronous operation and its resulting value
- A Promise is in one of these states pending, fulfilled or rejected
- Primice.all executed only all promice resolved succesfully.one of promice is rejected it only send reject response.

```javascript
let promice = new Promice(function(resolve, reject) {
    setTimeout(() => resolve('resolve'), 1000);
});

let promice2 = new Promice(function(resolve, reject) {
    setTimeout(() => reject('reject'), 2000);
});

Promice.all([promice, promice2])
    .then((success) => console.log(success))
    .catch((error) => console.log(error));
// print reject, if we use Promice.race then it will return resolve promices

```
