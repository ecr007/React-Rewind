# Functional Form

Refers to using the functional update pattern when updating state in react or similar state management system.

The functional form is beneficial when the new state depends on the previous state. This helps to avoid issues related to asynchronous state update and ensures that you are working with the latest state when updating.  

## Example

```js
useEffect(() => {
    setPagination( (prev) => {
        // prev.current = list.length;
        // prev.total = pokemons.length;
        return {...prev, current: list.length, total: pokemons.length};
    });

    // prev => ({...prev,"current": list.length, "total": pokemons.length})

    /*setPagination(prevPagination => ({
        ...prevPagination,
        "total": pokemons.length,
        "current": list.length
    }));*/
    
    // eslint-disable-next-line react-hooks/exhaustive-deps
},[list.length, pokemons.length]);
```