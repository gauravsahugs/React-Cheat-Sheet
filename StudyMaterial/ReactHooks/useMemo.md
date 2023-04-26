UseMemo -- url https://www.geeksforgeeks.org/react-js-usememo-hook/

The useMemo is a hook used in the functional component of react that returns a memoized value. In Computer Science, memoization is a concept used in general when we don’t need to recompute the function with a given argument for the next time as it returns the cached result.

Note: Memorization is never free, we are trading space for time.

const memoizedValue = useMemo(functionThatReturnsValue,
arrayDependencies)

In the Example below this func will use number as a memozed value for rendering , it'll prevent unnecessay rendering when counter is increase

import React, {useState} from 'react';

function App() {
const [number, setNumber] = useState(0)
// Using useMemo
const squaredNum = useMemo(()=> {
return squareNum(number);
}, [number])
const [counter, setCounter] = useState(0);

// Change the state to the input
const onChangeHandler = (e) => {
setNumber(e.target.value);
}

// Increases the counter by 1
const counterHander = () => {
setCounter(counter + 1);
}
return (

<div className="App">
<h1>Welcome to Geeksforgeeks</h1>
<input type="number" placeholder="Enter a number"
		value={number} onChange={onChangeHandler}>
</input>
<div>OUTPUT: {squaredNum}</div>
<button onClick= {counterHander}>Counter ++</button>
<div>Counter : {counter}</div>
</div>
);
}

// function to square the value
function squareNum(number){
console.log("Squaring will be done!");
return Math.pow(number, 2);
}

export default App;
