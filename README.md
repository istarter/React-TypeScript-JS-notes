
# React-TypeScript-JS-notes


# Javascript 

### This script takes a string and capitalizes the first letter.


```
const myString = 'developer';

let myNewString;
myNewString= myString.charAt(0).toUpperCase() + myString.substring(1);

console.log(myNewString);
Working with Numbers
This script demonstrates creating a Number object and formatting it.

const num = new Number(5);
let x;
x = num.toString().length;
x = num.toFixed(2);
console.log(x);

Math Operations
This script showcases various mathematical operations.

let x;
x = Math.sqrt(9);
x = Math.floor(4.9);
x = Math.ceil(4.3);
x = Math.round(4.3);
x = Math.floor(Math.random() * 200 + 1);
console.log(x);

Random Sum of Two Numbers
This script generates two random numbers and displays their sum.

const x = Math.floor(Math.random() * 100 + 1);
const y = Math.floor(Math.random() * 50 + 1);

const sum = x + y;
const sumPlus = `${x} + ${y} = ${sum}`;

console.log(sumPlus);

Working with Dates This script retrieves and logs the current year.
let d = new Date();
d = d.getFullYear();
console.log(d);

Working with Arrays
This script demonstrates array manipulation including concatenation and the spread operator.
let x;
const fruits = new Array('apple', 'Banana', 'Orange');
const berries = ['strawberry', 'blueberry', 'raspberry'];
fruits.push(berries);
x = fruits[3][1];
const allFruites = [fruits, berries];
x = allFruites;
x = fruits.concat(berries);

// Spread operator
x = [...fruits, ...berries];
console.log(x);

Flatten Arrays
This script demonstrates how to flatten a nested array.
const arr = [1, 2, [3, 4], 5, [6, 7], 8];
x = arr.flat();
console.log(x);

Array Manipulation Challenge
This script reverses an array, adds 0 at the end, and 6 at the beginning.
const arr = [1, 2, 3, 4, 5];
arr.reverse();
arr.push(0);
arr.unshift(6);
console.log(arr);

Remove Duplicate Numbers
First Solution
This script combines two arrays and removes duplicates.
const arr1 = [1, 2, 3, 4, 5];
const arr2 = [5, 6, 7, 8, 9, 10];
const arr3 = arr1.slice(0, 4).concat(arr2);
console.log(arr3);

Second Solution
This script uses the spread operator and Set to remove duplicates.
let arr4 = [...arr1, arr2];
const newArray = [...new Set(arr4)];
arr4.splice(4, 1);
console.log(newArray);

Combining and Removing Duplicates from Arrays
This script combines two arrays using concat and removes duplicates using filter.
const arr1 = [1, 2, 3, 4, 5];
const arr2 = [5, 6, 7, 8, 9, 10];

// Step 1: Combine the arrays using concat
const combinedArray = arr1.concat(arr2);

// Step 2: Remove duplicates using filter
const uniqueArray = combinedArray.filter((item, index) => {
  return combinedArray.indexOf(item) === index;
});

console.log(uniqueArray);
Working with Objects
This script demonstrates creating and manipulating objects.

let x;
const person = {
  name: "John Doe",
  age: 30,
  isAdmin: true,
};
x = person.name;
x = person['age'];

const todo = new Object();
todo.id = 1;
todo.name = 'Buy Milk';
todo.complete = false;

x = todo;

console.log(x);
Creating Objects with a Function
This script defines a function to create objects and demonstrates its use.

function createToDo(name, id, complete) {
  return {
    name: name,
    id: id,
    complete: complete
  };
}

const todo = createToDo('jhon', 1, true);
let x = todo;
console.log(x);
Merging Objects

This script demonstrates merging objects using the spread operator and other object methods.

const obj1 = { a: 1, b: 2 };
const obj2 = { c: 3, d: 4 };
const obj3 = { ...obj1, ...obj2 };

let x;
x = obj3;
x = Object.keys(obj3);
x = Object.keys(obj3).length;
x = Object.entries(obj3);
x = Object.values(obj3);
x = obj3.hasOwnProperty('age');
console.log(x);

 Destructuring
let x;
const todo = {
    id: 1,
    title: 'Take out',
    user: {
        name: 'john',
    }
}

const {id: todoId, title, user: {name}} = todo;
console.log(name)

// Object Challenge
const library = [
    {
    title: "Harry Poter",
    author: "Berry John",
    status: {
        own: true,
        reading: false,
        read: false
    }
},
{
    title: "Bill",
    author: "Simoe",
    status: {
        own: true,
        reading: false,
        read: false
    }
},
{
    title: "M.j asdi",
    author: "brown dim",
    status: {
        own: true,
        reading: false,
        read: false
    }
}
]
 
 library[0].status.read = true;
 library[1].status.read = true;
 library[2].status.read = true;
 
 const {title: firsbook} = library[0]

 console.log(firsbook)
 const libraryJSON = JSON.stringify(library);
 console.log(libraryJSON)

// Rest Paramaters

function sum(...numbers) {
    let total = 0;
    for (const num of numbers) {
        total += num;
        // console.log(total)
    }
    return total;
}

console.log(sum(1,2,3,4,6)

function loginUser(user) {
    return `The user ${user.name} with the id of ${user.id} is login in`
}
const client = {
    id: 1, 
    name: "jhon",
}

console.log(loginUser(client))

// Function Declaration
function addDollarSign(value) {
    return '$' + value;
}

console.log(addDollarSign(200))

// Function expression
const addPlusSign = function(value) {
    return '+' + value;
}
console.log(addPlusSign(33))

// Falsy Values:
// - false
// - 0
// - "" or '' (Empty string)
// - null
// - undefined
// - NaN

// Truthy Values:
// - Everything else that is not falsy
// - true
// - '0' (0 in a string)
// - ' ' (space in a string)
// - 'false' (false in a string)
// - [] (empty array)
// - {} (empty object)
// - function () {} (empty function)

const x = function () {};

if (x) {
  console.log('This is truthy');
} else {
  console.log('This is falsy');
}

console.log(Boolean(x));

// Truthy and falsy caveats
const children = 3;

// Checking for literal 0
if (children) {
  console.log(`You have ${children} children`);
} else {
  console.log('Please enter number of children');
}

// Solution
if (!isNaN(children)) {
  console.log(`You have ${children} children`);
} else {
  console.log('Please enter number of children');
}

// Checking for empty arrays
const posts = ['Post One'];

// Always true even when empty
if (posts) {
  console.log('List Posts');
} else {
  console.log('No Posts To List');
}

// Solution
if (posts.length > 0) {
  console.log('List Posts');
} else {
  console.log('No Posts To List');
}

// Checking for empty objects
const user = {
  name: 'Brad',
};

// Always true, even when no properties
if (user) {
  console.log('List User');
} else {
  console.log('No User');
}

// Solution
if (Object.keys(user).length > 0) {
  console.log('List User');
} else {
  console.log('No User');
}

// Loose Equality (==)
console.log(false == 0); // true
console.log('' == 0); // true
console.log(null == undefined); // true

// Strict Equality
console.log(false === 0); // false
console.log('' === 0); // false
console.log(null === undefined); // false

```
# React


