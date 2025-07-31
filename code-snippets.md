# Code snippets
from the blog: https://pieces.app/blog/10-react-code-snippets-that-every-developer-needs

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

## Modal Component

Description: A component for displaying overlay modals.
Use case: Displaying a notification modal.
Code Snippet:

```
import React from 'react';
const Modal = ({ isOpen, onClose, children }) => {
  return isOpen ? (
              {children}        Close          
  ) : null;
};
export default Modal;
```

## Tabs Component

Description: A tab component for switching between different content.
Use Case: Implementing tabbed navigation for different sections of a page
Code Snippet:

```
import React, { useState } from 'react';
const Tabs = ({ tabs }) => {
  const [activeTab, setActiveTab] = useState(0);
  return (
      {tabs.map((tab, index) => (                  key={index}          className={`tab ${index === activeTab ? 'active' : ''}`}          onClick={() => setActiveTab(index)}        >          {tab.title}        
      ))}
{tabs[activeTab].content}
);
};
export default Tabs;
```

## Image Slider Component

Description: An image slider for displaying multiple images.
Use case: Image carousel
Code snippet:

```
import React, { useState } from 'react';
const ImageSlider = ({ images }) => {
 const [currentIndex, setCurrentIndex] = useState(0);
  const nextSlide = () => setCurrentIndex((prevIndex) => (prevIndex === images.length - 1 ? 0 : prevIndex + 1));
  const prevSlide = () => setCurrentIndex((prevIndex) => (prevIndex === 0 
images.length - 1 : prevIndex - 1));
  return (
      Prev            Next    
  );
};
export default ImageSlider;
```

## Button Component

Description: Reusable button component in React code.
Use case: A UI button component that accepts different props.

Code snippet:

```
import React from 'react';
import PropTypes from 'prop-types';
const Button = ({ type, className, children, ...props }) => {
  return (
    
      type={type}
      className={className}
      {...props}
    >
      {children}
  );
};
Button.propTypes = {
  type: PropTypes.oneOf(['button', 'submit', 'reset']),
  className: PropTypes.string,
  children: PropTypes.node.isRequired,
};
Button.defaultProps = {
  type: 'button',
  className: '',
};
export default Button;
```

## Loading Spinner Component

Description: A reusable loading spinner to simulate a loading effect.
Use case: Show loading spinner when data from an API is yet to arrive.
Code Snippet:

```
import React from 'react';
const Spinner = ({ size, color }) => {
  const spinnerStyle = {
    width: size,
    height: size,
    borderTopColor: color,
    borderLeftColor: 'transparent',
    animation: 'spin 1s linear infinite',
    borderWidth: '2px',
    borderStyle: 'solid',
    borderRadius: '50%',
  };
  return (
  );
};
Spinner.defaultProps = {
  size: '6',
  color: 'rgba(59, 130, 246, 1)',
};
export default Spinner;
```

## Dropdown Component

Description: A component for selecting options.
Use case: Select options based on a filter or category.

Code snippet:

```
import React from 'react';
const Dropdown = ({ options, onSelect }) => {
  return (
 onSelect(e.target.value)}>      {options.map((option) => (                  {option.label}              ))}    
  );
};
export default Dropdown;
```
