

- App.js
```js
import React,{useState} from 'react';
import './style.css';

export default function App (){
  const [number, setNumber] = useState(1);

  return (
    <div id='container'>
      <h1>Root- App component : {number}</h1>
      <div id='grid'>
      <Left1 number={number}></Left1>
      <Right1></Right1>
     </div>
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
      <Right3></Right3>
    </div>
  )
 }

 function Right3(props){
  return(
    <div>
      <h1>Right3 </h1>
    </div>
  )
 }

```

- style.css

```css
#container, 
#container> div div{
    border:5px solid green;
    margin:10px;
    
}

#grid{
    display: grid;
    grid-template-columns: 1fr 1fr;
}
```

- In this part, create input type = "button" in Right3
and need to change value in Root when
I click on the button in Right3.

```js
 function Right3(props){
  return(
    <div>
      <h1>Right3 </h1>
      <input type='button'value=" + "></input>
    </div>
  )
 }

```

- ver with props.onIncrease()
```js
import React,{useState} from 'react';
import './style.css';

export default function App (){
  const [number, setNumber] = useState(1);

  return (
    <div id='container'>
      <h1>Root- App component : {number}</h1>
      <div id='grid'>
      <Left1 number={number}></Left1>
      <Right1 onIncrease={()=> {
        setNumber(number +1);
      }}
      
      ></Right1>
     </div>
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

 function Right1(props){
  return(
    <div>
      <h1>Right1 </h1>
      <Right2
      onIncrease={()=> {
        props.onIncrease();
      }}
      ></Right2>
    </div>
  )
 }

 function Right2(props){
  return(
    <div>
      <h1>Right2 </h1>
      <Right3
      onIncrease={()=> {
        props.onIncrease();
      }}
      ></Right3>
    </div>
  )
 }

 function Right3(props){
  return(
    <div>
      <h1>Right3 </h1>
      <input 
      type='button'
      value=" + "
      onClick={()=> {
        props.onIncrease();
      }}
      >
      </input>
    </div>
  )
 }

```
