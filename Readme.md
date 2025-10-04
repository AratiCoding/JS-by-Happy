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
