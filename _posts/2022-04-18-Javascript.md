---
layout: post
title: JavaScript sample programs
comments: true
---

## 1. Example: Convert Date to Number

```js
// program to convert date to number
// create date
const d1 = new Date();
console.log(d1);

// converting to number
const result = d1.getTime();
console.log(result);
```

{: .box-note}
**Output**
Mon Nov 09 2020 10:52:32 GMT+0545 (Nepal Time)  
1604898452084

## 2. JavaScript Program to Write to Console
In this example, you will learn to write a JavaScript program that will allow you to write to the console.
Example: Using console.log()

```js
// program to write to console

// passing number 
console.log(8);

// passing string
console.log('hello');

// passing variable
const x = 'hello';
console.log(x);

// passing function
function sayName() {
    return 'Hello John';
}
console.log(sayName());

// passing string and a variable
const name = 'John';
console.log('Hello ' + name);

// passing object
let obj = {
    name: 'John',
    age: 28
}
console.log(obj);
```


{: .box-note}
**Output**  
8  
hello  
hello  
Hello John  
Hello John  
{  
  age: 28,  
  name: "John"  
}  



## 3. JavaScript Program to Remove All Whitespaces From a Text
In this example, you will learn to write a JavaScript program that will remove all whitespaces from a text.
To understand this example, you should have the knowledge of the following JavaScript programming topics:
JavaScript String split()
Javascript Array join()
JavaScript Regex

Example 1: Using split() and join()

```js
// program to trim a string

const string = '      Hello World       ';

const result = string.split(' ').join('');

console.log(result);
```


{: .box-note}
**Output**
HelloWorld  
In the above program,  
The split(' ') method is used to split the strings into individual array elements. ["", "", "", "", "", "", "Hello", "World", "", "", "", "", "", "", ""]  
The join('') method merges the array into a string.  

Example 2: Using Regular Expression
```js
// program to trim a string

function trimString(x) {

    const result = x.replace(/\s/g,'');
    return result

}

const result = trimString('    Hello World    ');
console.log(result);
```


{: .box-note}
**Output**  
HelloWorld



## 4. JavaScript Program to Get the Dimensions of an Image
In this example, you will learn to write a JavaScript program that will get the dimensions of an image.
Example: Get Dimensions of an Image
```js
// program to get the dimensions of an image

const img = new Image();

// get the image
img.src = '//cdn.programiz.com/sites/tutorial2program/files/cover-artwork.png';

// get height and width
img.onload = function() {
  console.log('width ' + this.width)
  console.log('height '+ this.height);
}
```


{: .box-note}
**Output**
width 1040  
height 922  
In the above program, new Image() constructor is used to create an image object.
The Image() constructor creates a new image element instance.


img.src is then used to add the image using an image URL source.
The img.onload() function is used to access the height and width of the image.

## 5. JavaScript Program to Pass a Function as Parameter
In this example, you will learn to write a JavaScript program that will pass a function as a parameter.
To understand this example, you should have the knowledge of the following JavaScript programming topics:
JavaScript Function and Function Expressions

Example: Function as Parameter
```js
// program to pass a function as a parameter

function greet() {
    return 'Hello';
}

// passing function greet() as a parameter
function name(user, func)
{

    // accessing passed function
    const message = func();

    console.log(`${message} ${user}`);
}

name('John', greet);
name('Jack', greet);
name('Sara', greet);
```


{: .box-note}
**Output**
Hello John  
Hello Jack  
Hello Sara  

In the above program, there are two functions: name() and greet().
The name() function takes two parameters.
The greet() function is passed as an argument to the name() function.

## 6. JavaScript Program to Implement a Queue
In this example, you will learn to write a JavaScript program that will implement a queue.
To understand this example, you should have the knowledge of the following JavaScript programming topics:
JavaScript Array push()
JavaScript Array shift()
JavaScript Methods and this Keyword

A queue is a data structure that follows First In First Out (FIFO) principle. The element that is added first is accessed at first. This is like being in a queue to get a movie ticket. The first one gets the ticket first.

