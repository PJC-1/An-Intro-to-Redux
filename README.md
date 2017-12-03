



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


Reducers
-------------
>
-	A **reducer** is a function that returns a piece of the application's state.
- The application's *state* is a plain javascript object.
- **Reducers** produce the value of the applications state.

>
> Creating a **reducer** is a two step process:
> 1) Create the *reducer*
> 2) Wire it into the application.
>  
>


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
> **Connect** takes a function and a component and produces a container.
>  
> The **container** is a component that is aware of the state that is contained by redux.


mapStateToProps
-------------
> Here is a link to an article that contains more information about [mapStateToProps](https://medium.com/mofed/reduxs-mysterious-connect-function-526efe1122e4).
>  
>  The **mapStateToProps()**'s first argument is the state and it returns an object.
>   
>  The object that is returned, Will be available to our component as ```this.props```.
>   
>  **mapStateToProps()** is basically the glue between *react* and *redux*.
>   
> If the application's **state** changes, the container will automatically re-render.
>  
> 
