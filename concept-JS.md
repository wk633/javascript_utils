# concept-JS

- Javascript Hoisting
- Array slice and splice
- difference between apply and call
- enumerate the properties of an object
- object copy using Object.assign()
- Array.prototype.slice.call
- difference between throttle and debounce
- what is closure
- AMD vs CommonJS?
- difference between a variable that is:```null```,```undefined```or undeclared
- Can you describe the main difference between a `forEach` loop and a `.map()` loop and why you would pick one versus the other?
- What's the difference between an "attribute" and a "property"?
- What are the differences between variables created using `let`, `var` or `const`?




### What's Javascript Hoisting

a javascript default behavior, moving ==declaration== to the top

```javascript
x = 5; // Assign 5 to x
var x; // Declare x
```

initialization are not hoisted

```javascript
var x = 5; // Initialize x

elem = document.getElementById("demo"); // Find an element 
elem.innerHTML = x + " " + y;           // Display x and y

var y = 7; // Initialize y
```

in this case y is ==undefined==



### Array slice and splice

```javascript
a = [1,2,3,4];
b = a.slice(0); // get a copy of original array
c = a.slice(1,3); // [2,3]
```

```javascript
// array.splice(start[, deleteCount[, item1[, item2[, ...]]]])

var months = ['Jan', 'March', 'April', 'June'];
months.splice(1, 0, 'Feb');
// inserts at 1st index position
console.log(months);
// expected output: Array ['Jan', 'Feb', 'March', 'April', 'June']

months.splice(4, 1, 'May');
// replaces 1 element at 4th index
console.log(months);
// expected output: Array ['Jan', 'Feb', 'March', 'April', 'May']
```

[Array.prototype.splice()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice)



### difference between apply and call

```javascript
	foo.call(this, arg1,arg2,arg3) 
 == foo.apply(this, arguments)
 == this.foo(arg1, arg2, arg3)
```



### enumerate the properties of an object

- for in loop
  - traverses ==all enumerable properties== of an object and its ==prototype chain==
- Object.keys(o)
  - returns an array with all the own (not in the prototype chain) enumerable properties' names ("keys") of an object `o`
- Object.getOwnPropertyNames(o)
  - returns an array containing all own properties' names (enumerable or not) of an object `o`



hasOwnProperty():  return a boolean whether the object has the specified property as its own property 

```javascript
function showProps(obj, objName) {
  var result = '';
  for (var i in obj) {
    // obj.hasOwnProperty() is used to filter out properties from the object's prototype chain
    if (obj.hasOwnProperty(i)) {
      result += objName + '.' + i + ' = ' + obj[i] + '\n';
    }
  }
  return result;
}
```





[Objects in javascript : object.assign/deep copy](https://medium.com/@tkssharma/objects-in-javascript-object-assign-deep-copy-64106c9aefab)



### object copy in JS

```javascript
let obj = {
  a: 1,
  b: {
    c: 2,
  },
}
let newObj = Object.assign({}, obj);
```

problem:

- Object.assign only do shallow copy
- Properties on the prototype chain and non-enumerable properties cannot be copied.

[Copying Objects in JavaScript](https://scotch.io/bar-talk/copying-objects-in-javascript)



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



```javascript
var Arr = [1,2,3,4,5,6,7,8];
var P = Arr.map((index,i,arr)=>{
  var I = index-2;
  return I;
})
console.log("P",P)       //是[-1, 0, 1, 2, 3, 4, 5, 6]
console.log("Arr",Arr)  //[1, 2, 3, 4, 5, 6, 7, 8]

var Arr = [1, 2, 3, 4, 5, 6, 7, 8];
var sum = 0;
Arr.forEach(function (index, i, arr) {
  // if use arr[i] = index*2, original array will be modified
  sum = index-2
  //no return
})
console.log(sum)//6
console.log(Arr)
// [1, 2, 3, 4, 5, 6, 7, 8]
```

[map和forEach的区别](https://www.jianshu.com/p/607668e607dd)



### attribute vs property



### let var const

`const` Const is block scoped, identifier can’t be reassigned.

`var` Globally scoped, Can be hoisted(在前面申明，但不赋值)

`let` Let is block scoped, Can't be hoisted