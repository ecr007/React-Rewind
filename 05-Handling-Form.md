# Handling Forms in React

## useRef()
To reach out to an individual element 

Note: Its necessary use ```ref="varToReference"``` to reference the value and follow change.

```js
import '../App.css';
import { useRef } from 'react';

const Ref = () => {
	const name = useRef("John Doe");

	// To define default value must be useState(default)
	// const [x, setX] = useState(default);

	const submit = (e) => {
		e.preventDefault();

		console.log(name.current.value);
		name.current.value = ""
	};

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

export default Ref;
```

## Building a custom Hook

Is a function and this function is going to always start with the keyword ```use``` e.g: ```useCatch()``` and inside of this use another one of these ```useState``` hooks.  

```{...nameOfVariable}``` spread all of the properties into the HTML tag like inputs. This is a technique that you should use sort of sparingly 