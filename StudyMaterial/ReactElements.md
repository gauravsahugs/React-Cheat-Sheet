1. React Elements

React elements are written just like regular HTML elements. You can write any valid HTML element in React.

<h1>My Header</h1>
<p>My paragraph>
<button>My button</button>
We write React elements using a feature called JSX.

2. React Element Attribute

JavaScript uses a camelcase naming convention (that is, “camelCase”), attributes are written differently than HTML

The most common example is the class attribute, which we write as className .

<div className="container"></div>

3. React Element Styles

<h1 style={{ fontSize: 24, margin: '0 auto',textAlign: 'center'}}>My header</h1>

4. React Fragments

If we don’t want to wrap our elements in a container element like a div, we can use a fragment:

function MyComponent() {
return (
<>

<h1>My header</h1>
</p>My paragraph</p>
</>
);
}
