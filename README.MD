# Javascript Fundamentals

Javascript is known as the language of the web. It is often used alongside HTML and CSS. If a website is performing any kind of dynamic display or interaction, it is probably using Javascript to accomplish it.

## Variables

Variables are what we use in Javascript to store values. They can be declared by using the keyword `var`. It's easy to think about a variable as a box and we will store our content inside the box. We will also give that box a name to have a way to reference it.

```javascript
var name;
```

We can also assign a value to our variable upon delcaration. We will use the `=` operator to assign a value on the rightside side of the operator to the variable that is declared on the left

```javascript
var name = "Tayte";
```

We can also reassign values to variable that has already been declared.

```javascript
var name = "Tayte";
name = "New Name";
```

## DataTypes

Variables in Javascript can hold any data type. Languages that allow this to happen are known as a `dynammically typed` language.

There are seven basic data types in Javascript.

### Number

The `number` data type represents integer and floating point numbers.

```javascript
var nine = 9;
var nineAndHalf = 9.5;
```

We can perform different opertaions on the `number` data type such as multiply, divide, subtracttion, addition, etc.

Other than integers and floating point numbers (decimals), there `special numeric values` that belong to the `number` data type.
An example of this is `NaN`.

`NaN` represents a computational error, it is a result of an undefined or an incorrect evaluation of a mathematical operation.

Example:

```javascript
alert("not a number" / 2);
```

This would return `NaN` because we can't divide a string by 2. `NaN` is sticky, meaning that whenever an operation hits `NaN`, it will always result as `NaN`.

### String

The `string` data type represents a set of characters, a word, or a sentence.

String must always be wrapped in quotes. We can use either double or single quotes to accomplish this.

```javascript
var stringOne = "This is a string using single quotes";
var stringTwo = "This is a string using double quotes";
```

Another way to create a string is by wrapping our words with backticks instead of quotes. This is known as a `template literal`. Using a `template literal` gives extended functionality to our strings by allowing us to embed variables into the string by wrapping them with curly braces being prefixed with a dollar sign.

```javascript
var name = "Tayte";
var greeting = `Hello, my name is ${name}`;
```

### Boolean

`Boolean` data types have only two values, `true` or `false`.

This data type is commonly used to store a yes or no value to a variable.
`true` means yes
`false` means no

```javascript
let nameFieldChecked = true; // yes, name field is checked
let ageFieldChecked = false; // no, age field is not checked
```

### Null

`Null` does not belong to any other datatype. It is it's own stand alone value representing that something does not exist.

```javascript
var age = null;
```

The code above dicatates that the `age` variable is unkown or does not have a value.

### Undefined

Just like null, `undefined` creates it's own stand alone data type that represents something exists, but does not have a value.

```javascript
var hello;

alert(hello); // this would return undefined since there has not been a value assigned to the hello variable
```

### Array

Arrays are the data type we can use to create an ordered collection or list of values in Javascript.

Arrays are created by using `[]` brackets.

Values are seperated by commas and the values in an array can be of multiple data types.

Arrays in Javascript are zero based index, meaning that the index value of the first item starts at 0 and moves up from there.

```javascript
var newArray = [1, "two", 3, null, undefined];
```

### Object

An object in Javascript is a comma seperated list of key-value pairs and are wrapped in curly braces. Objects are used to encapsulate data.

The key, also referred to as the property, of a value is the name that we will use to reference some data inside the object.

```javascript
var myObj = {
  name: "Tayte",
  hobbies: ["Coding", "Video Games", "Music"]
};
```

### Function

Functions are reusable blocks of code inside of our programs that will perform a serious of events to create the logic we desire. It's easy to think about these as an algorithim or mini-program inside of our programs.

```javascript
function myFunc() {
  // perform logic inside of the curly braces
}
```

## Truthy & Falsy

truthy and falsy are values that we can use to check for a specific condition.

There are 6 `falsy` values:

`null` - non-existent
`undefined` - it exists but does not have a value
`false` - it means it's false
`''` - empty strings represent nothing
`0` - zero is another falsy value
'NaN' - not a number is another falsy value

Anything other these six values are `truthy`

## Logical Operators
We can use `logical operators` to act as a comparison to test for a certain condition.

`&&` is the AND operator, this will check for the expression on the left AND the expression on the right to be truthy. If it is, the logical operator will return true.

`||` the double pipes is the OR operator. This will check to see if the expression on the left OR the expression on the right is true. Notice that only one needs to run true for the OR operator to return true.

`==` the double equals will compare the value on the left side with the value on the right side. It goes through a process called `type coercion` which is where the values are only compared after attempting to turn them into a common data type. It's easy to think that if the value is the same but a didfferent data type, it will be true.