Example: Implement Queue
```js
// program to implement queue data structure

class Queue {
    constructor() {
        this.items = [];
    }
    
    // add element to the queue
    enqueue(element) {
        return this.items.push(element);
    }
    
    // remove element from the queue
    dequeue() {
        if(this.items.length > 0) {
            return this.items.shift();
        }
    }
    
    // view the last element
    peek() {
        return this.items[this.items.length - 1];
    }
    
    // check if the queue is empty
    isEmpty(){
       return this.items.length == 0;
    }
   
    // the size of the queue
    size(){
        return this.items.length;
    }
 
    // empty the queue
    clear(){
        this.items = [];
    }
}

let queue = new Queue();
queue.enqueue(1);
queue.enqueue(2);
queue.enqueue(4);
queue.enqueue(8);
console.log(queue.items);

queue.dequeue();
console.log(queue.items);

console.log(queue.peek());

console.log(queue.isEmpty());

console.log(queue.size());

queue.clear();
console.log(queue.items);
```


{: .box-note}
**Output**
[1, 2, 4, 8]  
[2, 4, 8]  
8  
false  
3  
[]  



In the above program, the Queue class is created to implement the queue data structure. The class includes methods like enqueue(), dequeue(), peek(), isEmpty(), size(), and clear().
A Queue object is created using a new operator and various methods are accessed through the object.
Initially, this.items is an empty array.
The push() method adds an element to this.items.
The shift() method removes the first element from this.items.
The length property gives the length of this.items.


## 7. JavaScript Program to Implement a Stack
In this example, you will learn to write a JavaScript program that will implement a stack.
To understand this example, you should have the knowledge of the following JavaScript programming topics:
JavaScript Array push()
JavaScript Array pop()
JavaScript Methods and this Keyword

The stack is a data structure that follows Last In First Out (LIFO) principle. The element that is added at last is accessed at first. This is like stacking your books on top of each other. The book that you put at last comes first.

Example: Implement Stack
```js
// program to implement stack data structure
class Stack {
    constructor() {
        this.items = [];
    }
    
    // add element to the stack
    add(element) {
        return this.items.push(element);
    }
    
    // remove element from the stack
    remove() {
        if(this.items.length > 0) {
            return this.items.pop();
        }
    }
    
    // view the last element
    peek() {
        return this.items[this.items.length - 1];
    }
    
    // check if the stack is empty
    isEmpty(){
       return this.items.length == 0;
    }
   
    // the size of the stack
    size(){
        return this.items.length;
    }
 
    // empty the stack
    clear(){
        this.items = [];
    }
}

let stack = new Stack();
stack.add(1);
stack.add(2);
stack.add(4);
stack.add(8);
console.log(stack.items);

stack.remove();
console.log(stack.items);

console.log(stack.peek());

console.log(stack.isEmpty());

console.log(stack.size());

stack.clear();
console.log(stack.items);
```


{: .box-note}
**Output**
[1, 2, 4, 8]  
[1, 2, 4]  
4  
false  
3  
[]  


In the above program, the Stack class is created to implement the stack data structure. The class methods like add(), remove(), peek(), isEmpty(), size(), clear() are implemented.
An object stack is created using a new operator and various methods are accessed through the object.
Here, initially this.items is an empty array.
The push() method adds an element to this.items.
The pop() method removes the last element from this.items.
The length property gives the length of this.items.


## 8. JavaScript Program to Perform Function Overloading
In this example, you will learn to write a JavaScript program that will perform function overloading.
To understand this example, you should have the knowledge of the following JavaScript programming topics:
JavaScript if...else Statement
JavaScript Switch Statement
JavaScript Function and Function Expressions

In programming, function overloading refers to the concept where multiple functions with the same names can have different implementations. However, in JavaScript, if there are multiple functions with the same name, the function that is defined at the last gets executed.
The function overloading feature can be implemented in some other ways.

Example 1: Using if/else-if Statement
```js
// program to perform function overloading

function sum() {  
    
    // if no argument        
    if (arguments.length == 0) {  
        console.log('You have not passed any argument');  
    }

    // if only one argument 
    else if (arguments.length == 1) {  
        console.log('Pass at least two arguments');  
    }

    // multiple arguments
    else {
        let result = 0;
        let length = arguments.length;
    
        for (i = 0; i < length; i++) {  
            result = result + arguments[i];  
        }  
        console.log(result); 
    }  
}

sum();
sum(5); 
sum(5, 9);    
sum(1, 2, 3, 4, 5, 6, 7, 8, 9); 
```


{: .box-note}
**Output**
You have not passed any argument  
Pass at least two arguments  
14  
45  



