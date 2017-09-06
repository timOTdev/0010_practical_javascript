# Practical JavaScript
## By Gordon Zhu
### Started 9/4/2017

# Introduction
## What is Practical JavaScript?
> If you've been a victim of boring tutorials that never teach you how to build anything, help save someone from the same fate by sharing Practical JavaScript.
- Courses out there are not teaching you practical application of JavaScript
- Most courses only teach you syntax and features 
- For example, a writing course teaches you only grammar but doesn't force you to write
- This course focuses on a single project and increases in difficulty

## The voice in your ear
> If you've experienced the struggle, take a second and help out by sharing Practical JavaScript.
- Gordon Zhu is founder at Watch and Code
- Studied business in college and does not have CS background
- Self-taught but initally had a lot of doubts
- Started with beginner resources but was frustrating
- Lots of tutorials were buggy or out of date
- There's a huge leap in logic with courses
- No one to ask for help even in the course

## Is this course right for you?
> If you like what you see, join the [Facebook group](https://www.facebook.com/groups/514043678767094/) to get updates and info about upcoming live office hours. Also, take a second and help out by sharing Practical JavaScript wherever you hang out online.
- Course designed for total beginners
- Also useful intermediate/advance developers because helps fills in knowledge gaps
- We are focusing on plain javascript
- We are making a basic to do list application
- [Project to build](todomvc.com/examples/vanillajs/)  
- [Source Code](https://github.com/tastejs/todomvc/tree/gh-pages/examples/vanillajs)

## What you'll build
- We are going to build a to do list with plain JavaScript
- We are going to look at an outline of how we are building
- User Stories:
    1. You can add items
    2. Tells how many items you have left to do
    3. An all item complete button
    4. Delete button
    5. Clear completed button
    6. All, active, completed filter toggle

## The development process
> The ability to break apart features into bite-sized requirements is one of the most important skills you can learn. You'll see this kind of thinking throughout Practical JavaScript.
- There will be different versions that implement new code to improve our app

# Support
## Getting Help
> There are a bunch of ways to get help as you're taking the course.
    You can ask your question during [live office hours](http://watchandcode.com/courses/practical-javascript/lectures/957331).
    You can ask questions in the [Watch and Code Facebook group](https://www.facebook.com/groups/514043678767094/).
    You can ask questions in the comments below each video.
If you're in the premium membership, you get some additional options.
    You can chat with me and other students in the members-only Slack channel.
    You can email me at gordon@watchandcode.com.

## Live office hours every week
> I hold live office hours on Google Hangouts every week. To get more information, submit questions, and RSVP for the next one, join the Watch and Code Facebook group. Use the link below to request access:
https://www.facebook.com/groups/514043678767094/
I also answer student questions and post updates about new material in the group, so it's the best way to keep up with new things about the course.

# Tools
## Track your progress
- You have to hit "Complete and continue" to track your progress

## Get Google Chrome
> If you like what you see, join the [Facebook group](https://www.facebook.com/groups/514043678767094/) to get updates and info about upcoming live office hours. Also, take a second and help out by sharing Practical JavaScript wherever you hang out online.
- It has good dev tools, everyone uses it, and well known

## Get Plunker
- [Plunker](plnkr.co) helps you save your code.

# Version 1 - Arrays
## Requirements
1. It should have a place to store todos
2. It should have a way to display todos
3. It should have a way to add new todos
4. It should have a way to change a todo
5. It should have a way to delete a todo

## It should have a place to store todos
- Opened chrome console to work
- Items should be surrounded by quotes
- A list should be surround by brackets, this is an array

**How do we access the array?**
- We store it in a variable  
``` 
var todos = ['item 1', 'item 2', 'item 3'];
todos // ["item 1", "item 2", "item 3"];
```

## It should have a way to display todos
- We use console.log() to print the to do items
```
console.log('hello there') // hello there
console.log('hello there, 'gordon') // hello there gordon

var todos = ['item 1', 'item 2', 'item 3']
console.log(todos) // ["item 1", "item 2", "item 3"]
console.log('My Todos:',todos) // My ToDos: ["item 1", "item 2", "item 3"]
```
- Notice that we don't put the todos in quotes inside the console.log
- This is because it is a variable

## It should have a way to add new todos
- Remember that "todos" was a variable
- We use .push() to add to an array
```
todos.push('item 4') // 4, means 4 items in the array
todos // ["item 1", "item 2", "item 3", "item 4"] 
```

## It should have a way to change a todo
- We use todos[] to target the items in an array
- Values start at 0 initially, not 1
```
var todos = ['item 1', 'item 2', 'item 3']
todos[0] // "item 1"
todos[1] // "item 2"
todos[2] // "item 3"
todos[3] // undefined
```
**How do we change an item?**
- We target that item and use equal sign
```
todos[0] = 'item 1 updated'
todos // ["item 1 updated', 'item 2', 'item 3'"]
```

## It should have a way to delete a todo
- We use splice() to cut out an item
- We start with where we want to start the deletion and end IE todos.splice(0, 1)
```
todos.splice(0, 1) // ["item 1 updated"]
todos // ['item 2', 'item 3'"]
```

## Review
- We learned about using variables
```
var todos = ['item 1', 'item 2', 'item 3']
todos // ["item 1", "item 2", "item 3"]
```
- We learned about console.log
```
console.log('My todos:', todos) // My Todos: ["item 1", "item 2", "item 3"]
```
- We learned about .push()
```
todos.push('new todo')
```
- We learned about accessing items in an array and changing
```
// Changing the first item
todos[0] = 'Changed!'
```
- We learned about .splice()
```
todos.splice(0, 1)
```
# Version 2 - Functions
## Functions are just recipes
- Pretend that we have a restaurant and we need to keep recipes
- It helps save us time by making functions reusable
```
// Written in pseudocode
makeTurkeySandwich
    Get one slice of bread.
    Add turkey.
    Put a slice of a bread on top.

// Written in JavaScript
function makeTurkeySandwich() {
    Get one slice of bread;
    Add turkey;
    Put a slice of a bread on top;
}

// To run the function
makeTurkeySandwich()
```

## Customizing functions
- If you have many recipes, some of the ingredients are repetitive
- We want to write recipes one time and not have 8 different ones for each topping
```
// Pseudocode
// What type of meat?
makeSandwichWith _____ 
    Get one slice of bread.
    Add _____.
    Put a slice of a bread on top.

// JavaScript
// Used filling as a parameter
// An argument is when you add ham for example
function makeSandwichWith(filling) {
    Get one slice of bread;
    Add filling;
    Put a slice of a bread on top;
}

// To run the function
makeSandwichWith_____ // Pseudocode
makeSandwichWith(ham) // JavaScript
```

## More on customizing functions
- A small observation: when you call sayHiTo('gordon'), think that it is setting person = 'gordon'
```
function sayHiTo(person) {
    console.log('hi', person);
}

sayHiTo('gordon') // hi gordon
```
## Requirements
1. It should have a function to display todos
2. It should have a function to add todos
3. It should have a function to change todos
4. It should have a function to delete todos

## It should have a function to display todos
- We need some data to work with
- In Chrome, you have to hit shift + enter to go to next line
- JS convention to lowercase first letter of word, and uppercase first letter of second word

```
var todos = ['item 1', 'item 2', 'item 3']

function displayTodos() {
    console.log('My todos:', todos);
}

displayTodos() // My todos: ["item 1", "item 2", "item 3"]
```
## It should have a function to add new todos
- Now we want to add new todos
- Variable todos and function displayTodos() are still there
- You can push up arrow to go to previous commands you have typed
```
function addTodo() {
    todos.push('new todo');
}

// Adding 1st todo
addTodo()
todos // ["item 1", "item 2", "item 3", "new todo"]
displayTodos() // My todos: ["item 1", "item 2", "item 3", "new todo"]

// Adding 2nd todo
addTodo()
todos // ["item 1", "item 2", "item 3", "new todo", "new todo"]
displayTodos() // My todos: ["item 1", "item 2", "item 3", "new todo", "new todo"]
```

- Now adding displayTodos() to run in the function automatically
```
function addTodo() {
    todos.push('new todo');
    displayTodos();
}

addToDo() // My todos: ["item 1", "item 2", "item 3", "new todo", "new todo", "new todo"]
```

- Now we add a parameter to the function
- So that means we have to add an argument when we call the function
- Remember that passing the argument 'hello there' is essentially setting the todo parameter equal to "hello there"
```
function addTodo(todo) {
    todos.push(todo);
    displayTodos();
}

addTodo('hello there') // My todos: ["item 1", "item 2", "item 3", "new todo", "new todo", "new todo", "hello there"]
```

## It should have a function to change a todo
- In version 1, we targetted items in array by using numbers
- This won't work in version 2
- Instead, we are using 2 parameters
```
// V1 function
function changeTodo() {
    todos[0] = 'some new value';
}

// V2 function
function changeTodo(position, newValue) {
    todos[position] = newValue;
}
```
- Let's look at our example again
```
displayTodos() // My todos: ["item 1", "item 2", "item 3", "new todo", "new todo", "new todo", "hello there"]

changeTodo(0, 'changed') 
displayTodos() // My todos: ["changed", "item 2", "item 3", "new todo", "new todo", "new todo", "hello there"]
```
- Now we add the displayTodos() call
```
// V2 function
function changeTodo(position, newValue) {
    todos[position] = newValue;
    displayTodos();
}
```
- Now we are going to change item 1 again
```
changeTodo(0, 'changed again') // My todos: ["changed again", "item 2", "item 3", "new todo", "new todo", "new todo", "hello there"]

```

## It should have a function to delete a todo
- In version 1, we used splice()
```
// V1 function
function deleteTodo() {
    todos.splice(0, 1);
}

// V2 function
function deleteTodo(position) {
    todos.splice(position, 1);
    displayTodos();
}
```

- Now we want to delete the 1st item
```
displayTodos() // My todos: ["item 2", "item 3", "new todo", "new todo", "hello there"]

deleteTodo(0) // My todos: ["item 3", "new todo",  "new todo", "hello there"]
deleteTodo(2) // My todos: ["item 3", "new todo", "hello there"]
```

## Review
- We can write comments for humans to read, computer will ignore these
- We use two forward slashes
- It is good practice to play around with the code to understand
- Copy the code below into the console and try out the functions
```
// It should have a function to display todos
var todos = ['item 1', 'item 2', 'item 3'];

function displayTodos() {
    console.log('My todos:', todos);
}

// It should have a function to add todos
function addTodo() {
    todos.push('new todo');
    displayTodos();
}

// It should have a function to change todos
function changeTodo(position, newValue) {
    todos[position] = newValue;
    displayTodos();
}

// It should have a function to delete todos
function deleteTodo(position) {
    todos.splice(position, 1);
    displayTodos();
}
```

# Version 3 - Objects
## What is an Object?
- Objects are used to group related data and functions together
- Use curly braces to show it's an object
- Each item is called a "property" and separated by comma
- Within each property, the value is separated by commas
- If it's text, you have to put quotes
- Then we set it to a variable to save it
```
var myComputer = {
    operatingSystem: 'mac',
    screenSize: '15 inches',
    purchaseYear: 2011,
}
```

- We can call the whole object or each property in the object
```
myComputer // Object {operatingSystem: "mac", screenSize: "15 inches", pucharseYear: 2011}

myComputer.operatingSystem // "mac"
myComputer.screenSize // "15 inches"
myComputer.purchaseYear // 2011

```

## Objects and functions
- You can place function in objects
- We can use the keyword "this" to reference the current object
- To say the name, we have to specify that with the name of the variable IE this.name
- We also call the sayName a "method", which is a function inside of an object
- You don't need to give a name to the function inside the object, it is an "anonymous" function.
```
var gordon = {
    name: 'Gordon',
    sayName: function() {
        console.log(this.name);
    },

}
```

## Using Plunker
- Reasons are using Plunker is that our code is getting longer and it saves our code
- "My plunks" are also different code files we saved

## Requirements
1. It should store the todos array on an object
2. It should have a displayTodos method
3. It should have an addTodo method
4. It should have a changeTodo method
5. It should have a deleteTodo method

## It should store the todos array on an object
```
var todoList = {
 todos: ['item1', 'item2', 'item 3'] 
};
```

## It should have a displayTodos method
- We used the "this" keyword in the code
```
// V2
function displayTodos() {
  console.log('My Todos:', todos);
}

// V3
var todoList = {
 todos: ['item1', 'item2', 'item 3'],
 displayTodos: function() {
   console.log('My Todos', this.todos);
 }
};
```

## It should have an addTodo method
```
// V2
function addTodo(todo) {
  todos.push(todo);
  displayTodos();
}

// V3
var todoList = {
 todos: ['item1', 'item2', 'item 3'],
 displayTodos: function() {
   console.log('My Todos', this.todos);
 },
 addTodo: function() {
  this.todos.push(todo);
  this.displayTodos();
 }
};
```
## It should have a changeTodo method
```
// V2
function changeTodo(position, newValue) {
  todos[position] = newValue;
  displayTodos();
}

// V3
var todoList = {
 todos: ['item1', 'item2', 'item 3'],
 displayTodos: function() {
   console.log('My Todos', this.todos);
 },
 addTodo: function() {
  this.todos.push(todo);
  this.displayTodos();
 },
 changeTodo: function(position, newValue) {
   this.todos[position] = newValue;
   this.displayTodos();
 }
};
```
## It should have a deleteTodo method
```
// V2
function deleteTodo(position) {
  todos.splice(poistion, 1);
  displayTodos();
}

// V3
var todoList = {
 todos: ['item1', 'item2', 'item 3'],
 displayTodos: function() {
   console.log('My Todos', this.todos);
 },
 addTodo: function() {
  this.todos.push(todo);
  this.displayTodos();
 },
 changeTodo: function(position, newValue) {
   this.todos[position] = newValue;
   this.displayTodos();
 },
 deleteTodo: function(position) {
   this.todos.splice(position, 1);
   this.displayTodos();
 }
};
```
## Review
- Notice how all our methods and data are organized in one object
- The tricky thing was to use the keyword "this"
- We used dot notation to reference different properties in the object
```
var todoList = {
 todos: ['item1', 'item2', 'item 3'],
 displayTodos: function() {
   console.log('My Todos', this.todos);
 },
 addTodo: function() {
  this.todos.push(todo);
  this.displayTodos();
 },
 changeTodo: function(position, newValue) {
   this.todos[position] = newValue;
   this.displayTodos();
 },
 deleteTodo: function(position) {
   this.todos.splice(position, 1);
   this.displayTodos();
 }
};
```

# Interlude - Success is the process
## Ability - Process * Time
- When you start, you compare yourself to other programmers
- Don't focus on things you can't change
- You can't change the amount of time someone has
- However, you can learn the process today and you can make the most of the time that you do have
- You might have a better process than a 10-year programmer
- Focus on the things you can control
- Make sure you understand things and make the connections
- Focus on fundamentals
- Learn [how to be great at asking coding questions](https://medium.com/@gordon_zhu/how-to-be-great-at-asking-questions-e37be04d0603)

## The most important part of your process
- You can read the article in the previous chapter
- People get stuck and can't ask the correct questions will stay stuck
- Move pass that by asking qood questions

- Asking questions in programming is difficult because it has many moving parts
- You want to be able to figure out things on your own as a skill
- If you can't figure something out with honest effort, then you ask your question