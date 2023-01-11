# Difference between `Math.trunc()` and `Math.floor()`

To get a random number, you normally use one of those built-in methods in JavaScript. They seem to work in the same way, but there is difference.

`Math.trunc()` rounds down a number to an integer towards `0` while `Math.floor()` rounds down a number to an integer towards `-Infinity`. As illustrated with the following number line, the direction will be the same for a positive number **while for a negative number, the directions will be the opposite**.

```
trunc: towards 0
floor: towards -Infinity


                   -3      -2     -1      0      1      2      3
-Infinity ... ------+----|--+------+------+------+------+--|----+------ .... Infinity
                         b                                 a
```

### Demo

```javascript
const a = 2.3,
  b = -2.3;
console.log(
  "\t\t\t" +
    a +
    "\t\t" +
    b +
    "\r\n" +
    "Math.trunc: " +
    Math.trunc(a) +
    "\t\t" +
    Math.trunc(b) +
    "\r\n" +
    "Math.floor: " +
    Math.floor(a) +
    "\t\t" +
    Math.floor(b)
);
```

### Output

```
            2.3     -2.3
Math.trunc: 2       -2
Math.floor: 2       -3
```

### Example from MDN

```javascript
Math.trunc(-Infinity); // -Infinity
Math.trunc("-1.123"); //⚠️ -1
Math.trunc(-0.123); // ⚠️ -0
Math.trunc(-0); // -0
Math.trunc(0); // 0
Math.trunc(0.123); // 0
Math.trunc(13.37); // 13
Math.trunc(42.84); // 42
Math.trunc(Infinity); // Infinity

Math.floor(-Infinity); // -Infinity
Math.floor("-1.123"); //⚠️ -2
Math.floor(-0.123); // ⚠️ -1
Math.floor(-0); // -0
Math.floor(0); // 0
Math.floor(0.123); // 0
Math.floor(13.37); // 13
Math.floor(42.84); // 42
Math.floor(Infinity); // Infinity
```

### Reference:

- [Stack Overflow] [Math.floor VS Math.trunc JavaScript](https://stackoverflow.com/questions/38702724/math-floor-vs-math-trunc-javascript#:~:text=in%20this%20answer.-,Math.,directions%20will%20be%20the%20opposite.)
- [MDN] [Math.floor](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/floor)
- [MDN] [Math.trunc](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/trunc)
