# JavaScriptCheatsheet

Useful: 	
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/
* https://www.w3schools.com/js/tryit.asp?filename=tryjs_editor
* https://apps.apple.com/us/app/flycut-clipboard-manager/id442160987?mt=12
* https://marketplace.visualstudio.com/items?itemName=usernamehw.errorlens
* https://threejs-journey.com/?gclid=Cj0KCQjw_4-SBhCgARIsAAlegrWT9w-Ixx7ahdxy1rk7cjUIBBwsJdzfO46_D8eGITnr1_5HNhEuSZAaAleqEALw_wcB
* https://docs.google.com/presentation/d/1CtxiAG9mJ6kslSl6psBBlVDafFD4b2Rh2G7ft1GQ08o/edit?pli=1#slide=id.g10df88dd1ed_4_546
 

Contents:
- [Variables](#variables)
    + [Definition](#definition)
    + [Operations](#operations)
- [Alerts & Prompts](#alerts--prompts)
- [Conditional and logical operations](#conditional-and-logical-operations)
	+ [Operators](#operators)
	+ [Special Rules and Conversion](#special-rules-and-conversion)
- [Arrays](#arrays)
- [Loops](#loops)
    + [while](#while)
    + [forEach](#forEach)
	+ [do while](#do-while)
	+ [for](#for)
- [Dates](#dates)
- [Objects](#objects)
- [Functions](#functions)
- [Selectors](#selectors)
- [Events](#events)
- [Callbacks](#callbacks)
	+ [Definition](#definition)
	+ [Callback checklist](#callback-checklist)
		* [Array.sort](#arraysort)
		* [Array.filter](#arrayfilter)
		* [Array.map](#arraymap)
		* [Array.reduce](#arrayreduce)
		* [setTimeout  / setInterval](#settimeout---setinterval)
		* [Map-Reduce](#map-reduce)
		* [JSX functional component: createElement(ACB,props)](#jsx-functional-component-createelementacbprops)
		* [onEvent={ACB} addEventListener(event, ACB)](#oneventacb-addeventlistenerevent-acb)
		* [customEvent={ACB}](#customeventacb)
		* [fetch(..).then(ACB)....catch(EACB)](#fetchthenacbcatcheacb)
		* [customEvent={ACB}](#customevent--acb-)
		* [addObserver(ACB)](#addobserveracb)
- [Custom components](#custom-components)
- [Inline Javascript](#inline-javascript)
- [Create Random ID](#create-random-id)
- [Print Page](#print-page)
- [Web APIs](#web-apis)
	+ [Synchronous Web API access](#synchronous-web-api-access)
	+ [Asynchronous Web API access](#asynchronous-web-api-access)
	+ [The Callback Pyramid of Doom](#the-callback-pyramid-of-doom)
	+ [Promises](#promises)
	+ [Passing parameters to APIs](#passing-parameters-to-apis)
	+ [Promise state](#promise-state)
- [Component state](#component-state)
  * [Why do we use it?](#why-do-we-use-it)
  * [Advantages](#advantages)
  * [Disadvantages](#disadvantages)
  * [State based update](#state-based-update)
- [Re-rendering](#re-rendering)
	* [Old approach: Incremental update](#old-approach-incremental-update)
	* [New approach: re-render & reconciliation](#new-approach-re-render--reconciliation)
- [Stateless vs Stateful Components](#stateless-vs-stateful-components)
  * [Stateless Components](#stateless-components)
  * [Stateful components](#stateful-components)
- [React Component State](#react-components-state)
  * [React State Hook](#react-state-hook)
    + [General format](#general-format)
    + [Example](#example)
  * [Shallow React](#shallow-react)
- [Top level state react?](#top-level-state-react-)
- [Observers](#observers)
  * [Useful functions](#useful-functions)
  * [Payload](#payload)
  * [Component lifecycle](#component-lifecycle)
    + [Licefycle motivation](#licefycle-motivation)
    + [Lifecycle usage](#lifecycle-usage)
    + [Example use-cases](#example-use-cases)
    + [React lifecycle](#react-lifecycle)
    + [React component state and re-rendering](#react-component-state-and-re-rendering)
    + [React simplification](#react-simplification)
    + [React custom hooks](#react-custom-hooks)







--------------------------------
# Variables

### Definition
```javascript
// Variables
let name = "Ladydiana";
let project = "JavaScriptCheatsheet";
let action = "publish";
let env = "Github";
let repos = 42;		// Number
let age = 17;
let semaphore = true;	// Boolean
let city = "Stockholm";	// String
let destinations = ["Porto", "Lisbon", "Vienna", "Bratislava", "Budapest"]; //Array
let next_travel = {
	country: "Russia",
	city: "Sankt Petersburg",
	transport: "ferry",
	price: 100,
	duration: 5,
	booked: false
};	//Object
let country = "Sweden";
let a = 1;
let b = 2;


```


### Operations
```javascript
// Operations
let place = city + " " + country; //Stockholm Sweden
let c = a + b; 	//3
```

# Alerts & Prompts
```javascript
let firstName = prompt("First name: ");
let lastName = prompt("Last name: ");
let fullName = firstName + " " + lastName;
alert(fullName);
```

# Conditional and logical operations
## Operators
```javascript

if (!firstName.trim()) {
	alert("Please insert a valid first name!");
}
else {  if (!lastName.trim()) {
			alert("Please insert a valid last name!");
		}
		else {
				alert("Something went wrong, please try again!");
		}
}

if (age < 18 || (age <21 && country === "USA"))  {
  alert("You cannot drink here!");
  
//condition ? ifTrue : ifFalse     is a complete if/else replacement
1+(42?9:0)  // 10
42?(""?false:3.1415):0  // 3.1415

}

```

## Special Rules and Conversion

===    !==     	do not convert               1==="1"    → false

==     !=       attempt conversion           1== "1"    → true

For many other operations it’s harder to escape conversion!

1+true → 2

1+"2"  → "12"

1+Number.parseInt("2")    →   3


# Arrays
```javascript

let fruits = ['Apple', 'Banana']
console.log(fruits.length) //2

let first = fruits[0] // Apple
let last = fruits[fruits.length - 1] // Banana

// Loop over an Array
fruits.forEach(function(item, index, array) {
  console.log(item, index)
}) // Apple 0 // Banana 1

// Add a item to the end of the array
fruits.push('Orange'); // ["Apple", "Banana", "Orange"];
console.log(fruits); // (3) ['Apple', 'Banana', 'Orange']

// Remove an item from the end of an Array
let last = fruits.pop();
console.log(fruits) // (2) ['Apple', 'Banana']
console.log(last) // Orange

// Add an item to the beginning of an Array
fruits.unshift('Strawberry') // add to the front

// Remove an item from the beginning of an Array
let first = fruits.shift();

// Find the index of an item in the Array
let pos = fruits.indexOf('Strawberry') // -1
console.log(pos);

pos = fruits.indexOf('Banana') // 1
console.log(pos);

// Remove an item by index position
fruits.splice(pos, 1);

// Remove items from an index position
let vegetables = ['Cabbage', 'Turnip', 'Radish', 'Carrot']

let pos = 1
let n = 2

let removedItems = vegetables.splice(pos, n)
// this is how to remove items, n defines the number of items to be removed,
// starting at the index position specified by pos and progressing toward the end of array.

console.log(vegetables) // (2) ['Cabbage', 'Carrot'] (the original array is changed)
console.log(removedItems) // (2) ['Turnip', 'Radish']

// Accessing array elements
console.log(vegetables[0]) // Cabbage
console.log(vegetables[1]) // Carrot

// Array spread
const cars2= [...cars, oneMoreCar ]; 

// Array destructuring     (used with React state)  
const [firstCar, secondCar]= cars;
const [firstCar, ...otherCars]= cars;

function doSth([firstElem, secondElem, ...others])  
// combine array destructuring with object destructuring
function doSth([{ someProp, someOtherProp, ...otherProps}, secondElem, ... others ])

```

# Loops

### While
```javascript
let i = 0;
while (i < 10) {
  console.log(i);
  i = i + 1;
}
```

### forEach
```javascript
fruits.forEach(function(fruit) {
  console.log(fruit)
})
```

### do while
```javascript
i = 0;
do {
  console.log(i);
  i = i + 1;
} while(i < 10)
```

### for
```javascript
for (let i = 0; i < 10; i++) {
  console.log("i is " + i);
}
```

# Dates
```javascript
let now = new Date();
now.getMinutes(); 
now.getHours(); 
now.getDate(); 
now.getDay(); 
now.getMonth(); 
now.getFullYear();

console.log(Date.parse("01 Jan 2025 00:00:00 GMT"));
```

# Objects
```javascript
let o1 = new Object()
let o2 = new Object(undefined)
let o3 = new Object(null)
let o4 = new Object(true) // // equivalent to o = new Boolean(true)

let user = {
  firstName: "John",
  lastName: "Doe",
  age: 31,
  greet: function () {
    alert("Welcome!");
  },
};

alert(user.firstName); // or alert(user["firstName"]);

// Adding a property
user.gender = "male";

let students = [
	{
		firstName: "Jack",
		lastName: "Robinson",
	},
	{
		firstName: "Dorothy",
		lastName: "Williams",
	},
];

// Enumerating
students.forEach(function (student, index) {
	for (let what in student) {
		alert(what + " is " + student[what]);
	}
});
```

# Functions
```javascript
function fullName(firstName, lastName) {
	alert(firstName + " " + lastName);
}

function fullName2(firstName, lastName) {
	return(firstName + " " + lastName);
}

firstName = prompt("What's your first name?");
lastName = prompt("What's your last name?");
fullName1(firstName, lastName);
let getname = fullName2(firstName, lastName);

// Closures
function init() {
  var name = 'Mozilla'; // name is a local variable created by init
  function displayName() { // displayName() is the inner function, a closure
    alert(name); // use variable declared in the parent function
  }
  displayName();
}
init();
```

# Selectors
```javascript
let h2 = document.querySelector("h2"); //Returns the first element (if any) on the page matching the selector.
h2.innerHTML = " JavaScriptCheatsheet ";

let p = document.querySelector("p");
p.innerHTML = "README <br> script_dump.txt"
// Adding a class to the element
p.classList.add("content");

document.getElementById("demo").innerHTML = "This is a demo."; // Returns the element by id
```

# Events
```javascript
// Function to change the content of t2
function modifyText() {
  const t2 = document.getElementById("t2");
  if (t2.firstChild.nodeValue == "three") {
    t2.firstChild.nodeValue = "two";
  } else {
    t2.firstChild.nodeValue = "three";
  }
}

// Add event listener to table
const el = document.getElementById("outside");
el.addEventListener("click", modifyText, false);
```

# Callbacks
## Definition
```javascript
function compareNumbersCB(a,b){   // a callback!
   if(a<b) { return 1; }   
   if(a>b) return -1;   // no need for {} if only one statement
   return 0;            // no need for else after return  
}               
[6,1,5].sort(compareNumbersCB)    // pass the callback!

function compareCarsCB(car1, car2){ return car1.doors-car2.doors; } 
cars.sort(compareCarsCB)
```

## Callback checklist

### Array.sort
| Question 												| Answer |
| -----------------------------------------------------	| ------ |
| How to pass the callback?     						| array.sort(CB) |  
| Other params needed besides the callback? 			| No |
| What does array.sort(CB) return?          			| Same array! Sorted |
| When does array.sort(CB) return?          			| When array is sorted  // this may seem like a stupid question, but there are no stupid questions |
| Who calls the callback, and sends parameters?       	| sort() execution |
| Role (and usual name?) of callback parameters      	| elem1, elem2  for comparison |
| What is the callback expected to return?       		| <0 → keep order,     >0 → reverse,     0 equal |
| When is the callback called?     						| When sort needs a comparison |
| Is the callback called once? Or repeatedly?       	| Zero or more times |
| What is the role of the callback?   					| Comparator |
| Example callback names                 				| compareCarsCB |

### Array.filter
| Question 												| Answer |
| -----------------------------------------------------	| ------ |
| How to pass the callback?     						| array.filter(CB) |  
| Other params needed besides the callback? 			| No |
| What does array.filter(CB) return?          			| New array, with only some elements kept |
| When does array.filter(CB) return?          			| After all array elements are visited |
| Who calls the callback, and sends parameters?       	| filter() |
| Role (and usual name?) of callback parameters      	| element    (optional:  index, array) |
| What is the callback expected to return?       		| true→ keep in returned array,    false→ don’t |
| When is the callback called?     						| Once per element, to decide whether to keep in result |
| Is the callback called once? Or repeatedly?       	| Once per element |
| What is the role of the callback?   					| Tester |
| Example callback names                 				| testCarCB,  hasAtLeastFourDoorsCB |

``` javascript
function hasAtLeastFourDoorsCB(car) { return car.doors > 3; }
```

### Array.map
| Question 												| Answer |
| -----------------------------------------------------	| ------ |
| How to pass the callback?     						| array.map(CB) |  
| Other params needed besides the callback? 			| No |
| What does array.map(CB) return?          			| New array, with all elements transformed by the CB |
| When does array.map(CB) return?          			| After all array elements are visited |
| Who calls the callback, and sends parameters?       	| map() |
| Role (and usual name?) of callback parameters      	| element    (optional:  index, array) |
| What is the callback expected to return?       		| Element in resulting array |
| When is the callback called?     						| Once per element |
| Is the callback called once? Or repeatedly?       	| Once per element |
| What is the role of the callback?   					| Transformer |
| Example callback names                 				| car2TextCB  , car2DoorsCB |

``` javascript
function carToTextCB(car) { return car.make+" "+car.model; }
function carToDoorsCB(car) { return car.doors; }
```

### Array.reduce
| Question 												| Answer |
| -----------------------------------------------------	| ------ |
| How to pass the callback?     						| array.reduce(CB, initialAccumulator)  |  
| Other params needed besides the callback? 			| Yes |
| What does array.reduce(CB) return?          			| Final value of accumulator, after applying CB to all elements|
| When does array.reduce(CB) return?          			| After all array elements are visited |
| Who calls the callback, and sends parameters?       	| reduce() |
| Role (and usual name?) of callback parameters      	| accumulator, element (optional:  index, array) |
| What is the callback expected to return?       		| New accumulator |
| When is the callback called?     						| Once per element |
| Is the callback called once? Or repeatedly?       	| Once per element |
| What is the role of the callback?   					| Reducer |
| Example callback names                 				| sumReducerCB , sumCarDoorsReducerCB |

``` javascript
function sumCarDoorsReducerCB(accumulator, car) { return accumulator + car.doors; }
function sumReducerCB(accumulator, element) { return accumulator + element; }        // general!
```

### setTimeout  / setInterval
!!! asynchronous!
| Question 												| Answer |
| -----------------------------------------------------	| ------ |
| How to pass the callback?     						| setTimeout(ACB, millis) |  
| Other params needed besides the callback? 			| Optional, default zero |
| What does setTimeout(ACB, millis) return?          	| setTimeout(ACB, millis)|
| When does setTimeout(ACB, millis) return?          	| immediately |
| Who calls the callback, and sends parameters?       	| browser timer / node.js timer |
| Role (and usual name?) of callback parameters      	| none |
| What is the callback expected to return?       		| nothing |
| When is the callback called?     						| When millis has passed |
| Is the callback called once? Or repeatedly?       	| Once  (see setInterval for repeated regularly) |
| What is the role of the callback?   					| Do something later  / without disturbing the current execution flow |
| Example callback names                 				| doLaterACB |

```javascript
function doAfter2SecACB(){console.log("2 seconds passed"); }
setTimeout(doAfter2SecACB, 2000);
```
:checkered_flag: **JS functions run to completion.** 

:checkered_flag: **setTimeout(ACB, 0) will execute ACB some time *after* the current function completes!**

### Map-Reduce
Just reduce
```javascript       
cars.reduce(sumCarDoorsReducerCB, 0)
```
map-reduce      
```javascript 
cars.map(car2doorsCB).reduce(sumReducerCB, 0)
```

filter and map can be written with reduce:
```javascript 
function myMap(array, transformer){ 
   function transformReducerCB(acc, elem){  return [...acc, transformer(elem)];  } 
   return array.reduce(transformReducerCB, []);   // an array as accumulator! 
}

function myFilter(array, tester){                   // no need for else after return
   function keepReducerCB(acc, elem){ if(tester(elem)) return [...acc, elem]; return acc; }
   return array.reduce(keepReducerCB, []);        // an array as accumulator! 
}
```

### JSX functional component: createElement(ACB,props)
!!! asynchronous!
| Question 												| Answer |
| -----------------------------------------------------	| ------ |
| How to pass the callback?								|``` <MyComponent  prop1={value1} prop2= {value2} /> ```|
|														|``` <MyComponent  {... {prop1:value1, prop2:value2} } /> ```|
|														|``` <MyComponent  {... someObject } /> ```|
|														|``` <MyComponent .. > <Child1.. />  <Child2 .. /></MyComponent> ```|
|														|``` React.createElement(MyComponent, props, children) ```|
|														|``` Vue.h(MyComponent, props, children) ```|  
| Other params needed besides the callback? 			| No |
| What does <MyComponent /> return?          			| Framework-dependent. Some plan to call MyComponent(props) |
| When does <MyComponent /> return?          			| Immediately. (just makes a plan that when rendering/update is needed ACB will be invoked) |
| Who calls the callback, and sends parameters?       	| The framework. |
| Role (and usual name?) of callback parameters      	| One parameter, a JS object. It is usually called props but it’s just a convention |
| What is the callback expected to return?       		| JSX, user interface |
| When is the callback called?     						| At initial render, and every time the framework deems that the component must update |
| Is the callback called once? Or repeatedly?       	| Repeatedly |
| What is the role of the callback?   					| Render user interface in a reusable manner |
| Example callback names                 				| Depends on the role of the component in the overall UI / project   |

### onEvent={ACB} addEventListener(event, ACB)
!!! asynchronous!
| Question 												| Answer |
| -----------------------------------------------------	| ------ |
| How to pass the callback?								| ``` <someHTMLTag onClick={acb} />  ```|
|														| ``` someDOMNode.addEventListener("click",  cb) ```| 
| Other params needed besides the callback? 			| No for onClick, yes for addEventListener ("click") |
| What does <someHTMLTag  onClick={acb} /> return?      | nothing |
| When does <someHTMLTag  onClick={acb} /> return?      | Immediately. (just makes a plan that when user clicks, ACB will be invoked) |
| Who calls the callback, and sends parameters?       	| browser event loop |
| Role (and usual name?) of callback parameters      	| event object (includes target, timestamp, etc, details later) |
| What is the callback expected to return?       		| nothing  any longer. false prevented default browser action (e.g. submit form) |
| When is the callback called?     						| When user interacts, or e.g. page load:   document.body.addEventListener("load”, cb) |
| Is the callback called once? Or repeatedly?       	| As many times as the user interacts |
| What is the role of the callback?   					| Programmatically react to user interaction |
| Example callback names                 				| buttonClickedACB |

### fetch(..).then(ACB)....catch(EACB)
!!! asynchronous!
| Question 												| Answer |
| -----------------------------------------------------	| ------ |
| How to pass the callback?								| ``` fetch(..).then(ACB) ``` catch is optional and may come later in the promise chain |
| Other params needed besides the callback? 			| No |
| What does fetch(..).then(ACB) return?      			| A Promise, which in turn has a then(..) method, catch(..) etc |
| When does fetch(..).then(ACB) return?      			| Immediately. Just makes a plan that when the HTTP response comes, ACB will be invoked |
| Who calls the ACB callback, and sends parameters?    	| Browser network layer. See the Network tab in DevTools |
| Role (and usual name?) of callback parameters      	| The HTTP response: response code, headers. No  data ! |
| What is the callback expected to return?       		| Typically response.json() or response.text(). That is, a new promise is returned, to treat the data content of the HTTP access. |
| When is the callback called?     						| When the HTTP response has arrived from the server. The data may still be in transit! |
| Is the callback called once? Or repeatedly?       	| Once or zero times (if there is an error in the HTTP call, EACB is called) |
| What is the role of the callback?   					| Look at the response and fire up the second fetch promise like json() or text(). Examine the response code, possibly throw if it is not 200 (HTTP OK). Then the EACB will be called  |
| Example callback names                 				| treatHTTPResonseACB |

### customEvent={ACB}
!!! asynchronous!
| Question 												| Answer |
| -----------------------------------------------------	| ------ |
| How to pass the callback?								| ``` <SomeComponent    customEvent={ACB} />   ```|
| Other params needed besides the callback? 			| No |
| What does <SomeComponent    customEvent={ACB} /> return?      | nothing |
| When does <SomeComponent    customEvent={ACB} /> return?      | Immediately  (just makes a plan that when the custom event is fired, ACB will be invoked) |
| Who calls the callback, and sends parameters?       	| SomeComponent code, typically in a native or custom event listener |
| Role (and usual name?) of callback parameters      	| Can vary. Typically abstract (non-graphical objects) |
| What is the callback expected to return?       		| nothing |
| When is the callback called?     						| Typically when a native or custom event handler invoked in SomeComponent |
| Is the callback called once? Or repeatedly?       	| Repeatedly |
| What is the role of the callback?   					| Interpret a lower level event in more abstract terms |
| Example callback names                 				| somethingHappenedACB |

### addObserver(ACB)
| Question 												| Answer |
| -----------------------------------------------------	| ------ |
| How to pass the callback?								| ``` addObserver(ACB)  ```|
| Other params needed besides the callback? 			| No |
| What does addObserver(ACB)  return?      | sometimes a CB that removes the observer!  |
| When does addObserver(ACB)  return?      | Immediately. Just makes a plan, that when something changes in the Subject (e.g. model), the obseverACB will be invoked. But it may call the observerACB once (synchronously!)|
| Who calls the callback, and sends parameters?       	| The Subject/Observable (model), on notifyObservers() |
| Role (and usual name?) of callback parameters      	| When available, name is payload |
| What is the callback expected to return?       		| nothing |
| When is the callback called?     						| When there are changes in the Subject = Observable = Mode |
| Is the callback called once? Or repeatedly?       	| Repeatedly |
| What is the role of the callback?   					| Update based on the latest data from the Subject = Observable = Model |
| Example callback names                 				| myObserverACB |

## Custom components
**!!! ACB !!!**
```javascript
function MyComponent(props){
  return (     // return alone on a line returns undefined!
<div>
   <button>click me</button>
   <input placeholder={props.holder}/>
   <select>
<option>My way</option>
<option>The highway</option>
  </select>    
</div>
  );
}

function MyComponent2(props){
  return <div>
     <button>click me</button>
      <input placeholder={props.holder}/>
      <select>
   <option>My way</option>
   <option>The highway</option>
      </select> 
   </div> ;
}
```
:checkered_flag: **The MyComponent function is called a functional custom component.**

:checkered_flag: **Name must begin with a capital letter which is unusual in JavaScript/C/Java coding conventions.**

## Inline Javascript
```javascript
<td class="number-right">{Number(menuPrice(2000/50).toFixed(2)}</td>
```
 
 
## Create random ID
```javascript
function generateID (){
        return Math.random().toString(36).slice(2);
     };


const UID = generateID();
const textarea = "textarea" + UID;
const seeM = "seeMore" + UID;
```
```html
<a id={seeM} onClick={toggleSeeMore} href="javascript:void(0);">See More</a>
```

## Print Page
```javascript
<button onclick="window.print()">Print This Page</button>
```

## Web APIs

### Synchronous Web API access

```javascript
function getDataCB(e){ getDataFromAPI("http://some.api", apiParameters); }
<button onClick={getDataCB}>Search!</button>
```
:rotating_light: When the button is clicked, if getDataFromAPI takes 5 seconds to return, the UI will be frozen for 5 seconds! 

Never take too long in your event listeners! If you need to perform time-consuming operations, you can use e.g.
```javascript
setTimeout(function longTimeACB(){ time ; consuming ; operations; }, 0);   // 0 is the delay in ms
```

### Asynchronous Web API access
```javascript
getDataFromAPI("http://api.server", apiParameters, successCallbackACB, errorCallbackACB)

getDataFromAPI("http://api.server", apiParameters	, function successACB(data){ ..}
, function errorACB(error){..})
```

:bulb: The advantage is that getDataFromAPI returns immediately so the UI (browser tab) is not frozen.

**Returns immediately** =  just makes a plan that when the web API will return successCallbackACB will be invoked if all goes OK and  errorCallbackACB will be invoked if something goes wrong (network, bad parameters to the API etc)

### The Callback Pyramid of Doom
```javascript
getDataFromAPI("http://api1.server", apiParameters, 
   function firstOperationACB(data1) {
               getDataFromAPI("http://api2.server", apiParametersUsingdata1,  
                      function secondStepACB(data2) {
                           getDataFromAPI("http://api3.server", apiParametersUsingdata1_data2,  
                                 function thirdStepACB(data3){  
                                            /* use data1, data2, data3 */
                                 }, 
                                function thirdStepErrorACB(error3){..}.
                          )
                 }, 
                function secondStepErrorACB(error2){..}
           )
   }, 
   function firstStepErrorACB(error1){..}
)
```

### Promises

Asynchronous Web API access in browsers: **fetch**
```javascript
fetch("http://api.server", parameters).then(successCallbackACB).catch(errorCallbackACB)
```

The object returned by fetch() is of type Promise
- then() is a method of Promise
- then() also returns a Promise (so another then() can come after, hence chaining) 
- catch() is also a promise method returning Promise

```javascript
fetch("http://api.server", parameters).then(acb1).then(acb2).catch(errorCallbackACB)
```

How the promise chain works:
1. If things go well in fetch() and acb1 is called, we say that the **promise resolves** (or fulfills) 
Otherwise the **promise rejects** (or fails) and errorCallbackACB is called.
2. If acb1 returns a Promise, that promise will be returned by then(acb1). 
otherwise then() will wrap its result into a promise that resolves immediately (so the next then() is called, if any)

### Passing parameters to APIs
- HTTP method
- HTTP resource path (path on server) and query string
- HTTP headers
- HTTP body (data)

#### HTTP method and REST. API Endpoints
- GET (read data from API). Default method in e.g. fetch()
- POST (create new data on the server, or send complex read requests)
- PUT (update data on the server)
- DELETE (remove data from server)

```javascript
fetch("http://api.server/resource/12445" ,{ method: "GET" }).then(...) 
fetch("http://api.server/resource/12445" )  // GET is default!
fetch("http://api.server/resource/12445" ,{ method: "DELETE" })
fetch("http://api.server/resource/12445" ,{ method: "PUT" , body: JSON.stringify(someObject)})
```

API Endpoint = method + resource path 

#### Query string
```javascript
cleverDishSearch?freeText=bla+bla&type=appetizer
```
? followed by name=value pairs separated by  & 

To avoid all escaping complexities, use the built-in class URLSearchParams, pass a JavaScript object to its constructor.
```javascript
fetch(API_SERVER+
"/cleverDishSearch?" + new URLSearchParams({ freeText:"bla bla", type:"appetizer" })
)  // GET HTTP method is default!

```

#### HTTP headers and body
Headers=key-value pairs

```javascript
fetch('https://api.server/endpoint', {
  method: 'POST', // or 'PUT'
  headers: {
    'Content-Type': 'application/json',
  },
  body: JSON.stringify(someObject),
}).then.
```
The server response also contains headers. We can retrieve them from the fetch() response.

```javascript
fetch("https://pokeapi.co/api/v2/pokemon/1").then(
   function responseACB(r){ r.headers.forEach( function headerCB(h){console.log(h);} ); }
);
```

## Promise state
```
{promise, data, error}
```

1. When promise changes*, data and error are set to null, waiting for the promise to resolve or to reject
2. When promise is resolved (aka fulfilled, aka successful), data is set
3. When promise is rejected, error is set

*due to user interaction (a new search, reading another dish)

### Naive setup 

```javascript
function resolvePromise(promiseToResolve, promiseState){
	promiseState.promise=promiseToResolve;
	promiseState.data= null;           // UI update! The user does not keep seeing results from previous search
	promiseState.error= null;
	function saveDataACB(result){ promiseState.data= result; }  // triggers UI update because of changing state
	function saveErrorACB(err)  { promiseState.error= err; }    // triggers UI update because of changing state
	promiseToResolve.then(saveDataACB).catch(saveErrorACB);
}

function AsyncPresenter(props){ 
	function doSearchACB(params){ resolvePromise(myAPICall(params), props.model.myPromiseState); }
	return <SomeView onSearch={doSearchACB} searchResults={props.model.myPromiseState.data} />
}

function SomeView(props){
 	function handleInputACB(event){ props.onSearch(event.target.value); }
	return <div><input onChange={handleInputACB} /> { props.searchResults }</div>;
}
```

:rotating_light: *Problems: race condition* -> second promise can resolve before the 1st promise

```javascript
// Bad scenario
000 doSearchACB("past")  
001 promiseState.data=null, fetch("?past")
007 doSearchACB("pastic")
008 promiseState.data=null, fetch("?pastic")

700 promiseState.data= "pasticcio"
800 promiseState.data= "lots of pasta"
```
User sees "pasticcio" for 100ms (if they manage), then "pasta", which is not what they were looking for

### Solutions 
#### Debouncing 
 -> not good enough
 
#### Only save if promiseState.promise is still the same
```javascript
function resolvePromise(promiseToResolve, promiseState){
	promiseState.promise=promiseToResolve;
	promiseState.data= null;         
	promiseState.error= null;
	function saveDataACB(result){ 
		if(promiseState.promise !== promiseToResolve) return;
	/* TODO save result in promiseState, as before */
	} 
	function saveErrorACB(err)  { 
		/* TODO same check as above */
	/* TODO save err in promiseState, as before */
	}
	promiseToResolve.then(saveDataACB).catch(saveErrorACB);
}
```
```000 doSearchACB("past") 
001 promiseState.promise=promise1;
    fetch("?past")
007 doSearchACB("pastic")
008 promiseState.promise=promise2;
    fetch("?pastic")

700 promiseState.data= "pasticcio"
800 promiseState.data= "lots of pasta"

User sees only “pasticcio” 
```

#### Cancel the old promise
->the promise might retreive a huge file, eating data
```javascript
function resolvePromise(promise, promiseState){
	if(promiseState.promise 
 	&& !promiseState.data && !promiseState.error)  // not yet resolved/rejected
		cancelPromise(promiseState.promise); 
	promiseState.promise=promise;
	promiseState.data= null;         
	promiseState.error= null;
	function saveDataACB(result){ 
		if(promiseState.promise!==promise) return;
		/* TODO save result in promiseState, as before */
	} 
	function saveErrorACB(err)  { 
		/* TODO same check as above */
		/* TODO save err in promiseState, as before */
	}
	promise.then(saveDataACB).catch(saveErrorACB);
}
```

### Notify when promise is resolved
Vue will detect any change under model.somePromiseState.  

React and other frameworks will not detect that, so they will need explicit notification (Observer) 

```javascript
function resolvePromise(promise, promiseState, notifyACB){
	promiseState.promise= promise;
	promiseState.data= null;         
	promiseState.error= null;
	if(notifyACB) notifyACB();    // notify every time promise, data, or error change
	function saveDataACB(result){ 
		if(promiseState.promise!==promise) return;
	/* TODO save result in promiseState */
	* TODO notify */
	} 
	function saveErrorACB(err)  { 
		/* TODO promise check as above */
	/* TODO save err in promiseState */
	/* TODO notify */
	}
	promise.then(saveDataACB).catch(saveErrorACB);
}
```

### promiseNoData(promiseState)
```javascript
return <div>
   <SomeViewForm onSearch={doSearchACB} />
   { promiseNoData(props.model.searchPromiseState) || 
 			<SomeViewResults searchResults={props.model.searchPromiseState.data}/>}
</div>;
```

promiseState.promise | promiseState.data | promiseState.error | promiseNoData() return value |
--- | --- | --- | --- |
falsy | don’t care | don’t care | ```<div>No data</div>``` |
truthy | falsy | falsy | ```<img src=TODO class=TODO />```   a "loading image" animated GIF |
truthy | falsy | truthy | ```<div class=TODO >{error}</div>``` |
truthy | *truthy* | falsy | *false* . This will ensure that the second || operand is evaluated:  there is data, so the View can render that data. Note that promiseNoData returns truthy in all other cases above! |


# Component state
## Why do we use it?
Some parameters do not need to be kept in Application state, as they are local and not shared between presenters.

## Advantages
- UI less dependent on Application state 
	- more portable
	- can be shared and reused

## Disadvantages
**X** Platform dependent

**X** Needs component lifecycle and watchers (observers / listeners)

**X** If the parameters from component state need persistance, then they need to be saved in the Application state anyway.

**X** Promise state management becomes framework dependent

## State based update
**Problem:** function parameters and variables are lost after function execution (excp. closures) 

1. Frameworks keep the data (component state) between Component function executions (renderings).
2. Using event listeners, observers, promises, cloud persistence, a Component can change its own state.
3. Framework updates (re-renders) the component when its State changes.

Frameworks only provide component state and we implement application state using that.

# Re-rendering

## Old approach: Incremental update
- Changed only the parts of the GUI that needed to be changed

**X** Needed both rendering code (HTML/XML/static UI), and updating code for various conditions(finding the element in the tree via getElementById(), querySelector(), etc)

**X** Hard to manage, render and update could be written in different languages

## New approach: re-render & reconciliation

**Re-render**= on every change, the component is re-rendered completely, even if only a small part of it changes

**Advantage:** only need to define rendering code

**Disadvantage:** Complete re-render is more resource-intensive than incremental update

To alleviate that, frameworks do not re-render in the browser UI tree (DOM) but in a virtual, in-memory tree (Virtual DOM).  
Then they compare the two trees and only implement the differences in the browser DOM (**Reconciliation**) 

# Stateless vs Stateful Components

## Stateless Components
- Functional
- Pure functions which render the same given the same props (Deterministic)
- No side-effects
## Stateful components
- Rendering depends on state, not just on parameter (props).
- Side effect: setting the state.

____
# React Component State

## React State Hook
### General format
```javascript
function ReactStatefulComponent(props){
  const [value, setter]= React.useState(initialValue);
  return <SomeTag someAttr={value} 
      onSomeEvent= {function handleEventACB(e){ setter(newValue); }  } />
}
```
### Example
```javascript
function Motd(props){ 
   const [message, setMsg]= React.useState("initial msg");   // state hook
   return <div> 
            <input onInput={ function handleInputACB(e){setMsg(e.target.value);}} />
            <div>message of the day is: { message } </div>
        </div>; 
}
```
Changing message (calling setMsg with a different value) will make React trigger a re-render.

**!!!** When setting the current value, React will avoid (**bail out**) re-rendering of sub-components.

**!!!** React controlled (INPUT) component (if you set value, you must define onInput or onChange).

## Shallow React
React re-renders **shallow**ly Arrays and Objects in component state. Adding an element to an Array (or changing a property of an Object) will not trigger re-render.

```javascript
const [dishes, setDishes]= React.useState([]);
dishes.push(someDish); setDishes(dishes)  // NO update! State is the same!
setDishes(dishes.concat(someDish))    // update!  State has changed (a new array)
setDishes([...dishes, someDish])    // update!  State has changed (a new array)
setDishes([someDish, ...dishes])    // update!  State has changed (a new array)
```

You always need to create new Array or Object if their properties or elements change.  

That means that the content of the Arrays and Objects in the React state should never change! They are immutable. 

If you want to change React state, you have to create new ones.

# Top level state react?
**!!! BAD IDEA !!!**

Setting the whole model as a state property  will not work because of the  React state: the model reference never changes, therefore no React re-render!

When one of the state properties changes, the App will re-render, therefore all its children and their children will re-render.

This is why we have the Presenters observing the model (=> **Observer**). For the Presenters to subscribe and observe the model, hey need component lifecycle.


__________________________
# Observers

## Useful functions 
- addObserver(callback) -> add callback to observers array
- removeObserver(callback) -> remove callback from the observers array, e.g. this.observers= this.observers.filter(..)  
```javascript
// 1. call the observer when it is added
/* 1. read data from the model */
model.addObserver(function myObserverACB(){  
    /* 2. read latest data from the model */ ;
});

//If we are sure that addObserver calls the observer once at addition, the code is simpler:
model.addObserver(function myObserverACB(){  
    /* read data from the model */ ;
});

//2. return observer removal at addition
function myObserverACB(){..}
model.addObserver(myObserverACB);
// Later in the code:
model.removeObserver(myObserverACB);
```
- notifyObservers(payload) -> call all the callbacks in the array

If an error occurs in an observer, all subsequent observers will lose the notification. This is why notifyObservers(payload) should be in a try catch block
```javascript
try{ /*call obs */ }catch(err){console.error(err); }  
```
If an observer takes too long to address the notification (cb takes long), the other observers will be delayed! 

## Payload
**Payload** is like an **event** fired by the Model (Observable, or Subject). 

Most Observers can ignore the payload parameter (similar to a click event handler, it rarely needs the click_event object) but the Persistor observer (Firebase) needs it to understand in more detail what has changed to only save that change to the cloud.

## Component lifecycle

### Licefycle motivation
An Observer component needs to: 
1. Add itself as observer to the Model when the component is created.
2. Remove itself as Model observer when the component is taken down.
		-> to avoid state change change of components no longer displayed
		-> to avoid memory leakes
		
### Lifecycle usage
1. Let us know when the component has been created.
2. Let us know when the component is taken down.

### Example use-cases
1. The component has been created. 
- add the component as Observer to an Observable (e.g. Model)
- subscribe to a browser-wide event (e.g. window "hashchange" event for navigation)
- initiating a promise
2. The component is being taken down (e.g. its parent does not want to render it any longer)
- Remove the component as Observer to an Observable (e.g. Model)
- Unsubscribe an event listener (though the browser usually takes care of this)

### React lifecycle
**subscribe at creation, unsubscribe at teardown**
```javascript
function ObserverPresenter(props){   
	const [number, setNumber]=React.useState(props.model.numberOfGuests);
	function observerACB(){ setNumber(props.model.numberOfGuests);}
	function wasCreatedACB(){  
		props.model.addObserver(observerACB);                                // 1. subscribe
		function isTakenDownACB(){ props.model.removeObserver(observerACB);} // 2. unsubscribe
		return isTakenDownACB;
	}
	React.useEffect(wasCreatedACB, []);//  stricter: [props.model] but that never changes 
	
	return <MyView 	someProp={props.model.numberOfGuests}  
					someEvent={function handleEventACB(e){model.setNumberOfGuests(x)}}  />
					
	// someEvent needs a function. Calling only setNumberOfGuests  will lead to re-render of this component but the model will not find out about the change, nor will its Observers!

}
```

On first render (invocation of wasCreatedACB) wasCreatedACB will be invoked.

At next renders (updates) the effect will not do anything.

When the component is taken down, isTakenDownACB is invoked.

### React component state and re-rendering
When the model notifies, component state may change and component re-renders. It will not always change!

If the numberOfGuests does not change in the model (and the model notifies observers for some other reason, like adding a dish), setNumber will not lead to React re-render.

### React simplification
```javascript
function ObserverPresenter(props){   
	const [/*(a) ignore!*/, setNumber]=React.useState(/*(b) no value, see initialization below! */);
	function observerACB(){ setNumber(props.model.numberOfGuests);}
	function wasCreatedACB(){
	  observerACB();    // (b) call observer when adding it, to initialize the state
	  props.model.addObserver(observerACB);                                // 1. subscribe
	  return function isTakenDownACB(){ props.model.removeObserver(observerACB);} // 2.unsubscribe
	}
	React.useEffect(wasCreatedACB, []);//  stricter: [props.model] but that never changes 
		// the JSX code is the same as in any props.model (Vue, TW1, TW2) presenter:
	return <MyView 	someProp={props.model.numberOfGuests}  
					someEvent={function handleEventACB(e){model.setNumberOfGuests(x)}} />	
}

```

a. Since the state variable name (formerly number) is not used in JSX (props.model.NumberOfGuests is used instead), it can be ignored at destructuring.
b. Calling the observer when adding it allows setting the state without initializing it in React.useState. This is especially useful when the observer copies several state properties from Application State.
c. The returned function can be used directly at its declaration.

### React custom hooks
Custom hooks are functions with names starting with use, and using other hooks (state, effect). 

They must obey rules of hooks:  
(1) always call (each render)  
(2) call in the same order!

Typically hooks are called at the functional component start.


