# concept-JS



- AMD vs CommonJS?
- difference between a variable that is:```null```,```undefined```or undeclared
- What is a closure
- Can you describe the main difference between a `forEach` loop and a `.map()` loop and why you would pick one versus the other?
- What's the difference between an "attribute" and a "property"?
- What are the differences between variables created using `let`, `var` or `const`?




### AMD vs CommonJS

AMD  was designed explicitly with the browser in mind

CommonJS was designed for a general-purpose JavaScript environment



### null vs undefined



### closure





### forEach vs map

`foreach`: executes a provided function once per array element.

unlike `map()`or `reduce()` it always returns the value `undefined` and is not chainable



`map`: creates a new array with the results of calling a provided function on every element in this array.

map会return一个新的copy



### attribute vs property



### let var const

`const` Const is block scoped, identifier can’t be reassigned.

`var` Globally scoped, Can be hoisted(在前面申明，但不赋值)

`let` Let is block scoped, Can't be hoisted