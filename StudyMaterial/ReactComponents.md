1. React Components

We can organized groups of elements into React components. A basic function component is written similarly to a regular JavaScript
function with a couple of differences.

a. Component names must start with a capital letter (that is,MyComponent, instead of myComponent)
b. Components, unlike JavaScript functions, must return JSX.

Here is the basic syntax of a React function component

function App() {
return (

<div>Hello world!</div>
);
}

2. React Props

React components can accept data passed to them called props.
Props are passed from the parent component to a child component and these are read-only and are immutable.

Here we are passing a prop name from App to the User component.

function App() {
return <User name="John Doe" />
}

function User(props) {
return <h1>Hello, {props.name}</h1>; // Hello, John Doe!
}

Props is an object, so we can select the name prop within User to get its value.

function App() {
return <User name="John Doe" />
}

function User({ name }) {
return <h1>Hello, {name}!</h1>; // Hello, John Doe!
}

Any JavaScript value can be passed as a prop, including other elements and components.

3. React Children

Props can also be passed by placing data between the opening and closing tags of a component.

Props that are passed this way are placed on the children property.
function App() {
return (
<User>

<h1>Hello, John Doe!</h1>
</User>
);
}
function User({ children }) {
return children; // Hello, John Doe!
}

4. React Conditionals

React components and elements can be conditionally displayed.

function App() {
const isAuthUser = useAuth();
return (
<>

<h1>My App</h1>
{isAuthUser ? <AuthApp /> : <UnAuthApp />}
</>
)
}

5. React Lists

Lists of React components can be output using the .map() function .map() allows us to loop over arrays of data and output JSX

function SoccerPlayers() {
const players = ["Messi", "Ronaldo", "Laspada"];
return (

<div>
{players.map((playerName) => (
<SoccerPlayer key={playerName} name={playerName} />
))}
</div>
);
}

Whenever you are looping over an array of data, you must include the key prop on the element or component over which you are looping.
Additionally, this key prop must be given a unique value, not just an element index.
In the example above, we are using a value which we know to be unique, which is the playerName