<Button onClick={handleClick}  />: if I use () with handleClick then it'll run after rendering the screen as soon as possible so go without handleClick. Passed function as a value.
forEach() is a array method. forEach() take a single argument must have to be a function. 


### Get random number from the array:

```
 const getMemeImage = () => {
   const memesArray = MamesData.data.memes;
   const randomNumber = Math.floor(Math.random() * memesArray.length);
   console.log(randomNumber);
 };
 
 ```


### Mapping over the Array: 

Generally map() method is used to iterate over an array and calling function on every element of array.

```
const thingsArray = ["Thing 1", "Thing 2"];
 const thingsElements = thingsArray.map((thing) => <p key={thing}>{thing}</p>);
 console.log(thingsElements);
 
 ```


### Adding new element to the array:

```
const thingsArray = ["Thing 1", "Thing 2"];
 const addItem = () => {
   const newThing = `Thing ${thingsArray.length + 1}`;
   thingsArray.push(newThing);
   console.log(thingsArray);
 };
 ```






### Using forEach() Loop


```
<div id="names"></div>
const namesDiv = document.querySelector("#names");
const names = [
 { first: "Kevin", last: "Nguyen" },
 { first: "Eric", last: "Nguyen" },
 { first: "Andrew", last: "Yamasaki" }
];

let template = "";


names.map( (name, i) => {
template += `<div key={i}>Hi my name is ge ${name.first} ${name.last}. This is my position ${i + 1}<div/>` 
})


namesDiv.innerHTML = template


Ternary Operator: let answer = isGoingOut === true ? "Yes" : "No"

Use in  JSX: <h2>{isGoingOut === true ? "Yes" : "No"}</h2>
```




### Used the ternary operator and add items to the existing list by using the spread operator.


```import React, { useState } from "react";
import Header from "./components/Header";
import Meme from "./components/Meme";
 
function App() {
 const [isGoingOut, setIsGoingOut] = useState(true);
 const [thingsArray, setThingsArray] = useState(["Thing1", "Thing2"]);
  const changeMind = () => {
   setIsGoingOut((prevState) => !prevState);
 };
 
 const addItem = () => {
   setThingsArray((prevState) => {
     return [...prevState, ` Thing ${prevState.length + 1}`];
   });
 };
 const thingsElement = thingsArray.map((thing) => <p key={thing}>{thing}</p>);
 
 return (
   <div>
     <Header />
     <Meme />
 
     <div onClick={changeMind} className="state">
       <h1 className="state-title">Do I feel like going out tonight?</h1>
       <h1>{isGoingOut ? "Yes" : "No"}</h1>
     </div>
     <div>
       <button onClick={addItem}>Add Item</button>
       {thingsElement}
     </div>
   </div>
 );
}
 
export default App;
```
 


 
 ### Get data from json file used map, state.


```import React from "react"
import boxes from "./boxes"
import Box from './Box'
export default function App() {
   const [squares, setSquares] = React.useState(boxes)
  
   const squareElements = squares.map(square => (
       <Box key={square.id} on={square.on} />
   ))
   /**
    * Challenge part 2:
    * 1. Create a separate component called "Box" and
    *    replace the `div` above with our <Box /> components
    * 2. Pass the Box component a prop called `on` with the
    *    value of the same name from the `boxes` objects
    * 3. In the Box component, apply dynamic styles to determine
    *    the backgroundColor of the box. If it's `on`, set the
    *    backgroundColor to "#222222". If off, set it to "none"
    */
  
   return (
       <main>
           {squareElements}
       </main>
   )
}
 ```



### Component which is rendered in the app.js
```
import React from 'react';
 
 
const Box = ({on}) => {
   const styles = {
   backgroundColor: on ? "#222222" : "none"
}
   return(
      
       <div style={styles} className="box"></div>
      
   )
}
 
 
export default Box;
```
 
### Change background color by clicking on off used state ternary operator.
```
import React from "react"
 
export default function Box(props) {
   const [on, setOn] = React.useState(props.on)
  
   const styles = {
       backgroundColor: on ? "#222222" : "transparent"
   }
  
   function toggle () {
       setOn(prev => !prev)
   }
  
   return (
       <div style={styles} className="box" onClick={toggle}></div>
   )
}
```

### Use setSquare do not modify directly, update the correct square by using id

```

import React from "react"
import boxes from "./boxes"
import Box from "./Box"
 
export default function App() {
   const [squares, setSquares] = React.useState(boxes)
  
   function toggle(id) {
       setSquares(prevSquares => {
           return prevSquares.map((square) => {
               return square.id === id ? {...square, on: !square.on} : square
           })
       })
   }
  
   const squareElements = squares.map(square => (
       <Box
           key={square.id}
           on={square.on}
           toggle={() => toggle(square.id)}
       />
   ))
  
   return (
       <main>
           {squareElements}
       </main>
   )
}
 
```


### Display punchline if the state is true.
```

import React from "react"
 
export default function Joke(props) {
   const [isShown, setIsShown] = React.useState(false)
   /**
    * Challenge:
    * - Only display the punchline paragraph if `isShown` is true
    */
   function toggleShown(){
       setIsShown(prevShown => !prevShown)
   }
   return (
       <div>
           {props.setup && <h3>{props.setup}</h3>}
           {isShown && <p>{props.punchline}</p>}
           <button onClick={toggleShown}>Show Punchline</button>
           <hr />
       </div>
   )
}
 
const cond1 = false
const cond2 = false
if(cond1 && console.log("Hello there")) {
   // this code will NOT run
}

```

### Display messages if there is new messages otherwise nothing on the screen
```

import React from "react"
 
export default function App() {
   const [messages, setMessages] = React.useState(["a", "b"])
   /**
    * Challenge:
    * - Only display the <h1> below if there are unread messages
    */
   return (
       <div>
           {messages.length > 0 && <h1>You have {messages.length} unread messages!</h1>}
       </div>
   )
}
 
```

### Condinionl rendinring ? Ternary vs &&

The && is great when wither want to display or not display.
The ternary? operator is great when you choose between 2 things. 


### Condiontonl rendering
```
import React from "react"
 
export default function App() {
   const [messages, setMessages] = React.useState(["a"])
   /**
    * Challenge:
    * - If there are no unread messages, display "You're all caught up!"
    * - If there are > 0 unread messages, display "You have <n> unread
    *   message(s)"
    *      - If there's exactly 1 unread message, it should read "message"
    *        (singular)
    */
   return (
       <div>
           {
           messages.length === 0 ? <h3>You're all caught up</h3> :
           <h3>You have {messages.length} unread {messages.length > 1 ? "Messages" : "Message"}</h3>
             
           }
       </div>
   )
}
 
 ```


## Quiz

1. What is "conditional rendering"?
When we want to only sometimes display something on the page
based on a condition of some sort


