## JavaScript

- JS is a programming language that is used for converting static web pages into interactive and dynamic web pages.
- JS engine is the program present in the browser that execute the JS code.

- A client is a device, application and software component which request and consumes services or resources from the server.
- A server is a device, computer or software application that provides services and resources or functions to clients.


## Scope

- Scope determines where the variables are defined and where they can be accessed.

```javascript
let globleVariable = "global";
greet();

function greet(){
    let functionVariable = "function";
    if(true){
        let blockVariable = "block";
        console.log(blockVariable);
        console.log(functionVariable);
        console.log(globleVariable);
    }
    console.log(globleVariable)
    console.log(functionVariable)
}
    console.log(globleVariable)
```

- "var" is the implicit type of variable when variable is declared without var,let and const keyword.
```javascript
if(true){
    variable = 10;
}
console.log(variable);     //output  : 10
```

## Hoisting

- Hoisting is the JS behavior where  functions and variables  declarations are moved to the top of their respective  scopes during the compilation phase.

```javascript
myFunction();

function myFunction(){
    console.log("this is function hoisting");
}
```
```javascript
// variable hoisting
x = 10;
console.log(x);
var x;
```

## JSON

- JSON (JavaScript Object Notation) is lightweight data interchange format.
- JSON consist of key-value pairs.
```javascript
{
    "name" : "Arati Chanda",
    "age" : 24,
    "isEmployee" : true,
    "address":{
        "city":"Jalna",
        "country":"INDIA"
    }
}
```

## Variables

- variables are used to store the data.
- "var" creates a function scoped variable.
- "let" creates a block scoped variable.
- "const" can be assigned only once and itsvalue can b=not be changed afterwards.


## Data Types

- Data type determines the type of variable.
##### primitive data types :
- Number, String, Booleans, Undefined, Null.
- can hold only single value.
- are immutable means value once assigned cannot be changed.
- simple
```javascript
// undefined
let x;
console.log(x);
```
- undefined can be used when you don't have the value right now but you will get it after some logic.
- Null can be used when you are sure you do not have any value for particular variable.

##### Non primitive
Object, Array, Function, Date, RegExp
- can hold multiple values.
- they are mutable
- complex

## what is typeof operator ?
- typeof operator is used to determine the type of each variable.
- Real application use  -> used to validate the data received from external sources (api).
```javascript
let num = 7;
let str = "Hello";
let bool = true;

console.log(typeof num);
console.log(typeof str);
console.log(typeof bool);
```

## what is type coercion in JS ?
- type coercion is the automatic conversion of values from 
one data type to another during certain operations or  comparisons.
- type coercion can be used during String and Number concatenation
- also can be used while using Camparison operators
```javascript
let string = "42";
let num = 42;

console.log(string + num);
// output is "4242"
```

## Operator Precedence
- As per operator precedence, operator with higher precedence are evaluated first.
- It works same as BODMAS rule (Brackets,Order,Division,Multiplication,Addition,Subtraction).
```javascript
let a = 6;
let b = 3;
let c = 2;

result = a + b * c + (a - b);
console.log(result);   // output : 15
```
- in above example the brackets get resolved first. (a - b)
- then multiplication.   b * c
- then addition.   a + 9

## Operators
- operators based on number of operands
* Unary operator
```javascript
let a = 5;
let b = -a;
console.log(b);  // output : -5

console.log(++a);  // output : 6
```
* Binary operator
```javascript
let a = 3;
let b = 4;
let c = a + b;

console.log(c);  // output : 7

```

* Ternary operator
```javascript
let result = condition ? "yes" :"no";
console.log(result);  // output : yes  
```

##  Short-circuit evaluation in JS
- short circuit evaluation stops the execution as soon as the result can be determined without evaluating the remaining sub-expression.

```javascript
// here first condition is false there is no need to check the second condition
 //(AND)
let result1 = false && someFunction();
console.log(result1);   // output :  

// here first is true so there is no need to check the second condition 
// (OR)
let result2 = true || someFunction();
console.log(result2);
```

## condition statements
1. if else statement
2. ternary operator
3. switch statement

