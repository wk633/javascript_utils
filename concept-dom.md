## DOM

- what's DOM
- what's the difference between bubbling and capturing
- event.target VS event.currentTarget



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