2. When would you use &&?
When you want to either display something or NOT display it


3. When would you use a ternary?
When you need to decide which thing among 2 options to display


4. What if you need to decide between > 2 options on
   what to display?
Use an `if...else if... else` conditional or a `switch` statement

```
function App() {
    let someVar
    if () {
        someVar = <SomeJSX />
    } else if() {
        ...
    } else {
        ...
    }
    return (
        <div>{someVar}</div>
    )
}

```
### onChange method update the state.

```
import React from "react"
 
export default function Form() {
   const [firstName, setFirstName] = React.useState("")
  
   console.log(firstName)
  
   function handleChange(event) {
       setFirstName(event.target.value)
   }
  
   return (
       <form>
           <input
               type="text"
               placeholder="First Name"
               onChange={handleChange}
           />
       </form>
   )
}
 

```

### Dealing with form data update state and maintaining previous data

```
import React from "react"
 
export default function Form() {
   const [formData, setFormData] = React.useState(
       {firstName: "Najib", lastName: "Khan"}
   )
  
   console.log(formData)
 
  
   function handleChange(event) {
      setFormData(prevData => {
          return {
              ...prevData,
              [event.target.name]: event.target.value
          }
      })
  }
  
   return (
       <form>
           <input
               type="text"
               placeholder="First Name"
               onChange={handleChange}
               name="firstName"
           />
           <input
               type="text"
               placeholder="Last Name"
               onChange={handleChange}
               name="lastName"
           />
       </form>
   )
}
 
```

### Controlled Component. The input no longer responsible to change our state react now controlling the input value.
In a controlled component, form data is handled by a React component. The alternative is uncontrolled components, where form data is handled by the DOM itself. To write an uncontrolled component, instead of writing an event handler for every state update, you can use a ref to get form values from the DOM
```
import React from "react"
 
export default function Form() {
   const [formData, setFormData] = React.useState(
       {firstName: "", lastName: "", email: "", comments: ""}
   )
  
   console.log(formData.comments)
  
   function handleChange(event) {
       setFormData(prevFormData => {
           return {
               ...prevFormData,
               [event.target.name]: event.target.value
           }
       })
   }
  
   /**
    * Challenge: Add a textarea for "comments" to the form
    * Make sure to update state when it changes.
    */
  
   return (
       <form>
           <input
               type="text"
               placeholder="First Name"
               onChange={handleChange}
               name="firstName"
               value={formData.firstName}
           />
           <input
               type="text"
               placeholder="Last Name"
               onChange={handleChange}
               name="lastName"
               value={formData.lastName}
           />
           <input
               type="email"
               placeholder="Email"
               onChange={handleChange}
               name="email"
               value={formData.email}
           />
           <textarea
               value={formData.comments}
               placeholder="Comments"
               onChange={handleChange}
               name="comments"
           />
       </form>
   )
}
 
```
### Better version of form with radio button and event.target.value is destructerd.
``` 
import React from "react"
 
export default function Form() {
   const [formData, setFormData] = React.useState(
       {
           firstName: "",
           lastName: "",
           email: "",
           comments: "",
           isFriendly: true
       }
   )
  
   function handleChange(event) {
       const {name, value, type, checked} = event.target
       setFormData(prevFormData => {
           return {
               ...prevFormData,
               [name]: type === "checkbox" ? checked : value
           }
       })
   }
  
   return (
       <form>
           <input
               type="text"
               placeholder="First Name"
               onChange={handleChange}
               name="firstName"
               value={formData.firstName}
           />
           <input
               type="text"
               placeholder="Last Name"
               onChange={handleChange}
               name="lastName"
               value={formData.lastName}
           />
           <input
               type="email"
               placeholder="Email"
               onChange={handleChange}
               name="email"
               value={formData.email}
           />
           <textarea
               value={formData.comments}
               placeholder="Comments"
               onChange={handleChange}
               name="comments"
           />
           <input
               type="checkbox"
               id="isFriendly"
               checked={formData.isFriendly}
               onChange={handleChange}
               name="isFriendly"
           />
           <label htmlFor="isFriendly">Are you friendly?</label>
           <br />
       </form>
   )
}
 

```
### Form with React check box and radio button.

```
import React from "react"
 
export default function Form() {
   const [formData, setFormData] = React.useState(
       {
           firstName: "",
           lastName: "",
           email: "",
           comments: "",
           isFriendly: true,
           employment: ""
       }
   )
   console.log(formData.employment)
  
   function handleChange(event) {
       const {name, value, type, checked} = event.target
       setFormData(prevFormData => {
           return {
               ...prevFormData,
               [name]: type === "checkbox" ? checked : value
           }
       })
   }
  
   return (
       <form>
           <input
               type="text"
               placeholder="First Name"
               onChange={handleChange}
               name="firstName"
               value={formData.firstName}
           />
           <input
               type="text"
               placeholder="Last Name"
               onChange={handleChange}
               name="lastName"
               value={formData.lastName}
           />
           <input
               type="email"
               placeholder="Email"
               onChange={handleChange}
               name="email"
               value={formData.email}
           />
           <textarea
               value={formData.comments}
               placeholder="Comments"
               onChange={handleChange}
               name="comments"
           />
           <input
               type="checkbox"
               id="isFriendly"
               checked={formData.isFriendly}
               onChange={handleChange}
               name="isFriendly"
           />
           <label htmlFor="isFriendly">Are you friendly?</label>
           <br />
           <br />
          
           <fieldset>
               <legend>Current employment status</legend>
              
               <input
                   type="radio"
                   id="unemployed"
                   name="employment"
                   value="unemployed"
                   checked={formData.employment === "unemployed"}
                   onChange={handleChange}
               />
               <label htmlFor="unemployed">Unemployed</label>
               <br />
              
               <input
                   type="radio"
                   id="part-time"
                   name="employment"
                   value="part-time"
                   checked={formData.employment === "part-time"}
                   onChange={handleChange}
               />
               <label htmlFor="part-time">Part-time</label>
               <br />
              
               <input
                   type="radio"
                   id="full-time"
                   name="employment"
                   value="full-time"
                   checked={formData.employment === "full-time"}
                   onChange={handleChange}
               />
               <label htmlFor="full-time">Full-time</label>
               <br />
              
           </fieldset>
       </form>
   )
}
 

```

### Complete form with updating state, input field, checklist, radio button, and dropdown.

