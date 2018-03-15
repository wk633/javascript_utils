# javascript_utils
collect javascript functions

- left padding
- duplicate
- isArray
- duplicate II
- debounce/throttle
- reduce to count frequency
- isArray
- currify sum function
- currySum
- flatten an array





### left padding

```javascript
// left padding
function leftpadding(str, width, ch){
    str = str + '';
    let len = width - str.length;
    if(len <= 0) return str;
    padding = '';
    while(true){
        if(len & 1) padding += ch;
        len >>= 1;
        if(len) padding += padding;
        else break;
    }
    return padding + str;
}

```



### duplicate/repeat

```javascript
// duplicate
function duplicate(str, count){
    count--;
    tmp = str;
    while(true){
        if(count & 1) str = tmp + str;
        count >>= 1;
        if (count) tmp += tmp;
        else break;
    }
    return str;
}
console.log(duplicate('ab', 1)); // ab
console.log(duplicate('ab', 2)); // abab
console.log(duplicate('ab', 3)); // ababab
console.log(duplicate('ab', 4)); // abababab
```

```javascript
const repeat = (str = '', times = 1)=>{
  let rst = '';
  if(!str || times < 1) return rst;
  while(times){
    if(times % 2) rst += str;
    times = Math.floor(times / 2);
    if(times) str += str;
  }
  return rst;
}
```





### duplicate II

```javascript
// duplicate([1,2,3,4,5]); // [1,2,3,4,5,1,2,3,4,5]

function duplicate(arr){
  return a.concat(a);
}

```



### debounce/throttle

```javascript
function throttle(fx, limit){
  var wait = false;
  return function(){
    let context = this;
    let args = arguments;
    if(!wait){
      wait = true;
      fx.apply(context, args);
      setTimeout(()=>{
        wait = true
      },limit)
    }
  }
}


function debounce(fn, delay) {
  // maintain a timer
  let timer = null;
  // closure function that has access to timer
  return function() {
    // get the scope and parameters of the function 
    // via 'this' and 'arguments'
    let context = this;
    let args = arguments;
    // if event is called, clear the timer and start over
    clearTimeout(timer);
    timer = setTimeout(function() {
      fn.apply(context, args);
    }, delay);
  }
}
```



throttle

- 函数触发一次后间隔一段时间后才能被触发（触发一次后，引发延时，延时结束后才可以再被触发）
- settimeout 里修改的是是否wait

debounce

- 等到一段时间后才触发（如果一直引发的debounce，则会不断后推迟）
- 进入后立即clearTimeout
- settimeout里面运行函数



### reduce to count frequency

```javascript
var inputWords = ['Apple', 'Banana', 'Apple', 'Durian', 'Durian', 'Durian']

console.log(countWords(inputWords))

// =>
// {
//   Apple: 2,
//   Banana: 1,
//   Durian: 3
// }
```

```javascript
function countWords(inputWords){
  return inputWords.reduce(function(map, item){
    map[item] = ++map[item] || 1
    return map;
  }, {})
}
```



### isArray

```javascript
function myIsArray(arg){
  if(Array.isArray) return Array.isArray(arg);
  else
    return Object.prototype.toString.call(arg) === '[object Array]';
}
```



### currify sum function

```javascript
let sum = function(a, b){
    return a + b;
}
let curry = function(fx){
    var length = fx.length;
    return function f1(){
        var args = Array.prototype.slice.call(arguments);
        if(args.length >= length){
            return fx.apply(null, args)
        }else{
            return function f2(){
                var args2 = Array.prototype.slice.call(arguments);
                return f1.apply(null, args.concat(args2));
            }
        }
    }
}
let add = curry(sum);
console.log(add(2,5));
console.log(add(2)(5));
console.log(add()(2)(5));
```



### currySum

```javascript
// support any length of arguments
function currySum(){
  let tmpSum = 0;
  return function f1(arg){
    if(arguments.length == 0){return tmpSum}
    for(let i = 0; i < arguments.length; i++){
      tmpSum += arguments[i];
    }
    return f1;
  }
}

var mySum1 = currySum();
var mySum2 = currySum();
console.log(mySum1(1)(1)(3)()); // 5
console.log(mySum3(1,2,4)()); // 7
```



### flatten an array

```javascript
const flatten = (arr) => {
    return arr.reduce((pre, val)=>{
        if(Array.isArray(val)){
            return pre.concat(flatten(val));
        }else{
            return pre.concat(val);
        }
    },[])
}
flatten([1,2,3,[4,5,[6]]]); //[1, 2, 3, 4, 5, 6]
```

non-recursive

```javascript
flatten = (arr)=>{
    let rst = [];
    let queue = arr.slice(0);
    while(queue.length != 0){
        let cur = queue.shift();
        if(Array.isArray(cur)){
            queue = cur.concat(queue);
        }else{
            rst.push(cur);
        }
    }
    return rst;
}
```

fast non-recursive

```javascript
fastFlatten = (arr)=>{
    let rst = [];
    let stack = arr.reverse();
    while(stack.length != 0){
        let cur = stack.pop();
        if(Array.isArray(cur)){
            cur.reverse();
            stack.concat(cur);
        }else{
            rst.push(cur);
        }
    }
    return rst;
}
```

