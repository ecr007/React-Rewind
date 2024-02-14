# Handling Forms in React

## useRef()
Hook is used to create a mutable object call a "ref" that can hold a reference to a DOM element or a value that persists across renders. 

use ```refInstance.current``` to get all parameter of tag DOM.

Remember use ```useRef``` is like to use ```document.getElementById()``` that return a instance of a element.

```js
import '../App.css';
import { useRef, useEffect } from 'react';

const FormWithRef = () => {
	const name = useRef(null);

	useEffect(() => {
		console.log(name.current.value)
	}, []);

	return (
		<form action="#" onSubmit={submit}>
			<div className="form-group">
				<label htmlFor='name' className='form-label'>Your name</label>
				<input type="text" ref={name} id='name' className='form-control' />
			</div>

			<hr />
			<button className='btn btn-success'>Send</button>
		</form>
	)
}

export default FormWithRef;
```

## Building a custom Hook

Is a function and this function is going to always start with the keyword ```use``` e.g: ```useCatch()``` and inside of this use another one of these ```useState``` hooks.  

Custom hooks are a powerful feature in React that allow you to extract and reuse logic across different components.

```js
import '../App.css';
import { useEffect, useState } from 'react';

const validateUsername = (value) => {
	
	const restult = {isValid: true, msj: ""};

	console.log(value.trim().length);

	if(value.trim().length == 0){
		restult.isValid = false;
		restult.msj = "";
		return restult; 
	}
	else if (value.length <= 5) {
		restult.isValid = false;
		restult.msj = "Username is required, must be greater than 5 characters.";
		return restult;
	}

	return restult;
}

// Define Hook
const useValidator = (initialValue, callbackFn) => {
	const [value, setValue] = useState(initialValue);
	const [error, setError] = useState(null);

	const getValidation = (mValue) => {

		// validation
		const validator = callbackFn(mValue);

		setValue(mValue);

		if (validator.isValid) {
			setError(null);
		}
		else{
			setError(validator.msj);
		}		
	}

	return [value, getValidation, error];
}

export default function CustomHook(){

	const [username, setUsername, error] = useValidator('', validateUsername);

	// useEffect(() => {
	// 	console.log(error);
	// })

	return (
		<>
			<h1>Smart Form</h1>

			<form action="" onSubmit={ (e) => e.preventDefault() }>
				<div className="from-group">
					<label htmlFor="username">Username:</label>
					<input type="text" className='form-control' name="username" id="username" onInput={(e) => {setUsername(e.target.value);}} />
					
					{error && <p className='text-danger'>{error}</p>}
				</div>
				
			</form>	
		</>
	);
}
```