```
import React from "react"
 
export default function Form() {
   const [formData, setFormData] = React.useState(
       {
           firstName: "",
           lastName: "",
           email: "",
           comments: "",
           isFriendly: true,
           employment: "",
           favColor: ""
       }
   )
  
   function handleChange(event) {
       const {name, value, type, checked} = event.target
       setFormData(prevFormData => {
           return {
               ...prevFormData,
               [name]: type === "checkbox" ? checked : value
           }
       })
   }
  
   function handleSubmit(event) {
       event.preventDefault()
       // submitToApi(formData)
       console.log(formData)
   }
  
   return (
       <form onSubmit={handleSubmit}>
           <input
               type="text"
               placeholder="First Name"
               onChange={handleChange}
               name="firstName"
               value={formData.firstName}
           />
           <input
               type="text"
               placeholder="Last Name"
               onChange={handleChange}
               name="lastName"
               value={formData.lastName}
           />
           <input
               type="email"
               placeholder="Email"
               onChange={handleChange}
               name="email"
               value={formData.email}
           />
           <textarea
               value={formData.comments}
               placeholder="Comments"
               onChange={handleChange}
               name="comments"
           />
           <input
               type="checkbox"
               id="isFriendly"
               checked={formData.isFriendly}
               onChange={handleChange}
               name="isFriendly"
           />
           <label htmlFor="isFriendly">Are you friendly?</label>
           <br />
           <br />
          
           <fieldset>
               <legend>Current employment status</legend>
               <input
                   type="radio"
                   id="unemployed"
                   name="employment"
                   value="unemployed"
                   checked={formData.employment === "unemployed"}
                   onChange={handleChange}
               />
               <label htmlFor="unemployed">Unemployed</label>
               <br />
              
               <input
                   type="radio"
                   id="part-time"
                   name="employment"
                   value="part-time"
                   checked={formData.employment === "part-time"}
                   onChange={handleChange}
               />
               <label htmlFor="part-time">Part-time</label>
               <br />
              
               <input
                   type="radio"
                   id="full-time"
                   name="employment"
                   value="full-time"
                   checked={formData.employment === "full-time"}
                   onChange={handleChange}
               />
               <label htmlFor="full-time">Full-time</label>
               <br />
           </fieldset>
           <br />
          
           <label htmlFor="favColor">What is your favorite color?</label>
           <br />
           <select
               id="favColor"
               value={formData.favColor}
               onChange={handleChange}
               name="favColor"
           >
               <option value="red">Red</option>
               <option value="orange">Orange</option>
               <option value="yellow">Yellow</option>
               <option value="green">Green</option>
               <option value="blue">Blue</option>
               <option value="indigo">Indigo</option>
               <option value="violet">Violet</option>
           </select>
           <br />
           <br />
           <button>Submit</button>
       </form>
   )
}
 
```

## Quiz;

1. In a vanilla JS app, at what point in the form submission
   process do you gather all the data from the filled-out form?
Right before the form is submitted.


2. In a React app, when do you gather all the data from
   the filled-out form?
As the form is being filled out. The data is all held in local state.


3. Which attribute in the form elements (value, name, onChange, etc.)
   should match the property name being held in state for that input?
`name` property.


4. What's different about saving the data from a checkbox element
   vs. other form elements?
A checkbox uses the `checked` property to determine what should
be saved in state. Other form elements use the `value` property instead.


5. How do you watch for a form submit? How can you trigger
   a form submit?
- Can watch for the submit with an onSubmit handler on the `form` element.
- Can trigger the form submit with a button click.


 ### Another Form Challenge 

 ```
import React from "react"
 
export default function App() {
   const [formData, setFormData] = React.useState({
       email: "",
       password: "",
       passwordConfirm: "",
       joinedNewsletter: true
   })
  
   /**
    * Challenge: Connect the form to local state
    *
    * 1. Create a state object to store the 4 values we need to save.
    * 2. Create a single handleChange function that can
    *    manage the state of all the inputs and set it up
    *    correctly
    * 3. When the user clicks "Sign up", check if the
    *    password & confirmation match each other. If
    *    so, log "Successfully signed up" to the console.
    *    If not, log "passwords do not match" to the console.
    * 4. Also when submitting the form, if the person checked
    *    the "newsletter" checkbox, log "Thanks for signing
    *    up for our newsletter!" to the console.
    */
  
   function handleChange(event) {
       const {name, value, type, checked} = event.target
       setFormData(prevFormData => ({
           ...prevFormData,
           [name]: type === "checkbox" ? checked : value
       }))
   }
  
   function handleSubmit(event) {
       event.preventDefault()
       if(formData.password === formData.passwordConfirm) {
           console.log("Successfully signed up")
       } else {
           console.log("Passwords do not match")
           return
       }
      
       if(formData.joinedNewsletter) {
           console.log("Thanks for signing up for our newsletter!")
       }
   }
  
   return (
       <div className="form-container">
           <form className="form" onSubmit={handleSubmit}>
               <input
                   type="email"
                   placeholder="Email address"
                   className="form--input"
                   name="email"
                   onChange={handleChange}
                   value={formData.email}
               />
               <input
                   type="password"
                   placeholder="Password"
                   className="form--input"
                   name="password"
                   onChange={handleChange}
                   value={formData.password}
               />
               <input
                   type="password"
                   placeholder="Confirm password"
                   className="form--input"
                   name="passwordConfirm"
                   onChange={handleChange}
                   value={formData.passwordConfirm}
               />
              
               <div className="form--marketing">
                   <input
                       id="okayToEmail"
                       type="checkbox"
                       name="joinedNewsletter"
                       onChange={handleChange}
                       checked={formData.joinedNewsletter}
                   />
                   <label htmlFor="okayToEmail">I want to join the newsletter</label>
               </div>
               <button
                   className="form--submit"
               >
                   Sign up
               </button>
           </form>
       </div>
   )
}
 

```
### Mistake I did on the input field I used name="top-text" which needs to be write name="topText" which I did not write same as define in the state. 


```
import React from "react"
import memesData from "../memesData.js"

export default function Meme() {
    /**
     * Challenge: 
     * 1. Set up the text inputs to save to
     *    the `topText` and `bottomText` state variables.
     * 2. Replace the hard-coded text on the image with
     *    the text being saved to state.
     */
    
    const [meme, setMeme] = React.useState({
        topText: "",
        bottomText: "",
        randomImage: "http://i.imgflip.com/1bij.jpg" 
    })
    const [allMemeImages, setAllMemeImages] = React.useState(memesData)
    
    
    function getMemeImage() {
        const memesArray = allMemeImages.data.memes
        const randomNumber = Math.floor(Math.random() * memesArray.length)
        const url = memesArray[randomNumber].url
        setMeme(prevMeme => ({
            ...prevMeme,
            randomImage: url
        }))
        
    }
    
    
    
     function handleChange(event) {
        const {name, value} = event.target
        setMeme(prevMeme => ({
            ...prevMeme,
            [name]: value
        }))
    }
    
    console.log(meme)
    
    
    return (
        <main>
            <div className="form">
                <input 
                    type="text"
                    placeholder="Top text"
                    className="form--input"
                    name="topText"
                    value={meme.topText}
                    onChange={handleChange}
                />
                <input 
                    type="text"
                    placeholder="Bottom text"
                    className="form--input"
                    name="bottomText"
                    value={meme.bottomText}
                    onChange={handleChange}
                />
                
                <button 
                    className="form--button"
                    onClick={getMemeImage}
                >
                    Get a new meme image 🖼
                </button>
            </div>
            <div className="meme">
                <img src={meme.randomImage} className="meme--image" />
                <h2 className="meme--text top">{meme.topText}</h2>
                <h2 className="meme--text bottom">{meme.bottomText}</h2>
            </div>
        </main>
    )
}
```

   
    
