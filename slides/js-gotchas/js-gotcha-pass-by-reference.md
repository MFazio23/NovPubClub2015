#JavaScript "Gotchas"
##Pass by Value/Reference

```
var num = 10,
    objA = { item: 7 },
    objB = { item: 11 };

function changeStuff(a, b, c) {
  a = a + 5;
  b.item = b.item + 3;
  c.item = c.item + ' extras';
}

num = 10;
objA = { item: 7 };
objB = { item: 11 };

changeStuff(num, objA, objB);

console.log("End =", num, objA, objB); //10, {item: 10}, {item: "11 extras"}
```

Note:
+ Pass by value, but...
    + The value passed for objects are references to the object
        + This means internal items on an object can be changed
        + Primitives look like they're pass by value (because they are)
+ Can be considered "call by sharing"
    + Also Java (considered pass-by-value) and Ruby (considered pass-by-reference)