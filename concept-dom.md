## DOM

- what's DOM
- what's the difference between bubbling and capturing
- event.target VS event.currentTarget
- describes 3 phases of event propagation
- what's event delegation



### What's DOM

Document Object Model (DOM) is a programming interface for HTML and XML documents



###difference between bubbling and capturing



With bubbling, the event is first captured and handled by the innermost element and then propagated to outer elements.

With capturing, the event is first captured by the outermost element and propagated to the inner elements.



[What is event bubbling and capturing?](https://stackoverflow.com/questions/4616694/what-is-event-bubbling-and-capturing)



### event.target VS event.currentTarget

A handler on a parent element can always get the details about where it actually happened.

**The most deeply nested element that caused the event is called a target element, accessible as event.target.**

`this` – is the “current” element, the one that has a currently running handler on it. (`this = event.currentTarget`)



[Bubbling and capturing](https://javascript.info/bubbling-and-capturing) 



### describes 3 phases of event propagation

1. Capturing phase – the event goes down to the element.
2. Target phase – the event reached the target element.
3. Bubbling phase – the event bubbles up from the element.

window - > document -> html -> body -> …...

Notes: html can be accessed by ==document.documentElement== not document.html

![](https://javascript.info/article/bubbling-and-capturing/eventflow@2x.png)



###what's event delegation

before

```javascript
document.getElementById("help-btn").onclick = function(event){
    openHelp();
};

document.getElementById("save-btn").onclick = function(event){
    saveDocument();
};

document.getElementById("undo-btn").onclick = function(event){
    undoChanges();
};
```



after

```javascript
document.onclick = function(event){
    //IE doesn't pass in the event object
    event = event || window.event;

    //IE uses srcElement as the target
    var target = event.target || event.srcElement;    

    switch(target.id){
        case "help-btn":
            openHelp();
            break;
        case "save-btn":
            saveDocument();
            break;
        case "undo-btn":
            undoChanges();
            break;
        //others?
    }
};
```

benefits:

1. Fewer functions to manage.
2. Takes up less memory.
3. Fewer ties between your code and the DOM.



[Event delegation in JavaScript](https://www.nczonline.net/blog/2009/06/30/event-delegation-in-javascript/)



### 