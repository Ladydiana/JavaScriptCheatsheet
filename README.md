# JavaScriptCheatsheet

Useful: https://developer.mozilla.org/en-US/docs/Web/JavaScript/

- [Variables](#variables)
    + [Definition](#definition)
    + [Operations](#operations)
- [Alerts & Prompts](#alerts---prompts)


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
let semaphore = true;	// Boolean
let city = "Stockholm";	// String
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