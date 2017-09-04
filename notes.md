# Practical JavaScript
## By Gordon Zhu
### Started 9/4/2017

# Introduction
## What is Practical JavaScript?
> If you've been a victim of boring tutorials that never teach you how to build anything, help save someone from the same fate by sharing Practical JavaScript.
- Courses out there are not teaching you practical application of JavaScript
- Most courses only teach you syntax and features 
- For example, a writing course teaches you only grammar but doesn't force you to write
- Courses focuses on a single project and increases in difficulty

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
- It should have a place to store todos
- It should have a way to display todos
- It should have a way to add new todos
- It should have a way to change a todo
- It should have a way to delete a todo

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
todos // ["item 1", "item 2", "item 3"];
```
- We learned about console.log
```
console.log('My todos:', todos)
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