1. Prop Drilling

Sometimes we pass props through components that don’t need to receive them. This problem is called props drilling.

2. React Context

React context allows us to pass data to our component tree without using props preventing unnecessary prop drilling

To use Context, we use the createContext function from React.
We can call it with an initial value to be put on context.

The created context includes a Provider and a Consumer property, which are each components.
We wrap the Provider around the component tree that we want to pass the given value down. Next, we place the Consumer in the
component we want to consume the value.

import { createContext } from 'react';

const NameContext = createContext('');

function App() {
return (
<NameContext.Provider value="John Doe">

 <Body />
 <NameContext.Provider>
 );
}
function Body() {
 return <Greeting />;
}
function Greeting() {
 return (
 <NameContext.Consumer>
 {name => <h1>Welcome, {name}</h1>}
 </NameContext.Consumer>
 );
}
