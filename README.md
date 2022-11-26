# Rest / Spread Operator Exercises

In this exercise, you’ll refactor some ES5 code into ES2015.

**Given this function:**

```JavaScript

function filterOutOdds() {
  var nums = Array.prototype.slice.call(arguments);
  return nums.filter(function(num) {
    return num % 2 === 0
  });
}

```
Refactor it to use the rest operator & an arrow function:

```JavaScript

/* Write an ES2015 Version */

const filterOutOdds = (...params) => {
    return params.filter(val => val % 2 === 0);
}

/** OR **/

const filterOutOdds = (...params) => (params.filter(val => val % 2 === 0));

```


**findMin**

Write a function called findMin that accepts a variable number of arguments and returns the smallest argument.

Make sure to do this using the rest and spread operator.

```JavaScript

const findMin = (...params) => { 
    return Math.min(...params);
};

/** OR **/

const findMin = (...params) => (Math.min(...params)) ;

findMin(1,4,12,-3) // -3
findMin(1,-1) // -1
findMin(3,1) // 1

```

**mergeObjects**

Write a function called mergeObjects that accepts two objects and returns a new object which contains all the keys and values of the first object and second object.

```JavaScript

const mergeObjects = (object1,object2) => {
    return {...object1, ...object2};
};

/** OR **/

const mergeObjects = (object1,object2) => ({...object1, ...object2});

mergeObjects({a:1, b:2}, {c:3, d:4}) // {a:1, b:2, c:3, d:4}

```

**doubleAndReturnArgs**

Write a function called doubleAndReturnArgs which accepts an array and a variable number of arguments. The function should return a new array with the original array values and all of additional arguments doubled.

```JavaScript

const doubleAndReturnArgs = (arr, ...params) => { 
    return [...arr, ...params.map(val => val * 2)];
}

/** OR **/

const doubleAndReturnArgs = (arr, ...params) => ([...arr, ...params.map(val => val * 2)]);

doubleAndReturnArgs([1,2,3],4,4) // [1,2,3,8,8]
doubleAndReturnArgs([2],10,4) // [2, 20, 8]

```

**Slice and Dice!**

For this section, write the following functions using rest, spread and refactor these functions to be arrow functions!

Make sure that you are always returning a new array or object and not modifying the existing inputs.

```JavaScript

/** remove a random element in the items array
and return a new array without that item. */


const removeRandom = (items) => {
    let indexItem = Math.floor(Math.random() * items.length);
    return [...items.slice(0, indexItem), ...items.slice(indexItem + 1)];
}

/** Return a new array with every item in array1 and array2. */

const extend = (array1, array2) => {
    return [...array1, ...array2];
}

/** OR **/

const extend = (array1, array2) => ([...array1, ...array2]);


/** Return a new object with all the keys and values
from obj and a new key/value pair */

const addKeyVal = (obj, key, val) => {
   return { ...obj, [key]: val };
}


/** Return a new object with a key removed. */

const removeKey = (obj, key) => {
    let newObject = { ...obj }
    delete newObject[key]
    return newObject;
}


/** Combine two objects and return a new object. */

const combine = (obj1, obj2) => {
   return {...obj1, ...obj2};
}

/** OR **/

const combine = (obj1, obj2) => ({...obj1, ...obj2});


/** Return a new object with a modified key and value. */

const update = (obj, key, val) => {
   return { ...obj, [key]: val };
}

/** OR **/

const update = (obj, key, val) => ({ ...obj, [key]: val });

```
