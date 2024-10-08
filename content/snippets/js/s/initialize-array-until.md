---
title: Initialize array until
type: snippet
language: javascript
tags: [array]
cover: neon-desk-2
dateModified: 2023-06-22
---

Initializes and fills an array with values generated by a function, until a condition is met.

- Create an empty array, `arr`, an index variable `i` and an element `el`.
- Use a `do...while` loop to add elements to the array, using the `mapFn` function, until the `conditionFn` function returns `true` for the given index `i` and element `el`.
- The condition function, `conditionFn`, takes three arguments: the current index, the previous element and the array itself.
- The mapping function, `mapFn`, takes three arguments: the current index, the current element and the array itself.

```js
const initializeArrayUntil = (conditionFn, mapFn) => {
  const arr = [];
  let i = 0;
  let el = undefined;
  do {
    el = mapFn(i, el, arr);
    arr.push(el);
    i++;
  } while (!conditionFn(i, el, arr));
  return arr;
};
```

```js
initializeArrayUntil(
  (i, val) => val > 10,
  (i, val, arr) => (i <= 1 ? 1 : val + arr[i - 2])
); // [1, 1, 2, 3, 5, 8, 13]
```
