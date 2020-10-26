---
title: sortObjectByValues
tags: object,sort,intermediate
---

Sort object by values

- First flatten object to list of arrays with `Object.entries(obj)`
- Sort list of arrays with `Array.prototype.sort()` and assign with function expression as a,b
- Wrap list of arrays to object with `Object.fromEntries(arr)`

```js
const sortObjectByValues = (obj, isReverse=false) => {
  if ( isReverse === false ) {
    const obj_sorted = Object.fromEntries(
    Object.entries(obj).sort(([,a],[,b]) => a-b) 
    )
    return obj_sorted;
  } else {
    const obj_sorted = Object.fromEntries(
    Object.entries(obj).sort(([,a],[,b]) => b-a) 
    )
    return obj_sorted;
  }
};

```

```js

console.log(sortObjectByValues({
    car: 300, 
    bike: 60, 
    motorbike: 200, 
    airplane: 1000,
    helicopter: 400, 
    rocket: 8 * 60 * 60
}, isReverse=false  )
); 
// Object { bike: 60, motorbike: 200, car: 300, helicopter: 400, airplane: 1000, rocket: 28800 }
```