In the above program, the overloading feature is accomplished by using the if/else...if statement.
In JavaScript, the arguments object is automatically available inside a function that represents the passed arguments to a function.
The multiple conditions are addressed to perform actions based on that particular condition.

Example 2: Using switch Statement
```js
// program to perform function overloading
function sum() {
    switch (arguments.length) {
    case 0:
        console.log('You have not passed any argument');
        break;
    case 1:
        console.log('Pass at least two arguments');
        break;
    default:
        let result = 0;
        let length = arguments.length;
    
        for (i = 0; i < length; i++) {  
            result = result + arguments[i];  
        }  
        console.log(result);
        break;
    }
}

sum();
sum(5); 
sum(5, 9);    
sum(1, 2, 3, 4, 5, 6, 7, 8, 9);
```


{: .box-note}
**Output**
You have not passed any argument    
Pass at least two arguments    
14    
45    

In the above program, the switch statement is used to accomplish the function overloading functionality. Different conditions result in different actions to be performed.  
Share on:  




## 9. JavaScript Program to Generate a Range of Numbers and Characters
In this example, you will learn to write a JavaScript program that will generate a range of numbers and characters by passing the upper and lower bounds.  
To understand this example, you should have the knowledge of the following JavaScript programming topics:  
JavaScript String fromCharCode()  
JavaScript String charCodeAt()  
JavaScript Array map()  
JavaScript Generators  

Example: Generate Range of Characters
```js
// program to generate range of numbers and characters
function* iterate(a, b) {
  for (let i = a; i <= b; i += 1) {
    yield i
  }
}

function range(a, b) {
    if(typeof a === 'string') {
        let result = [...iterate(a.charCodeAt(), b.charCodeAt())].map(n => String.fromCharCode(n));
        console.log(result);
    }
    else {
        let result = [...iterate(a, b)];
        console.log(result);
    }
}

range(1, 5);
range('A', 'G');
```


{: .box-note}
**Output**
[1, 2, 3, 4, 5]    
["A", "B", "C", "D", "E", "F", "G"]    

In the above program, a range of numbers and characters is generated between the upper and the lower bounds.  
The iterate generator function is used to iterate through lower and upper bounds.  
The spread syntax ... is then used to include all the elements returned by the iterate function.  
The charCodeAt() method takes in an index value and returns an integer representing its UTF-16 (16-bit Unicode Transformation Format) code.  
The map() method iterates through all the array elements.  
The fromCharCode() method converts Unicode values into characters.  


## 10. JavaScript Program to Pass Parameter to a setTimeout() Function

In this example, you will learn to write a JavaScript program that will pass a parameter to a setTimeout() function.

To understand this example, you should have the knowledge of the following JavaScript programming topics:

JavaScript Function and Function Expressions
Javascript setTimeout()
The setTimeout() method executes a block of code after the specified time. The method executes the code only once.

The commonly used syntax of JavaScript setTimeout is:

setTimeout(function, milliseconds);
Its parameters are:

function - a function containing a block of code
milliseconds - the time after which the function is executed
Example 1: Passing Parameter to setTimeout
```js
// program to pass parameter to a setTimeout() function

function greet() {
    console.log('Hello world');
}

// passing parameter
setTimeout(greet, 3000);
console.log('This message is shown first');
```

{: .box-note}
**Output**
This message is shown first  
Hello world  

In the above program, the greet() function is passed to the setTimeout().    

The greet() function then gets called after 3000 milliseconds (3 seconds).  

Hence, the program displays the text Hello world only once after 3 seconds.  

Example 2: Passing Parameter to Function
```js
// program to pass parameter to function in setTimeout()
function greet(x, y) {
    console.log(x);
    console.log(y);
}

// passing parameter
setTimeout(greet, 3000, 'hello', 'world');
console.log('This message is shown first');
```


{: .box-note}
**Output**
This message is shown first  
hello  
world  

In the above program, additional parameters x and y are required in the greet() function.  

When calling the setTimeout() function, additional arguments 'hello' and 'world' are passed which are used by the greet() function.


## 11. JavaScript Program To Work With Constants

In this example, you will learn to write a JavaScript program to work with constants.

To understand this example, you should have the knowledge of the following JavaScript programming topics:

