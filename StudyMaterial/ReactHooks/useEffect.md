UseEffect

If we want to interact with the “outside world”, such as using an API, we use the useEffect hook.

useEffect is used to perform a side effect, which means to perform an operation that exists outside of our app that doesn’t have a
predictable result.
The basic syntax of useEffect requires a function as a first argument and an array as the second argument.

import { useEffect } from 'react';
function MyComponent() {
useEffect(() => {
// perform side effect here
}, []);
}

The function passed to useEffect is a callback function. This will be called after the component renders.
The second argument is an array, called the dependencies array. This array should include all of the values that our side effect relies upon.

If you do not provide the dependencies array at all and only provide a function to useEffect, it will run after every render.
After the first render, useEffect will be run, state will be updated, which will cause a re-render, which will cause useEffect to run again, starting the process over again ad infinitum.

What is the cleanup function in useEffect?
The final part of performing side effects properly in React is the effect cleanup function.

Sometimes our side effects need to be shut off. For example, if you have a countdown timer using the setInterval function, that interval will not stop unless we use the clearInterval function.

The problem with this if the component is destroying, is that setInterval will try to update a variable a piece of state time that no longer exists. This is an error called a memory leak.

function Timer() {
const [time, setTime] = useState(0);

useEffect(() => {
let interval = setInterval(() => setTime(1), 1000);

    return () => {
      // setInterval cleared when component unmounts
      clearInterval(interval);
    }

}, []);
}
