# javascript_utils
collect javascript functions

- left padding
- duplicate





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



