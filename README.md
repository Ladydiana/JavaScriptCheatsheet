# JavaScriptCheatsheet

Useful: 	
* https://developer.mozilla.org/en-US/docs/Web/JavaScript/
* https://www.w3schools.com/js/tryit.asp?filename=tryjs_editor

TOC:
- [Variables](#variables)
    + [Definition](#definition)
    + [Operations](#operations)
- [Alerts & Prompts](#alerts--prompts)
- [Conditional and logical operations](#conditional-and-logical-operations)
- [Arrays](#arrays)
- [Loops](#loops)
    + [while](#while)
    + [forEach](#forEach)
	+ [do while](#do-while)
	+ [for](#for)


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
}

```

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

```