### Quiz about useEffect function

1. What is a "side effect" in React? What are some examples?
- Any code that affects an outside system.
- local storage, API, websockets, two states to keep in sync


2. What is NOT a "side effect" in React? Examples?
- Anything that React is in charge of.
- Maintaining state, keeping the UI in sync with the data, 
  render DOM elements


3. When does React run your useEffect function? When does it NOT run
   the effect function?
- As soon as the component loads (first render)
- On every re-render of the component (assuming no dependencies array)
- Will NOT run the effect when the values of the dependencies in the
  array stay the same between renders


4. How would you explain what the "dependecies array" is?
- Second paramter to the useEffect function
- A way for React to know whether it should re-run the effect function

### useEffect example starwars api.

```
import React from "react"

export default function App() {
    const [starWarsData, setStarWarsData] = React.useState({})
    const [count, setCount] = React.useState(1)
    
    /**
     * Challenge: Combine `count` with the request URL
     * so pressing the "Get Next Character" button will
     * get a new character from the Star Wars API.
     * Remember: don't forget to consider the dependencies
     * array!
     */
    
    React.useEffect(function() {
        console.log("Effect ran")
        fetch(`https://swapi.dev/api/people/${count}`)
            .then(res => res.json())
            .then(data => setStarWarsData(data))
    }, [count])
    
    return (
        <div>
            <h2>The count is {count}</h2>
            <button onClick={() => setCount(prevCount => prevCount + 1)}>Get Next Character</button>
            <pre>{JSON.stringify(starWarsData, null, 2)}</pre>
        </div>
    )
}

```

### useEffect example as soon the window width increasing at the run time it showing in h1 tag.

```
import React from "react"

export default function WindowTracker() {
    /**
     * Challenge:
     * 1. Create state called `windowWidth`, default to 
     *    `window.innerWidth`
     * 2. When the window width changes, update the state
     * 3. Display the window width in the h1 so it updates
     *    every time it changes
     */
    
    const [windowWidth, setWindowWidth] = React.useState(window.innerWidth)
    
    React.useEffect(() => {
        window.addEventListener("resize", function() {
            setWindowWidth(window.innerWidth)
        })
    }, [])
    
    return (
        <h1>Window width: {windowWidth}</h1>
    )
}
```

### useEffect cleaning the function after leaking the memory. 


```
import React from "react"

export default function WindowTracker() {
    
    const [windowWidth, setWindowWidth] = React.useState(window.innerWidth)
    
    React.useEffect(() => {
        function watchWidth() {
            console.log("Setting up...")
            setWindowWidth(window.innerWidth)
        }
        
        window.addEventListener("resize", watchWidth)
        
        return function() {
            console.log("Cleaning up...")
            window.removeEventListener("resize", watchWidth)
        }
    }, [])
    
    return (
        <h1>Window width: {windowWidth}</h1>
    )
}

