
- 
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
      <Left2></Left2>
    </div>
  )
 }

 function Left2(props){
  return(
    <div>
      <h1>Left2</h1>
      <Left3></Left3>
    </div>
  )
 }


 function Left3(props){
  return(
    <div>
      <h1>Left3</h1>
    </div>
  )
 }
```

### 

- Define the state/useState 
in Root/App component 

```js
import React,{useState} from 'react';
import './style.css';

export default function App (){
  const [number, setNumber] = useState(1);

  return (
    <div id='container'>
      <h1>Root- App component</h1>
      <Left1 number={number}></Left1>
    </div>
  )
}

 function Left1(props){
  return(
    <div>
      <h1>Left1 : {props.number}</h1>
      <Left2 number= {props.number}></Left2>
    </div>
  )
 }

 function Left2(props){
  return(
    <div>
      <h1>Left2 : {props.number} </h1>
      <Left3 number={props.number}></Left3>
    </div>
  )
 }


 function Left3(props){
  return(
    <div>
      <h1>Left3 : {props.number}</h1>
    </div>
  )
 }
```