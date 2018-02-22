# javascript_utils
collect javascript functions

- left padding
- duplicate
- isArray
- duplicate II
- throttle





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



### duplicate

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



### isArray

```javascript
function isArray(arr){
    return {}.toString.call(arr) === '[object Array]';
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
    if(!wait){
      wait = true;
      fx();
      setTimeout(()=>{
        wait = true
      },limit)
    }
  }
}
```

