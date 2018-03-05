# concept-JS



- Array.prototype.slice.call
- difference between throttle and debounce
- what is closure
- AMD vs CommonJS?
- difference between a variable that is:```null```,```undefined```or undeclared
- Can you describe the main difference between a `forEach` loop and a `.map()` loop and why you would pick one versus the other?
- What's the difference between an "attribute" and a "property"?
- What are the differences between variables created using `let`, `var` or `const`?








### Array.prototype.slice.call

能将具有length属性的对象转成数组

[Array.prototype.slice.call()方法详解](http://blog.csdn.net/i10630226/article/details/49702375)



### difference between throttle and debounce

throttle

- 函数触发一次后间隔一段时间后才能被触发（触发一次后，引发延时，延时结束后才可以再被触发）
- settimeout 里修改的是是否wait

debounce

- 等到一段时间后才触发（如果一直引发的debounce，则会不断后推迟）
- 进入后立即clearTimeout
- settimeout里面运行函数



### what is closure

A *closure* is the combination of ==a function== and the ==lexical environment== within which that function was declared. 

```javascript
function makeFunc() {
  var name = 'Mozilla';
  function displayName() {
    alert(name);
  }
  return displayName;
}

var myFunc = makeFunc();
myFunc();
```



### AMD vs CommonJS

AMD  was designed explicitly with the browser in mind

CommonJS was designed for a general-purpose JavaScript environment



### null vs undefined





### forEach vs map

`foreach`: executes a provided function once per array element.

unlike `map()`or `reduce()` it always returns the value `undefined` and is not chainable



`map`: creates ==a new array== with the results of calling a provided function on every element in this array.

map会return一个新的copy



### attribute vs property



### let var const

`const` Const is block scoped, identifier can’t be reassigned.

`var` Globally scoped, Can be hoisted(在前面申明，但不赋值)

`let` Let is block scoped, Can't be hoisted