##  Difference == and ===
- Loose equality(==) operator compares two values for equality after performing the type coercion.
```javascript
console.log(1 == '1');  // number 1 is converted to string and then compare 
console.log(true == 1);  // true is converted to 1 and then compare
// this way both gives true as output
```
- Strict equality(===) operator compares two values for equality without performing the coercion.
```javascript
// here values compare as actually they are without performing type coercion
console.log(1 === '1');   
console.log(true === 1);  
// both output will be false
```
- Normally === is preferred in use to get more accurate comparisons

## Spread and Rest operator
1. Spread operator(...) is used to expand or spread element from an iterable(array,string,object) into a individual element.
- used when copying an array, merging array or passing multiple arguments to a function.
```javascript
// spread operator
const array = [1,2,3];
console.log(...array); // output : 1,2,3

// Copying an array
const originalArray = [1,2,3];
const copiedArray = [...originalArray];
console.log(copiedArray);  //output : [1,2,3]

// merging arrays
const firstArray = [1,2,3];
const secondArray = [4,5,6];
const finalArray = [ ...firstArray, ...secondArray];
console.log(finalArray);  // output : [1,2,3,4,5,6]

// passing multiple arguments to a function
const numbers = [1,2,3,4,5];
sum(...numbers);
function sum(a,b,c,d,e){
    console.log(a+b+c+d+e);
}
```
2. Rest operator is used in function parameters  to collect all remaining argument into an array.
```javascript
display(1,2,3,4,5,6);
function display(first,second,...restArguments){
    console.log(first);   // output : 1
    console.log(second);   // output : 2
    console.log(remainig); // output : [3,4,5,6]
}
```

## Array
- An array is a data type that allows you to store multiple values in a single variable
- It is used to structure the data in a better way
- Get methods (indexOf(), find(), filter(), Slice())
- Add methods (push(), concat())
- Remove methods (pop(), shift(), splice())
- Modify methods (map(), forEach())
- Other (join(), length(), sort(), reverse(), reduce(), some(), every())

- indexOf() method gets the index of specified element in the array
```javascript
const array = [1,2,3,4,5];
let a = array.indexOf(3);
console.log(a);    // output : 2
```


#### Difference between find() and filter() methods
- find() method get the first element that satisfies a condition.
```javascript
const array = [1,2,3,4,5];
let a = array.find((num)=> num % 2 === 0);
console.log(a);    // output : 2
```
- filter() method get an array of elements that satisfies a condition.
```javascript
const array = [1,2,3,4,5];
let a = array.find((num)=> num % 2 === 0);
console.log(a);    // output : [2, 4]
```

- slice() method get a subset of the array from start index to end index.(end is not included)
```javascript
const array = [1,2,3,4,5];
let e = array.slice(1,4);
console.log(a);    // output : [2,3,4]
```

#### Difference between push() and concat() methods
- both are used to add elements to array
- push() method will modify the original array itself
```javascript
const array = [1,2];
array.push(3,4);
console.log(array);    // output : [1,2,3,4]
```
- concat() method will create a new array and not modify the original array
```javascript
let array = [1,2];
let array2 = array.cancat(3,4);
console.log(array2);    // output : [1,2,3,4]     new
console.log(array);    // output : [1,2]     original
```
#### Difference between pop() and shift() methods
- array methods for removing elements
- pop() method will remove the last element of array
```javascript
let arr = [1,2,3,4];
let popped = arr.pop(1);
console.log(popped);   //  4
console.log(arr);   //  [1,2,3]

```
- shift() will remove the first element of array
```javascript
let arr = [1,2,3,4];
let shifted = arr.shift(1);
console.log(shifted);   //  1
console.log(arr);    //  [2,3,4]
```

#### what is the splice() method of an array ?
- The splice() is used to add, remove or replace elements in an array.
```javascript
array.splice(startIndex,deleteCount,...itemsToAdd);
```

```javascript
let letters = ['a','b','c','d'];
// add 'x' and 'y' at index 1
letters.splice(1,0,'x','y');
console.log(letters);
// output : ['a','x','y','b','c','d']
```
```javascript
let letters = ['a','b','c','d'];
// remove one element starting from 1 index 
letters.splice(1,1);
console.log(letters);
// output : ['a','y','b','c','d']
```
```javascript
let letters = ['a','b','c','d'];
// replace the element at index 2 with 'q'
letters.splice(2,1,'q');
console.log(letters);
// output : ['a','y','q','c','d']
```

