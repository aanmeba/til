# [Condition] String has lowercase and uppercase

The easiest way to check a string has minimum 1 character for both uppercase and lowercase letter without regex.

### Type 1

This solution below is what I have done to solve this problem.

```javascript
const stringToLowerCase = (str) => {
  // str = "abc"
  // "abc" === "abc" => true
  // str = "ABc"
  // "abc" === "ABc" => false
  // str = "ABC"
  // "abc" === "ABC" => false
  return str.toLowerCase() === str;
};

const stringToUpperCase = (str) => {
  // str = "abc"
  // "ABC" === "abc" => false
  // str = "ABc"
  // "ABC" === "ABc" => false
  // str = "ABC"
  // "ABC" === "ABC" => true
  return str.toUpperCase() === str;
};

if (!stringToLowerCase(text) && !stringToUpperCase(text))
  return "You need minimum 1 character for both uppercase and lowercase letter";
```

### Type 2

This code below is what I found in the internet and I want to understand which makes it better code.

```javascript
const hasLowerCase = (str) => {
  // str = "abc"
  // "ABC" !== "abc" => true
  // str = "ABc"
  // "ABC" !== "ABc" => true
  // str = "ABC"
  // "ABC" !== "ABC" => false
  return str.toUpperCase() !== str;
};

const hasUpperCase = (str) => {
  // str = "abc"
  // "abc" !== "abc" => false
  // str = "ABc"
  // "abc" !== "ABc" => true
  // str = "ABC"
  // "abc" !== "ABC" => true
  return str.toLowerCase() !== str;
};

if (!hasLowerCase(text) || !hasUpperCase(text))
  return "You need minimum 1 character for both uppercase and lowercase letter";
```

If you name the functions, `hasUpperCase`, it should return `true` if a string has uppercase characters.

```javascript
let str = "abcd";
str.toUpperCase(); // ABCD
str.toLowerCase(); // abcd

str = "ABCD";
str.toUpperCase(); // ABCD
str.toLowerCase(); // abcd

str = "ABcd";
str.toUpperCase(); // ABCD
str.toLowerCase(); // abcd

function hasUpperCase(string) {
  // return string.toUpperCase() === string // => make no sense, it will return true at any case
  // return string.toUpperCase() !== string // => make no sense, it works the opposite way
  // return string.toLowerCase() === string // => make no sense, it works the opposite way
  return string.toLowerCase() !== string; // => works! it will return true if a string has uppercase characters
}
```