```

### useEffect 

 useEffect takes a function as its parameter. If that function
   returns something, it needs to be a cleanup function. Otherwise,
   it should return nothing. If we make it an async function, it
   automatically retuns a promise instead of a function or nothing.
   Therefore, if you want to use async operations inside of useEffect,
   you need to define the function separately inside of the callback
   function,

# Window.localStorage

The localStorage read-only property of the window interface allows you to access a Storage object for the Document's origin; the stored data is saved across browser sessions.
localStorage is similar to sessionStorage, except that while localStorage data has no expiration time, sessionStorage data gets cleared when the page session ends — that is, when the page is closed. (localStorage data for a document loaded in a "private browsing" or "incognito" session is cleared when the last "private" tab is closed.) https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage
# Example
```
export default function App() {
    /**
     * Challenge:
     * 1. Every time the `notes` array changes, save it 
     *    in localStorage. You'll need to use JSON.stringify()
     *    to turn the array into a string to save in localStorage.
     * 2. When the app first loads, initialize the notes state
     *    with the notes saved in localStorage. You'll need to
     *    use JSON.parse() to turn the stringified array back
     *    into a real JS array.
     */
    
    const [notes, setNotes] = React.useState(
        JSON.parse(localStorage.getItem("notes")) || []
    )
    const [currentNoteId, setCurrentNoteId] = React.useState(
        (notes[0] && notes[0].id) || ""
    )
    
    React.useEffect(() => {
        localStorage.setItem("notes", JSON.stringify(notes))
    }, [notes])
   ```
# Split Method

 The split() method splits a string into an array of substrings.

The split() method returns the new array.

The split() method does not change the original string.

If (" ") is used as separator, the string is split between words.

```
<script>
let text = "How are you doing today?";
const myArray = text.split(" ");

document.getElementById("demo").innerHTML = myArray[2]; 
</script>

```

### Async Await
Now by using this async keyword within our async function, we're now suddenly allowed to use the await keyword. And what await does is it pauses the function's execution until what is being awaited is completed and comes back with a value.

![image](https://user-images.githubusercontent.com/11480617/208422801-0aba8565-ac7a-4051-9f7f-f6ae37fe99f0.png)

![image](https://user-images.githubusercontent.com/11480617/208424491-61f07df0-2ecd-45be-89db-e112bfb1f29a.png)

### Find()
find is a great way for us when we're let's say we have an array of objects, right? And we want to find a specific object based on some condition. Right. You can imagine if we had, let's say, people array where we had an array of objects where the ID was one.
![image](https://user-images.githubusercontent.com/11480617/208425299-f0f7acd1-7932-42f4-9303-3794783a22d0.png)



# Unshift method
The unshift() method adds new elements to the beginning of an array.
The unshift() method overwrites the original array.

```
<script>
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.unshift("Lemon", "Pineapple");

document.getElementById("demo").innerHTML = fruits;
</script>
```
### Reduce Method
Reduce is a great array method to use when we want to do two things. The first is that we want to end up with one value in the end. Right? Not an array but some value in the end. The second is when we want to persist the return or the outcome of iterating over our elements in each subsequent iteration.
![image](https://user-images.githubusercontent.com/11480617/208473069-136e2246-803f-4ede-97e3-dd7c208054fe.png)

### Memoization Caching
Caching is a way to store values so you can use them later on. Ideally, you can think of caching as a backpack they take to school. Instead of going all the way home. When you need something like a pencil, you have a small box on your back that holds items that you need so that when you go to school, you can just reuse them fast over and over. Now that's a bit of a silly example. Caching is just a way for us to speed up programs and hold some piece of data in an easily accessible box. And memorization is a specific form of caching that we're going to be talking about, because we use it a lot in dynmaic programming.
So remember, this memorization is simply a way to remember a solution to a problem. So you don't have to calculate it again.
![image](https://user-images.githubusercontent.com/11480617/208476916-579d2a25-f931-49c1-b46c-8795d6308128.png)


# Random number Generate 
```
import React from "react"
import Die from "./Die"

/**
 * Challenge:
 * 
 * Create state to hold our array of numbers. (Initialize
 * the state by calling our `allNewDice` function so it 
 * loads all new dice as soon as the app loads)
 * 
 * Map over the state numbers array to generate our array
 * of Die elements and render those in place of our
 * manually-written 10 Die elements.
 */

export default function App() {
    const [dice, setDice] = React.useState(allNewDice())
    
    function allNewDice() {
        const newDice = []
        for (let i = 0; i < 10; i++) {
            newDice.push(Math.ceil(Math.random() * 6))
        }
        return newDice
    }
    
    const diceElements = dice.map(die => <Die value={die} />)
    
    return (
        <main>
            <div className="dice-container">
                {diceElements}
            </div>
        </main>
    )
}
```

# Every Method

The every() method executes a function for each array element.
The every() method returns true if the function returns true for all elements.
The every() method returns false if the function returns false for one element.
The every() method does not execute the function for empty elements.
The every() method does not change the original array

# Host for free using Surge

```
 surge
 npm run build
 cd build
 cp index.html 200.html
 surge
 ```
# Searching Challenge
Have the function SearchingChallenge(str) take the str parameter being passed and return 1 if the brackets are correctly matched and each one is accounted for. Otherwise return 0. For example: if str is "(hello (world))", then the output should be 1, but if str is "((hello (world))" the the output should be 0 because the brackets do not correctly match up. Only "(" and ")" will be used as brackets. If str contains no brackets return 1.

# Palindrome challange 
Have the function PalindromeTwo(str) take the str parameter being passed and return the string true if the parameter is a palindrome, (the string is the same forward as it is backward) otherwise return the string false. The parameter entered may have punctuation and symbols but they should not affect whether the string is in fact a palindrome.

# Array challange 1
Have the function ArrayChallenge(arr) take the array of integers stored in arr, and find the four largest elements and return their sum. For example: if arr is [4, 5, -2, 3, 1, 2, 6, 6] then the four largest elements in this array are 6, 6, 4, and 5 and the total sum of these numbers is 21, so your program should return 21. If there are less than four numbers in the array your program should return the sum of all the numbers in the array.
# Array challange 2
Have the function ArrayChallenge(arr) take the array of numbers stored in arr which will contain 5 positive integers, the first two representing a range of numbers (a to b), the next 2 also representing another range of integers (c to d), and a final 5th element (x) which will also be a positive integer, and return the string true if both sets of ranges overlap by at least x numbers. For example: if arr is [4, 10, 2, 6, 3] then your program should return the string true. The first range of numbers are 4, 5, 6, 7, 8, 9, 10 and the second range of numbers are 2, 3, 4, 5, 6. The last element in the array is 3, and there are 3 numbers that overlap between both ranges: 4, 5, and 6. If both ranges do not overlap by at least x numbers, then your program should return the string false.

### Shift() method
The shift() method removes the first element of an array (and "shifts" the other elements to the left):
Banana,Orange,Apple,Mango
Orange,Apple,Mango

# HOC in React
A component that takes a component as an input and return that component as an output with own logic execution. 

# Closure in Javascript 
A closure is a function having access to the parent scope it preserve the data from outside. A closure is a inner function that has access to the outer enclsing function's variable. A function that remember it's enviroment like define variable etc. A closure function may have more function within it the function will remember vairables outside of the function. For every closure we have three scope. 
1. Local scope (own scope): example a variable outside of the function can be access. 
2. Outer functions scope.
3. Global scope. 
function=>function(can access parent and outer function variables).
parent function cannot access inner function variables.

# useRef()
useRef allows us to get direct access to a JSX element.For example, if we wanted to write some code that focuses a search input when the users use the key combination Control + K.
```
import { useWindowEvent } from "@mantine/hooks";
import { useRef } from "react";

function Header() {
	const inputRef = useRef();

  useWindowEvent("keydown", (event) => {
    if (event.code === "KeyK" && event.ctrlKey) {
      event.preventDefault();
      inputRef.current.focus();
    }
  });
  
  return <input ref={inputRef} />
}
```
# useCallback() 
useCallback will return a memoized version of the callback that only changes if one of the dependencies has changed. This is useful when passing callbacks to optimized child components that rely on reference equality to prevent unnecessary renders (e.g. shouldComponentUpdate ).
Problem: passing props or (functions) from parents to child component every time the main component render the child component render unnecessary because the child component props methods called why they think we got new updates but did not. 
Example: 
```
const Todo = useCallback(() => {
console.log("Now it won't do unnecssary re-render")
}, [dependency])
```
# useMemo()
when we useMemo basically it memorize the child component to stop it from rerending everytime if there is change on props element then it ll rerender otherwise it won't rerender.
# Difference Between useMemo And useCallback
It's primarily for when you have expensive functions that need to re compute and they depend on these
values inside of your functional component. If you want to memorize those values and make sure that they don't get interrupted or they don't get rerun unnecessarily during a re render cycle, then you use the use memo hook. So that's the difference between use memo and use callback. Use callback memorizes the function itself.Use memo. Memo is the return value of the function.
# useReducer() 
The useReducer() hook in React lets you separate the state management from the rendering logic of the component. useReducer also lets you optimize performance for components that trigger deep updates because you can pass dispatch down instead of callbacks.
1. useReducer is a hook that used for state management.
2. useReducer is an alternative to useState.
3. useReducer hook accepts 2 paramater useReducer(reducer,initialState)
4. ruducer funtion also accepts 2 paramter (currentState, action)
Detail Reading: https://dmitripavlutin.com/react-usereducer/#:~:text=4.-,Conclusion,function%20and%20the%20initial%20state.
Store: Globalized state
Action: Increment press the button will add one (how to change state object).
Reducer(function that manages changes to an object): The action is gonna be called the reducer will check which action you did based on that action it’s gonna modify our store. Or using a reducer to manage our state  Function that manages changes to an object. 
  Argument #1: object that has all of our state in it.
Argument #2: object that describes the update we want to make (update state).
Two technicalities (1) we never change argument #1 directly. (2) we must always return a value to be used as argument  #1. 2nd argument would be an object that describes exactly how we are supposed to change that state. 
Why do we use a reducer because some pieces of state are extremely related.
- CombineReducers: This is a reducer where all other reducer put together in the root reducer which produce the store available to the entire application. 

# useReducer with useContext
useRducer local state management. 
Global state management: Share state between components => useContext + useRedcuer
Import reducer file and create context example here:
Import { createContext, useReducer  } from ‘react’;
Import whatever reducer file has been made import that:
Import AppReducer from ‘reducerfolder’;
Make an object for the values like: 
Const initialState = []
Making context hook:
export const contextName = createContext(initialState);
Initializing reducer: first argument should be reducer file which has been imported, second argument must be initial state.
	Let [state, dispatch] = useReducer(AppReducer, initialState);
Now making Provider component : 
Export const ProviderName = ({}) => {
Let [state, dispatch] = useReducer(AppReducer, initialState);
}
Make action then create <GlobalContext.Provider> </GlobalContext.Provider>


### Redux

- Pure Function: And in turn they return you back some object that represents the values in the state. This store is just in order to facilitate the movement and passing of actions through these reducers.
- Middle Wears: In order to do that, we actually need to create this thing called middle wears. Middle wears our kind of like little library helpers that run before an action hits the reducer. So whenever you dispatch an action before that action hits the reducers, it hits the middleware first.
***React 18 ****

```
import React from "react";
import ReactDOM from "react-dom/client";
import "./index.css";
import App from "./App";
import reportWebVitals from "./reportWebVitals";

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);