#### Difference between slice() and splice() methods 
- The slice() method is used to get the subset of the array from the start index to the end index but end element is not included.
- The splice() is used to add, remove or replace elements of an array.

#### Difference between map() amd forEach() method
- Array methods for modification or iteration.
- The map() method is used when you want to modify each element of the array and create a new array with the modified values.
```javascript
let array =[1,2,3];
let mapArray = array.map((e) => e * 2);
console.log(mapArray);  // [2,4,6]
```
- The forEach() method is used when you want to perform some operation on each element of an array without creating a new array.
```javascript
let array =[1,2,3];
array.forEach((e) => {
    console.log(e * 2);
});
  // output : 2 4 6
console.log(array);  // output : [1,2,3]
```

#### How to sort and reverse and array ?
- Array can be sorted or reversed using sort() and reverse() method of array.
```javascript
let array = ['c','e','a','t'];
array.sort();
console.log(array);  //output : ['a','c','e','t']

array.reverse();
console.log(array);  // output : ['t','e','c','a']
```

#### What is Array Destructuring in JS ?
- Array destructuring allows you to extract elements from array and assigne them to individual  variables in asingle statement.
- Array destructuring is introduced in ECMA script
```javascript
const fruits = ['apple','orange'.'banana'];
const [firstfruit,secondfruit,thirdfruit] = fruits;
console.log(firstfruit);    // output : apple
console.log(secondfruit);   // output : orange
console.log(thirdfruit);    // output : banana
```

#### What are array-like objects in JS ?
- Array-like objects are objects which have indexed elements and a length property similar to arrays
but they may not have all methods of arrays like push(), pop() and others
- Example string, arguments, HTML collection
```javascript
// String
let str = 'Hello';
console.log(str);      // output : Hello
console.log(str.length);  // output : 5
console.log(str[0]);    // output : H
```
```javascript
// Arguments object
sum(1,2,3);
function sum(){
    console.log(arguments);  //output : [1,2,3]
    console.log(arguments.length);  //output :  3
    console.log(arguments[0]);  //output : 1
}
```
```javascript
// Accessing HTML collection
var boxes = document.getElementByClassName('box');
console.log(boxes.length);
console.log(boxes[0]);
```
#### How to convert an array-like object into an array ?
- There are 3 ways to convert an array-like object into an array
   1. Array.from()
```javascript
 var arrayLike = {0:'a',1:'b',2:'c',length:3};
 var array1 = Array.from(arrayLike);
 console.log(array1);    //output : ['a','b','c']
```
   2. Spread syntax(...)
```javascript
 var arrayLike = {0:'a',1:'b',2:'c',length:3};
 var array2 = (...arrayLike);
 console.log(array2);    //output : ['a','b','c']
```
   3. Array.prototype.slice.call()
```javascript
 var arrayLike = {0:'a',1:'b',2:'c',length:3};
 var array3 = Array.prototype.slice.call(arrayLike);
 console.log(array3);    //output : ['a','b','c']
```

## What is loop ? what are type of loops in JS ?
- loop is a programming way to run a peice of code repeatedly until a certain condition is met
- Types of loop
   1. for
   - for loop allows to iterate a block of code a specific number of time.
```javascript
for(i = 0; i < 5; i++){
    console.log(i);
}
//  output : 0,1,2,3,4
```
   2. while
   - while loop excute a block of code while a certain condition is true
```javascript
let j = 5;
while(j<5){
    console.log(j);
    j++;
}
```
   3. do-while
- do while loop is similar to the while loop except that the block of code is executed at least once even if the condotion is false.
```javascript
let k=0;
do{
    console.log(k);
    k++;
}while(k>1);  // output : 0
```
   4. for...of
```javascript

```
   5. for...in
```javascript

```

