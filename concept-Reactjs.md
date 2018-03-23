## concept-React & Redux

## outline-React

- features of React
- major advantages of React
- what do you understand by Virtual DOM
- ES6 syntax using React
- how to update state of a component



### features of React

- use virtual DOM instead of real DOM
- server-side rendering
- uni-directional data flow



### major advantages of React

- increase application performance
- used on the client as well as server side
- JSX increase readability
- easy to integrate with other frameworks like Meteor
- writing UI test cases become extremely easy



###what do you understand by Virtual DOM

A virtual DOM is a lightweight JavaScript object which originally is just the copy of the real DOM.

1. Whenever any underlying data changes, the entire UI is re-rendered in Virtual DOM representation.
2. Then the difference between the previous DOM representation and the new one is calculated.
3. Once the calculations are done, the real DOM will be updated with only the things that have actually changed. 

no memory wastage



### ES6 syntax using React

```javascript
import React from 'react';

export default Component;

class MyComponent extends React.Component {
  constructor(){
    super();
    this.state = {name: 'World'}
  }
  render(){
    return <h3>{this.props.name}</h3>
  }
}
  
```



### how to update state of a component

```javascript
this.setState(....);
```



### arrow function in React

```javascript
render(){
  return <input onChange={(e)=>this.handleChange(e)}>
}
// without arrow function
render(){
  return <input onChange={this.handleChange.bind(this)}>
} 
```



## outline-Redux

- explain Flux
- three princles that Redux follows
- role of Reducer
- how is state changed in Redux



### explain Flux

Flux is an architectural pattern which enforces the uni-directional data flow. 

using a central Store, it ==controls derived data== and ==enables communication== between multiple components 



### three principles that Redux follows

- single source of truth(one store)
- state is read-only
- changes are made with pure functions



### role of Reducer

Reducers are ==pure functions== which specify how the application’s state changes in response to an ==ACTION==.



### how is state changed in Redux

The only way to change the state is to emit an action,





### reference

[Redux interview questions](http://www.punch.cool/community/questions-answers/engineering/redux/)