reportWebVitals();

```

# Typescript Notes

### Now, what would be the reasons for adding static typing to JavaScript?

I can list at least three:

1. You can avoid masterfully-hidden-ninja errors like the classic 'undefined' is not a function. 
2. It is easier to refactor code without breaking it significantly.
3. Orienting oneself in complex, large-scale systems is not a nightmare anymore.
Actually, a study shows that 15% of all JavaScript bugs can be detected by TypeScript.

1. Validate your code is to working correctly.
2. Client and server side development.
3. Writing types is optinal.
4. Transcompiles to javascript.
5. Browser can't compile trypescript. 
Pros of Typescript:
 - Less error
 - Cleaner
 - More readable
 - No need for psodoucode
 - Client and server side
 - Optinal

#### Progressive Web App

![image](https://user-images.githubusercontent.com/11480617/206696506-283f1e77-bde9-4ca9-ae65-7e9bae5b164f.png)


## Testing in React 

![image](https://user-images.githubusercontent.com/11480617/206752753-c64786c3-b41c-481c-b3d0-30c74503c13f.png)

***Unit Tests*** Unit tests, as the name suggests, tests, individual functions or classes. So if I had a some function, I'm going to just test that one function to make sure that it does what
it says it does. Maybe if it accepts parameter A and B, I want to make sure that A and B get added with that function. They are the cheapest to implement, the easiest to implement. And 90% of your time, you're going to be working on writing unit tests. Unit tests should cover all small, pure functions of an application. You may have heard that small pure functions that take an input and return an output.
***Integration Tests:*** The second one is something called integration tests. This is testing how different pieces of code work together. So it can be testing of whether the database works with the Express app that's requesting some data from the database. Or it could be how a function works with another function and how this connection between them works and testing that. Integration tests are all about cross communication between different units of code. Comparing to unit tests, you would probably use something like spies from a marking library to ensure expected side effects instead of just asserting an output. Or you might use stubs to mock and modify parts of a process that are not inside of the specific test. Such as mocking a database call. We can say run in a test to a function that says Get user to mock the database, call and just fake it and return, let's say a fake user just for the test. Overall though, think of integration tasks as connecting components to see how they work together instead of individual small units that unit tests test. Well, you test the connection between them.
The downside with to them is that they are expensive. They're slower. There's more deaf time involved in thinking them out and writing them compared to unit tests which are much faster to run.
***Automated Test***: Automation tests, like I said before, are UI tests that are always running inside a browser or a browser like environment. Because they need to simulate user behavior in these environments such as clicking, typing, scrolling. And finally they need to make sure that these scenarios actually work from the point of view of an end
- [Jest CheatSheet](https://github.com/sapegin/jest-cheat-sheet')


### Enzyme
- ***Shallow***: So what does shallow do? Simply by running this syntax, we're saying, Hey, shallow, render this card component and shallow rendering is useful because it just renders the card component. If the cart component for some reason, let's say, had another component inside of it, that is the hello component. Well, it's not going to render that as well. It's just going to shallowly render just this component. And it's useful because it constrains yourself to testing one component at a time, one unit. As you might remember, a unit test is something that just tests one unit at a time, one small piece at a time.
- [Enzyme Documenation](https://enzymejs.github.io/enzyme/docs/api/')
***SnapShot Testing***: Wouldn't it be great if we can just take a snapshot of whatever this card component renders at any time  while we're writing our card component, anything changes and the component doesn't look as we expected it to as the snapshot that we took a picture of. Well, if it looks any different, then we fail the tests. That's what snapshot testing is.

### GraphQl

- Edges: QraphQl edges will be the array of the number of files that we have inside of our images folder.
- Node: Now, inside of every edge will be a node, and that node is the representation of what that file is.
# Interview asked questions
- [React Interview Questions](https://github.com/sudheerj/reactjs-interview-questions')
1. controlled component vs uncontrolled componenet?: ** 
In a controlled component, form data is handled by a React component. The alternative is uncontrolled components, where form data is handled by the DOM itself. To write an uncontrolled component, instead of writing an event handler for every state update, you can use a ref to get form values from the DOM.**
2. **call by value and call by refernce?:***  
3. compiler vs interpreter?
4. static vs const difference? 
5. what is super()?
6. mvc vs mvvm?
7. strict mode
8. what is typeof?
9. what is doctype in html? 
10. do while vs while loop?
11. what methodologies you have used? 
12. can I pass the function in the state declaration
13. anonymous function?
14. strutered langague vs OOP.
15. Why use key in react: Key is used to identify react each component. 
16. Difference between private,static, protected and public?
17. what is lazy loading?
18. ***Undefined vs null***: undefined is a variable that refers to something that doesn't exist, and the variable isn't defined to be anything. null is a variable that is defined but is missing a value. example undefiend let a; console.log(a). null: let b = null console.log(b)
19. **absolute vs relative url**: An absolute URL contains all the information necessary to locate a resource. A relative URL locates a resource using an absolute URL as a starting point. In effect, the "complete URL" of the target is specified by concatenating the absolute and relative URLs.
20. **why and advantage of typescript lanaguage?**: TypeScript is a superset of typed JavaScript (optional) that can help build and manage large-scale JavaScript projects. It can be considered JavaScript with additional features like strong static typing, compilation, and object-oriented programming. TypeScript, as you may have guessed from the name, is a superset of JavaScript that introduces optional types (amongst other features) to JavaScript’s functionality, providing improved reliability by lowering the chance of bugs. Even better: Angular 2 itself is actually written in TypeScript. 
21. **Difference between responsive design and adoptive design?**: A responsive design can change its layout and appearance based on the screen size of the device it’s accessed on, from a large desktop computer to a small mobile phone.
An adaptive design requires the creation of a different layout for each device the website will be accessed on.
Responsive design often takes less work for a UX designer to create, but they will have to work with the developer to ensure the layout of the site is usable at each possible screen size.
Adaptive design requires a UX designer to create up to six different versions of a single website for different-sized screens. While this is a lot of work, it enables the UX designer to optimize the user experience for every device these layouts cover.
Responsive design often works best for bigger sites that are being designed from scratch.
Adaptive design often works best for smaller sites that are being refreshed.
22. **Difference between even.target and current target?**: Target is the element that triggered the event (e.g., the user clicked on)
currentTarget is the element that the event listener is attached to.
23. **Difference between POST & GET**: Differentiate between GET and POST.
Both GET and POST method is used to transfer data from client to server in HTTP protocol but Main difference between POST and GET method is that GET carries request parameter appended in URL string while POST carries request parameter in message body which makes it more secure way of transferring data from client to server.
***Promises***: Well, a promise is kind of exactly as what it's named. It is a promise that this object will eventually have a value. It will either be a resolved value or a rejected value. The resolve value we use when our API call, for example, is successful. Our reject call we use when our API call gives us an error. But the promise will be in a state where it's pending until either the resolve or the reject has been called.
- [Promise well explaind](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise')
- ***Filter()***: const myArray = [2,3, 5, 6 , 8]; myArray.filter(el => el > 4) // Result [5, 6, 8]
- ***Include()***: The other array methods that we've covered so far includes is essentially a method that takes a single argument, and that argument will be any element that we want. And what it does is it checks inside the array to see if the element that we passed it exists in our array.

24. **What is callback function**
This function is anynomus no name. 
Callbacks are generally used when the function needs to perform events before the callback is executed, or when the function does not (or cannot) have meaningful return values to act on, as is the case for Asynchronous JavaScript (based on timers) or XMLHttpRequest requests.
24. ***What is Portal***: Portals provide a first-class way to render children into a DOM node that exists outside the DOM hierarchy of the parent component. ReactDOM. createPortal(child, container) The first argument ( child ) is any renderable React child, such as an element, string, or fragment.
25. ***UseRef***: ref is use to access dom element or to manipulate the dom, useRef can also be used if there's only needs to read a data in this case useRef is good option instead of useState.
26. ***Pure and Impure***: Pure functions return the same output if we use the same input parameters. However, impure functions give different outcomes when we pass the same arguments multiple times. 
27. ***Side Effect***: A side effect is when a function creates some kind of effect outside of it's scope. and the scope is whatever is inside of the function. The outside variable can be accessible in the inside scope, and it is also accessible outside of the funciton. if a variable is declared outside of the function and we change it inside the function it's called Side Effect.  

# TypeScript 
 #### JavaScript Types....
 Primitives:
 - Boolean : typeof instance === "boolean"
 - Number : typeof instance === "number"
 - String : typeof instance === "string"
 - BigInt : typeof instance === "bigint"
 - Symbol : typeof instance === "symbol"
 - undefined : typeof instance === "undefined"

Structural Types:
 - Object : typeof instance === "object"
 - Function : typeof instance === "function"
 - Structural Root Primitive:
 - null : typeof instance === "object"
**** All Types
1. Boolean type
2. Number type
3. String type
4. Objet type:
5. Array type: stayted: string[] array only inculded strings. 
6. Enum type: In simple words, enums allow us to declare a set of named constants i.e. a collection of related values that can be numeric or string values. There are three types of enums:
		- Numeric enum
		- String enum
		- Heterogeneous enum. 
7. Any type
8. Union type
9. Literal type: In addition to the general types string and number, we can refer to specific strings and numbers in type positions. whatever the value has been assigned it ll be the same value in the varible can't assign another value to it. type Price = 45 | 30 | 25 set of values in the object will have price: Price
10. Function type: Typescript has many ways to describe how funtions can be called. Let's learn about how to write types that describe functions. 
11. Unknown type
12. Never type
13. Void type: In typescript there is also undefined in the function so you have return undefined as well instead of undefine we can write void.
14. Custom type: ``` const ADMIN = 'admin'
const READ_ONLY = 'read-only'