#### Difference between break and continue statement 
- break statement is used to terminate the loop
```javascript
for(let i=1; i<= 5; i++){
    if(i=== 3){
        break;
    }
    console.log(i);
}
//  output : 1 2
```
- continue statement is used to skip the current iteration of the loop and move on to the next iteration.
```javascript
for(let i=1; i<= 5; i++){
    if(i=== 3){
        continue;
    }
    console.log(i);
}
//  output : 1 2 4 5
```

#### Difference between for and for...of loop
- for loop is sligthly more complex having more lines of code whereas for of is much simpler and better for iterating arrays.
```javascript
let arr = [1,2,3];
for(let i=0; i<= arr.length; i++){

    console.log(arr[i]);
}
//  output : 1 2 3
```
```javascript
// works for arrays and objects only.
let arr = [1,2,3];
for(let val of arr){

    console.log(val);
}
//  output : 1 2 3
```

#### Difference between for..of and for..in loop

- for...of loop is used to loop through the values of object like array and string
- allows to access value directly without having to use index
```javascript
let arr = [1,2,3];
for(let val of arr){
    console.log(val);
}
//output : 1 2 3
```

- for...in loop is used to loop through the  properties of an object
- allows you to iterate over the keys of an object.
- use keys as index.
```javascript
const person = {
    name : "Arati",
    role : "Frontend Developer"
};
for(let  key in person){
    console.log(person[key]);
}
//output : Arati Frontend Developer
```

#### What is forEach method ?
- forEach is a method available on array or object that allows you to iterate over each element of the array and perform some action on each element.

```javascript
const arr = [1,2,3];
array.forEach(function(item){
    console.log(item)
});
// output :  1 2 3   
```
```javascript
const person={
    name : "arati",
    role : "Developer"
};
Object.value(person).forEach(value => {
    console.log(value);
});
// output :  arati Developer
```

#### When to use for...of loop and when to use forEach() method in application ?
-   for..of loop is suitable when you need more control over the loop, such as using break statement or continue statement inside.
- if we use break statement inside forEach loop we get Illigal break statement error
- forEach method iterate over each element of an array and perform some action on each element.


##  Functions :
#### What are the functions in JS and types of functions ?
- A function is reusable block of code that perform a specific task.
- here is the list of types of functions

1. Named function 
- used for big and complex logic
- use it when you want to reuse one function at multiple places
```javascript
function sum(a,b){
    return a+b;
};
console.log(sum(2,5));
// output : 7
```

2. Anonymous function
- used for small logic
- use it when you want to use a function at single place
```javascript
console.log(function(a,b){
    return a*b;
}(2,3));

// output : 6
```

3. Function expression
- An anonymous function is assigned to a variable
- this can be named or anonymous but mostly they are used with anoonymous functions only
```javascript
const add = function(a,b){
    return a+b;
};
console.log(add(2,3));
// output : 5
```

4. Arrow function
- shorter way of definig a function
```javascript
const add = (a,b) => a+b ;
console.log(add(2,3));
// output : 5
```
5. IIFE
6. Callback function
- A callback function is a function that is passed as an argument to another function.
```javascript
function add(x,y){
    return x+y;
}
function display(x,y,operation){
    var result = operation(x,y);
    console.log(result);
}
display(3,4,add);

// display(3,4,multiply);
// display(3,4,subtract);
// display(3,4,divide);
```
7. Higher order function
- take one or more function as argument or return a function as result
- above both are higher order function
first takes function as an argumnet
```javascript
function  hof(func){
    func(); 
}

hof(sayHello);
function sayHello(){
    console.log("Hello!");
}

// output : "Hello!"
```
second return a function
```javascript
function createAdder(number){
    return function(value){
        return value + number;
    };
}

const addFive =  createAdder(5);

console.log(addFive(2));
// output : 7
```

#### What is the difference between arguments and parameters ?
- Parameters are the placeholders defined in the function declaration
```javascript
// a and b are parameters
function sum(a,b){
    console.log(a+b);
}
```
- Argumnets are the actual values passed to a function when it is called
```javascript
// 2 and 3 are arguments
sum(2,3);
```

