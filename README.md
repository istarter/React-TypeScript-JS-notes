
# React-TypeScript-JS-notes

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