enum Permissions {
    ADMIN,
    READ_ONLY
}

const you = {
    firstName: 'Bobby',
    lastName: 'Brown',
    permissions: Permissions.ADMIN,
    isReturning: true,
    age: 35,
    stayedAt: ['florida-home', 'oman-flat', 'tokyo-bungalow']
} ```
14. Tuples type: Allow you to express an array with a fixed number of elements whose types are known. example [string, string, number] values must ['hi','bye',6] we know here ar 2 strings and one integer.
15. Array of objects:  which means in [ {list of item syntex would like like this.}]

```
        name: 'Sheia',
        stars: 5,
        loyaltyUser: true,
        date: '01-04-2021'
    },
    {
        name: 'Andrzej',
        stars: 3,
        loyaltyUser: false,
        date: '28-03-2021'
    },
    {
        name: 'Omar',
        stars: 4,
        loyaltyUser: true,
        date: '27-03-2021'
    },
]

```

```

const you: {  // object type syntex
    firstName: string;
    lastName: string;
    isReturning: boolean;
    age: number;
    stayedAt: string[]; // array in object only include strings
    // what if we have number in below object? the stayedt would be 
    //stayedAt: (string[] | number[]) now string and number both included
} = {
    firstName: 'Bobby',
    lastName: 'Brown',
    isReturning: true,
    age: 35,
    stayedAt: ['florida-home', 'oman-flat', 'tokyo-bungalow', 23]
}

```

Component with interface 

```
interface ChildProps {
color: string
}
export const ChildAsFC: React.FC<ChildProps> = ({color}) => {
    
}
```

we can add other type of values in interface definition

```

interface ChildProps {
color: string;
onClick: () => void;
}
//use useRef() with typescript
const inputRef = useRef<HTMLInputElement | null>(null);

```



### React Routes 
- Outlet: It ll show on each page on top of every component for example for the Navbar.



### Firebase
 - Answers 1 : of What is the equivalent of a collection and a document of firebase in sql
 - A Firestore collection is roughly anycodings_sql equivalent to a SQL table.
 - A Firestore document is roughly anycodings_sql equivalent to a SQL row.
 - Nested subcollections in Firestore don't anycodings_sql have a direct SQL equivalent. You would  anycodings_sql just use another table for that. Since anycodings_sql tables can't be "nested" in  SQL, it has anycodings_sql to exist at the top level along with all anycodings_sql the others.


### The coding interview bootcamp

```
// Fibnachi series

function fib(n) {
if(n<2){
return n;
} 
return fib(n-1) + fib(n-2);}

```

# Additinal links for the interview js,react,typescript,css,html
1. [CSS ](https://www.simplilearn.com/tutorials/css-tutorial/css-interview-questions)
2. [CSS top questions ](https://www.interviewbit.com/css-interview-questions/)
3. [JavaScript questions](https://www.fullstack.cafe/blog/advanced-javascript-interview-questions)

# Resume samples
1. [DevOps resume](https://www.hireitpeople.com/resume-database/67-quality-assurance-qa-resumes/229157-jr-devops-engineer-intern-resume-lewis-center-oh)
2. [DevOps resume 2](https://www.livecareer.com/resume-search/r/devops-intern-dfe8cd098100442fb7b0057599b6b0fa)
3. [DevOps Course and Interview Questions](https://www.simplilearn.com/tutorials/devops-tutorial')
4. [DevOps Interview](https://www.edureka.co/blog/interview-questions/top-devops-interview-questions/')
