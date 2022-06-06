# Map

- The Map object holds key-value pairs and remembers the original insertion order of the keys.
- A Map object iterates its elements in insertion order — a for...of loop returns an array of [key, value] for each iteration

## Objects vs. Maps

- Object: An Object has a prototype, so it contains default keys. Map: A Map does not contain any keys by default.
- A Map's keys can be any value (including functions, objects, or any primitive). The keys of an Object must be either a String or a Symbol.
- A Map object iterates its elements in insertion order.
that no single mechanism iterates all of an object's properties. for..of, Object.keys etc
- The number of items in a Map is easily retrieved from its size property. The number of items in an Object must be determined manually.
- Performs better in scenarios involving frequent additions and removals of key-value pairs in Map. Object Not optimized for frequent additions and removals of key-value pairs.

```javascript
const contacts = new Map()
contacts.set('Jessie', {phone: "213-555-1234", address: "123 N 1st Ave"})
contacts.has('Jessie') // true
contacts.get('Jessie')
```

## weakMap

- The keys of WeakMap, on the other hand, must be objects, whereas the values can be anything.
- The object references in the keys are held weakly, which means that if there is no other reference to the object, it will be eligible for garbage collection.

```javascript
const wm1 = new WeakMap(),
      wm2 = new WeakMap(),
      wm3 = new WeakMap();
const o1 = {},
      o2 = function() {},
      o3 = window;

wm1.set(o1, 37);
wm1.set(o2, 'azerty');
wm2.set(o1, o2);
```

## set

- A JavaScript Set is a collection of unique values. Each value can only occur once in a Set.

```javascript
let set = new Set([1,1,1]);
set.add(2);
for(element of set) {
    console.log(element) // 1, 2
}
```

## weakset

- A WeakSet() is a collection that is similar to a Set because it retains unique values; but it can only hold Objects. If an object in your WeakSet has no other reference variables left, it will be removed automatically.

```javascript
var weakSet1 = new WeakSet([{x:1}]);
var ob1 = {o:1};
var ob2 = {o:2};
```

## set vs weakset

- A set can contain all types of values. A weakSet can only contain objects.
- set Use .size to find the number of elements, weakset Use .length to find the number of elements.
- .forEach() is available for iteration. weakset .forEach() is not available for iteration.
- Nothing is auto-destroyed in set, In weakset An element object will be auto released to the garbage collector if it has no other reference left.