#### What is the use of event handling in JS ?
- Event handling is the process of responding to users action on webpage.
- The addEventListner method in JS allows attach an event name with function you want to perform on it
```javascript
<button id="myButton">click</button>

const button = document.getElementById('myButton');

button.addEventListner('click',function(){
   alert("button clicked!");
});
```
- Event types : click, mouseover, keydown, keyup, submit, focus, blur, change, load, resize

#### What are First Class fucntion in JS ?
- A programming language is said to have First-Class functions if functions in that language are treated like other variables.
- function expression concept in javascript makes First Class function.

#### What are pure and inpure function in JS ?
- Pure function is the function which produce the same output for the same input.
- can not have side effect 
```javascript
function add(a,b){
   return a+b;
}
console.log(add(2,3));
```

- An impure function can produce different output for same input
- can have side effects
```javascript
let total = 0;
function addTototal(value){
    total += value;
    return total;
}
console.log(addTototal(5)); 
```

#### What is function Currying in JS ?
- Currying in JS transforms afunction with multiple argument  into a nested series of functions, each taking a single argument.


#### What are call, apply and bind in JS ?
- These methods provide a way to manipulate the this value and pass argumnet to function.
- call() accepts arguments individually, separated by commas, while apply() accepts arguments as an array.
- call() and apply() execute the function immediately, while bind() returns a new function that needs to be invoked separately
1. call() method
```javascript
const person={
    firstName : "Peter",
    lastName : "Jones"
};
function greet(city,country){
    console.log(`Hello, ${this.firstName} ${this.lastName} from ${city} ${country}`);
}
greet.call(person,"New York","USA");
// output : Hello, Peter Jones from New York USA

```
```javascript
const person={
    firstName : "Peter",
    lastName : "Jones"
};
function greet(city,country){
    console.log(`Hello, ${this.firstName} ${this.lastName} from ${city} ${country}`);
}
greet.apply(person,["New York","USA"]);
// output : Hello, Peter Jones from New York USA
```
```javascript
const person={
    firstName : "Peter",
    lastName : "Jones"
};
function greet(city,country){
    console.log(`Hello, ${this.firstName} ${this.lastName} from ${city} ${country}`);
}
const boundGreet = greet.bind(person,"New York","USA");

boundGreet(); 
// output : Hello, Peter Jones from New York USA
```

#### What is a string ?
- string is a data type used to store and manipulate data
```javascript
var str = 'Hello';
```
#### What are string literals and interpolation in strings
- backticks are used to desfine template literals
```javascript
var myname = "Happy";
var str = `Hello ${myname}`;
console.log(str);
```
- here str is template literal 
- ${myname} is template and Hello is literal
- Some important string operations
   substr(), indexOf(), trim(), substring(), includes(), charAt(), replace(), search(), slice(),
   valueOf(), cancat(), split(), toLocaleLowerCase(), toString()


#### What is string immutability ?
- Strings in JS are considered immutable because you cannot modify the content of an existing string directly.
- Every time you modify string it takes new memory

#### how many ways you can concatenat strings ?
1. + operator
2. concat() method
3. template literals
4. join() method
```javascript
let str1 = 'Hello';
let str2 = 'World';
let strings = [str1,str2];
let result = strings.join('');
console.log(result);
// output : 
```

# DOM and Difference between HTML and DOM
- A tree like representation of a webpage that allows programming languages like JS to dynamically interact with and modify pages structure, content and style.
- methods to select DOM elements
  1. getElementById()
  2. getElementByClassname()
  3. getElementByTagName()
  4. getElementByName()
  5. querySelector
  6. querySelectorAll

- modifying element attributes and properties
  1. textContent
  2. innerHTML
  3. setAttribute(name,value)
  4. removeAttribute(name)
  5. style.property

- creating and appending elements
  1. createElement(tagName)
  2. appendChild(node)
  3. cloneNode(deep)

- Removing element
  1. remove()
  2. removeChild()

- Adding and removing event listners
  1. addEventListner(type,listner)
  2. removeEventListner(type,listner)

#### what are selectors in JS ?
- Selector in JS help to get specific element from DOM based on IDs, class name or tag names
- example :
  1. getElementById()
  2. getElementByClassname()
  3. getElementByTagName()
  4. getElementByName()
  5. querySelector
  6. querySelectorAll

