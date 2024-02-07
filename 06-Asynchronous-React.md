# Asynchronous React

Fetch data from a external API, we use ```useEffect(callback, [])```. The second parameter of them must be empty to run it one time.

Note: Is important to define the key in ```for``` parameter with unique value. 

```js
import '../App.css';
import React, { useEffect, useState } from 'react';

const Card = ( {data} ) => {

	let content = [];

	var i = 0;

	// Interating Object
	for (const item in data) {
		if( data.hasOwnProperty(item) ){
			content.push(<li className="list-group-item" key={item}><strong>{item}:</strong> {data[item]}</li>);
		}

		if(i === 4){
			break;
		}

		++i;
	}

	return (
		<>
		<div className="d-flex justify-content-center">
			<div className="card" style={{width: "18rem"}}>
				<img src="https://openclipart.org/image/800px/346704" className="card-img-top" alt={data.query} height={"250px"} />
				<div className="card-body">
					<h5 className="card-title">IP: {data.query}</h5>
					<ul className="list-group list-group-flush" style={{textTransform: "capitalize", margin: "0 -1.25rem -1.25rem"}}>{content}</ul>
				</div>
			</div>
		</div>
		</>
	)
}

const AsyncFetch = () => {
	const [data, setData] = useState(null);
	const [error, setError] = useState(null);
	const [loading, setLoading] = useState(false);

	useEffect(() => {
		// Loading
		setLoading(true);

		// Request
		fetch("http://ip-api.com/json/173.245.58.104")
			.then((response) => response.json())
			.then(setData)
			.then(() => setLoading(true))
			.catch(setError)
	}, []);

	// if(loading) return <h1>Loading...</h1>;
	
	if(error){
		return (
			<>
				<div className="alert alert-danger" role="alert">
					{JSON.stringify(error)}
				</div>
			</>
		);
	}

	if (data !== null) {
		return (
			<>
				<Card data={data} ></Card>
			</>
		);
	}
}

export default AsyncFetch;
```

## Fetching Data with GraphQL

**What is GraphQL?**
GraphQL is a query language for APIs (Application Programming Interfaces) and a server-side runtime for executing those queries with your existing data. It was developed by Facebook in 2012 and later open-sourced in 2015. GraphQL provides a more efficient, powerful, and flexible alternative to the traditional REST (Representational State Transfer) API.

## Working With Render Probs

