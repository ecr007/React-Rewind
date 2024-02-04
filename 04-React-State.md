# React State in the Component Tree


## Start a react project

**Doc to read aboud how create a react js app**
https://create-react-app.dev/docs/getting-started

### Requirements

- Node
- NPM

### Step Command

**What is ```npx``` Command?** The NPX stands for Node Package Execute and It come with npm above 5.2.0 version then automatically npx will installed.

It's a npm package runner that can execute any package that you want from the npm registry without even installing that package.

```shell
# Starting project
npx create-react-app . or name of directory

npm start
    # Starts the Developement Server

npm run build
    # Bundles the app into static files for production.

npm test
    # Starts the test runner.
```

## Turning a create React App Project

- react-scripts package: is how we handle all of our bundling.

- npm install: installs all dependencies inside in package.json

## Destructuring Arrays and Object

Is concise way to extract values from arrays and objects and assign them to variables.

**Destructuring Arrays**

```js
// Basic Array Destructuring
const list = ["John", "Doe", 54, "545486562"];
const [firstname, lastname] = list;

console.log(firstname); // John.

// Skipping Values
const [firstname, ,age] = list;

console.log(age); // 54
```

**Destructuring Objects**

Destructuring simplifies the process of working with array and objects, macking the code more readable and concise.

```js
const person = {name: "John", age: 18};
const {name, age} = person;

console.log(name); // John

// Renaming variables during destructuring
const {name: fullname, age: yearAge} = person;
console.log(yearAge); // 18

// Default Values if the destructuring name does not exists
const {role = "Unknown"} = person;

console.log(role); // Unknown

// Destructuring in function parameters
// Default function with object as a parameter

function runAway(props){console.log(props.name);}

// Destructuring
function runAway( {name, age} ){
    console.log(name); // John
    console.log(age); // 18
}
```

## Understanfing the useState Hook

**What is a Hook?** is a function that allows you to use state and others react features in functional components. 

**The most commonly used hook are:**

## useState()
Manages state within functional components allowing you to declare and update state variables.

```js
import {useState} from "react";

function Header(  ){
    
    const [name, setName] = useState("Pedro"); // Return an Array with two parameter, undifined firts and a funcion as second.

    return (
        <p className="whatever">{name}<p>
        <button onClick={ () => setName("Pablo")} > Set Name</>
    );
}

export default Header;
```

## useEffect(callback, [dependecies list])
Performs side effects in functional components such as data feching, subscription, or manual DOM manipulations. 

Dependencies List: To modify stateful value it needed set it in dependencies list. 

Note: Following variables changed.

```js
import '../App.css';
import { useEffect, useState } from 'react';

const Counter = () => {

	const [number, setNumber] = useState(0);

	useEffect(() => {
		if(number === 5){
			setNumber(0);
		}	
	},[number])

	return (
		<>
			<div className="card text-center">
			<h1 id='counter'>{number}</h1>
			<br />
			<button className='btn btn-sm btn-success' onClick={
				() => {
					setNumber(number + 1)
				}
			}>+ Add</button>
			</div>
		</>
	)
}

export default Counter;
```

## useReducer()
Is going to take in two different arguments, the first is the function that we're going to use to update our state, the second argument is the default initial state.

Note the different between ```useReducer``` and ```useState```, it does not need past function to being execute.

```js
import '../App.css';
import {useReducer} from 'react';

export default function Reducer(){
	const [checked, setChecked] = useReducer((value) => !value, false);
	return (
		<>
			<h1>The option is {checked ? "Ok" : "no Ok"}</h1>
			<button onClick={setChecked}>Click me!</button>
		</>
	);
}
```

## useContext()
Allows you to subscribe to React context without indroduce nesting. 