#### Difference between querySelector() and querySelectorAll()

```javascript
<body>
<div class="myClass">Element 1</div>
<div class="myClass">Element 2</div>
<div class="myClass">Element 3</div>
</body>

var element = document.querySelector('.myClass');
console.log(element.textContent);
// output : Element 1
// this returns the first element
```

```javascript
<body>
<div class="myClass">Element 1</div>
<div class="myClass">Element 2</div>
<div class="myClass">Element 3</div>
</body>

var elements = document.querySelectorAll('.myClass');
console.log(elements.textContent);
// output : Element 1, Element 2, Element 3
// this returns all element
```
#### What are the methods to modify elements properties and attributes ?
  1. textContent
  2. innerHTML
  3. setAttribute(name,value)
  4. removeAttribute(name)
  5. style.property
  6. classList.add()

#### What is the difference between innerHTML and textContent ?


```javascript
<body>
<div id="myElement1">Hello</div>
<div id="myElement2">World</div>
</body>
```

```javascript
var element1 = document.getElementById('myElement1');
element1.textContent = '<strong>Hello</strong>';
// output :  <strong>Hello</strong>
```
```javascript
var element1 = document.getElementById('myElement1');
element1.innerHTML = '<strong>Hello</strong>';
// output : Hello                 (in bold font)
```

#### How to add or remove properties of HTML element in the DOM using JS ?

```javascript
<div id="myElement">Hello</div>

var element = documnet.getElemetById("myElement");
element.setAttribute("data-info","new value");

// output
<div id="myElement" data-info="new value">Hello</div>
```

```javascript
<div id="myElement" data-info="new value">Hello</div>

var element = documnet.getElemetById("myElement");
element.setAttribute("data-info");

// output :
<div id="myElement">Hello</div>
```

#### How tp add and remove style from HTML elements in DOM using JS ?
```javascript
<div id="myElement">Hello world</div>

var element = documnet.getElmentById('myElement');
element.steProperty("color","red");
// this will modify the style of element
<div id="myElement" style="color : red;">Hello world</div>
```
```javascript
<div id="myElement">Hello world</div>

var element = documnet.getElmentById('myElement');
element.classList.add('highlight');
// output :
<div id="myElement" class="highlight">Hello world</div>

element.classList.remove('highlight');
// output
<div id="myElement">Hello world</div>


// there is one more
element.classList.toggle('highlight');
```

#### How to create new element in DOM using JS ? what is difference between createElement() and cloneNode() ?
- creating and appending elements
  1. createElement(tagName)
  2. appendChild(node)
  3. cloneNode(deep)

```javascript
   var newDiv = document.createElement('div');
   newDiv.textContent = "this is new div";
   document.body.appendChild(newDiv);

// output :
  <div>this is new div</div>
```
```javascript
<div id="parentElement">
<h1>Existing Element</h1>
</div>

var existingElement = document.getElementById('parentElement');
var clonedElement = existingElement.cloneNode(true);
clonedElement.textContent = "This is clone element";
document.body.appendChild(clonedElement);
// output :
<div id="parentElement">Cloned element  </div>
```

#### What is the difference between createElement() and createTextNode() ?
```javascript
var newDiv = document.createElement('div');
newDiv.textContent = "Newly created div";
documnet.body.appendChild(newDiv);
// output :
<div>Newly created div</div>
```
```javascript
<div id="parentElement">
<h1>Existing Element</h1>
</div>

var parentElement = documnet.getElemetById('parentElement');
var newText = documnet.createTextNode("This is some text");
parentElement.appendChild(newText);

// output :
<div id="parentElement">
<h1>Existing Element</h1>
"This is some text"
</div>
```

