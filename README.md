# Getting Started with React Redux

- Redux is not a tool dependent on React, but
a tool that can be used alone. 

1. Create a simple app using only this pure React app,
and experience what kind of despair can arise in its class.

2. Redus will be used as a tool to overcome
that despair.

### App.js

1. First  create empty component
2. Let's add another component inside 
that component. 
the name of component will be Left1
with outermost div tag
will be. The tittle will be Left1 with h1 tag.

and this component is used to insert 
the parent component (App)

3. To make the boundary between compoents
App and Left1

Give this outermost  container an id
called container  of this component.

Then , open CSS file and change 
the id. For all tags in the container and for
all the divs under the tag whose id container div

```js
import React from 'react';
import './style.css';

export default function App (){
  return (
    <div>
      <Left1></Left1>
    </div>
  )
}

 function Left1(props){
  return(
    <div>
      <h1>Left1</h1>
    </div>
  )
 }
```
- App.js
```js
import React from 'react';
import './style.css';

export default function App (){
  return (
    <div id='container'>
      <h1>Root- App component</h1>
      <Left1></Left1>
    </div>
  )
}

 function Left1(props){
  return(
    <div>
      <h1>Left1</h1>
    </div>
  )
 }
```
- style.css

```css
#container, 
#container div{
    border:5px solid green;
    margin:10px;
    
}
```

### React Redux

Doc link : (https://react-redux.js.org/)

- update App.js with using react-redux 

### Some functions provided by Redux

import {Provider, useSelector, useDispatch, connect}
from "react-redux";


```js
import React,{useState} from 'react';
import './style.css';
import {createStore} from "redux";
import {Provider, useSelectior, useDispatch, connect, useSelector} from "react-redux";

function reducer(currentState, action) {
  if(currentState === undefined) {
  return {
    number:1,
  };
}
const newState = {...currentState};
if(action.type ==="plus"){
  newState.number++;
}
  return newState;
}
const store =createStore(reducer);

export default function App (){
 
  return (
    <div id='container'>
      <h1>Root- App component : </h1>
      <div id='grid'>
        <Provider store={store}>
      <Left1 ></Left1>
      <Right1 ></Right1>
      </Provider>
     </div>
    </div>
  )
}

 function Left1(props){
  return(
    <div>
      <h1>Left1 :</h1>
      <Left2 ></Left2>
    </div>
  )
 }

 function Left2(props){
  console.log("2")
  return(
    <div>
      <h1>Left2 :  </h1>
      <Left3 ></Left3>
    </div>
  )
 }


 function Left3(props){
  console.log("3");
  const number = useSelector((state)=>state.number);
  return(
    <div>
      <h1>Left3 :{number} </h1>
    </div>
  )
 }

 function Right1(props){
  return(
    <div>
      <h1>Right1 </h1>
      <Right2></Right2>
    </div>
  )
 }

 function Right2(props){
  return(
    <div>
      <h1>Right2 </h1>
      <Right3
     
      ></Right3>
    </div>
  )
 }

 function Right3(props){
  const dispatch = useDispatch();
  return(
    <div>
      <h1>Right3 </h1>
      <input 
      type='button'
      value=" + "
      onClick={()=> {
      dispatch({type:"plus"});
       }}
      >
      </input>
    </div>
  )
 }

```

- console.log("2");
console.log("3");

strict value that is using 
estate changes.

- The parent, 
because it is not re-rendering, it can 
greatly help with performance. 
