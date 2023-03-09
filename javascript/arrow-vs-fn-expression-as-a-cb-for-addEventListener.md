# Arrow function vs function expression as a callback for `addEventListener`

I tried to access `this.style` inside of the callback function of an event listener. When I used an arrow fucnction for a callback, it returned `undefiend`, while it returned as I expected when I used a regular function expression.

What's happening?

When using an arrow function as the callback function for `addEventListener`, the value of `this` is determined by the **lexical scope**, which means that `this` refers to the `this` value of the enclosing function. This can be different from the `this` value that would be set when using a regular function expression.

On the other hand, when using a regular function expression as the callback function, the value of `this` is set to the **value of the object that dispatched the event**. In other words, the value of `this` is dynamically determined at the time the function is called.

For example, if you have an HTML button element and you want to change its color when it is clicked, you could use the following code:

```javascript
const button = document.querySelector("button");

// using an arrow function
button.addEventListener("click", () => {
  // 'this' refers to the enclosing function's 'this' value, not the button element
  this.style.backgroundColor = "red"; // throws an error
});

// using a function expression
button.addEventListener("click", function () {
  // 'this' refers to the button element
  this.style.backgroundColor = "red"; // works
});
```

In the first example, the arrow function is not able to access the `style` property of the button element because `this` does not refer to the button element, but rather to the enclosing function's `this` value, which in this case would be the global window object.

In the second example, the regular function expression is able to access the `style` property of the button element because `this` is dynamically set to the button element when the function is called.