#### What is error handling in JS ?
- Error handling is the process of managing errors
```javascript
// try block contains the code that might throw an error
try{
    const result = someUndefinedVar + 10 ;
    console.log(result);
}catch(error){
    // catch block is where the error is handled
    console.log("An error occured",error.message);
}

// output :
// An error occured : someUndefindVar is not defined
```
#### what is the role of finlly block in JS ?
- finally block is used to execute some code irresoective of error.
```javascript
// try block contains the code that might throw an error
try{
    const result = someUndefinedVar + 10 ;
    console.log(result);
}catch(error){
    // catch block is where the error is handled
    console.log("An error occured",error.message);
}finally{
    // finally block to execute code regardless of wheather an error occured or not
    console.log("finally block is executed");
}

// output :
// An error occured : someUndefindVar is not defined
// finally block is executed
```
#### what is the purpose of throw statement in JS ?
- The throw statement stops the execution of current function and passes the error to the catch block of calling function.
```javascript
function userData(){
    try{
        validateUserAge(25);
        validateUserAge('invalid');
        validateUserAge(15);
    }catch(error){
        console.error("Error:",error.message);
    }
}

function validateUserAge(age){
    if(typeof age !== "number"){
        throw new Error("Age must be a Number");
    }
    console.log("User age is valid");
}
```

#### What is error propagation in JS ?
- Error propagation refers to the process of passing an error from one part of the code to another by using the throw statement with try catch
```javascript
function userData(){
    try{
        validateUserAge(25);
        validateUserAge('invalid');
        validateUserAge(15);
    }catch(error){
        console.error("Error:",error.message);
    }
}

function validateUserAge(age){
    if(typeof age !== "number"){
        throw new Error("Age must be a Number");
    }
    console.log("User age is valid");
}
```

#### what are the best practices for error handling ?
1. Always use try catch and handle errors appropriately
2. Use descriptive error messages
3. Avoid swallowing errors (never leave catch block empty)
4. Log the errors properly  
```javascript
try{

}catch(error){
    console.error("error message",error);
}
```

#### What are different types of error in JS ?
1. Syntax error
- missing paranthesis and similar
```javascript
console.log("this is the syntax error"
```

2. Reference error
- Using some variable without declaring or defining
```javascript
console.log(myVar);
// error :
//  myVar is not defined
```

3. Type error
```javascript
const number = 7;
console.log(number.toUpperCase());

// error : 
// number.toUpperCase() is not a function
```
4. range error
```javascript
const array = [1,2,3];
console.log(array[10]);

// error : 
// index 10 is out of bounds
```

## Objects
- An object is a data type that allows you to store key-value pairs
- properties of an object can be string, number, boolean, undefined, null, function, array and another object

#### In how many ways we can create an object ?
1. Object literals 
```javascript
var person = {
    name : "John",
    age : 24,
    role : "SOftware Developer"
};
console.log(person);
```
2. Object Constructor
```javascript
var person = new Object();
person.name = "Krish";
person.age = 20;
person.role = "Web Developer";
console.log(person);
```
3. Object.create() Method
```javascript
var person = {
    name : "",
    age : 0,
    role : ""
};
 
var men = Object.create(person);
men.name = "keshav";
men.age = 24;
men.role = "Developer";
```

#### What is the difference between an array and an object ?
1. Arrays
- collection of values
- denoted by square brackets
- ordered
```javascript
var arr = ["apple","banana","orange"];
```

2. Objects
- collection of key-value pair
- denoted by curly braces
- unordered
```javascript
var person={
    name : "Madhav",
    age : 25,
    role : "Software Developer"
};
```

#### How to add or modify or delete properties from an object ?
```javascript
var person ={};
// Adding properties
person.name = "Krish";
person.age = 20;
person.role = "Web Developer";

// modifying properties
person.age = 25;

// deleting properties
delete person.age;
```

#### What is the difference between dot notation and bracket notation ?
- both dot notation and bracket notation are used to access properties or method  of an object.
- dot notation is more popular and used for its simplicity
```javascript
const person = {
    name: 'happy',
    age : 35,
};
console.log(person.name);
console.log(person['name']);
```

- Limitation of dot noatation : In some scenarios bracket notation is the only option, such as when accessing properties when property name is stored in variable
```javascript
// Dynamically assgin property name to a variable 
var propertyName = 'age';
console.log(person[propertyName]);
// output : '35'

console.log(person.propertyName);
//output : undefined
```

#### What are some common methods to iterate over the properties of an object ?
- there are 4 ways
1. for...in loop
```javascript
const person = {
    name : "John",
    age :30,
};

for(let prop in person){
    console.log(prop + ": " + person[prop]);
}
// output :
     name : "John"   age :30
```

