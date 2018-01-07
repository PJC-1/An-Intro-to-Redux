



Intro to Redux
===================
> Following **StephenGrider**'s tutorial: *Modern React with Redux* on udemy, here's the [link](https://www.udemy.com/react-redux/).
> Bellow are a mix of notes from the tutorial, react documentation, and other sources.


----------

Helpful Links
-------------
>
-	[redux](https://redux.js.org/)
-	[react-redux](https://github.com/reactjs/react-redux/blob/master/docs/api.md)

----------

Redux
-------------
> Main take away is that *Redux* is used to maintain the application's *state*, and that the *state* is a plain javascript *object*.
>  
>  The *application's state* is completely different than a *component's state* and not connected in any way whatsoever.
>  
>  
> **Actions**
>  The *reducers* are in charge of *manipulating* or *changing* the *application state* over time. This is done through the use of *actions*, so whenever an *action* is dispatched, it flows through all of the different *reducers* in the application. Where, each *reducer* has the option to return a different piece of *state* than normal, based on the *type* of action received.
>  **actions** will always have a ```type``` defined. And can optionally have a ```payload``` or any number of other properties. Generally (by convention), we use ```payload``` when we are passing a piece of data along with the *action*.
>   
>   **bindActionCreators(actionCreators, dispatch)**
>  
>  We use the *bindActionCreators()* function to turn an object whose values are *action creators*, into an object with the same keys, but with every action creator wrapped into a *dispatch* call so they may be invoked directly.
>  In *Redux* used with *React*, *react-redux* will provide you with the ```dispatch``` function so you can call it directly.
>   
>  The only use case for *bindActionCreators* is when you want to pass some action creators down to a component that isn't aware of *Redux*, and you don't want to pass ```dispatch``` or the Redux store to it.
>  
>  [redux documentation](https://redux.js.org/docs/api/bindActionCreators.html) for more information/examples about the *bindActionCreators()* function.
>   
>  **Action Creators**
>   
>   *Action Creators* are simple functions that return an *action*, and an *action* is a plain javascript object.

Redux/React-Redux/React
-------------
>
> Redux serves to construct the application state and React provides the views to display that state.
>  
> **Redux** and **React** are inherently disconnected and it's only through the use of **React-Redux** that we get any clear *connection* between the two libraries. In other words, we use *React-Redux* as a bridge between the two separate libraries.
>  
>

----------


Reducers
-------------
>
-	A **reducer** is a function that returns a piece of the application's state.
- The application's *state* is a plain javascript object.
- **Reducers** produce the value of the applications state.
- The *application's state* is formed by the *reducers*.
- All *reducers* are combined together with the use of the ```combineReducers()``` method.
- For each key in the ```combineReducers()``` object a single *reducer* is assigned. Where that specific reducer assigned is responsible for producing that particular piece of *state*
>
```
//example
import { combineReducers } from 'redux';
import BooksReducer from './reducer_books';
import ActiveBook from './reducer_active_book';

const rootReducer = combineReducers({
  books: BooksReducer,
  activeBook: ActiveBook
});

export default rootReducer;
```
>
> In the above example, whatever *state* ```ActiveBook``` returns will be available as ```activeBook``` piece of *application state*
>
> Creating a **reducer** is a two step process:
> 1) Create the *reducer*
> 2) Wire it into the application.
>  
> All *reducers* get **2** arguments:
- **current state**
- **action**
>
> The [redux.js](https://redux.js.org/docs/api/combineReducers.html) docs define ```combineReducers()``` function as:
> The ```combineReducers``` helper function turns an object whose values are different reducing functions into a single reducing function you can pass to ```createStore```.
>
```
//Example:

rootReducer = combineReducers({potato: potatoReducer, tomato: tomatoReducer})
// This would produce the following state object
{
  potato: {
    // ... potatoes, and other state managed by the potatoReducer ...
  }
  tomato: {
    // ... tomatoes, and other state managed by the tomatoReducer, maybe some nice sauce? ...
  }
}
```


----------

Smart Component vs Dumb Component
-------------
> Here is a link for more information on [**Smart Components vs Dumb Components**](https://jaketrent.com/post/smart-dumb-components-react/)
>  
> Typically **Smart Components** and **Dumb Components** would be saved to separate locations.
>  
>

Connect
-------------
>
>*React-Redux* makes the **connect** function available, which takes a function and a component and produces a container.
>  
> The **container** is a component that is aware of the state that is contained by redux.


mapStateToProps
-------------
> Here is a link to an article that contains more information about [mapStateToProps](https://medium.com/mofed/reduxs-mysterious-connect-function-526efe1122e4).
>  
>  The **mapStateToProps()**'s first argument is the applications state and it returns an object.
>   
>  The object that is returned, Will be available to our component as ```this.props```.
>   
>  **mapStateToProps()** is basically the glue between *react* and *redux*.
>   
> If the application's **state** changes, the container will automatically re-render.
>  
> 
