---
title: fold
tags: array,intermediate
firstSeen: 2021-12-12T08:10:00+00:00
---

Applies a function against an initial value and each element in the array (from left to right), returning a reduced value.

- Use `Array.prototype.reduce()` to reduce the array.

```js
const fold = (arr, initial, fn) => {
  return arr.reduce((acc, current) => fn(acc, current), initial);
};
```

```js
fold([1, 2, 3], 0, (a, b) => a + b); // 6
fold([1, 2, 3], 10, (a, b) => a + b); // 16
fold([-10, 2, 4], 1, (a, b) => a * b); // -80
fold([5, 25, 20], 150, (a, b) => a - b); // 100
fold([2, 2, 3, 5, 10], 600, (a, b) => a / b); // 1
fold([true, true, true, true], true, (a, b) => a && b); // true
fold([true, false, true, true], true, (a, b) => a && b); // false
fold([false, false, false, false], false, (a, b) => a || b); // false
fold([false, false, true, false], false, (a, b) => a || b); // true
```