2. Object.keys() & forEach()
```javascript
const person = {
    name : "John",
    age :30,
};

Object.keys(person).forEach((prop)=>{
    console.log(prop + ": " + person[prop]);
});
// output :
     name : "John"  age :30
```

3. Object.values() & forEach()
```javascript
const person = {
    name : "John",
    age :30,
};

Object.values(person).forEach((value)=>{
    console.log(value + ": " + person[prop]);
});
// output :
     name : "John"  age :30
```

#### How do you check if a property exist in an object ?
1. in  operator
```javascript
var person = {
    name : "Harry",
    age : 24
};

console.log("name" in person);    // output : true
console.log("name" in person);    // output : false
```
2. hasOwnproperty() method
```javascript
var person = {
    name : "Harry",
    age : 24
};

console.log(person.hasOwnProperty('name'));    // output : true
console.log(person.hasOwnProperty('city'));    // output : false
```
3. Comparing with undefined
```javascript
var person = {
    name : "Harry",
    age : 24
};

console.log(person.name !== undefined);    // output : true
console.log(person.age !== undefined);    // output : false
```

#### How do you clone or copy an object ?
1. Using spread operator
```javascript
const originalObject = {
    name :"Happy",
    age : 30,
    city : Jalna
};
const clonedObject =  {...originalObject};
```
2. Using Object.assign()
```javascript
const originalObject = {
    name :"Happy",
    age : 30,
    city : Jalna
};
const clonedObject = Object.assign({},originalObject);
```
3. JSON.stringify() & JSON.parse()
```javascript
const originalObject = {
    name :"Happy",
    age : 30,
    city : Jalna
};
const clonedObject = JSON.parse(JSON.stringify(originalObject));
```

#### What is the difference between deep copy and shallow copy in JS ?
1. Shallow copy :
```javascript
conat person = {
  name : "Happy",
  age : 30,
  address : {
    city : "Jalna",
    country : "India"
  }
};
const shallowCopy = Object.assign({},person);
shallowCopy.address.city = 'Mumbai';
console.log(person.address.city);    // output : Mumbai
console.log(shallowCopy.address.city);    // output : Mumbai
```
2. deep copy
```javascript
conat person = {
  name : "Happy",
  age : 30,
  address : {
    city : "Jalna",
    country : "India"
  }
};
const shallowCopy = Object.assign({},person);
shallowCopy.address.city = 'Mumbai';
console.log(person.address.city);    // output : Jalna
console.log(shallowCopy.address.city);    // output : Mumbai
```

#### What is the set Object in JS ?
- The Set object is a collection of unique values, meaning that duplicate values are not allowed.
- Set provides methods for adding, deleting and checking the existance of value in the set.
```javascript
const uniqueNum = new Set();
uniqueNum.add(5);
uniqueNum.add(10);
uniqueNum.add(5);
console.log(uniqueNum);
// output : {5, 10}

console.log(uniqueNum.size);
// output : 2

console.log(uniqueNum.has(10));
// output : true

uniqueNum.delete(10);
console.log(uniqueNum.size);
// output : 1
```
- Set can be used to remove duplicate values from the arrays.
```javascript
let myarr = [1,2,3,4,3];
let myset = new Set(myarr);
let uniqueArr = [...myset];
conssole.log(uniqueArr);
// output : [1,2,3,4]
```

#### What is the Map object in JS ?
- The Map object is a collection of key-value pairs where each key can be of any type and each value can also be of any type
- Map maintains the order of key value pair

```javascript
const personDetails = new Map();
personDetails.set("name","Alice");
personDetails.set("age",30);

console.log(personDetails.get("name"));
// output : Alice
console.log(personDetails.has("age"));
// output : true

personDetails.delete("age");
console.log(personDetails.size);
// output : 1
```

#### What is the difference between Map and Object in JS ?
1. Map : 
- keys can be of any data type, including strings, numbers, objects, functions
- maintains the order of key-value pair 
- Useful when keys are of different types
    
2. Object : 
- keys are limited to strings and symbols
- No guaranteed order of keys
- Usefull when keys are strings or symbols