JavaScript Variables and Constants
Example: Work With Constants
```js
// program to include constants

const a = 5;
console.log(a);

// constants are block-scoped
{
    const a = 50;
    console.log(a);
}
console.log(a);

const arr = ['work', 'exercise', 'eat'];
console.log(arr);

// add elements to arr array
arr[3] = 'hello';
console.log(arr);

// the following code gives error
// changing the value of a throws an error
// uncomment to verify
// a = 8;

// throws an error
// const x; 
```

{: .box-note}
**Output**
5  
50  
5  
["work", "exercise", "eat"]  
["work", "exercise", "eat", "hello"]  

JavaScript ES6 has introduced the const keyword to work with constants. const denotes that the reference to value is constant and cannot be changed.

For example,

const a = 5;
a = 44; // throws an error
Constants are block-scoped. Hence the variable defined inside a block represents a different value than the one outside. For example,
```js
{
    const a = 50;
    console.log(a); // 50
}

console.log(a); // 5
```

The arr array value is changed and a new element is added. In array, the values can be changed. However, the array reference cannot be changed. For example,

```js
const arr = ['work', 'exercise', 'eat'];
arr[3] = 'hello';
```
Also, the constant should be initialized. You cannot just declare a constant. For example,

const x;
// SyntaxError: const declared variable 'x' must have an initializer.

## 12. JavaScript Program to Check If a Variable is of Function Type

In this example, you will learn to write a JavaScript program that will check if a variable is of function type.

To understand this example, you should have the knowledge of the following JavaScript programming topics:

JavaScript typeof Operator  
Javascript Function call()  
Javascript Object toString()  
Example 1: Using instanceof Operator  

```js
// program to check if a variable is of function type

function testVariable(variable) {
      
    if(variable instanceof Function) {
        console.log('The variable is of function type');
    }
    else {
        console.log('The variable is not of function type');
    }
}

const count = true;
const x = function() {
    console.log('hello')
};

testVariable(count);
testVariable(x);
```


{: .box-note}
**Output**
The variable is not of function type  
The variable is of function type  
In the above program, the instanceof operator is used to check the type of variable.  

Example 2: Using typeof Operator
```js
// program to check if a variable is of function type

function testVariable(variable) {
      
    if(typeof variable === 'function') {
        console.log('The variable is of function type');
    }
    else {
        console.log('The variable is not of function type');
    }
}

const count = true;
const x = function() {
    console.log('hello')
};

testVariable(count);
testVariable(x);
```

{: .box-note}
**Output**
The variable is not of function type
The variable is of function type
In the above program, the typeof operator is used with strict equal to === operator to check the type of variable.

The typeof operator gives the variable data type. === checks if the variable is equal in terms of value as well as the data type.

Example 3: Using Object.prototype.toString.call() Method
```js
// program to check if a variable is of function type

function testVariable(variable) {
      
    if(Object.prototype.toString.call(variable) == '[object Function]') {
        console.log('The variable is of function type');
    }
    else {
        console.log('The variable is not of function type');
    }
}

const count = true;
const x = function() {
    console.log('hello')
};

testVariable(count);
testVariable(x);
```

{: .box-note}
**Output**
The variable is not of function type  
The variable is of function type  
The Object.prototype.toString.call() method returns a string that specifies the object type.  

## 13. JavaScript Program to Validate An Email Address

In this example, you will learn to write a JavaScript program that will validate an email address.

To understand this example, you should have the knowledge of the following JavaScript programming topics:

JavaScript Regex  
JavaScript Function and Function Expressions  
JavaScript if...else Statement  
Example: Using Regex  

```js
// program to validate an email address

function validateEmail(email_id) {
    const regex_pattern =      /^(([^<>()[\]\\.,;:\s@\"]+(\.[^<>()[\]\\.,;:\s@\"]+)*)|(\".+\"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
    
    if (regex_pattern.test(email_id)) {
        console.log('The email address is valid');
    }
    else {
        console.log('The email address is not valid');
    }
}

validateEmail('abc123@gmail.com');
validateEmail('hello@com');
```
{: .box-note}
**Output**
The email address is valid  
The email address is not valid  
In the above program, the regular expression pattern  

/^(([^<>()[\]\\.,;:\s@\"]+(\.[^<>()[\]\\.,;:\s@\"]+)*)|(\".+\"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/
checks if an email address is valid or not.  

The test() method returns true if there is a match in the string with the regex pattern.

The regular expression (regex) describes a sequence of characters used for defining a search pattern.