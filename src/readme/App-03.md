

### Remove  props.onIncrease();

### React Redux

doc link :(https://react-redux.js.org/)

An Existing React App

```bash
npm install redux react-redux
```

-  an action called plus is delivered.

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
  return(
    <div>
      <h1>Left2 :  </h1>
      <Left3 ></Left3>
    </div>
  )
 }


 function Left3(props){
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