```javascript
'7' == 7
```

the above statement would run true because it goes through type coercion and finds a common data type between them.

`===` triple equals, also known as a strict comparison, is similar to the double equals but it does not go through type coercion and will only run true if the value and the data type ares the same.

```javascript
'7' === 7
```

the above statement runs false because a string and an integer are not the same data type.

`!` the bang operator pretty much means the opposite. If we use a logical operator with a prefix of `!`, we will be looking for the opposite of whatever we are checking for.

```javascript
'7' !== 7
```

the above statement would return true because the string of 7 does not match the integeer of 7.

## If Statements

An if statement is a block of code that checks for a specfic condition to be truthy, if it is, it will execute the logic inside the block of code.

the if statement starts using the keyword `if` then uses parenthesis to check for a specific condition to be true, if it is the code insie the code block (curly braces) will be executed. If the condition runs false we can use an `else if` statement to check for another condition, and if that runs false, we can either use another `else if` or use a catch-all block and run an `else` statement.

We can use logical operators to check for truthy or falsy conditions inside of the parenthesis of the if statment.

```javascript
if('7' === 7){
    console.log('we will never see this console log since the string of seven doesnt match the integer of seven');
} else if ('7' == 7){
    console.log('after type coercion the string of seven matches the integer of seven');
} else {
    console.log('this will only log if the first two conditions run false');
}
```

## Functions

Like we mentioned earlier in the `Data Types` sections, functions are reusable blocks of code inside of our programs that will perform a serious of events to create the logic we desire. It's easy to think about these as an algorithim or mini-program inside of our programs.

There are multiple ways to create a function:

Function Express is where will store an anonymous function into a variable.

```javascript
var myFunc = function(){
    // some logic here
};
```

Function Declarations is the more common way to create a function.

```javascript
function myFunc(){
    // some logic here
};
```

There are multiple parts to a function, first we need to use the keyword `function` to declare a new function, next we will use paranthesis to accept arguments into the function, and the curly braces to create the block of code that the function will execute.

To run the function within our code, we will need to `invoke` it. We will add `()` parenthesis as a suffix to the name of our function invoke it

```javascript
myFunc();
```

Above we are calling or invoking our function `myFunc` that we created earlier.

### Arguments

Arguments are data that we can pass to our function inside the paranthesis when we invoke our function.

```javascript
var myName = 'tayte';

function sayName(name){
    console.log(name);
};

sayName(myName);
```

above we are creating a variable and storing a string of our name inside of it. Then we have a function that has a `parameter` to allow us to accept arguments, that we then console log. We then invoke our function passing in our `myName` variable as an argument which will now be referenced as `name` inside of our function because we set the `parameter` to be called name.

### Parameters

Parameters are variables that we can use to capture data that is passed into our functions.

```javascript
var myName = 'tayte';

function sayName(name){
    console.log(name);
};

sayName(myName);
```

`name` is the parameter set in our function and we can access any data that is passed into our function by referencing the `name` parameter variable.


### Returning From A Function

When we want a function to `return` some sort of data, we will need to use the `return` keyword. This `return` keyword is a special keyword that is used to tell our function to return whatever is to the right side of the statement from our function.

```javascript
function add(numOne){
    return numOne + 5;
}

add(5) // this will return 10
```

In the code above, we are returning whatever is to the right of the `return` statement. Notice how we are adding our parameter variable numOne to with the number 5. Javascript will execute the code on the right side of the `return` statement before returning from the function.


NOTICE: the function is completely done executing as soon as it hits the `return` statment

```javascript
function add(){
    return 2 + 2;
    console.log('the answer is 4');
}
```

the console log after the `return` statement is never hit and will never be executed because the `return` statment kills the execution of the funciton.


## Scope

Scope is the context in which values and expressions are 'avilable' in your code. 

The `global scope` is available anywhere in your code.

Scopes have a hierechy system. When a function is created it creates it's own scope, but when we have nested functions this hierechy comes into play where parent scopes can not access their child scopes.

```javascript

var name = 'Tayte'; // this is on the global scope and available everywhere

function sayName(){
    // this function has just created it's own scope, think about it as the space between the curly braces
    console.log(name); // this will log 'Tayte' since children scopes have access to their parents scope
    var lastName = 'Stokes';
};

console.log(lastName); // this will return undefined because lastName is not available in the global or parent scope of where we are trying to refer to it
```


## Let Keyword

`Let` is another keyword that we can use to declare variables. However, unlike `var`, `let` will block scope your variable meaning that the variable is only available inside the block of code it is defined in. `var` will declare variables globally.

```javascript
if(1 === 1){
    let result = true;
};

console.log(result) // this will be undefined because result is scoped to the block of the if statement
```