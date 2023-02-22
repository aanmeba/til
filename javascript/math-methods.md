# Math object and its methods

There are a couple of methods that are frequently used. Here is the list of the methods.

### `Math.max()` & `Math.min()`

`Math.max()` returns the largest of zero or more numbers, while `Math.min()` returns the smallest of zero or more numbers.

```
const arr = [0, 4, -3]

Math.max(1, 3, -2) // 3
Math.max(...arr) // 4

Math.min(1, 3, -2) // -2
Math.min(...arr) // -3
```

### `Math.random()`

Returns a pseudo-random number between 0 and 1.

```
Math.random() // a number from 0 to < 1

function getRandomNum (maxNum) {
  return Math.floor(Math.random() * max)
}

getRandomNum(3) // 0, 1 or 2
getRandomNum(1) // 0
```

## Confusing `Math` methods

| Methods        | What it does                                                              | Example                   |
| -------------- | ------------------------------------------------------------------------- | ------------------------- |
| `Math.abs()`   | Returns the **absolute value** of x.                                      | `Math.abs(-5) // 5`       |
| `Math.ceil()`  | **Rounds up** and returns the smaller integer greater than or equal to x. | `Math.ceil(5.004) // 6`   |
| `Math.floor()` | **Rounds down** and returns the largest integer less than or equal to x.  | `Math.floor(7.95) // 7`   |
| `Math.round()` | Returns the value of the number x **rounded to the nearest integer**.     | `Math.round(8.5) // 9`    |
| `Math.trunc()` | Returns the integer portion of x, **removing any fractional digits**.     | `Math.trunc(10.01) // 10` |

Reference:

- [MDN - Math](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math)
