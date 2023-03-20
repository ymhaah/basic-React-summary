# React summary

Date Created: October 25, 2022 3:09 PM
Link: https://reactjs.org/
Status: stoped
Summary: No
type: Library, front-end, programming

## Links

[React Course - Beginner's Tutorial for React JavaScript Library [2022]](https://www.youtube.com/watch?v=bMknfKXIFA8&list=PLPeqRhIotBsxfNjHfqOuTNZV1m8vFTtYO&index=1&t=15093s&ab_channel=freeCodeCamp.org)

[Quick Start](https://react.dev/learn)

[GitHub - ymhaah/30-Day-React-Learning-Journey](https://github.com/ymhaah/30-Day-React-Learning-Journey)

---

# First of React:

## how to start using React

## [CDN Links](https://reactjs.org/docs/cdn-links.html)

React provides quick links to use all the basic features,and It provides two versions of the links:

- development version: easy to handle and modify and more suitable in the development stage.

```html
<script crossorigin src="<https://unpkg.com/react@18/umd/react.development.js>"></script>
<script crossorigin src="<https://unpkg.com/react-dom@18/umd/react-dom.development.js>"></script>

```

- production versions: Minified and optimized production versions of React

```html
<script crossorigin src="<https://unpkg.com/react@18/umd/react.production.min.js>"></script>
<script crossorigin src="<https://unpkg.com/react-dom@18/umd/react-dom.production.min.js>"></script>

```

> react recommend to keep the crossorigin attribute set.
> 

```html
<script crossorigin src="..."></script>

```

At the beginning of the courses, everyone is advised to use this method for learning, as it is easy to use.

But it is not recommended at the advanced level; Where it affects speed and performance, But for the educational purpose I will use it for the rest of the trip and we will learn the rest of the ways as well.

There is an additional link to something called JSX Added without question for now, we will talk about it in depth in the future.

Now you can use JSX in any `<script>` tag by adding `type="text/babel"` attribute to it.

```html
<script src="<https://unpkg.com/babel-standalone@6/babel.min.js>"></script>

<script src="./index.js" type="text/babel"></script>

```

---

## [create-react-app](https://reactjs.org/docs/create-a-new-react-app.html)

```
npx create-react-app my-app
cd my-app
npm start

```

> If you use Npm way you will find Pre-made files that contain everything you need to get started
> 

 it is clear that this method takes a long time to work; So I recommend you to try [vite](https://vitejs.dev/) They are way faster than normal methods.

[Vite](https://www.notion.so/Vite-9f37969726164e058717748d3fc187fb)

---

And if you use any package, you must generally import this package to your file And most importantly to React is:

```jsx
import React from "react";
import ReactDOM from "react-dom/client";
```

and to use its like this: 

```jsx
ReactDOM + .createRoot(.....
React + .useState(.....
```

And you can, of course, specify which properties of React are imported, for more info on this see:  JS [Import](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import) and [Export](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export).

## first line [createRoot]

[GitHub - ymhaah/30-Day-React-Learning-Journey at cbe09c8f114777dc2452729625bcf52165e5c83e](https://github.com/ymhaah/30-Day-React-Learning-Journey/tree/cbe09c8f114777dc2452729625bcf52165e5c83e)

[30-Day React Learning Journey (part 1)](https://www.notion.so/30-Day-React-Learning-Journey-part-1-541a601c02ce43ae956691e1b54d4c46)

First, open the HTML file you want react to work on, and Add an empty `<div>` tag to mark the spot where you want to display something with React.

I prefer to use an empty `[<main>](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/main)` As if I will use React it will be for the whole site.

we will use an [id](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/id) To select this item, and It is common to use words like [ app, root, main ] But you are free to choose any id.

```html
<main id="app"></main>

```

- Create a variable and link it to the element you create
- Create a variable and then link it with the first property in React, which is `[createRoot()](https://reactjs.org/docs/react-dom-client.html#createroot)` It is common to use words like [ react, root, mainRoot, reactRoot ]
- pass "container" to "createRoot()"

```jsx
// Create a variable and link it to the element you create ( <main id="app"></main> ).
let container = document.querySelector("#app");

// Create a variable and then link it with the first property in React,
//  which is createRoot() and It is common to use words like [ react, root, mainRoot, reactRoot ]
// pass "container" to "createRoot()"
const root = ReactDOM.createRoot(container);

```

 `[createRoot()](https://reactjs.org/docs/react-dom-client.html#createroot)`: From the name you specify which element is the root that React will work on

Create a React root for the supplied `container` and return the root. The root can be used to render a React element into the DOM with `render`:

`const root = createRoot(container);
root.render(element);`

---

# JSX:

## JSX vs js

- *to Create and add an element to DOM using just JS You need to:*
    1. *select the parent element.*
    2. *create the element you want.*
    3. *Add the contents of the element.*
    4. *append the element to the parent.*

```jsx
let father = document.querySelector("#app");
let h1 = document.createElement("h1");
h1.append("Hallo, react"); 
father.append(h1);
```

- *with React you can just use JSX! with the main root we create*

```jsx
root.render(<h1>Hallo, react</h1>);
```

## **JSX basics**

you can use react without JSX:

[React Without JSX - React](https://reactjs.org/docs/react-without-jsx.html)

- *with jsx:*
    
    ```jsx
    const JSX = <h1 className="greeting">Hello, world!</h1>;
    ```
    
- *without jsx:*
    
    ```jsx
    const noJsx = React.createElement(
    	"h1",
    	{ className: "greeting" },
    	"Hello, world!"
    );
    ```
    

---

### JSX

[Introducing JSX - React](https://reactjs.org/docs/introducing-jsx.html)

- JSX is just an object that contains the attributes of the element that you want React to create!
- *link a JSX element to a variable*
    
    ```jsx
    let myHeading1 = <h1>Hallo, react</h1>;
    console.log(myHeading1);
    ```
    
- *using it with a function or if:*
    
    ```jsx
    if (reactISGood) {
    	let myHeading2 = <h1>Hallo, react</h1>;
    } else {
    	let myHeading2 = <h1>Hallo, vue</h1>;
    }
    ```
    
- *butting JSX inside an array or an object*
    
    ```jsx
    let myHeading3 = [<h1>Hallo, react</h1>, <h1>Hallo, vue</h1>];
    ```
    
- *the word **"class"** is already taken so we need to use "className" instead*
    
    ```jsx
    let myHeading4 = <h1 className="veryBigHeading">Hallo, react</h1>;
    ```
    
- *write whatever you want to be a JS code inside { }*
- don't but the inside “ “ like this “{ }”, if if the out but a string it will work.
    
    ```jsx
    let bestFramework = "Svelte";
    let myHeading5 = <h1 className="veryBigHeading">Hallo, {bestFramework}</h1>;
    ```
    
- *a JSX element can contain more than one child, but you can not have more than one element on one variable.*
- for multiple-line JSX code, put the code inside ( )

```jsx
const element = (
	<div>
		<ul className="bestFramework">
			<li>Vue</li>
			<li>Svelte</li>
			<li>Remix</li>
		</ul>
	</div>
);

// you do not need the father to be an element it can be a <></>
const element = (
	<>
		<ul className="bestFramework">
			<li>Vue</li>
			<li>Svelte</li>
			<li>Remix</li>
		</ul>
	</>
);
```

---

# Components:

## Components

[Components and Props – React](https://reactjs.org/docs/components-and-props.html)

> components are like JavaScript functions. They accept arbitrary inputs (called “props”) and return React elements describing what should appear on the screen.
> 
- The working principle of a component is that you make a custom HTML element from scratch; you add all the logic and JSX elements you need in one place.
- The simplest way to define a component is to write a JavaScript function that returns a [JSX](https://www.notion.so/React-summary-065b74152727409b8197b656226bf041) element.
- to render a Component you need to call it like a normal dom element but with <Comp  />
    - `<Welcome name="Sara" />`
    
    > **Always start component names with a capital letter.**
    > 

```jsx
function Welcome(props) {
	let num = 2 + 54; 
  return (
		<h1>Hello, {props.name}, your age is {num} you are so fucking old</h1>
	);
}

<Welcome name="Sara" />
```

- The power of a Component Comes through in its ability to create UI elements like a full header or a footer or nav

```jsx
function Nav(){
    return(
        <nav className="header__nav">
          <ul>
            <li>home</li>
            <li>about us</li>
            <li>are really reading this</li>
          </ul>
        </nav>
    )
}
```

- you can use a Component inside another Component the same like you can use a function inside another function add whit this you can make an entire website section.

```jsx
function App(){
    return(
				<Header/>
        <Nav />
				<Hero />
				<Products />
				<Footer />
    )
}
```

- I remind you from now on that you will name a Component similar to an HTML Dom element and You will spend all of your days trying to figure out why this element is not working.
- In the future, we will talk about the correct way to use [ if, loops, variable, …] inside a  Component to add all the js logic we need for it.

## Components props

[Components and Props – React](https://reactjs.org/docs/components-and-props.html#rendering-a-component)

> When React sees an element representing a user-defined component, it passes JSX attributes and children to this component as a single object. We call this object “props”.
> 
1. We call `root.render()` with the `<Welcome name="Sara" />` element.
2. React calls the `Welcome` component with `{name: 'Sara'}` as the props.
3. Our `Welcome` component returns a `<h1>Hello, Sara</h1>` element as the result.
4. React DOM efficiently updates the DOM to match `<h1>Hello, Sara</h1>`.

```jsx
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
<Welcome name="Sara" />;
```

- You can pass any kind of data through the props object [str, num, obj, arr, boll, …..] and then use them in the component
    
    ```jsx
    function Welcome(props) {
      return <h1>Hello, {props.info.name}</h1>;
    }
    let info ={name: king, age: 120}
    <Welcome info={info} />;
    ```
    
- you can use the [JS ES6 obj Destructuring](https://www.javatpoint.com/es6-object-destructuring) with the prop obj through it, you can expect a better picture of the type of information received and You can also specify initial values
    
    ```jsx
    function Welcome({name, age: 18}) {
      return <h1>Hello, {info.name}</h1>;
    }
    <Welcome name="king" age={150} />;
    ```
    
    - `Don't forget to delete “prop” when you call it`

> Whether you declare a component [as a function or a class](https://reactjs.org/docs/components-and-props.html#function-and-class-components) , it must never modify its own props.
> 
- the component does not own the prop values so it can just use them
- if you use a component prop do not reassign a value to it or just treat a component like a normal function and pass the props value to it

```jsx
function Welcome({name, age}) {
name = "do not do it"
  return <h1>Hello, {info.name}</h1>;
}
Welcome(king, 150)
```

---

# ****Lists and Keys:****

## React element lists & Map()

[Lists and Keys – React](https://reactjs.org/docs/lists-and-keys.html)

### **React list:**

- **React list →** an array that Contains JSX elements [ `<li>1</li>` , `<li>2</li>` , `<li>3</li>`, …..]
    - Do not forget that [JSX](https://www.notion.so/React-summary-065b74152727409b8197b656226bf041) is just an object that contains the attributes of the element that you want React to create, so a React list is just an array with objects inside of it!
    - if you pass a React list direct to a component React is smart enough to know that you want to use all of these elements inside the component
    
    ```jsx
    let listItems = [ <li>1</li>, <li>2</li>, <li>3</li>];
    
    <ul>{listItems}</ul> 
    // Expected output: 
    <ul>
    	<li>1</li>
    	<li>2</li>
    	<li>3</li>
    </ul> 
    ```
    
- Usually, you receive information from a server and then distribute this information to the elements of the site, so we can use a React list of elements as a template waiting for data to be passed to them.

### map( ):

- the [Map()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map) method loops over an array and applies a function that may or may not modify the array element and return a new array with the modified versions of the old array after applying the function
    
    ```jsx
    const array1 = [1, 4, 9, 16];
    
    // Pass a function to map
    const map1 = array1.map(x => x * 2);
    
    console.log(map1);
    // Expected output: Array [2, 8, 18, 32]
    ```
    
- Therefore, because of its unique way of working, it is widely used in React to modify a group of elements
- By using it, you can distribute a set of data to elements without changing the data
- Below, we loop through the `numbers` array using the JavaScript `[map()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)`function. We return an `<li>`element for each item, we assign the resulting array of elements to `listItems`
- Then, we can include the entire `listItems`array inside an `<ul>` element:

```jsx
const numbers = [1, 2, 3, 4, 5];
const listItems = numbers.map((number) =>
  <li>{number}</li>
);
<ul>{listItems}</ul>
```

1. you gave map( ) an array with data → `numbers = [1, 2, 3, 4, 5];`
2. map( ) applies a function to the data → make an `<li>` JSX element and put the array item inside `<li>{number}</li>`
3. map() returns a new array with the modified data → listItems = [ `<li>1</li>` , `<li>2</li>` , `<li>3</li>`, …..]
4. when you call `listItems` React loops into the list and render every list element

## **Keys & Embedding map() in JSX**

[Lists and Keys – React](https://reactjs.org/docs/lists-and-keys.html#keys)

- if you use a map( ) function to generate an element with the same JSX template Like if you distribute four numbers inside an `<li>` For React all four elements are the same; Since they come from the same JSX template that has the same properties Therefore, in order to help React differentiate between these elements, you must give each element a unique ID ( Key )

> Keys help React identify which items have changed, are added, or are removed. Keys should be
> 

```jsx
const numbers = [1, 2, 3, 4, 5];
const listItems = numbers.map((number) =>
  <li key={id}>{number}</li>
);
<ul>{listItems}</ul>
```

- You have to pass for each item a unique ID and pass it with the attributes `key={id}`
    - Keys serve as a hint to React but they don’t get passed to your components. If you need the same value in your component, pass it explicitly as a prop with a different name

```jsx
function NumberList(props) {
  const numbers = props.numbers;
  return (
    <ul>
      {
				numbers.map((number) =>        
					<ListItem 
							key={number.toString()}                  
							value={number} />)
			}    
		</ul>);
}
```

- Keys used within arrays should be unique among their siblings. However, they don’t need to be globally unique. We can use the same keys when we produce two different arrays
- if you use the list with a map() in a component you pass the id when you call it
    
    ```jsx
    function ListItem(props) {
      // Correct! There is no need to specify the key here:
      return <li>{props.value}</li>;
    }
    
    function NumberList(props) {
      const numbers = props.numbers;
      const listItems = numbers.map((number) =>
        // Correct! Key should be specified inside the array.
        <ListItem key={number.toString()} value={number} />
      );
      return (
        <ul>
          {listItems}
        </ul>
      );
    }
    ```
    

---

# ****Conditional Rendering:****

## IF in React

[Conditional Rendering – React](https://reactjs.org/docs/conditional-rendering.html)

> In React, you can create distinct components that encapsulate behavior you need. Then, you can render only some of them, depending on the state of your application.
> 
- you can't use a normal IF( ) inline with JSX for some reason but you can write it anywhere else and then use the output in JSX

```jsx
if (true) {
		state = "a king";
	} else {
		state = "not a king";
	}
function App(prop) {
	return (
		<div>
			<p>{state}</p>
		</div>
	);
}
```

- if want to use an IF( ) inline with JSX you can use the ES6 way or the && way
    - ES6: **[Conditional (ternary) operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator) →** `[condition? true: false](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Operators/Conditional_Operator)`
    
    ```jsx
    function App(prop) {
    	return (
    		<div>
    			{state? <p>a king</p> : <p>not a king</p>
    		</div>
    	);
    }
    ```
    
    - with [&&](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_AND) you just but what happens if true
        - It works because in JavaScript, `true && expression` always evaluates to `expression`, and `false && expression` always evaluates to `false`.
        - Therefore, if the condition is `true`, the element right after `&&` will appear in the output. If it is `false`, React will ignore and skip it.
    
    ```jsx
    function App(prop) {
    	return (
    		<div>
    			{state && <p>a king</p>}
    		</div>
    	);
    }
    ```
    
- In rare cases you might want a component to hide itself even though it was rendered by another component. To do this return `null`
 instead of its render output.
    
    ```jsx
    function WarningBanner(props) {
      if (!props.warn) {
        return null;
      }
    
      return (
        <div className="warning">
          Warning!
        </div>
      );
    }
    ```
    

---

# interactive web & ****Handling Events:****

## ****Handling Events****

[Handling Events – React](https://reactjs.org/docs/handling-events.html)

- Without React If you want to add interactivity to an element you can:
    1. add the function name that you want to run on a specific event directly to the HTML Dom element or use the onClick ( browser API ) js function in js. 
        
        ```html
        <button onclick="activateLasers()">
          Activate Lasers
        </button>
        ```
        
        ```jsx
        button.onclick= function activateLasers() {
        		console.log("why are you reading this!?")
        }
        ```
        
    2. You can use JavaScript to target the element and then use [addEventListener()](https://www.w3schools.com/js/js_htmldom_eventlistener.asp)
        
        ```jsx
        document.getElementById("myBtn").addEventListener("click", activateLasers);
        ```
        
    - ****[addEventListener vs on click in JavaScript](https://linuxhint.com/addeventlistener-vs-onclick-javascript/)****
- with React ( JSX ) It's similar to the first way But there are some differences:
    - React events are named using camelCase, rather than lowercase.
        - camelCase → onClick, lowercase → onclick.
    - Another difference is that you cannot return `false` to prevent default behavior in React. You must call `preventDefault`
        - **[Event.preventDefault()](https://developer.mozilla.org/en-US/docs/Web/API/Event/preventDefault)**
    - when you call the function you call it without parentheses
        - React → `onClick={activateLasers}` , Dom → `onclick="activateLasers()"`
    
    ```jsx
    <button onClick={activateLasers}>  
    	Activate Lasers
    </button>
    ```
    

> When using React, you generally don’t need to call `addEventListener`
 to add listeners to a DOM element after it is created. Instead, just provide a listener when the element is initially rendered.
> 
- When using the first method, you are just using the browser API Like when using the onclike event on a Dom element the browser will just give you the Event object with all the  Properties and functions to use them → [onClick event](https://developer.mozilla.org/en-US/docs/Web/API/Element/click_event)
- with React Your event handlers will receive a React **[Event object](https://beta.reactjs.org/reference/react-dom/components/common#react-event-object)** It is also sometimes known as a “synthetic event”
    - It conforms to the same standard as the underlying DOM events but fixes some browser inconsistencies.
    
    ```jsx
    <button onClick={e => {
      console.log(e); // React event object
    }} />
    ```
    
- it is common to name event handlers as `handle` followed by the event name. You’ll often see `onClick={handleClick}` `onMouseEnter={handleMouseEnter}` and so on.
- if you want to define your event handler inline, wrap it in an anonymous function like so:
    
    ```jsx
    <button onClick={() => alert('You clicked me!')}>
    ```
    

## ****Passing event handlers****

[Responding to Events](https://beta.reactjs.org/learn/responding-to-events#reading-props-in-event-handlers)

- event handlers are declared inside of a component, they have access to the component’s props.
- you can not add a React Event directly on a component you can just add it on a Dom element but you still can pass the event as a prop from a parent component to specify a child’s event handler.

```jsx
function handlePlayClick() {
    alert("Do not click again");
}
<PlayButton handlePlayClick={handlePlayClick}/> 

function PlayButton(prop) {
  return (
    <Button onClick={prop.handlePlayClick}>
      click here
    </Button>
  );
}
```

<aside>
💡 ****Recap****

- You can handle events by passing a function as a prop to an element like `<button>`.
- Event handlers must be passed, **not called!** `onClick={handleClick}`, not `onClick={handleClick()}`.
- You can define an event handler function separately or inline.
- Event handlers are defined inside a component, so they can access props.
- You can declare an event handler in a parent and pass it as a prop to a child.
- You can define your own event handler props with application-specific names.
- Events propagate upwards. Call `e.stopPropagation()` on the first argument to prevent that.
- Events may have unwanted default browser behavior. Call `e.preventDefault()` to prevent that.
- Explicitly calling an event handler prop from a child handler is a good alternative to propagation.
</aside>

---

# UseState (****Component's Memory****)

## useState

[State: A Component's Memory](https://beta.reactjs.org/learn/state-a-components-memory)

[Learn useState In 15 Minutes - React Hooks Explained](https://www.youtube.com/watch?v=O6P86uwfdR0&list=PLZlA0Gpn_vH8EtggFGERCwMY5u5hOjf-h&index=1&ab_channel=WebDevSimplified)

- From my future self: I will tell you about the flaws in React that I noticed
    - render the component many times more than it needs.
    - render the component less than it needs.
- The way React determines when to update a component is by Comparing the previous value and the current value If it is different React rerender the component ( a React component or JSX is just a big object with data describing the properties of the UI elements ), But don't forget React is not JS; it does not control a Local variable.

> **Changes to local variable won’t trigger renders.** React doesn’t realize it needs to render the component again with the new data.
> 

- so to tell React to maintain the data and update it upon request you need to use the `[useState](https://react.dev/reference/react/useState)`Hook.
    
    > In React, `useState`, as well as any other function starting with `use`, is called a Hook.
    > 

To update a component with new data, two things need to happen:

1. **Retain** the data between renders.
2. **Trigger** React to render the component with new data (re-rendering).

- To add a state variable, import `useState` from React at the top of the file or just use it from React

```jsx
import { useState } from 'react';

const [index, setIndex] = useState(0);
// or
const [index, setIndex] = React.useState(0);
```

- when you use the `useState` function it returns two things:
    1. A **state variable** to retain the data between renders.
    2. A **state setter function** to update the variable and trigger React to render the component again.
- using [array destructuring](https://javascript.info/destructuring-assignment) You can distribute the given value to a **variable.**

> When you call `[useState](https://react.dev/reference/react/useState)`, you are telling React that you want this component to remember something.
> 

1. you pass the value you went React to **Retain** to the `useState` Hook → useState( value )
2. the `useState` hook returns an array with two values:
    1.  **state variable.** 
    2.  **state setter function.**
3. we use [array destructuring](https://javascript.info/destructuring-assignment) to distribute the given values to a **variable.**
    1. The **state variable** (`index`) with the value you stored.
    2. The **state setter function** (`setIndex`) which can update the state variable and trigger React to render the component again.
        - the **state setter function** is usually named in this manner **→ set + state variable name.**

```jsx
const [index, setIndex] = useState(0);
```

- You can have as many state variables of as many types as you like in one component.
- you can pass any data type to `useState` ( str, num, arr, obj,…… ) And choosing the appropriate type and number of states may greatly help in improving the quality of the code learn more: [Choosing the State Structure](https://react.dev/learn/choosing-the-state-structure)
- State is private to the component. If you render it in two places, each copy gets its own state.
- state is only a top-level component function so do not put it in a loop or an if or another function.

## state setter function

[Queueing a Series of State Updates](https://react.dev/learn/queueing-a-series-of-state-updates)

```jsx
function Gallery() {
  const [index, setIndex] = useState(0);

  function handleClick() {
    setIndex(index + 1);
  }

  let sculpture = sculptureList[index];
  return 
      <button onClick={handleClick}>
        Next
      </button>
```

- setIndex is a **state setter function** ( a function that you pass to it the new value you need the state to be ) → setIndex( the new value )
- If the new value is not dependent on the old value, you can pass it directly to the `[useState](https://react.dev/reference/react/useState)` Hook → setIndex( 3 )
- if the new value depends on the old value You have to take into account the following:
    - the state value will only update when the component re-render so this will not work as you think
        
        ```jsx
          function handleClick() {
            setIndex(index + 1);
        		setIndex(index + 1);
        		setIndex(index + 1);
          }
        // output is 1 ,not 3
        ```
        
        > React waits until *all* code in the event handlers has run before processing your state updates**, t**his is why the re-render only happens *after* all these `setIndex()`calls.
        > 
    - you are passing the new value to the `setIndex()` function you are not resetting a variable So don't use any JS methods to set a new value
        
        ```jsx
        function handleClick() {
        // bad
            setIndex(index= index + 1);
        		setIndex(index++);
        // good
        		setIndex(index + 1);
          }
        ```
        
    - In general, if the new value depends on making an adjustment to the old value, and also the possibility of performing more than one operation at the same time before updating the component you can pass a *function (* **updater function** *)* that calculates the next state based on the previous one in the queue:
        
        ```jsx
        function handleClick() {
        		setIndex( (prevIndex) => {
        				return prevIndex + 1;
        		}));
        		setIndex( (i) => {
        				return i + 1;
        		}));
        		setIndex( (num) => {
        				return num + 1;
        		}));
        // this will work and it will return 3
          }
        ```
        
        1. React queues this function to be processed after all the other code in the event handler has run.
        2. During the next render, React goes through the queue and gives you the final updated state.
        
        > It’s common to name the updater function argument by the first letters of the corresponding state variable or prev + state variable name
        > 
- 

## Array with useState

- with useState, you can use [ string, number, array, object, true ] all of them but each one of them has a way to do it

### Array:

[Updating Arrays in State](https://react.dev/learn/updating-arrays-in-state)

```jsx
let [num, setNum] = React.useState([1, 2, 3]);

	function Fun() {
		setNum(function (prevNum) {
			return [...prevNum, prevNum.length + 1];
		});
	}
```

- now num ⇒ [1, 2, 3]
- don't use anything like .push() or any Array method to edit it.
- to update the array [...prevNum, prevNum.length + 1]
    - ...prevNum ⇒ for the old value
    - then add the new ones like ⇒ prevNum.length + 1 ( to add 1 )

## obj with useState

[Updating Objects in State](https://react.dev/learn/updating-objects-in-state)

- with objects, things are a little more complicated because we have a key and value

```jsx
function Fun() {
		setAboutName(function (prevAboutName) {
			return {
				...prevAboutName,
				king: !prevAboutName.king,
			};
		});
	}
```

- we use the same trick with Array but if you want to update an old value just rewrite it and it will be updated automatically
- king has already existed we just updated it
- [ !prevAboutName.king ] is there to reverse the value of king each time the fun gets called
- 

---

- you can use prop and state in the same comp, when a comp update React update the state and the comp prop that is liked at the same time

## how to pass a useState function and value

- you can pass a useState function and value from the father element into his sons
- you can not add an event to a comp directly but:

```jsx
function Par(prop) {
	return (
		<div>
			<p onClick={prop.handelClick}>{prop.num}</p>
		</div>
	);
}

function App() {
	let [aboutName, setAboutName] = React.useState(1);
	function Fun() {
		setAboutName(function (prevAboutName) {
			return prevAboutName + 1;
		});
	}
	return (
		<div>
			<Par num={aboutName} handelClick={Fun} />
		</div>
	);
}
```

- you pass the fun() as a normal prop from Par with any name you want but prefer to be (handle + the event)
- in the original comp in the element, you want to add the event to it and pass to it a real event with the value prop.handelClick

## day 22

- 

```jsx
let info = [
	{
		id: 0,
		con: "eg",
		name: "yousef",
		age: 20,
	}
];

function Son1(prop) {
	return (
		<div>
			{prop.state.map(function (ele) {
				return (
					<button
						key={ele.id}
						onClick={function () {
							prop.cons(ele.id);
						}}
					>
						{ele.age}
					</button>
				);
			})}
		</div>
	);
}

function App() {
	let [main, setMain] = React.useState(info);

	// how to change a value inside an array
	function fun(returnedId) {
		setMain((prevMain) => {
			return prevMain.map((ele) => {
				return ele.id == returnedId
					? { ...ele, age: ele.age + 1 }
					: ele;
			});
		});
	}

	return (
		<div>
			<Son1 state={main} cons={fun} />
		</div>
	);
}
```

---

# Forms:

## forms

[Forms - React](https://reactjs.org/docs/forms.html)

- With most of the form elements, there is an [onChange](https://www.javatpoint.com/javascript-change-event) event, which Activates when there is a change in the state of the element; Where, for example, when writing, it is activated when any additional letter is added.
- if you link the onChange event to any function the Browser will automatically give you an object back we can call it “**event”**
    - the **event object has inside him Most of the values and properties of the** element in **which the** onChange event happens
    - the most important property in the **event object is “event.target” Which gives back the element on which the event happened.**
        - **“event.target.value” → It gives you the value inside the element [ the input ]**
        - **“event.target.name” → give you the value of the “[name attributes](https://www.w3schools.com/tags/att_name.asp)” [ name=”__” ]**
- And from the above, we can link **“event.target.value” with a State This gives us more control over the element**
- we can update the state value with a function that is linked to the onChange event and just use the **set** function with **“event.target.value”**

```jsx
function App() {
	let [main, setMain] = React.useState("");

	function fun(**event**) {
		// setMain((prevMain) => {
		// 	return (prevMain = **event.target.value**);
		// });
		// or if you do not care about the old value
		setMain(**event.target.value**);
	}

	return (
		<div>
			<form>
				<input type="text" placeholder="name" onChange={fun} />
			</form>
		</div>
	);
}
```

---

### event function:

- if we have more than one form element it will be hard to make a state and a set state function for every one of them
- The easiest way to solve this problem is to add all the similar values in a state project
    - [day 20 ( obj with useState )](https://www.notion.so/React-summary-065b74152727409b8197b656226bf041)
- The easiest way to distinguish each element from the other is to add **the “[name attributes](https://www.w3schools.com/tags/att_name.asp)”  and give it the same value as the key name on the state opj**
    - **[** firstName: "" → name="firstName" **]**
- All you have to do is update the value of the state with the set function using the kay as **“event.target.name” and the value as “event.target.value”**
    - [**event.target.name**]: **event.target.value**,

> the [ ] with the key is an ES6 feature It gives you the ability to add a changing value as a key
> 

```jsx
function App() {
	let [main, setMain] = React.useState({
		firstName: "",
		lastName: "",
	});

	function fun(event) {
		setMain((prevMain) => {
			return {
				...prevMain,
				[**event.target.name**]: **event.target.value**,
			};
		});
	}

	return (
		<div>
			<form>
				<input
					type="text"
					placeholder="firstName"
					onChange={fun}
					name="firstName"
				/>
				<input
					type="text"
					placeholder="lastName"
					onChange={fun}
					name="lastName"
				/>
			</form>
		</div>
	);
}
```

## controlled components &  T*extarea, checkbox*

### controlled components:

[Forms - React](https://reactjs.org/docs/forms.html#controlled-components)

1. In HTML, form elements such as `<input>` or `<textarea>`, typically maintain their own state and update it based on user input and are managed by the browser.
2. In React, we create a custom state to manage the form input typically kept in the state property of components 

> Now we have the same information in two sources, which may lead to errors due to the incompatibility of information
> 
- The solution is to combine the two by making the React state the **“single source of truth”** by connecting the react state with the form value property `value={main.firstName}`
- Then the React component that renders a form also controls what happens in that form on subsequent user input. An input form element whose value is controlled by React in this way is called a “controlled component”.

```jsx
function App() {
	let [main, setMain] = React.useState({
		firstName: "",
	});
	return (
			<form>
				<input
					type="text"
					placeholder="firstName"
					name="firstName"
					// ##############################
					value={main.firstName}
				/>
			</form>
	);
}
```

---

### T*extarea:*

[Forms - React](https://reactjs.org/docs/forms.html#the-textarea-tag)

- In HTML, `<textarea>` element defines its text by its children like this:

```html
<textarea>
  Hello there, this is some text in a text area
</textarea>
```

- In React, a `<textarea>`uses a value attribute instead. This way, a form using a `<textarea>` can be written very similarly to a form that uses a single-line input:

```jsx
function App() {
	let [main, setMain] = React.useState({
		comment: "",
	});
	return (
			<form>
				{/* <textarea> value </textarea> */}
				{/* or the react way */}
				<textarea
					placeholder="comment"
					name="comment"
					value={main.comment}
				/>
			</form>
	);
}
```

---

### *checkbox and the new event function:*

[Forms - React](https://reactjs.org/docs/forms.html#handling-multiple-inputs)

- the *`checkbox` element is just an `input` element with the* type="checkbox" on it, but it has a main difference; which is that the event object does not return “value” but returns “checked“
    - **“event.target.**checked**” →** this element can only be checked or not checked ( true or false )

> Now there is a problem, which is that there are two types of data ( text, boolean ) from two different sources ( **event.target.value**, **event.target.**checked ) that must be updated with the same function
> 
- the old function we made in [day 24 ( forms )](https://www.notion.so/React-summary-065b74152727409b8197b656226bf041) can just update text which came from **event.target.value**

> we can make a new function But where are the creativity and professionalism?
> 

### the new Event function:

1. using js [object restructuring](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment) we can simplify the **event object** 
    1. `let { name, value, checked, type } = event.target;` Which translates to the following:
        1. ``event.target.name` 
        2. ``event.target.value` 
        3. ``event.target.checked` → true \ false
        4. `event.target.type` → text \ checkbox
2. the new event function is like the one we made on [day 24 ( forms )](https://www.notion.so/React-summary-065b74152727409b8197b656226bf041) but with some new things:
    1.  `[name]: type == "checkbox" ? checked : value,` 
        1. we use a **[ternary operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator)  [** `type == "checkbox" ? checked : value,` **] from** [day 23 ( IF in React )](https://www.notion.so/React-summary-065b74152727409b8197b656226bf041) To determine which value to update Depending on the type of element →  text \ checkbox

- Now we can add different types of data from more than one source, which allows the ability to increase the volume in the future easily

```jsx
function App() {
	let [main, setMain] = React.useState({
		firstName: "",
		checkBox: true,
	});

	// ##############################
	// to work with value and checked
	function fun(event) {
	  let { name, value, checked, type } = event.target;
		setMain((prevMain) => {
			return {
				...prevMain,
				[name]: type == "checkbox" ? checked : value,
			};
		});
	}
	// ##############################

	return 
			<form>
				<input
					type="text"
					placeholder="firstName"
					onChange={fun}
					name="firstName"
					value={main.firstName}
				/>
				<input
					type="checkbox"
					checked={main.checkBox}
					name="checkBox"
					onChange={fun}
				/>
			</form>
	);
}
```

## radio & Select & submit button

### radio button:

- it is the same as a [checkBox](https://www.notion.so/React-summary-065b74152727409b8197b656226bf041) so if you want more go read about:
    - how a *`checkbox`* is different from a normal input tag
    - the new **“event.target.**checked**”**
    - the new [onChange function](https://www.notion.so/React-summary-065b74152727409b8197b656226bf041).
- with a `*radio*` button, Each button contains a unique text as its value
    
    [https://www.notion.so](https://www.notion.so)
    
    - the **“event.target.**checked**” only takes** true or false, But the values that we will store will be the unique text, so we will use a [comparison operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators?retiredLocale=ar) ( == ) [ If the stored value is equal to the value inside the button ] to give **“event.target.**checked**”** true or false ( read more about “[controlled components](https://www.notion.so/React-summary-065b74152727409b8197b656226bf041)” )
    
    ```jsx
    <input
    						type="radio"
    						value="radio button1"
    						checked={main.radio == "radio button1"}
    					/>
    ```
    
    ---
    
- as I said we only store one value with a  `*radio*` button which is the “value” of the selected one
- So all the elements will have the same name but the “value” will differ depending on the selected element
- And if you look, you will find that the new [onChange function](https://www.notion.so/React-summary-065b74152727409b8197b656226bf041) is still working

```jsx
function App() {
	let [main, setMain] = React.useState({
		radio: "",
	});

	function fun(event) {
		let { name, value, checked, type } = event.target;
		setMain((prevMain) => {
			return {
				...prevMain,
				[name]: type == "checkbox" ? checked : value,
			};
		});
	}
	console.log(main);
	return (
		<div>
			<form>
				<fieldset>
					<legend>radio buttons</legend>
					<input
						type="radio"
						id="r1"
						name="radio"
						value="radio button1"
						onChange={fun}
						checked={main.radio == "radio button1"}
					/>
					<label htmlFor="r1">radio button1</label>
					<br />
					<input
						type="radio"
						id="r2"
						name="radio"
						value="radio button2"
						onChange={fun}
						checked={main.radio == "radio button2"}
					/>
					<label htmlFor="r2">radio button2</label>
				</fieldset>
			</form>
		</div>
	);

```

---

### Select Box:

- the new [onChange function](https://www.notion.so/React-summary-065b74152727409b8197b656226bf041) is still working
- the value ( “[controlled components](https://www.notion.so/React-summary-065b74152727409b8197b656226bf041)” ) still working
- the naming trick still working
- The only thing special is the way of writing a `select` element and how to put items Inside it with the  `option`  element [ give the `option`  element a value equal to what you write inside of the element ]

```
function App() {
	let [main, setMain] = React.useState({
		select: "",
	});
	function fun(event) {
		let { name, value, checked, type } = event.target;
		setMain((prevMain) => {
			return {
				...prevMain,
				[name]: type == "checkbox" ? checked : value,
			};
		});
	}
	return (
		<div>
			<form>
				<select value={main.select} name="select" onChange={fun}>
					<option value="Yousef">Yousef</option>
					<option value="Hafnawy">Hafnawy</option>
				</select>
			</form>
		</div>
	);
}
```

---

### submitting the form:

- to submit the form to an API or some back-end server or anything else you need a submit button.
    - you can use an `input` with `type="submit"`
    - or you can use a normal button [ if there is one button inside a form it will be a submit button automatically   ]
- you do not need to do anything to submit button because the form will do the work
    - when you submit the form it sends the reply to the [onSubmit](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFormElement/submit_event) event [ it is like the [onChange](https://www.javatpoint.com/javascript-change-event) event ( you now have the event object ) ]
    - `event.preventDefault()`  prevent the default action of the Browser, learn [more](https://www.folkstalk.com/2022/09/onsubmit-prevent-default-with-code-examples.html)
    - Of course, after all this, you must have a function that sends the “main state” to an API or  back-end server, learn [more](https://developer.mozilla.org/en-US/docs/Learn/Forms/Sending_forms_through_JavaScript)

```
function App() {
	let [main, setMain] = React.useState({
		firstName: "",
		comment: "",
		checkBox: true,
		radio: "",
		select: "",
	});

	function subFun(event) {
		event.preventDefault();
		apiThing(main);
	}

	return (
		<div>
			<form onSubmit={subFun}>
				<input type="submit" value="submit it man" /> 
				{/* or a normal button */}
				<button>submit it man</button>
			</form>
		</div>
	);
}
```

---

# API calls & useEffect:

## fetch & useEffect basics

### fetch:

- If you want to know more, here are some resources
    
    [JavaScript](https://www.notion.so/JavaScript-5b49a10ceef64c819e8f84e78925e275)
    

```
fetch("https://dummyjson.com/products/1")
	.then((res) => res.json())
	.then((date) => console.log(date));
```

[Learn Fetch API In 6 Minutes](https://www.youtube.com/watch?v=cuEtnrL9-H0&ab_channel=WebDevSimplified)

[DummyJSON](https://dummyjson.com/)

---

### useEffect:

[Using the Effect Hook - React](https://reactjs.org/docs/hooks-effect.html)

- In general, React is not designed to handle data that comes from outside project files, something like ( localStorage, API, database, …. ) We call these things side effects.
    - for example: If you call an API inside a *Component the component will refresh and when it refreshes it will call the API again in an endless cycle*
- useEffect: Allows you to control when the value of a specific state is updated so that an infinite loop does not happen
- useEffect( function(), [] )
    1. function() → pass the changed state or the value that case the side effect inside it to tell React to only update it when the value change 
        - useEffect  update after the component is fully loaded
    2. [ changed value ]  → every time the component gets rerendered react  compares the value before the update and after the update, and if there is a difference, it is allowed to change the value inside the useEffect, otherwise the value remains constant
        - if just want to use this value once and never update it just use an empty array

```
React.useEffect(function () {
		fetch("https://dummyjson.com/products/1")
			.then((res) => res.json())
			.then((date) => setMain(date));
	}, []);
```

## useEffect Memory leak & async / await

### async / await:

- If you want to know more, here are some resources

---

- the function you pass to the useEffect accepts another function as a return value, this function is used to stop the original function from running if the component does not render yet

```jsx
function FriendStatus(props) {
  // ...
  useEffect(() => {
    // ...
    ChatAPI.subscribeToFriendStatus(props.friend.id, handleStatusChange);
    return () => {
      ChatAPI.unsubscribeFromFriendStatus(props.friend.id, handleStatusChange);
    };
  });
```

## day 29 ( )