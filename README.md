# JavaScriptCheatsheet

Useful: 	
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/
* https://www.w3schools.com/js/tryit.asp?filename=tryjs_editor

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
JS functions run to completion. 
setTimeout(ACB, 0) will execute ACB some time *after* the current function completes!

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