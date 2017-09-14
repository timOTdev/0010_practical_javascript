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
- Each item is called a "property" and separated by a comma
- Within each property, the value is separated by a semicolon
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
myComputer // Object {operatingSystem: "mac", screenSize: "15 inches", purchaseYear: 2011}

myComputer.operatingSystem // "mac"
myComputer.screenSize // "15 inches"
myComputer.purchaseYear // 2011

```

## Objects and functions
- You can place function in objects
- We can use the keyword "this" to reference the current object
- To say the name, we have to specify that with the name of the variable IE this.name
- We also call the sayName a "method", which is a function inside of an object
- You don't need to give a name to the function inside the object, it is an "anonymous" function
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
- "My plunks" are different code files we saved

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
 addTodo: function(todo) {
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
- We used dot notation to reference different properties in the object IE this.todos.push()
```
var todoList = {
 todos: ['item1', 'item2', 'item 3'],
 displayTodos: function() {
   console.log('My Todos', this.todos);
 },
 addTodo: function(todo) {
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
- There are two factors: process and time
- You can't change the amount of time (experience) someone has
- However, you can learn the process today and you can make the most of the time that you do have
- Focus on the things you can control like the process
- You might have a better process than a 10-year programmer
- Make sure you understand things and make the connections
- Focus on fundamentals
- Learn [how to be great at asking coding questions](https://medium.com/@gordon_zhu/how-to-be-great-at-asking-questions-e37be04d0603)

## The most important part of your process
- Read the medium article as a guide
- People get stuck and can't ask the correct questions will stay stuck
- Move pass that by asking qood questions
- Asking questions in programming is difficult because it has many moving parts
- You want to be able to figure out things on your own as a skill
- If you can't figure something out with honest effort, then you ask your question

# Version 4 - Booleans
## Requirements
- Now we want to add objects in arrays instead of just text
- So now we have to properties in each object: the task and if task is completed
1. todoList.addTodo should add objects
2. todoList.changeTodo should change the todoText property
3. todoList.toggleCompleted should flip the completed property

## todoList.addTodo should add objects
- First, we want to add objects instead of text to the array
- Objects are able to hold more data than just text
- Here's an example of a Boolean
```
{
  todoText: 'item 1',
  completed: false // Boolean: true or false
}
```

- Now we format our code to create objects with text and a boolean
```
var todoList = {
 todos: [],
 displayTodos: function() {
   console.log('My Todos', this.todos);
 },
 addTodo: function(todoText) {
  this.todos.push({
    todoText: todoText, // the 2nd is the parameter
    completed: false
  });
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

todoList.addTodo("Code a project")
```

## todoList.changeTodo should change the todoText property
- We are now changing some parameter names to make it more intuitive
- Notice that we have to format the changeTodo code to follow the object structure
```
var todoList = {
 todos: [],
 displayTodos: function() {
   console.log('My Todos', this.todos);
 },
 addTodo: function(todoText) {
  this.todos.push({
    todoText: todoText, // the 2nd is the parameter
    completed: false
  });
  this.displayTodos();
 },
 changeTodo: function(position, todoText) {
   this.todos[position].todoText = todoText;
   this.displayTodos();
 },
 deleteTodo: function(position) {
   this.todos.splice(position, 1);
   this.displayTodos();
 }
};

todoList.changeTodo(0, "Code tomorow")
```

## todoList.toggleCompleted should flip the completed property
- Bang operator: !
- It means the opposite of whatever you type
```
!true // false
!false // true
```

- Remember the variable is constant, the value is what we are changing
- Notice we are asking the opposite of gordonBoolean in the 3rd line
```
var gordonBoolean = false; 
!gordonBoolean // true
gordonBoolean = !gordonBoolean; // true
```

- Now we continue with our project
- We basically added a new method called toggleCompleted
- This method flips values of the Boolean of true and false
```
var todoList = {
 todos: [],
 displayTodos: function() {
   console.log('My Todos', this.todos);
 },
 addTodo: function(todoText) {
  this.todos.push({
    todoText: todoText, // the 2nd is the parameter
    completed: false
  });
  this.displayTodos();
 },
 changeTodo: function(position, todoText) {
   this.todos[position].todoText = todoText;
   this.displayTodos();
 },
 deleteTodo: function(position) {
   this.todos.splice(position, 1);
   this.displayTodos();
 }
 toggleCompleted: function(position) {
     var todo = this.todos[position];
     todo.completed = !todo.completed;
     this.displayTodos();
 }
};

todoList.toggleCompleted() // true
```

## Review
- We change our array to objects
- We change property to change todos in an objects
- We learned about Boolean values and the bang operator

# Version 5 - Loops of Logic
## The for loop
- We are learning "for loops" so you can repeat a certain amount of codes multiple times
- In this example below, it stops at 2 and not 3
- In JavaScript, you can change many of the conditions in the examples below
```
// Pseudocode
i = 0               // Initialization
Say "hey" if i < 3  // Condition
Increase i by 1     // Expression

0 "hey"
1 "hey"
2 "hey"
3 // the conditions doesn't ask for equal to 3

// JavaScript

// "hey" x 3
// i = i + 1 is the same as i++
for (var i = 0; i < 3; i++) {
    console.log("hey");
}

// "hey" x 10
for (var i = 0; i < 10; i++) {
    console.log("hey");
}

// "hey" x 5
for (var i = 0; i < 10; i = i + 2) {
    console.log("hey");
}

// "hey" x 2
for (var i = 6; i < 10; i = i + 2) {
    console.log("hey");
}
```

## Looping over arrays
- Notice that "i" is a variable also
```
for (var i = 0; i < 3; i++) {
    console.log(i);
}
// 0, 1, 2
```

- We can also look at an array
```
var testArray = ['item 1', 'item 2', 'item 3'];
testArray[0] // "item 1"
testArray[1] // "item 2"
testArray[2] // "item 3"

for (var i = 0; i < 3; i++) {
    console.log(testArray[i]);
}
// item 1, item 2, item 3
```

- You can also specify the conditions to be more dynamic
- Here we set the condition to be "i < testArray.length":
```
for (var i = 0; i < testArray.length; i++) {
    console.log(testArray[i]);
}
```

- So for example if you want to print out all the items in an array
- This soft coding is helpful if your array changes in length IE i < testArray.length
- Hard coding would be setting a number IE i < 3
- This .length property will help make your code dynamic
```
for (var i = 0; i < 3; i++) {
    console.log(testArray[i]);
}
// item 1, item 2, item 3

testArray.push('extra item');
for (var i = 0; i < testArray.length; i++) {
    console.log(testArray[i]);
}
// item 1, item 2, item 3, extra item
```

## Requirements
1. displayTodos should show .todoText
2. displayTodos should tell you if .todos is empty
3. displayTodos should show .completed

## displayTodos should show .todoText
- Now we are going to adapt our code
```
var todoList = {
 todos: [],
 displayTodos: function() {
   for (var i = 0; i < this.todos.length; i++) {
     console.log(this.todos[i].todoText);
   }

todoList.addTodo('first');
todoList.addTodo('second');
}
```

## displayTodos should tell you if .todos is empty
- If our todo list is empty, print some text
- Otherwise, display the todo items
```
var todoList = {
    todos: [],
    displayTodos: function() {
        if (this.todos.length === 0) {
        console.log('Your todo list is empty!');
        } else {
        console.log('My Todos: ');
        for (var i = 0; i < this.todos.length; i++) {
            console.log(this.todos[i].todoText);
        }    
    }
}

todoList.displayTodos(); // Your todo list is empty!
todoList.addTodo('an item'); // My Todos: an item
todoList.deleteTodo(0); // Your todo list is empty!
```

## displayTodos should show .completed
- Now we want to show if an item is completed with (x), or ( ) if not completed
```
var todoList = {
    todos: [],
    displayTodos: function() {
        if (this.todos.length === 0) {
        console.log('Your todo list is empty!');
        } else {
        console.log('My Todos:');
        for (var i = 0; i < this.todos.length; i++) {
            if (this.todos[i].completed === true) {
                console.log('(x)', this.todos[i].todoText);
            } else {
                console.log('( )', this.todos[i].todoText);
            }
        }    
    }
}

todoList.addTodo('first'); // My Todos: ( ) first ( ) second
todoList.addTodo('second'); // My Todos: ( ) first ( ) second
todoList.toggleCompleted(1); // My Todos: ( ) first (x) second
todoList.toggleCompleted(1); // My Todos: ( ) first ( ) second
todoList.toggleCompleted(0); // My Todos: (x) first ( ) second
todoList.toggleCompleted(0); // My Todos: ( ) first ( ) second

todoList.addTodo('third'); // My Todos: ( ) first ( ) second ( ) third
todoList.addTodo('fourth'); // My Todos: ( ) first ( ) second ( ) third ( ) fourth
todoList.addTodo('fifth'); // My Todos: ( ) first ( ) second ( ) third ( ) fourth ( ) fifth
todoList.addTodo('sixth'); // My Todos: ( ) first ( ) second ( ) third ( ) fourth ( ) fifth ( ) sixth
todoList.toggleCompleted(5); // My Todos: ( ) first ( ) second ( ) third ( ) fourth ( ) fifth (x) sixth
todoList.toggleCompleted(2); // My Todos: ( ) first ( ) second (x) third ( ) fourth ( ) fifth (x) sixth
```

## Review
- We combined learning "for loops" and "if statements"

# Version 6 - Thinking in Code
## Requirements
1. .toggleAll: If everything's true, make everything false
2. .toggleAll: Otherwise, make everything true
- This includes if some if already checked or true
- It helps to think about the code ahead of time

## .toggleAll: If everything's true, make everything false
- We will basically loop through all the todos to see if everything is complete/true
- It will check the total todos in the list to the match equally with the same number of complete
- If both values are equal, then toggleAll function will mark all as incomplete/false
```
var todoList = {
 todos: [],
 displayTodos: function() {
   console.log('My Todos', this.todos);
 },
 addTodo: function(todoText) {
  this.todos.push({
    todoText: todoText, // the 2nd is the parameter
    completed: false
  });
  this.displayTodos();
 },
 changeTodo: function(position, todoText) {
   this.todos[position].todoText = todoText;
   this.displayTodos();
 },
 deleteTodo: function(position) {
   this.todos.splice(position, 1);
   this.displayTodos();
 }
 toggleCompleted: function(position) {
     var todo = this.todos[position];
     todo.completed = !todo.completed;
     this.displayTodos();
 }
 toggleAll: function() {
     var totalTodos = this.todos.length;
     var completed Todos = 0;

     // Get number of completed todos.
     for (var i = 0; i < totalTodos; i++) {
         if (this.todos[i].completed === true) {
             completedTodos++;
         }
     }

     // Case 1: If everything's true, make everything false
     if (completedTodos === totalTodos) {
         // Make everything false.
        for (var i =0; i < totalTodos; i++) {
            this.todos[i].completed = false;
        }
     }

    this.displayTodos();
 }
};
```

## .toggleAll: Otherwise, make everything true
- If you find yourself saying "otherwise", this is perfect for the else statement
- Here's where we are working on case 2:
```
var todoList = {
 todos: [],
 displayTodos: function() {
   console.log('My Todos', this.todos);
 },
 addTodo: function(todoText) {
  this.todos.push({
    todoText: todoText, // the 2nd is the parameter
    completed: false
  });
  this.displayTodos();
 },
 changeTodo: function(position, todoText) {
   this.todos[position].todoText = todoText;
   this.displayTodos();
 },
 deleteTodo: function(position) {
   this.todos.splice(position, 1);
   this.displayTodos();
 }
 toggleCompleted: function(position) {
     var todo = this.todos[position];
     todo.completed = !todo.completed;
     this.displayTodos();
 }
 toggleAll: function() {
     var totalTodos = this.todos.length;
     var completed Todos = 0;

     // Get number of completed todos.
     for (var i = 0; i < totalTodos; i++) {
         if (this.todos[i].completed === true) {
             completedTodos++;
         }
     }

     // Case 1: If everything's true, make everything false
     if (completedTodos === totalTodos) {
         // Make everything false.
        for (var i =0; i < totalTodos; i++) {
            this.todos[i].completed = false;
        }

    // Case 2: Otherwise, make evertyhing true
     } else {
         for (var i= 0; i < totalTodos; i++) {
             this.todos[i].completed = true;
         }
     }

    this.displayTodos();
 }
};
```
## Review
- We had a more complex behavior in this version
- We practiced a lot of "for loops"
- You should understand the whole project when assigned in the real world
- Then give it some pre-thought before you write the code

# Interlude - Data types and comparisons
## Data types overview
1. Objects (can be as complex as you want)
- {} // todoList, arrays, functions

2. Primitives (building blocks)
- String // 'Look at this string!'
- Number // 1, 2, 3, 4
- Boolean // true, false
- Undefined // value that hasn't been set yet
- Null // 'Nothing'

## Comparisons with primitives
- If it looks the same, it is generally the same
1. With strings
```
'gordon' === 'gordon'; // true
'gordon1' === 'gordon'; // false
```

2. Number
```
1 === 1 // true
1 === 2 // false
100 === 100 // true
```

3. Boolean
```
true === true // true
true === false // false
false === false // false
```

4. Undefined & Null
```
undefined === undefined // true
null === null // true
```

## Comparisons with objects
- Comparing objects is much different that primitives
- Some weird examples are below:
```
{} === {} // false
[1, 2, 3] === [1, 2, 3] // false
```

- We then compare 3 identical houses
- Using primitives, the analogy is the houses look the same
- With objects, it cares about the addresses of all the houses
- Another example:
```
// Identical Street
1001 Identical Street
1002 Identical Street
1003 Identical Street
```

- In JavaScript, each object is created a specific location in memory
- So it is only true if you're talking about the same location
- It doesn't matter that the data looks the same
```
// JavaScript
{} Memory address 1
{} Memory address 2
{} Memory address 3

var houseA = {};
houseA === houseA // true
```

## Review
1. Primitives (values)
- A comparison between all of these values is true
- It's comparing the value of the data
```
2
2
2
```

2. Objects (references)
- The values might be the same but the values are at different locations
- That's why they are not the same
```
{} Memory address 1
{} Memory address 2
{} Memory address 3
```
# Version 7 - HTML and the DOM
## Requirements
- Our app is reaching logic limit, now we are working on user experience
1. There should be a "Display todos" button and a "Toggle all" button in the app
2. Clicking "Display todos" should run todoList.displayTodos
3. Clicking "Toggle all" should run todoList.toggleAll

## HTML essentials
- HTML tags - defines how the element is displayed
- Elements are usually contained in an opening and closing tag
- The DOCTYPE tells the browser what version of HTML you are using
- <link> tags don't have closing tags
- It's better to not memorize, you'll learn as you go
- There are a ton of tags
- <html> is where all our codes go
- <head> is where you link all the local css and js files to run our page
- <body> is where all the text users will see when visiting your site
- <h1> to <h6> is how you show headings 
- <p> is the paragraph text

## What's the DOM?
- Means "document object model"
- It's what the browser's interpretation of your html file
- It uses the DOM to build the website
- You can right-click on the page and hit inspect
- We mainly use the DOM with just JavaScript but it is involved in other languages

## There should be a "Display todos" button and a "Toggle all' button in the app
- We are going to use the html to fulfill this requirement
- The buttons won't do anything yet, we will hook them later
```
<!DOCTYPE html>
<html>
    <head>
        <link rel="stylesheet" href="style.css">
        <script src="script.js"></script>
    </head>

    <body>
        <h1>Todo List</h1>

        <button id="displayTodosButton">Display Todos</button>
        <button>Toggle All</button>
    </body>
</html>
```
## Clicking "Display todos" should run todoList.displayTodos
- You can see the DOM by typing document in the JavaScript console
- There are methods on the document object to select specific elements
- We can use an **attribute** called id to select the specific button element
- Use console.log to test if your selectors are working
- Don't forget to put the script link at the bottom of body the html file
- We use .addEventListener to listen for events like clicks
```
// 1. We want to get access to the display todos button
var displayTodosButton = document.getElementById('displaysTodosButton');
console.log(displayTodosButton);

// 2. We want to run displayTodos method, when someone clicks the display todos button
displayTodosButton.addEventListener('click', function() {
    todoList.displayTodos();
});
```

## Clicking "Toggle all" should run todoList.toggleAll
- We need to add an id in the html
```
<!DOCTYPE html>
<html>
    <head>
        <link rel="stylesheet" href="style.css">
        <script src="script.js"></script>
    </head>

    <body>
        <h1>Todo List</h1>

        <button id="displayTodosButton">Display Todos</button>
        <button id="toggleAllButton">Toggle All</button>
    </body>
</html>
```

- Then add the button in javascript
- We also add an event listener for clicks
```
// 1. We want to get access to the display todos button
var displayTodosButton = document.getElementById('displaysTodosButton');
var toggleAllButton = document.getElementById('toggleAllButton');

// 2. We want to run displayTodos method, when someone clicks the display todos button
displayTodos.Button.addEventListener('click', function() {
    todoList.displayTodos();
});

toggleAllButton.addEventListener('click', function() {
    todoList.toggleAll();
})
```

## Review
- We learned new concepts
- Don't forget to put script tag at the end of the body
- We also learned how to add the id attribute
- There are a lot of tags and event listeners so don't go study them

# Interlude - Don't wonder about things the debugger can tell you
## todoList.displayTodos
- Debugging is the process of fixing codes that create errors
- We were manually debugging with just our eyes, there's a more efficient tool
- We do that by adding the line debugger;
- It will stop at that line where we added the debugger
- Now you can see all the objects defined
- You can also see more if you hover over the objects
- Use "step over next function call" to simulate the process running line by line
```
var todoList = {
    todos: [],
    displayTodos: function() {
        debugger;
        if (this.todos.length === 0) {
        console.log('Your todo list is empty!');
        } else {
        console.log('My Todos: ');
        for (var i = 0; i < this.todos.length; i++) {
            console.log(this.todos[i].todoText);
        }    
    }
}
```

## todoList.addTodo
- Now we are going to run debugger on the addTodo method
- There's also a "step into function call" that lets you go into the method
```
TodoList.addTodo('runnin the debugger');

addTodo: function(todoText) {
    debugger;
    this.todos.push({
    todoText: todoText, // the 2nd is the parameter
    completed: false
    });
    this.displayTodos();
},
```

## todoList.changeTodo
- Now we try debugger on changeTodo method
```
todoList.addTodo('Something that we want to change');
todoList.changeTodo(0, 'Changed happened!);

changeTodo: function(position, todoText) {
    debugger;
   this.todos[position].todoText = todoText;
   this.displayTodos();
 },
```

## todoList.deleteTodo
```
todoList.addTodo('delete this garbage');
todoList.deleteTodo(0);

deleteTodo: function(position) {
    debugger;
    this.todos.splice(position, 1);
    this.displayTodos();
}
```

## todoList.toggleCompleted
```
todoList.addTodo('to be toggled');
todoList.toggleCompleted(0);

toggleCompleted: function(position) {
    debugger;
    var todo = this.todos[position];
    todo.completed = !todo.completed;
    this.displayTodos();
}
```

## todoList.toggleAll
- This one is more thorough
- Run through Case 2 on your own
```
todoList.addTodo('this is true');
todoList.toggleCompleted(0);

 toggleAll: function() {
     debugger;
     var totalTodos = this.todos.length;
     var completed Todos = 0;

     // Get number of completed todos.
     for (var i = 0; i < totalTodos; i++) {
         if (this.todos[i].completed === true) {
             completedTodos++;
         }
     }

     // Case 1: If everything's true, make everything false
     if (completedTodos === totalTodos) {
         // Make everything false.
        for (var i =0; i < totalTodos; i++) {
            this.todos[i].completed = false;
        }

    // Case 2: Otherwise, make evertyhing true
     } else {
         for (var i= 0; i < totalTodos; i++) {
             this.todos[i].completed = true;
         }
     }

    this.displayTodos();
 }
};
```

## Use the debugger all the time
- This helps you spots problems with your code
- It helps you understanding your code

## Focus on understanding, not building from scratch
- Most courses fail to set reasonable expectations about what your abilities should be
- So you have unrealistic expectations about building projects from scratch
- Focus completely on understanding concepts
- Focus on understading things deeply and then forget about it
- It is a human condition that you cannot remember everything
- When you need something, you can search again and refresh your knowledge quickly
- The debugger helps you understand your code deeply

# Version 8 - Getting data from inputs
## Our first refactoring
- Refactoring is the process of restructuring exisiting computer code without changing its external behavior
- It helps our code easier to read, easier to understand, and neater
- In the code below we are using .getElementById
- But it adds a lot of code 
- There is a way to get rid of the variable line and ID's
```
var displayTodosButton = document.getElementById('displaysTodosButton');
var toggleAllButton = document.getElementById('toggleAllButton');

displayTodosButton.addEventListener('click', function() {
    todoList.displayTodos();
});

toggleAllButton.addEventListener('click", function() {
    todoList.toggleAll();
});
```

- Now we refactor our html first to remove the id's
- We now add onclick attribute to the button
```
<button id="displayTodosButton">Display Todos</button>
<button id="toggleAllButton">Toggle All</button>

<button onclick="">Display Todos</button>
<button onclick="">Toggle All</button>
```

- We will add the functions to these onclick attrtibutes
- We need to create a handler in the JavaScript
```
var displayTodosButton = document.getElementById('displaysTodosButton');
var toggleAllButton = document.getElementById('toggleAllButton');

<!-- displayTodosButton.addEventListener('click', function() {
    todoList.displayTodos();
});

toggleAllButton.addEventListener('click", function() {
    todoList.toggleAll();
}); -->

var handlers = {
    displayTodos: function() {
    todoList.displayTodos();
    },
    toggleAll: function() {
    todoList.toggleAll();
    }
}
```

- Then we will add the handler inside the html
```
<button onclick="handlers.displayTodos()">Display Todos</button>
<button onclick="handlers.toggleAll()">Toggle All</button>
```

**Comparison**
```
var displayTodosButton = document.getElementById('displaysTodosButton');
var toggleAllButton = document.getElementById('toggleAllButton');

displayTodosButton.addEventListener('click', function() {
    todoList.displayTodos();
});

toggleAllButton.addEventListener('click", function() {
    todoList.toggleAll();
});

<!-- versus -->

var handlers = {
    displayTodos: function() {
    todoList.displayTodos();
    },
    toggleAll: function() {
    todoList.toggleAll();
    }
}    
```

## More on refactoring
- Refactoring happens a lot in the real world
- It is rarely mentioned in different courses
- First you want your code to work
- Then you want to optimize it later
- Often you don't realize that you can refactor beforehand
- Neither is it a clear decision to use .addEventListener vs handler's
- It is a judgment call depending the situation

## Requirements
1. It should have working controls for .addTodo
2. It should have working controls for .changeTodo
3. It should have working controls for .delete Todo
4. It should have working controls for .toggleCompleted

## There should be a button for adding todos
- We are going to add a new button for adding todos
- We need to add a new button for users to input data
- We are using a div to separate the buttons
- We use type attribute on input but there are many types
```
<div>
    <button onclick="handlers.displayTodos()">Display Todos</button>
    <button onclick="handlers.toggleAll()">Toggle All</button>
</div>

<div>
    <button onclick="">Add</button>
    <input id="addTodoTextInput type="text">
</div>
```

- Now we move over to the JavaScript 
```
var handlers = {
    displayTodos: function() {
    todoList.displayTodos();
    },
    toggleAll: function() {
    todoList.toggleAll();
    },
    addTodo: function() {
        var addTodoTextInput = document.getElementById('addTodoTextInput');
        todoList.addTodo(addTodoTextInput.value);
    }
}    
```

- We still need to add the onclick element
```
<div>
    <button onclick="handlers.displayTodos()">Display Todos</button>
    <button onclick="handlers.toggleAll()">Toggle All</button>
</div>

<div>
    <button onclick="handlers.addTodo()">Add</button>
    <input id="addTodoTextInput" type="text">
</div>
```

- We also need to clear the box after the user adds text
- We do this by adding to JavaScript
```
var handlers = {
    displayTodos: function() {
    todoList.displayTodos();
    },
    toggleAll: function() {
    todoList.toggleAll();
    },
    addTodo: function() {
        var addTodoTextInput = document.getElementById('addTodoTextInput');
        todoList.addTodo(addTodoTextInput.value);
        addTodoTextInput.value = '';
    }
}    
```

- So in this lesson, we are using the same onclick attribute
- The new thing is adding the input id

## There should be a button for changing todos
- We need one input for the position we are going to change
- We need another input for the todo text
- Number inputs are different from text
- Number input has arrows that you and incr/decr values
```
<div>
    <button onclick="handlers.displayTodos()">Display Todos</button>
    <button onclick="handlers.toggleAll()">Toggle All</button>
</div>

<div>
    <button onclick="handlers.addTodo()">Add</button>
    <input id="addTodoTextInput" type="text">
</div>

<div>
    <button onclick="handlers.changeTodo()">Change Todo</button>
    <input id="changeTodoPositionInput" type="number">
    <input id="changeTodoTextInput" type="text">
</div>
```

- Now we also need to add the handler function in JS
- We use .valueAsNumber to get values as numbers instead of a string when we just use .value
```
var handlers = {
    displayTodos: function() {
    todoList.displayTodos();
    },
    toggleAll: function() {
    todoList.toggleAll();
    },
    addTodo: function() {
        var addTodoTextInput = document.getElementById('addTodoTextInput');
        todoList.addTodo(addTodoTextInput.value);
        addTodoTextInput.value = '';
    },
    changeTodo: function() {
        var changeTodoPositionInput = document.getElementById('changeTodoPositionInput');
        var changeTodoTextInput = document.getElementById('changeTodoTextInput');
        todoList.changeTodo(changeTodoPositionInput.valueAsNumber, changeTodoTextInput.value);
        changeTodoPositionInput.value = '';
        changeTodoTextInput.value = '';
    }
}   
```

## There should be a button for deleting todos
- Now we are adding a new div for the deleting todos button
```
<div>
    <button onclick="handlers.displayTodos()">Display Todos</button>
    <button onclick="handlers.toggleAll()">Toggle All</button>
</div>

<div>
    <button onclick="handlers.addTodo()">Add</button>
    <input id="addTodoTextInput" type="text">
</div>

<div>
    <button onclick="handlers.changeTodo()">Change Todo</button>
    <input id="changeTodoPositionInput" type="number">
    <input id="changeTodoTextInput" type="text">
</div>

<div>
    <button onclick="handlers.deleteTodo()"></button>
    <input id="deleteTodoPositionInput" type="number">
</div>
```

-Now over to JS to add a new method
```
var handlers = {
    displayTodos: function() {
    todoList.displayTodos();
    },
    toggleAll: function() {
    todoList.toggleAll();
    },
    addTodo: function() {
        var addTodoTextInput = document.getElementById('addTodoTextInput');
        todoList.addTodo(addTodoTextInput.value);
        addTodoTextInput.value = '';
    },
    changeTodo: function() {
        var changeTodoPositionInput = document.getElementById('changeTodoPositionInput');
        var changeTodoTextInput = document.getElementById('changeTodoTextInput');
        todoList.changeTodo(changeTodoPositionInput.valueAsNumber, changeTodoTextInput.value);
        changeTodoPositionInput.value = '';
        changeTodoTextInput.value = '';
    },
    deleteTodo: function() {
        var deleteTodoPositionInput = document.getElementById('deleteTodoPositionInput');
        todoList.deleteTodo(deleteTodoPositionInput.valueAsNumber);
        deleteTodoPositionInput.value = '';
    }
}   
```

## There should be a button for toggling a todo
- Now we are adding a new div for the toggling todo button
```
<div>
    <button onclick="handlers.displayTodos()">Display Todos</button>
    <button onclick="handlers.toggleAll()">Toggle All</button>
</div>

<div>
    <button onclick="handlers.addTodo()">Add</button>
    <input id="addTodoTextInput" type="text">
</div>

<div>
    <button onclick="handlers.changeTodo()">Change Todo</button>
    <input id="changeTodoPositionInput" type="number">
    <input id="changeTodoTextInput" type="text">
</div>

<div>
    <button onclick="handlers.deleteTodo()"></button>
    <input id="deleteTodoPositionInput" type="number">
</div>

<div>
    <button onclick="handlers.toggleCompleted>Toggle Completed</button>
    <input id="toggleCompletedPositionInput" type="number">
</div>
```

- Now over to JS to add a new method
- In your handlers, keep the methods consistent with the other functions
```
var handlers = {
    displayTodos: function() {
    todoList.displayTodos();
    },
    addTodo: function() {
        var addTodoTextInput = document.getElementById('addTodoTextInput');
        todoList.addTodo(addTodoTextInput.value);
        addTodoTextInput.value = '';
    },
    changeTodo: function() {
        var changeTodoPositionInput = document.getElementById('changeTodoPositionInput');
        var changeTodoTextInput = document.getElementById('changeTodoTextInput');
        todoList.changeTodo(changeTodoPositionInput.valueAsNumber, changeTodoTextInput.value);
        changeTodoPositionInput.value = '';
        changeTodoTextInput.value = '';
    },
    deleteTodo: function() {
        var deleteTodoPositionInput = document.getElementById('deleteTodoPositionInput');
        todoList.deleteTodo(deleteTodoPositionInput.valueAsNumber);
        deleteTodoPositionInput.value = '';
    },
    toggleCompleted: function() {
        var toggleCompletedPositionInput = document.getElementById('toggleCompletedPositionInput');
        todoList.toggleCompleted(toggleCompletedPositionInput.valueAsNumber);
        toggleCompletedPositionInput.value = '';
    },
    toggleAll: function() {
        todoList.toggleAll();
    }
}   
```

## Review
- In version 8, we learned how to use inputs to grab user input
- We also use some extra processing with .valueAsNumber

# Version 9 - Escape from the console
## Requirements
- We are not going to use the console anymore
- We will be using the user interface to issue all of our commands
- We will be displaying our to do list right in the app itself
- The requirements are:
1. There should be an li element for every todo
2. Each li element should contain .todoText
3. Each li element should show .completed

## Inserting li elements into the DOM
- We are going to learn how to insert elements into the DOM
- We learned about <ul>, <ol>, <li>
- When you add an <li> to <ul>, you get bullets
- When you add an <li> to <ol>, you get numbers
```
<div>
    <button onclick="handlers.displayTodos()">Display Todos</button>
    <button onclick="handlers.toggleAll()">Toggle All</button>
</div>

<div>
    <button onclick="handlers.addTodo()">Add</button>
    <input id="addTodoTextInput" type="text">
</div>

<div>
    <button onclick="handlers.changeTodo()">Change Todo</button>
    <input id="changeTodoPositionInput" type="number">
    <input id="changeTodoTextInput" type="text">
</div>

<div>
    <button onclick="handlers.deleteTodo()"></button>
    <input id="deleteTodoPositionInput" type="number">
</div>

<div>
    <button onclick="handlers.toggleCompleted>Toggle Completed</button>
    <input id="toggleCompletedPositionInput" type="number">
</div>

<ul>
</ul>
```

- Now we are going to use JS to manipulate the DOM
- We use .createElement to create li elements to our DOM
- We use .querySelector to select different elements, it's very flexible
- We use . appendChild to add elements as child to a parent
```
var todoLi = document.createElement('li');
todoLi // <li></li>

var todosUl = document.querySelector('ul');
todosUl // <ul></ul>

todosUl.appendChild(todoLi);
```

## There should be an li element for every todo
- We want are code to update as we add li's
- First, make sure you have an empty <ul> in html

- We are adding a variable view to display todos array on the screen
- It doesn't add any logic
- We add this to our JS file:
```
var view = {
    displayTodos: function() {        
        var todosUl = document.querySelector('ul');
        todosUl.innerHTML = '';
        for (var i = 0; i < todoList.todos.length; i++) {
            var todoLi = document.createChild('li');
            todosUl = appendChild(todoLi);
        }
    }
}
```

## Each li element should contain .todoText
- We are just going to add one line of code in JS:
- We use .textContent will let you set the text content of the element
```
var view = {
    displayTodos: function() {        
        var todosUl = document.querySelector('ul');
        todosUl.innerHTML = '';
        for (var i = 0; i < todoList.todos.length; i++) {
            var todoLi = document.createChild('li');
            todoLi.textContent = todoList.todos.[i].todoText;
            todosUl = appendChild(todoLi);
        }
    }
}
```

## Each li element should show .completed
- The line that is commented out was replaced with the line above it
- We are basically adding logic about how to display completed tasks
```
var view = {
    displayTodos: function() {        
        var todosUl = document.querySelector('ul');
        todosUl.innerHTML = '';
        for (var i = 0; i < todoList.todos.length; i++) {
            var todoLi = document.createChild('li');
            var todo = todoList.todos[i];

            // var todoTextWithCompletion = '';
            // if (todo.completed === true)
                // (x) todoText
            // else
                // ( ) todoText
                // todoLi.textContent = todoTextWithComplettion;

            var todoTextWithCompletion = '';
            if (todo.completed === true) {
                todoTextWithCompletion = '(x) ' + todo.todoText;
            } else {
                todoTextWithCompletion = '( ) ' + todo.todoText;
            }

            todoLi.textContent = todoTextWithCompletion;
            <!-- todoLi.textContent = todoList.todos.[i].todoText; -->
            todosUl = appendChild(todoLi);
        }
    }
}
```

- Gordon then ran the example in the console
```
view.displayTodos();
```

## Escaping the console
- To display the app, we have to think about how we want to display it
- We want to run it at the end of our handlers
- We are getting rid of displayTodos handlers since now it automatically displays todos
- We are running view.displayTodos(); at the end of every handler
```
var handlers = {
    addTodo: function() {
        var addTodoTextInput = document.getElementById('addTodoTextInput');
        todoList.addTodo(addTodoTextInput.value);
        addTodoTextInput.value = '';
        view.displayTodos();
    },
    changeTodo: function() {
        var changeTodoPositionInput = document.getElementById('changeTodoPositionInput');
        var changeTodoTextInput = document.getElementById('changeTodoTextInput');
        todoList.changeTodo(changeTodoPositionInput.valueAsNumber, changeTodoTextInput.value);
        changeTodoPositionInput.value = '';
        changeTodoTextInput.value = '';
        view.displayTodos();
    },
    deleteTodo: function() {
        var deleteTodoPositionInput = document.getElementById('deleteTodoPositionInput');
        todoList.deleteTodo(deleteTodoPositionInput.valueAsNumber);
        deleteTodoPositionInput.value = '';
        view.displayTodos();
    },
    toggleCompleted: function() {
        var toggleCompletedPositionInput = document.getElementById('toggleCompletedPositionInput');
        todoList.toggleCompleted(toggleCompletedPositionInput.valueAsNumber);
        toggleCompletedPositionInput.value = '';
        view.displayTodos();
    },
    toggleAll: function() {
        todoList.toggleAll();
        view.displayTodos();
    }
}   
```
```
var view = {
    displayTodos: function() {        
        var todosUl = document.querySelector('ul');
        todosUl.innerHTML = '';
        for (var i = 0; i < todoList.todos.length; i++) {
            var todoLi = document.createChild('li');
            var todo = todoList.todos[i];

            // var todoTextWithCompletion = '';
            // if (todo.completed === true)
                // (x) todoText
            // else
                // ( ) todoText
                // todoLi.textContent = todoTextWithComplettion;

            var todoTextWithCompletion = '';
            if (todo.completed === true) {
                todoTextWithCompletion = '(x) ' + todo.todoText;
            } else {
                todoTextWithCompletion = '( ) ' + todo.todoText;
            }

            todoLi.textContent = todoTextWithCompletion;
            <!-- todoLi.textContent = todoList.todos.[i].todoText; -->
            todosUl = appendChild(todoLi);
        }
    }
}
```

- We are also displaytodos button from the HTML and handlers;
```
    <button onclick="handlers.displayTodos()">Display Todos</button>
```
```
    displayTodos: function() {
    todoList.displayTodos();
    },
```

- We also no longer need to run displayTodos in the console
- We remove it from JS:
```
    this.displayTodos();
```
```
var todoList = {
    todos: [],
    displayTodos: function() {
        if (this.todos.length === 0) {
        console.log('Your todo list is empty!');
        } else {
        console.log('My Todos:');
        for (var i = 0; i < this.todos.length; i++) {
            if (this.todos[i].completed === true) {
                console.log('(x)', this.todos[i].todoText);
            } else {
                console.log('( )', this.todos[i].todoText);
            }
        }    
    }
}
```

## Review
- We wrote a lot of code in the view object
- The difference is that we are not working with the console anymore
- Now we are working with the DOM
- We inserted the <ul> in the html
- We are now use the view object in every handler
- The handlers is designed to help shorten our code
- The view object is just meant to display to do items
- Now you can understand how to declutter and refactor your code

# Interlude - Functions inside of functions
## runWithDebugger
- We are going to work with a function that logs 10 numbers
```
function logTenNumbers() {
    for (var i = 0; i < 10; i++) {
        console.log(i);
    }
}

logTenNumbers() // 0, 1, 2, 3, 4, 5, 6, 7, 8, 9
debugger;
logTenNumbers
```

- It would be nice if we had a debugger function
```
// dbugger;
// OurFunction();

// debugger;
// logTenNumbers();
```

- It's a function that enhances another function
- It is a powerful concept
- We can also see that functions can be passed into other functions
- Let's write a debugger function:
```
function runWithDebugger(ourFunction) {
    debugger;
    ourFunction();
}

runWithDebugger(function logTenNumbers() {
    for (var i = 0; i < 10; i++) {
        console.log(i);
    }
});
```

## setTimeout
- We are going to use a function to run another function after a certain amount of time
- Time is in milliseconds
```
setTimout(function() {
    console.log('Wake up Gordon!');
}, 5000)
```

## forEach
- Sometimes you want to run a function on every item in an array
```
var students = ['jonathan', 'jenny', 'elliot'];
function logName(name) {
    console.log(name);
}

logName(student[0]) // jonathan
logName(student[1]) // jenny
logName(student[2]) // elliot
```

- You can use a for loop instead
```
for (var i = 0; i < students.length; i++) {
    logName(students[i]);
}
```

- However, there is a function already built into all arrays called .forEach()
- It will automatically run the function on every item in the array
- There are 3 ways you can do this:
```
students.forEach(logName)

students.forEach(function logName(name) {
    console.log(name);
})


students.forEach(function(name) {
    console.log(name);
})
```

- Now we are going to create our own .forEach() function
```
function forEach(myArray, myFunction) {
    for (var i = 0; i < myArray.length; i++) {
        myFunction(myArray[i]);
    }
}

forEach(students, function(student) {
    console.log(student);
})

// Or

forEach(students, logName)
```

## addEventListener
- Here's an example of another function that enhances another function
- In chrome, you can reference the element on the page with something like "$0"
```
$0 // <h2 id="Tutorials">Tutorials</h2>
var tutorialsElement = $0;
tutorialsElement // <h2 id="Tutorials">Tutorials</h2>
```

- Elements in the DOM have a method called .addEventListener
- It will listen for different types of events 
```
tutorialsElement.addEventListener('click', function() {
    console.log('The tutuorials element was clicked!');
})
```

- If you happen to use the event parameter, you can see the console logs the action
- It will result in showing you MouseEvent with a bunch of information
```
tutorialsElement.addEventListener('click', function(event) {
    console.log(event);
    console.log('The tutuorials element was clicked!');
})
```

## Buzzwords: higher order functions and callback functions
- Here is some vocabulary to empower you in discussions 

1. Higher order functions:
- Functions that accept other functions
- Enhance the behavior of other functions
- Like .runWithDebugger(), .setTimeout(), .forEach(), and .addEventListener()

2. Callback functions:
- The functions are passed into higher order functions

- Double-stars are higher order functions
- Single-starts are callback functions
```
**runWithDebugger**(*function() {
    for (var i = 0; i < 10; i++) {
        console.log (i);
    }
}*);

**setTimeout** (*function() {
    console.log('Wake up Gordon!');
}*, 5000);

var students = ['jonathan', 'jenny', 'elliot'];
**forEach**(students, *function(student) {
    console.log(student);
}*);

tutorialsElement.**addEventListener**('click', *function(event) {
    console.log('The tutorials element was clicked!');
}*);
```