# Code snippets

## Functional Component with Props

    Description: A fundamental building block in React apps that creates reusable UI components.

    Use case: Displaying a message passed as a prop.

    Code snippet:

```
import React from 'react';
  const MyComponent = (props) => {
    return 
 {props.message} 
;
  };
  export default MyComponent;
```

## List Rendering

    Description: Renders items in a list, mostly from an API or database, to be displayed on the user interface.

    Use case: Displaying a list of items.

    Code snippet:

```
import React from 'react';
const List = ({ items }) => {
  return (
      {items.map(item => (
{item.name}
      ))}
  );
};
export default List;
```

## Forms

    Description: React code that handles forms and input submission.

    Use case: Creating a form for user input.

    Code snippet:

```
import React, { useState } from 'react';
const Form = () => {
const [value, setValue] = useState('');
  const handleChange = (e) => setValue(e.target.value);
  const handleSubmit = (e) => {
    e.preventDefault();
    // Handle form submission
  };
  return (
Submit    
  );
};
export default Form;
```

## Custom Hooks

    Description: Creates a hook for reusing stateful logic.

    Use case: Fetching data from an API with reusable logic.

    Code snippet:

```
import { useState, useEffect } from 'react';
const useFetch = (url) => {
  const [data, setData] = useState(null);
  const [loading, setLoading] = useState(true);
  useEffect(() => {
    const fetchData = async () => {
      const response = await fetch(url);
      const data = await response.json();
      setData(data);
      setLoading(false);
    };
    fetchData();
  }, [url]);
  return { data, loading };
};
export default useFetch;
```
