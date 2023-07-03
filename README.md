# Redux-React
Redux tutorial

•To share data between siblings, you have to lift state up in react tree to a common parent & then do prop drilling to pass data to childrens that want to share it.

<h3>basics</h3>
Every store has multiple slices,</br>
each slice may have multiple actions,</br>
one reducer may handle mutiple actions for a slice</br>

**we can combine multiple reducers in an object and pass them in the createStrore() function**

<h3>Store</h3>
Store is the single source of truth, we will create and export it.

```
import {createStore} from 'redux';
import reducer from './reducer';      //importing reducer function

const store = createStore(reducer);

export default store;
```
    
<h3>Actions</h3>
Action is an object that contains type and payload.

```
{
type:"BugAdded",
payload:{
description:"Bug in UI"
}
```

<h3>Reducer</h3>

Reducer is a function that updates the store based on action

Reducers takes a store & an action as an argument & returns the updated store based on that

```
let id = 0;


function reducer(store = [],action){

if(action.type === 'BugAdded'){
return [
...store,
    {
      id:++id,
      description:action.payload.id,
      resolved:false,
    }
      ]
}

else if(action.type === "BugRemoved"){
 return state.filter(bug => bug.id!==action.payload.id)
}

return state,

export default reducer
```

<h3>Dispathing actions</h3>

```

function bugAdded(bugdescription){
    return {
    type: "BugAdded",
    payload: {description: bugdescription}
}
}

store.dispatch(bugAdded('bug1'));
store.dispatch(bugRemoved(1));
```
<img width="592" alt="Screenshot 2023-07-03 at 3 06 37 PM" src="https://github.com/Rahul12Arora/Redux-React/assets/108695777/98f025f1-bff6-4aa9-ba90-68867198f69d">

![State in a React App](https://user-images.githubusercontent.com/108695777/236199426-3b3d367a-eea8-4f2c-ac94-d85b2818e7fa.jpeg)
![Redux-1](https://user-images.githubusercontent.com/108695777/236202578-84e11fc4-53c4-479e-a3ce-a4c0efb1ec03.jpeg)
![Redux-1](https://user-images.githubusercontent.com/108695777/236202786-fb083907-e693-4d67-85d6-938be33d0d70.jpeg)
![Redux-1](https://user-images.githubusercontent.com/108695777/236203146-e5c9c88a-7b24-4612-bd58-b23bbae334e0.jpeg)
<img width="838" alt="Screenshot 2023-05-04 at 6 12 30 PM" src="https://user-images.githubusercontent.com/108695777/236207978-c00a4cb9-ec02-4749-9ec6-6ccb6eb8a29a.png">
![Three Core Concepts contd](https://user-images.githubusercontent.com/108695777/236218140-4676ac68-f55b-471b-aea0-a4dfad3b9407.jpeg)
