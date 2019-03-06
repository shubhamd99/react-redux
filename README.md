# react-redux

![alt text](https://i.imgur.com/K7dSZ3y.jpg)

# redux 4 steps

![alt text](https://i.imgur.com/wU4nkNg.png)

```
import React, { Component } from 'react';
import './App.css';

import { createStore } from 'redux';

class ReduxDemo extends Component {

  render() {

     // step 2 : Reducer = state and action
     const reducer = function(state, action){
        if(action.type === 'Attack'){
            return action.payload
        }
        if(action.type === 'Green Attack'){
            return action.payload
        }
       return state; // if no attack than simply return the state
    }

    // step 1 : create a Store which has reducer and state
    const store = createStore(reducer, 'Peace');

    // step 3 : Subscribe
    store.subscribe(() => {
        console.log('Store is now: ', store.getState());
    }) 

    // step 4 : Dispatch action
    store.dispatch({type: 'Attack', payload: 'IronMan'})
    store.dispatch({type: 'Attack', payload: 'Hulk'})

    return (
    <Provider store={store} >
      
    </Provider>
    );
  }
}

export default ReduxDemo;
```

### Link - https://shubhamd99.github.io/react-redux


