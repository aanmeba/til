# Convert value to boolean

You need to convert a value into boolean at times.

What I did originally was using ternary operator:

```
const value = 'value'
value ? true : false
```

A better way is using `!!`:

```
const value = 'value'
!value // false
!!value // true
```

If `disabled` property takes a boolean value in a component, you can pass the value using `!!`.

```
disabled={!!value}
```
